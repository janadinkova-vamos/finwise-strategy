# The Validation · FinWise

> Module 5 · Experimentation Methods. The experiment brief that tests the bet.

**Experiment:** Decision-Led Onboarding Test

**Objective:** raise trial-to-paid conversion (about 2%, flat for 13 months). To do that, help more trial users reach the Aha moment during the reverse trial: a forecast that answers a real business decision. This feeds the North Star, monthly decision-active accounts (see [`04-signals`](../04-signals/data-signals.md)).

_____

## Method

**Method:** A/B test, 50/50, randomised by new trial user, rolled out behind a feature flag.

**Why:** My hypothesis is about onboarding. A decision-led flow should get more trial users to a forecast that answers a real decision. Each new trial user goes through onboarding alone, so user-level random assignment is simple and clean. Before I scale this flow and build the habit mechanic (M3) on top of it, I need a precise, causal read. That is what an A/B test gives.

**Why not the other methods:**

- **Multi-armed bandit:** I need a causal read on whether the flow works, not live optimisation of traffic.
- **Holdout:** right for long-term effects, which is why the accountant loop and the retention triggers use holdouts. Activation within 7 days is a short-window effect, so an A/B test fits.
- **Geo-testing:** FinWise operates in one market (Spain), and user-level randomisation is possible.
- **Switchback:** each user onboards alone; there is no shared environment to contaminate.

_____

## What I'm testing

- **Current experience (control):** generic onboarding with full premium access and no guided first outcome. Users explore features such as import and modeling on their own.
- **The single change (treatment):** the decision-led onboarding flow, four screens: choose a decision, add six numbers, see the forecast, then save it. Only this core flow is tested. "Example first" and the accountant path are tested separately later.
- **Target segment:** new trial users who sign up on their own.
  - **Excluded:** users invited by an accountant (they belong to the collaboration-loop holdout, so including them would make the two tests collide) and existing accounts.
- **The optional accountant invite** on the save screen stays in the flow, but here it is only a secondary signal. The loop's effect is measured separately in its own holdout.

[Prototype of the treatment flow](https://deal-horizon-predictor.lovable.app)

_____

## Hypothesis + primary metric

**Hypothesis:** If we replace generic onboarding with a decision-led flow for new FinWise trial users, we expect the decision-forecast rate within 7 days to rise by at least 10 percentage points over control. It should work because value comes from a decision answered, not from feature activity: import and modeling usage roughly doubled in M1 and M4 with no change in conversion.

**Primary metric:** decision-forecast rate within 7 days, the share of new trial users who save a forecast using their own numbers within 7 days of sign-up (M4 leading indicator). Forecasts made with sample data don't count.

**Making both groups comparable:** control users have no decision flow, so both groups are measured on one shared event: _saved any forecast or model built on the user's own data within 7 days_. This is a known limitation: the treatment makes that event easier to reach (six numbers instead of importing data), so part of any lift could come from a simpler task rather than more value. That's why the lagging reads (trial-to-paid and 90-day retention) are what confirm real value.

**Three thresholds, kept separate:**

- **Minimum detectable effect (what the test can detect): about 8 percentage points.** With about 1,000 trials over 8 weeks (about 500 per group), the experiment is designed to detect an uplift of about 8 points at a 25% baseline, with 80% power and p < 0.05 (about 7 points at a 20% baseline, just over 8 at 30%). I'll confirm the real baseline from historical data before launch and check the sample size against it.
- **Minimum worthwhile uplift (what justifies rollout): +10 percentage points absolute over control, statistically significant (p < 0.05).** At about 500 trials a month, +10 points means about 50 more trial users a month, roughly 600 a year, reaching a real decision answered during the trial. This is a proposed decision threshold, not one already proven to be commercially optimal.
- **Business validation (what proves it was worth it):** improved trial-to-paid conversion and 90-day paid retention, read later on their own dates.

**How results are reported:** the lift with its 95% confidence interval and p-value, so the read shows both whether the effect is real and how precisely it is known.

**Secondary value check:** after saving a forecast, treatment users get one optional in-product question: _"Did this help you evaluate a real decision?"_ Saving a forecast is behaviour; the Aha is understanding the decision. This helps separate users who click through from users who see real value. It is a secondary signal only, because answers are biased towards users who choose to respond.

**Predicted outcome:** the decision-forecast rate rises from roughly 20–30% to 30–40% within 7 days, and day-1 drop-off stays within 5 points of control.

_____

## Decision rules

Set before launch, following the four messy scenarios:

| Result | What it looks like | The call |
|---|---|---|
| **Clear win** | Significant, lift ≥ +10 points, guardrails within bounds | Ship: staged rollout to all new trials, then long-term validation |
| **Modest win** | Positive and significant, but below +10 points | Evaluate the cost of rolling out, iterate on the flow (e.g. fewer inputs) and retest |
| **Inconclusive** | Positive, but the 95% confidence interval crosses zero | Not proof the idea is wrong: review precision and gather more evidence before deciding |
| **Mixed signal** | Primary metric up, but day-1 drop-off up more than 5 points | Investigate: find where users leave before deciding |
| **J-curve** | Weak in the first weeks, then recovers | Wait for the read date; don't stop early |
| **False peak** | Strong in weeks 1–2, fading by weeks 7–8 | Don't ship on the early lift; treat it as novelty |
| **No effect** | Lift close to zero, with a narrow confidence interval | Treat as unsuccessful (see below) |
| **Harmful** | Credible evidence of a negative effect on activation or guardrails | Stop or redesign |

A p-value of 0.05 or above doesn't by itself mean the hypothesis is false; it means this test couldn't show the effect clearly. The confidence interval shows which of the cases above applies.

**If successful:** roll out to all new trials behind the feature flag. Then run the next tests separately: "example first" vs "form first", then the accountant loop holdout. Read trial-to-paid and 90-day retention on their own dates to check that activation turns into revenue.

**If unsuccessful:** check where users dropped out, using abandonment by screen and session replays on the inputs screen. If people start but don't finish, simplify the inputs. If they finish but activation doesn't rise, the Aha hypothesis is wrong, so go back to cohort data before building more.

_____

## Guardrail + read date

- **Guardrail:** day-1 drop-off. The share of new trial users who don't return after their first session must not rise more than 5 percentage points above control. The new flow adds intake questions at the start of the trial, so this shows whether the extra effort pushes people away.
- **Also monitored:**
  - Onboarding abandonment by screen
  - Input errors
  - Support tickets
  - The share of saves made only on sample data (high means users are clicking through, not activating)
- **Guardrails are checked weekly** so the test can be stopped if something breaks badly (for example, day-1 drop-off up more than 10 points). Checking guardrails is not peeking: the primary metric is read only once, on the read date.
- **Read date:** 8 weeks of enrollment, plus 7 days so the last group of users completes its 7-day window. I'll read the primary result once, on that date.
- **Lagging indicators get their own later reads:**
  - Trial-to-paid, after the last group's trial ends.
  - 90-day paid retention, 90 days after conversion.
- **Why the decision rests on the leading indicator:** at about 500 trials a month, detecting a 2% → 2.5% lift in conversion directly would need roughly 13,000–14,000 users per group, over four years of traffic.
- **Seasonality:** an 8-week window will probably include a Spanish quarterly tax deadline (20 January, April, July or October). Random assignment keeps both groups balanced, but tax-season behaviour may not represent the rest of the year. I'd avoid a window dominated by a single deadline, and note the timing when reading results.

_____
