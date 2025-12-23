```markdown
# AI Outbound Infrastructure

> We install outbound infrastructure that books meetings or tells you why outbound won’t work.

---

## What This Is

This repository installs and runs a **self-operating outbound engine**.

It:
- Executes cold email outbound at safe limits
- Stops automatically on replies or failures
- Judges outcomes without human bias
- Produces **exactly one result**:
  - Meetings booked  
  - OR a clear diagnosis

This is **infrastructure**, not software you “use”.

---

## What This Is Not

This is **not**:
- A lead generation agency
- An AI copywriting tool
- A growth experimentation platform
- A customizable outbound service

There are:
- No dashboards
- No A/B tests
- No manual tweaks
- No client preferences

If you want flexibility, this system is not for you.

---

## Core Principle (Non-Negotiable)

> If the system intervenes less, it works more.

Human judgment is removed **by design**.

---

## System Doctrine (Frozen)

The outbound system operates under a fixed doctrine.

### Inputs (Required)
- ICP: Founder / CEO / Managing Partner  
- Company size: 3–25 employees  
- Geography: US, UK, Canada, Australia, Western Europe  
- Offer: exactly 1 sentence, outcome-based  
- Calendar link  
- Google Workspace inbox (domain age ≥ 6 months)

If any input is missing → **campaign is rejected**.

---

### Rules (Hard-Coded)
- 30 emails per day per inbox
- 1 personalization variable (company name)
- Stop per contact on reply or bounce
- Escalate after 150 delivered emails with no replies

No opinions. No overrides.

---

### Outcomes (Binary Only)

The system may output **one and only one** of the following:

- `success` → meeting booked  
- `bad_icp`  
- `weak_offer`  
- `deliverability_issue`

There is no partial success.

---

## Architecture Overview

Each campaign is a **state machine**:

```

pending → approved → running → diagnosed

```

Execution flow:

```

Input → Validate → Build List → Generate Copy
→ Daily Send (cron) → Log Events → Judge → Stop

```

No mid-run changes are allowed.

---

## Agents (Autonomous)

The system is composed of five agents:

1. **ICP Interpreter**  
   Approves or rejects targeting.

2. **List Builder**  
   Produces a send-ready contact list or fails fast.

3. **Message Engine**  
   Generates and selects outbound copy without human input.

4. **Delivery Controller**  
   Sends email safely and enforces limits.

5. **Outcome Judge**  
   Decides truth. This is the product.

If an agent requires human input, the system is broken.

---

## The Judge (Product Truth)

The Outcome Judge enforces these rules:

- Bounce rate ≥ 5% → `deliverability_issue`
- ≥ 150 delivered + reply rate < 1% → `bad_icp`
- Reply rate ≥ 1% + 0 meetings → `weak_offer`
- ≥ 1 meeting → `success`

All logic is covered by CI tests.  
Any change requires intentional test updates.

---

## Repository Rules

- No UI logic inside agents
- No manual overrides without logging
- No doctrine changes without review
- No feature work before truth is enforced

If CI fails, the product is broken.

---

## What This Repository Guarantees

- Outbound runs without human bias
- Results are honest
- Failure is explicit
- Scale is possible

---

## What This Repository Does Not Guarantee

- Sales
- Revenue
- Conversion rates
- Market fit

It guarantees **truth**, not outcomes.

---

## Contribution Policy

This is not an open collaboration project.

Changes are acceptable **only** if they:
- Preserve doctrine
- Strengthen enforcement
- Do not introduce flexibility

If a change makes the system easier to “tweak”, it will be rejected.

---

## Final Warning

If you:
- Manually tweak copy
- Override the Judge
- Restart diagnosed campaigns
- Explain outbound theory instead of enforcing rules

You are no longer running infrastructure.  
You have reverted to an agency.

---

## Status

This repository represents **outbound as infrastructure**.

Use it accordingly.
```

---
