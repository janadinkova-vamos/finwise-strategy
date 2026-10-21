# The Signals · FinWise

> Module 4 · Data & Analytics. The data pattern you found and the indicators you'll steer by.

## The data pattern

The headline pattern is a Ceiling: trial-to-paid holds at about 2% every month. The real problem behind it is that conversion is disconnected from usage. Over the same 13 months:

- modeling usage swung from 11% to 58%;
- import usage rose from about 31% to 45%;
- sessions per user went from 3 to 9;
- session length fell sharply in July 2024.

None of this moved conversion. Whatever users do in the trial, the same 2% pay. So the ceiling isn’t caused by low engagement. Users are active, but their activity doesn’t produce an outcome worth paying for.

The session data points the same way. Since July 2024, users come back more often but stay much shorter (about 5–9 minutes, down from 11–14). That looks like checking in rather than completing meaningful work: they browse, run a model, and leave without an answer to a real business question. More activity has simply been added on top of the same missing value.

The real problem: FinWise is measuring and growing feature activity when the thing that would make someone pay is a decision answered. That’s why pushing more users into import or modeling hasn’t moved conversion, and why the fix has to change what users get out of the trial, not how much they use it.

**What the Ceiling means for the strategy.** A Ceiling is a product limitation, not a funnel problem: tweaking the trial won't break it, only something new will. That is why the strategy introduces a new value moment, a forecast that answers a real decision, instead of pushing more users into existing features.

**Vanity metrics to stop steering by.** Sessions per user tripled (3 to 9) while session length fell and conversion stayed flat. Import and modeling usage behave the same way. They look like progress but don't predict whether users pay or stay, and optimising for them could make the product worse (for example, pushing users to import before they see any value).

What the data can’t tell me: whether price or the paywall moment also contributes. With conversion this flat, a pricing barrier at the downgrade can’t be ruled out. I’d check it with exit feedback from users who drop to the free tier.

_Metric patterns: Conversion, Ceiling. It holds between 1.87% and 2.08% for all 13 months, with no meaningful movement in either direction. Flag: it never grew before flattening; it was flat from the start. That makes it a hard ceiling. Whatever changed in usage over the year, conversion didn’t respond. Modeling usage, Doesn’t fit cleanly. Closest to growth, then a volatile Ceiling. Import usage, Ceiling. After a dip to about 31% in Jan–Mar 2024, it recovers and holds at 39–45% from April onward, never going above 45.4%. More than half of users still never import. Flag: the Jan 2024 drop (42.7% → 30.6%) was sharp but temporary, a small Cliff that recovered. Session duration, Cliff (July 2024). It rises to a peak of about 14 minutes (Dec 2023 – Mar 2024) and eases slightly to 11–13 minutes through June. Then it falls sharply in July (12.1 → 7.0 minutes, −42%) and bottoms at 5.1 in August. It recovers only partially, to 7.9–9.0. The gentle decline before July is a minor Slow Leak; the defining moment is the July drop. Sessions/user, Doesn’t fit cleanly. A V-shape that ends at a Ceiling._

**Correlation test (result: hypothesis revised).** Plotting modeling and import usage against trial-to-paid conversion showed no relationship: usage swung widely while conversion stayed at about 2%. So feature usage isn't the value moment, and I revised the hypothesis to a forecast tied to a real decision. The decision-forecast rate isn't in the Module 1 dataset, so it needs user-level tracking, and I'd confirm that it predicts conversion and retention before relying on it in the A/B test. That would show prediction, not cause; the A/B test is what tests cause.

_____

## North Star (Aim)

**Monthly decision-active accounts:** the number of accounts where, in the month, the owner saved or updated a decision with their own numbers, or a collaborator (accountant or partner) reviewed one.

It measures the value FinWise exists to deliver: a real decision answered, often together with the accountant. It matches the retention definition, works for owners and accountants, and can't be inflated by clicks or sessions. I don't experiment on it directly; every experiment has to draw a line back to it.

_____

## Leading indicators (Move)

_Activation window: 7 days from trial start, used consistently across the repo._

- **Time to first value: the time from sign-up to the first decision forecast saved with the user's own numbers.** The most undertracked metric in PLG, and the most direct read of whether onboarding gets users to the Aha faster. Report non-completers separately, so faster successful users don't hide rising abandonment.
- **Decision-forecast rate within 7 days: % of new trial users who save a forecast tied to a real decision (a contract, hire or tax payment), using their own numbers.** M1 showed that modeling doubled while trial → paid stayed at about 2%, so a generic first model isn't enough. This tests whether a model that answers a real decision is the kind of activation that actually predicts conversion.

_Own-data import within 48 hours is kept as a diagnostic, not a target. Import is setup, not value: it rose with no change in conversion, and the onboarding prototype deliberately doesn't require it._

_____

## Lagging results (Prove)

- **Trial-to-paid conversion rate (currently about 2%), confirmed by 90-day paid retention.** If users who reach a decision answered faster convert and stay at higher rates, at scale, the strategy worked. Both are earned through the leading indicators, not moved directly.

_Added for the final project: retention indicators (see [`03-mechanic`](../03-mechanic/engagement-mechanic.md#retention-strategy-final-project))._

- **Leading: monthly decision-active rate.** The share of paying accounts where, in the last 30 days, the owner saved or updated a decision with their own numbers, or a collaborator reviewed one. FinWise's rhythm is monthly, so this replaces DAU/MAU.
- **Leading: collaborative-account rate.** The share of paying accounts with the owner plus at least one active collaborator (accountant or partner).
- **Lagging: customer retention, reported by plan.** Monthly plans: the share of each paying cohort still paying and active at months 3, 6 and 12. Annual plans: renewal rate, plus an in-year activity check, because an inactive annual customer is churn that hasn't shown up yet. The two plans are never blended into one number.

## Metrics across the funnel

| Stage | Metric | Why this one |
|---|---|---|
| Acquisition | Cost per activated account, by channel | Judges channels by users who reach value, not by sign-ups, which answers the reliance on paid ads |
| Activation | Time to first value; decision-forecast rate within 7 days | Speed and share of users reaching the Aha |
| Engagement | Monthly decision-active rate | Matches FinWise's monthly rhythm; DAU/MAU would be the wrong metric |
| Retention | Retention by plan (monthly) and renewal rate (annual) | Shows whether users keep getting value, without annual plans hiding churn |
| Referral | % of invited accountants who bring in another business; % of those businesses reaching a first decision | Measures the loop's reach and its value, not just invitations |
| Revenue | Trial-to-paid conversion; MRR | Confirms value turns into durable revenue |

_____

## Qualitative layer (triangulation)

The quantitative data shows how much; it can't show why. Current qualitative evidence is one accountant interview (n=1). To find out why users drop off or stay:

- **Session replays on the inputs screen (screen 2)**, where drop-off is most likely, to see which fields cause hesitation.
- **Exit feedback from users who downgrade to free at the end of the reverse trial**, to separate a value problem from a price or paywall problem.
- **Short interviews with retained and churned customers**, comparing what they did in their first two weeks.

AI synthesis can then combine both, surfacing patterns and new hypotheses faster, but the call on what to test stays mine.

_____

<img width="800" height="401" alt="image" src="https://github.com/user-attachments/assets/1714235d-1d3e-4af7-9b95-5216d801093d" />

<img width="795" height="245" alt="image" src="https://github.com/user-attachments/assets/6c2f58d8-5af4-4277-ae23-6f32c611c682" />

<img width="792" height="254" alt="image" src="https://github.com/user-attachments/assets/1ba31ba7-0d82-42f2-983c-49b06c0ade39" />

<img width="800" height="215" alt="image" src="https://github.com/user-attachments/assets/a1ae00e5-1a74-4cd5-a0ab-f73ca157b2c1" />

_____
