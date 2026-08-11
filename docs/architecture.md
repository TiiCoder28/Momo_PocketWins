# Proposed Architecture

## Goal

PocketWins should separate financial calculations, behavioural analytics, AI-generated language, and MoMo integration so that important financial insights remain explainable and testable.

## High-level architecture

```text
MoMo App / Mini App Host
        |
        v
PocketWins PWA
Vue 3 + TypeScript + Vite
        |
        v
FastAPI Backend
        |
        +-------------------+
        |                   |
        v                   v
PostgreSQL / Supabase   MoMo Integration Layer
        |                   |
        v                   v
Behavioural Engine      MoMo APIs
        |
        v
Structured Insights
        |
        v
LLM / Personalised Explanation Layer
        |
        v
User-facing guidance
```

## Proposed frontend

- Vue 3
- TypeScript
- Vite
- PWA/mobile-first layout
- lightweight state management as needed

Primary screens:

- Today
- Reflect
- Pay Yourself
- Future Me

## Proposed backend

- Python
- FastAPI
- REST endpoints
- Pydantic models
- deterministic financial calculations
- behavioural event processing
- MoMo API adapter/service layer

## Data model direction

Likely core entities:

### User

- id
- MoMo/session identifier where permitted
- preferred currency
- income/pay cycle
- created_at

### FinancialPlan

- id
- user_id
- cycle_start
- cycle_end
- income amount
- safe-to-spend amount

### PlannedExpense

- id
- financial_plan_id
- category
- amount
- essential flag

### Transaction / SpendingEvent

- id
- user_id
- amount
- category
- timestamp
- source
- planned/unplanned status

### BehaviourEvent

- id
- user_id
- event_type
- linked transaction if relevant
- user label
- optional note
- created_at

Possible types:

- impulse_purchase
- regretted_purchase
- avoided_purchase
- stayed_within_plan
- personal_win

### SavingsGoal

- id
- user_id
- name
- target_amount
- tracked_progress
- created_at

### PayYourselfEvent

- id
- user_id
- savings_goal_id
- behaviour_event_id
- amount
- reason
- MoMo transaction reference if applicable
- status
- created_at

### Insight

- id
- user_id
- insight_type
- structured evidence
- period_start
- period_end
- created_at

## Behavioural intelligence pipeline

```text
Transactions + user reflections
            |
            v
Normalisation / categorisation
            |
            v
Behavioural events
            |
            v
Historical analytics
            |
            v
Trend + pattern engine
            |
            v
Structured user profile
            |
            v
Verified insight objects
            |
            v
LLM explanation / recommendation
```

## Important design rule

The backend calculates the fact.

The AI explains the fact.

Example:

Backend:

```json
{
  "metric": "flexible_overspend",
  "previous_month": 470,
  "current_month": 210,
  "change_percentage": -55.3,
  "trend": "improving"
}
```

AI/UI:

> Your flexible overspend dropped from R470 last month to R210 this month — an improvement of about 55%.

This reduces hallucination risk and makes the system easier to test.

## Personalisation strategy

The user profile can be derived from structured history rather than storing a vague AI-written personality summary.

Useful signals may include:

- category spend averages
- budget adherence by week/month
- periods of overspending
- user-labelled impulse purchases
- avoided-purchase frequency
- reward behaviour
- active goals
- streaks
- trend direction

## MoMo integration layer

MoMo integration should be isolated behind a backend service layer so the rest of PocketWins is not tightly coupled to sandbox-specific implementation details.

Example conceptual interface:

```text
MomoService
- initialise_session(...)
- request_payment(...)
- get_payment_status(...)
- pay_or_transfer(...), if supported
```

Exact supported APIs and Mini App events must be validated against current official hackathon documentation before implementation.

## Security considerations

For a prototype and later production direction:

- keep API credentials server-side
- never expose secrets in the PWA bundle
- validate session/token context
- store the minimum personal data needed
- separate demo data from production-like data
- audit money-movement events
- use idempotency/reference IDs for payment actions
- avoid treating LLM output as authoritative financial calculation

## Hackathon implementation philosophy

Prefer a small architecture that works end-to-end over a large architecture that only exists on slides.

Priority order:

1. Core user journey
2. MoMo integration
3. Behavioural calculations
4. polished mobile UX
5. AI explanation
6. optional enhancements
