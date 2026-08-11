# Hackathon Preparation Plan

## Event

**MoMo Mini App Hackathon 2026**  
**Date:** 2–3 September 2026  
**Format:** 24-hour in-person hackathon  
**Location:** Johannesburg  
**Team:** Binary Bandit  
**Project:** PocketWins

## Preparation objective

Arrive at the hackathon with the product direction, architecture, API understanding, user flow, and demo strategy already clear so that the 24-hour build can focus on execution rather than discovery.

## Phase 1 — Product definition

### 11–13 August

Goals:

- lock the problem statement
- define PocketWins product principles
- define the core behavioural loop
- distinguish MVP from future features
- create project documentation
- draft hackathon registration answers
- validate that PocketWins is sufficiently differentiated from a standard budgeting chatbot

Deliverables:

- product vision
- product principles
- MVP scope
- architecture draft
- registration draft

## Phase 2 — MoMo feasibility

### 12–17 August

Goals:

- review current official MoMo Mini App/PWA documentation
- set up developer/sandbox access
- understand authentication/session requirements
- identify available APIs relevant to PocketWins
- successfully test at least one sandbox payment flow
- confirm what form of money movement can support the Pay Yourself concept

Questions to resolve:

- How is a Mini App launched and authenticated inside MoMo?
- Which Collections/Request to Pay functions are available to hackathon teams?
- Is there any supported wallet-to-wallet, disbursement, savings pocket, or sub-wallet capability suitable for Pay Yourself?
- What transaction data is available to the Mini App?
- What data must PocketWins capture itself?
- What limitations apply in the sandbox versus production?

## Phase 3 — Product and UX prototype

### 18–23 August

Goals:

- design the four primary screens
- define complete happy-path user journey
- create sample data and behavioural history
- define insight cards and weekly-summary experience
- test the product story with realistic scenarios

Primary screens:

1. Today
2. Reflect
3. Pay Yourself
4. Future Me

## Phase 4 — Technical rehearsal

### 24–28 August

Goals:

- create a lightweight Vue PWA shell
- create a lightweight FastAPI backend shell
- rehearse MoMo API integration
- implement one or two behavioural analytics calculations
- test frontend/backend deployment strategy
- identify likely hackathon blockers before the event

The rehearsal is intended to teach the integration and reduce risk. Final competition work must follow the hackathon's rules on pre-existing code and permitted preparation.

## Phase 5 — Demo and pitch preparation

### 29 August–1 September

Goals:

- finalise feature priority
- write the 24-hour task board
- prepare demo data/story
- prepare architecture explanation
- prepare pitch narrative
- prepare fallback plan if an external API becomes unavailable
- verify equipment, credentials, chargers, internet options, and local tooling

## 24-hour build priority

### Must work

1. PocketWins Mini App/PWA opens and has a polished mobile journey.
2. User can create/view a simple financial plan.
3. Safe-to-spend calculation works.
4. User can record a behavioural reflection.
5. Pay Yourself flow works end-to-end at the level supported by MoMo APIs.
6. Future Me goal/progress updates.
7. At least one historical personalised insight is calculated correctly.
8. MoMo integration is visibly demonstrated.

### Should work

- weekly summary
- multiple savings goals
- richer trend cards
- natural-language planning
- AI-generated explanation of verified insight

### Nice to have

- advanced gamification
- badges
- third-party reward partnerships
- health/fitness integrations
- extensive dashboards

## Demo narrative

A strong demo should tell one simple story:

> A user has a limited amount of money until payday. PocketWins helps them understand what is safe to spend. They reflect on an everyday decision, recognise a positive choice, pay a small amount toward Future Me, and then see how their behaviour has improved compared with their own previous weeks or months.

The judge should understand the behavioural value and MoMo integration without needing a long explanation.

## Risk register

### Risk: Pay Yourself cannot move money in the intended way

Mitigation: validate supported MoMo APIs early. Use honest goal tracking in the prototype and clearly distinguish simulated/tracked goal balances from real stored-value savings if no suitable API exists.

### Risk: AI takes too much implementation time

Mitigation: build deterministic behavioural analytics first. AI is an enhancement layer.

### Risk: scope becomes too large

Mitigation: protect the four-screen MVP and core loop. Move every non-critical feature to the roadmap.

### Risk: no historical data exists during a 24-hour hackathon

Mitigation: create clearly labelled seeded demo history so judges can see how long-term personalisation would work.

### Risk: MoMo sandbox/API instability

Mitigation: prepare a graceful fallback/demo mode while still demonstrating the real integration whenever available.
