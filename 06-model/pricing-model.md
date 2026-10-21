# The Model · FinWise

> Module 6 · Pricing & Monetization. The pricing & packaging recommendation memo for FinWise.

**The question this memo answers:** are FinWise customers failing to convert because the price is wrong, or because they haven't experienced enough value to justify paying?

_____

## Memo to the leadership team

**To:** FinWise leadership team
**From:** Senior PM, Growth
**Re:** Pricing recommendation: move the paywall to where users act on a decision

**The problem**
FinWise has product-market fit and $10M ARR, but only 2% of trial users convert to paid, only 40% of paying customers stay beyond a year, and growth depends on paid acquisition. Over 13 months, import and modeling usage roughly doubled while conversion stayed flat. Users are active, but they don't reach an outcome worth paying for. This is a value problem, not a price problem. Lowering prices or adding discounts would buy more low-fit users who leave, and price changes are hard to reverse.

**Where we are**
Stage 1 · Value Creation. Our priority is proving that users experience lasting value, not tuning price points. We keep the subscription model and the reverse trial; subscription fits because FinWise delivers value continuously, through monthly cash planning, quarterly tax deadlines and new contracts and hires.

**Recommendation**
For new signup cohorts, change what users keep when their reverse trial ends:
- **Free:** saved decision forecasts stay visible (read-only), and the quarterly VAT estimate stays free.
- **Paid:** creating, updating and comparing decision forecasts, and sharing them with an accountant.

Users keep the value they've already experienced, and they hit the paywall at the moment they need to act on their next decision, often around a tax deadline.

**Why this is the right move now**
- **It targets the right signal.** It increases the value of the decision-forecast rate within 7 days, the share of trial users who save a forecast tied to a real decision with their own numbers. That forecast is what users keep, and what brings them back to the paywall. Feature activity has already shown it doesn't predict payment.
- **It builds trust instead of eroding it.** Nothing users have experienced is taken away, which matters in a finance product.
- **It creates a recurring upgrade moment** at each quarterly tax deadline, without ad spend.

**How we'll know**
We'll roll this out to new signup cohorts only, so no existing customer sees a different offer, and track them over 2–3 billing cycles. Success means upgrades cluster at the moment users act on or share a decision, cohorts keep paying through the second and third billing cycles, and paid conversion doesn't fall. If conversion drops without a retention gain, the free tier is giving away too much, and we adjust the line before scaling.

_The detailed analysis behind this memo follows below._

_____

## Stage + model

**Stage:** Stage 1 · Value Creation, moving into Stage 2 · Revenue Expansion.

- **Why Stage 1:** the evidence points to a value problem, not a pricing problem. Trial-to-paid has stayed at about 2% for 13 months while import and modeling usage roughly doubled ([`04-signals`](../04-signals/data-signals.md)). Users are active, but their activity doesn't produce an outcome worth paying for. One-year retention of 40% points the same way. Changing the price would not fix value that users never experience.
- **Why one Stage 2 bet:** a pricing or paywall barrier can't be ruled out from the data. So this memo makes one structural bet, where the paywall sits, and deliberately avoids Stage 3 tuning (price points, segment pricing, new discounts).

**Model:** subscription with a reverse trial.

- New users get full premium access during the trial, then drop to a free tier unless they pay.
- Paid plans are monthly or annual, with a discount on annual. (The brief doesn't specify billing; this is my assumption.)
- **Why subscription:** FinWise delivers value continuously (monthly cash planning, quarterly tax deadlines, new contracts and hires), and retention is the primary growth lever.
- **The reverse trial stays.** It isn't replaced with freemium. What this memo changes is what the free tier keeps after the trial ends.
- **Market:** Spain (scope assumption from the retention strategy).

_____

## Recommendation

**Put the paywall where users feel they need more: at acting on a decision, not at seeing their numbers.**

| Tier | What's included | Why |
|---|---|---|
| **Foundational (free, after the reverse trial)** | Saved decision forecasts stay visible (read-only), plus the quarterly VAT and tax estimate | Value already experienced is never taken back. The investment from the trial (data, history, accountant reviews) survives the downgrade, and every fiscal deadline brings users back. Trust and habit before cost, as in the Spotify example. |
| **Enhanced (paid)** | Create, update and compare decision forecasts (contracts, hires, tax payments, cash scenarios), plus sharing and review with the accountant | This is the Aha and the switching cost. Users hit the paywall exactly when they want to act on a decision: update a forecast, test a new scenario, or ask their accountant. |
| **Premium (later)** | Accountant plan covering multiple clients, multi-business workflows | The expansion route towards net dollar retention above 100%, once the floor holds. Not for now. |

**Why the VAT estimate is free:** it brings every free user back four times a year, at a moment when they also face decisions such as _"Can I pay this VAT and take on the new contract?"_ The estimate is the hook; the decision around it is what users pay for. In Spain the gestor usually files VAT, and existing tools already cover tax filing, so FinWise's difference is the decision, not the calculation.

**The pricing bet:** if saved forecasts and the VAT estimate stay free after the reverse trial, while creating, updating, comparing and sharing decision forecasts sits behind the paywall, then upgrades will cluster at the moment users try to act on or share a decision, and paying cohorts will retain better, because they pay for value they have already experienced.

**How to test it:**

- **Cohorts by signup date, not a user-level A/B test.** New signups in the test period get the new free tier; earlier cohorts keep the current one. No existing customer ever sees a different offer, which avoids price leakage.
- **Track over 2–3 billing cycles,** not just the first month: upgrade rate, where upgrades happen (which action triggered them), retention, ARPU, churn and net revenue.
- **Measure cannibalisation:** check whether the extra free access creates additional paying customers, or gives away value people would have paid for. Compare cohorts on paid conversion, ARPU and retention, not on free-tier usage alone.
- **Treat it as a one-way door:** once users have free read-only forecasts and the VAT estimate, that value can't be taken back without damaging trust. The boundary is decided carefully before launch.
- **Keep it separate from the other experiments:** the onboarding A/B test, the accountant-loop holdout and the retention holdout run on different populations or surfaces, so results can be attributed.
- **Guardrails:** no dark patterns (no pre-ticked annual plan, easy cancellation, clear renewal reminders), and no features moved from free to paid later. The competitor review benchmark shows that taking value back causes the angriest churn.

**Deliberately not tested yet:**

- **Monthly vs annual as an experiment:** revenue per user isn't comparable across billing models (the two arms produce revenue on different curves), and the annual discount may mostly reward users who would have paid anyway. Annual is offered with a discount, but it isn't the bet.
- **An accountant collaboration bundle at a higher price:** risks the bundle failure mode, paying to deliver features users don't value. Collaboration sits in the paid tier instead.
- **Higher prices or psychological price points:** Stage 3 questions, premature while the value moment is unproven, and price-point tests need samples FinWise doesn't have.
- **A VAT-only paid plan:** a candidate Stage 3 test, triggered if the data shows a stable segment of users who use only the VAT estimate every quarter and never upgrade. Then a low-price tier designed for that segment would be justified by evidence, not assumption.

_____

## Model signal

**What success looks like in the data:**

- **Upgrades cluster at the paywall boundary:** most upgrades happen when a user tries to update, compare or share a decision forecast, often around a fiscal deadline.
- **Paying cohorts hold:** cohorts that upgrade this way keep paying through the 2nd and 3rd billing cycles, and net revenue (after churn) holds, not just a first-month spike.
- **Free users return:** free-tier users come back at each quarterly deadline, and a growing share of them upgrade at that moment.
- **No cannibalisation:** paid conversion and ARPU for the new cohorts are equal to or higher than for earlier cohorts.

**What failure looks like:** upgrades spread randomly rather than clustering at the boundary (the line is in the wrong place), free users never return after the trial (the free tier holds no reason to come back), or paid conversion falls with no retention gain (the free tier gives away too much).

_____
