# The Mechanic · FinWise

> Module 3 · Retention & Engagement. The engagement mechanic that builds the habit loop, with rationale and a wireframe.

## The mechanic

**Mechanic:** Progress Bar

- **Trigger:** External at first: an upcoming decision that FinWise surfaces automatically, such as a new contract to price, a hire, the quarterly VAT payment or month-end payroll. A real change, like a client payment date slipping, also triggers it by flagging a saved forecast as out of date. Over time the trigger becomes internal: before committing to anything, the owner thinks “let me check it in FinWise first.”
- **Action:** Open the decision and take it one step closer to “Ready”: add or update your numbers, review the forecast, or choose a funding plan, such as an upfront payment or a short credit line. Each step takes a few minutes, and the progress bar shows the next one.
- **Reward:** A clear answer, varying each time: whether this decision pays off and whether you can afford it. Sometimes it’s reassurance (“You can fund this from cash”). Sometimes it’s an early warning (“You’ll be €4,000 short for 60 days; a 30% upfront payment closes the gap”). The bar then reaches “Ready”, and the monthly summary moves forward (“2 of 3 decisions ready”).
- **Investment:** Each saved decision stores the business’s real costs, payment patterns and funding choices, plus the accountant’s review. That makes the next forecast faster and more accurate, because it starts pre-filled. It also builds a shared decision history with the accountant that would be lost by leaving FinWise.

_____

## Rationale

My churn diagnosis points to value, not price. Modeling usage almost doubled while churn rose, and revenue per customer stayed flat. Users were active, but their activity wasn’t producing answers they’d pay to keep, and once a single decision was made there was no reason to return.

The habit loop targets both problems during the reverse trial, before the user hits the paywall:

- It ties every visit to a decision answered, not a model run, so value is felt rather than just activity.
- It turns a one-off forecast into a recurring job, because there’s always a next contract, hire or tax payment.
- It builds investment (data, history, accountant context) that makes FinWise more useful the longer it’s used.

By the time the trial ends, a user should have one or two decisions made “Ready” with their own numbers. At that point, downgrading means losing something they already rely on, not giving up a tool they merely explored.

This is a hypothesis. I’d test it with a holdout, measuring decisions made “Ready” per trial as the leading signal and trial-to-paid plus 90-day retention as the outcomes.

_____

## Wireframe

<img width="492" height="476" alt="image" src="https://github.com/user-attachments/assets/25192b60-a2e4-4995-ac11-79de381b1936" />

_____

## Retention strategy (final project)

_Added for the final project (October 2026). This builds the Progress Bar mechanic into a full retention strategy, including the fiscal-calendar triggers._

### Scope and assumptions

- **Market:** FinWise operates in Spain. The fiscal calendar could be configured for other countries later.
- **Billing:** the brief doesn't specify billing. I assume monthly or annual plans after the reverse trial, with a discount on annual.

### What counts as retained

A retained customer pays **and** uses FinWise in a meaningful way: they make a decision with FinWise's help or share a decision with their accountant or partner. Otherwise the product isn't delivering value.

**Measurable definition:** a paying account where, in the last 30 days, the owner saved or updated a decision with their own numbers, or a collaborator reviewed one. (Check sensitivity with 60- and 90-day windows, since some decisions are quarterly.)

### Diagnosis

- **Floor before ceiling.** One-year retention is 40% and revenue per customer is flat. Customer retention is the priority. NDR becomes the target only once the floor holds.
- **Measurement first.** "40% at one year" is one point, not a curve. Step one is cohort retention curves by month since first payment: does the curve flatten (a core of users who get lasting value) or keep falling (a product problem)?
- **Hypotheses to check with cohort data:**
  - Customers churn after their one big decision is done, because nothing brings them back.
  - Retained customers, in their first two weeks, saved a decision with their own numbers and had a collaborator join. This is a predictor to check within segments, not proof of cause.

### Natural rhythm

| Frequency | Decisions |
|---|---|
| Monthly | Cash planning, payroll |
| Quarterly | VAT and tax payments |
| Occasional | A new contract, a hire |

FinWise's rhythm is monthly, not daily, so DAU/MAU is the wrong metric. The engagement metric is the **monthly decision-active rate**: the share of paying accounts that are retained under the definition above each month.

### The retention bet: fiscal-calendar triggers

Every Spanish SMB faces the same tax obligations at the same time. FinWise uses these deadlines to start personalised forecasts and notifications, for example: _"Review your estimated VAT payment and cash position, then share it with your accountant."_ The value can be triggered by the product, not only by the user remembering to come back.

**2026 calendar the triggers are built on:**

- Quarterly VAT (modelo 303), self-employed income-tax prepayment (modelo 130) and withholdings (modelos 111 and 115): **20 April, 20 July, 20 October**, and 30 January for Q4 (20 January for 111/115).
- Company tax prepayments (modelo 202): 20 April, 20 October and 21 December.
- Annual VAT summary (modelo 390): 30 January.
- Personal income tax (Renta): filing from 8 April, payment by 30 June.

**Design principles:**

- **Plan before the rush.** Triggers go out two to three weeks before each deadline (early-to-mid March, June, September and December), not in the final days, when accountants are at their busiest.
- **Monthly jobs fill the gaps.** Cash planning and payroll prompts keep value flowing between quarterly deadlines, so users don't join for one VAT payment and leave.
- **Ask for data when it becomes relevant.** VAT regime and legal form are asked once, at the first fiscal trigger, or inferred from imported data, not added to onboarding.
- **Estimates, not tax advice.** FinWise prepares the numbers and the accountant confirms them. That makes FinWise the accountant's ally, not their replacement.
- **VAT-only users.** The quarterly VAT estimate stays in the free tier after the reverse trial, so users who come for VAT keep returning each quarter, and the decision around the payment is the upgrade moment. A low-price VAT-only paid plan stays a candidate Stage 3 test if the data shows a stable segment of VAT-only users (see [`06-model`](../06-model/pricing-model.md)).

**Acquisition benefit:** deadlines create predictable intent windows for organic content and AEO (e.g. "how much VAT will I owe this quarter?"), and trials that start shortly before a deadline give users a real decision to make inside the trial.

### Levers by customer type

- **Monthly customers (habit):** prompts for the next recurring decision, the fiscal triggers, and a monthly "decisions Ready" summary.
- **Annual customers (value before renewal):** a pre-renewal value recap (e.g. "This year you made 9 decisions Ready, and your accountant reviewed 6"), and a flag when an annual account goes inactive mid-year.
- **Collaborative accounts:** the SMB version of "3+ active users" is the owner plus at least one active collaborator. The shared decision history with the accountant creates an organisational switching cost. Hypothesis: collaborative accounts retain much better than solo ones.
- **Later, not now:** expansion through more collaborators, more decision types and an accountant plan covering multiple clients. This is the route to NDR above 100%, once the floor holds.

### Experiment

- **Hypothesis:** if we trigger personalised forecasts for upcoming fiscal deadlines and recurring monthly decisions, then the monthly decision-active rate will rise and 6-month retention will improve, because users get value between their big decisions instead of only once.
- **Method:** holdout. About 20% of paying customers don't receive the triggers for at least one full quarterly cycle. Retention effects take months to show, which is what holdouts are for.
- **Sample size:** at about 500 trials a month and 2% conversion, FinWise gains only about 10 new paying customers a month. A test on new payers alone would never reach significance, so it runs across the whole paying base. The leading metric is the main read; the retention outcome is directional.
- **Leading metrics:** share of triggered users who review the deadline forecast; share who share it with their accountant; monthly decision-active rate; collaborative-account rate.
- **Lagging metrics:** monthly retention at 6 and 12 months; annual renewal rate.
- **Guardrails:** notification opt-outs, cancellations, support demand, complaints about estimate accuracy, and no dark patterns (easy cancellation, clear renewal reminder, no pre-ticked annual plan).
- **Read dates:** leading metrics at 90 days (one full quarterly cycle), lagging at 6 months. Set before launch, no peeking. Watch for a False Peak: the effect only counts if it still holds in month 3.

### How it connects

One value mechanism across the funnel: **activation** delivers the first decision answered, **retention** repeats it every month and every fiscal deadline, and **collaboration** makes it shared and hard to leave while bringing in new businesses through the accountant.

### Not doing

- Win-back discounts or friction when cancelling.
- Notifications or gamification aimed at activity rather than decisions.
- Pushing expansion or NDR before the floor holds.
- Treating annual lock-in as a retention fix.

_____
