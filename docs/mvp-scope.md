# Hackathon MVP Scope

## Objective

Build the smallest convincing PocketWins experience that demonstrates the behavioural loop, meaningful personalisation, and a genuine MoMo use case within the 24-hour hackathon window.

## MVP user journey

1. User opens PocketWins inside the MoMo Mini App environment.
2. User creates a simple money plan for the current cycle.
3. PocketWins calculates a safe-to-spend amount after planned essentials.
4. User records or reflects on a spending decision or positive personal choice.
5. PocketWins classifies or records the behavioural event.
6. The system recognises a positive action or relevant spending pattern.
7. User is offered the option to "Pay Yourself" a small amount toward a selected goal.
8. The goal balance/progress updates.
9. The Today/Future Me view reflects the updated progress.
10. A weekly or historical summary demonstrates how PocketWins learns from behaviour over time.

## Four primary MVP screens

### 1. Today

Purpose: give the user an immediate picture of today's financial position and progress.

Potential content:

- current balance or demo balance
- protected/planned essentials
- safe-to-spend amount
- daily flexible amount
- current PocketWins streak
- quick actions: Reflect, Pay Yourself, Check Progress

### 2. Reflect

Purpose: capture meaningful behavioural events.

Possible event types:

- Planned purchase
- Flexible purchase
- Unplanned purchase
- Impulse purchase (user-labelled)
- Regretted purchase
- Avoided purchase
- Positive personal win

The reflection should remain quick enough to use in everyday life.

### 3. Pay Yourself

Purpose: turn a positive behaviour into an optional micro-saving action.

Flow:

- reason for reward
- suggested or custom amount
- choose destination goal
- confirm action
- show updated goal progress

Example:

> You cooked instead of ordering takeaway. Pay Future You R20?

### 4. Future Me

Purpose: make behavioural progress tangible.

Potential content:

- savings goals
- total amount paid to self
- progress bars
- recent wins
- streaks
- weekly summary
- historical behavioural trend

## Required behavioural intelligence for MVP

We do not need a sophisticated ML model during the hackathon.

The MVP should be able to calculate a small number of reliable insights such as:

- current cycle overspend/underspend
- month-over-month or week-over-week change
- number of impulse purchases logged
- number of avoided purchases
- consecutive periods within plan
- category trend
- amount paid to self
- streaks

Seeded historical/demo data can be used where necessary to demonstrate long-term personalisation during a 24-hour event.

## AI scope

AI is a supporting layer, not the core dependency.

For MVP, AI may:

- phrase structured insights naturally
- summarise a user's week
- help interpret a natural-language money plan
- suggest a behavioural rule based on verified patterns

AI should not be responsible for calculating financial totals or inventing trends.

## MoMo integration target

Priority is to demonstrate at least one authentic MoMo integration flow available to hackathon participants.

Potential integration points to validate with official hackathon/API documentation:

- Mini App/PWA session integration
- Request to Pay / Collections
- payment status
- transfer/disbursement or suitable money movement for Pay Yourself

If a true consumer savings/sub-wallet API is not available, PocketWins must not misrepresent a database goal balance as a regulated savings account. The UI can use terms such as "Goal", "Future Me", or "Pay Yourself Pot" until the permitted money movement is confirmed.

## Explicitly out of scope for the 24-hour MVP

- full bank account aggregation
- automatic health/fitness integrations
- complex rewards marketplace
- production-grade financial advice
- credit scoring
- investment recommendations
- extensive social/community features
- dozens of charts
- large multi-agent AI architecture
- full production compliance implementation

These may appear in the roadmap or pitch as future extensions.

## Demo success condition

A judge should be able to understand the entire PocketWins idea in one short flow:

**I make a plan → PocketWins understands my behaviour → I make a better choice → I reward that choice → my future goal grows → PocketWins shows that my behaviour is improving over time.**
