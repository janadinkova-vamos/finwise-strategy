# The Solution · FinWise

> Module 2 · Acquisition & Activation. The onboarding solution and the Aha moment that makes value land.

## Aha moment

FinWise’s Aha moment: the moment a small-business owner sees, for a real decision in front of them, whether it pays off and whether they can afford it. For example: “This new contract is profitable, but I’ll be €4,000 short for 60 days before the client pays. Now I know I need a short credit line, or that a 30% upfront payment closes the gap.”

How I’ll measure it: a trial user completes and saves a decision-linked forecast using their own numbers, within 7 days of starting the trial. Sample data doesn’t count.

How I landed on it with Claude: the Module 1 data showed that data import and modeling usage roughly doubled while trial-to-paid stayed at about 2%. Feature usage isn’t the value moment. Importing data is setup. Combined with an interview with a senior accountant, Claude helped me reframe the value around forward-looking decisions: what to charge, what margin I’ll make, and whether I need financing. That is more valuable than bookkeeping, and it repeats with every new contract, hire or tax payment.

Status: this is a candidate Aha, not a validated one. Next, I’d check whether users who save a decision forecast convert and retain better than those who don’t, and then A/B test the onboarding flow that gets users there.

_____

## Onboarding prototype

[Prototype link](https://contract-compass-forecast.lovable.app) (Module 2 version)

**Final project version:** [FinWise onboarding prototype, extended](https://deal-horizon-predictor.lovable.app)

The extended version keeps the Module 2 flow and adds three things, switchable from the header:

- **Example first:** an exploring user can see an example forecast before entering any data, then click "Try it with my numbers". Example forecasts can't be saved, so they never count as activation.
- **Accountant path:** an invited accountant lands directly on the shared forecast with no setup, tries their own upfront-payment scenario next to the owner's, sends a review, and can optionally invite another client. This demonstrates the accountant-as-multiplier loop.
- **Event tracking by entry point:** every event records whether it came from an owner trial or an accountant invite. Only a forecast saved after editing the owner's own inputs counts as activation.

The core owner flow (screens 1–4) is what the first A/B test compares with current onboarding. "Example first" and the accountant path are tested separately later.

<img width="711" height="434" alt="image" src="https://github.com/user-attachments/assets/7fd897d1-0a8b-4f1e-b274-caae414ce6b5" />

_____

<img width="418" height="424" alt="image" src="https://github.com/user-attachments/assets/e042dc08-e8fa-4346-ba5c-4f643c6e9da4" />

_____

<img width="413" height="449" alt="image" src="https://github.com/user-attachments/assets/fca10fbd-cec3-4572-b883-76b888ca4b0e" />

_____

<img width="429" height="410" alt="image" src="https://github.com/user-attachments/assets/8394b72d-020d-4af9-8768-bf1046a9bf88" />

_____

## Why this activates

This works because it answers a real decision. A bank balance or a chart shows information that most banks already offer to SMBs. This tells the owner what to do: take the contract or not, take it but ask for a credit line, or hire an additional person. It also repeats. There is always a new contract for SMBs, always a new decision to make, which gives the user a reason to come back to the tool and keep paying, because it is useful. It is also naturally collaborative: SMB owners always share their decisions with someone, such as an accountant or a business associate, which feeds the collaboration loop.

_____
