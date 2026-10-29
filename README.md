# Case Interview Drill Kit

A practice kit for **problem-solving case interviews** at fintech and product companies: the 35-minute, interviewee-led cases where you're told something like *"profit fell 20% while users grew 10%, what's going on?"* and have to find the cause, size it, and recommend what to do.

Everything here was built and tested over two weeks of daily practice. All companies, plans and numbers in the cases are **fictional** ("Acme" is a made-up digital bank).

## What's inside

| Folder / file | What it's for |
|---|---|
| [`METHOD.md`](METHOD.md) | The 8-step method, timing, maths habits and the summary formula. Read this first. |
| [`RUBRIC.md`](RUBRIC.md) | How to score a case (8 dimensions, 1–4) and what a "4" looks like. |
| [`COACH_PROMPT.md`](COACH_PROMPT.md) | A prompt that turns an AI assistant into a strict interviewer, plus rules for a friend playing interviewer. |
| [`GENERATE_CASES.md`](GENERATE_CASES.md) | **A prompt that writes a fresh case every day**, aimed at your weak spots, in the same format as the examples. |
| [`cases/`](cases/) | 9 worked cases to start with. Each has the opening prompt, a hidden interviewer key and a model answer. |
| [`warmups/`](warmups/) | 3-minute maths warm-ups and 60-second summary drills. |
| [`tools/mock-interviewer.html`](tools/mock-interviewer.html) | Open in a browser, paste an interviewer line, and hear it read aloud. |

## How to practise

1. **Read [`METHOD.md`](METHOD.md)** and copy the 8 steps onto a sheet of paper.
2. **Pick a partner.** Either a friend (they read the interviewer key) or an AI assistant using [`COACH_PROMPT.md`](COACH_PROMPT.md) (paste in the case file).
3. **Don't open the interviewer key** of a case you plan to do. Keys sit inside collapsed sections marked *Interviewer only*.
4. **Warm up for 3 minutes** with a set from [`warmups/maths-warmups.md`](warmups/maths-warmups.md).
5. **Run the case for 35 minutes**, with time checks at 6, 20 and 30 minutes.
6. **Score it** with [`RUBRIC.md`](RUBRIC.md), then read the model answer.
7. **Redo the same case** a day later if you scored under 20/32. Repeating a case you know drills the method.
8. **Once you've done a few, generate a new case every day** with [`GENERATE_CASES.md`](GENERATE_CASES.md), and keep a short log so each new case targets your weak spots.

## The 9 worked cases (suggested order)

| # | Case | Type | Main skill |
|---|---|---|---|
| 01 | [Card top-ups drop](cases/01-card-top-ups.md) | Operational root cause | Confirm the mechanism before solving |
| 02 | [Transfer revenue down, volume up](cases/02-transfer-revenue.md) | Pricing / P&L | Build a revenue bridge |
| 03 | [Crypto revenue down, market up](cases/03-crypto-revenue.md) | Cannibalisation | Who moved, and were they at risk? |
| 04 | [Onboarding drop-off](cases/04-onboarding-dropoff.md) | Funnel | Narrow down step → platform → device |
| 05 | [Card fraud losses double](cases/05-card-fraud.md) | Risk vs growth | Weigh an OKR win against its cost |
| 06 | [Paid plans: profit down, subscribers up](cases/06-paid-plans-profit.md) | Commercial, multi-step maths | Customer value vs acquisition cost |
| 07 | [Checkout profit down, volume up](cases/07-checkout-profit.md) | Commercial | Check every branch before solving |
| 08 | [Trading: profit negative, users up](cases/08-trading-free-trades.md) | **Sparse data**, unit economics | Profit per user per plan, "assume 100 users" |
| 09 | [Gym chain (10-min mini)](cases/09-gym-mini.md) | Unfamiliar industry | Fast frame, goal and tree |

Case 08 is the hardest type: the interviewer gives almost no absolute numbers, so you have to build the unit economics yourself. If you only have time for one case, do that one.
