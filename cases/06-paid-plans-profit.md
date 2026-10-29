# 06 · Paid Plans: Profit Down, Subscribers Up

**Type:** commercial, multi-step maths · **Time:** 35 min · **Main skill:** what's a customer worth vs what they cost to acquire

## Opening prompt (read aloud)

> "Acme sells two paid plans in Asia-Pacific, Plus and Pro. Over the last quarter, subscription gross profit fell about 20%, even though the number of paid subscribers grew about 10%. The Head of Subscriptions wants to know what's going on and what to do about it."

<details>
<summary><b>Interviewer only: data key</b> (don't open if you're the candidate)</summary>

Currency S$, quarterly. Reveal only when asked specifically.

**Profit model**
- Subscription gross profit = fee revenue (list price × subscribers, minus discounts, promos and free trials) − benefit costs (cashback, lounge access, travel insurance claims, partner perks, Pro's premium card).
- FX, interchange and interest sit in **other** P&L lines. Acquisition cost sits in marketing.
- Free-trial users **count** as paid subscribers.

**Headline**

| | Q1 | Q2 |
|---|---|---|
| Paid subscribers | 1.00M | 1.10M (+10%) |
| Plus / Pro | 650k / 350k | 800k / 300k |
| List price per quarter | Plus S$30, Pro S$60 | no change |
| Gross revenue | 40.5M | 42.0M |
| Discounts | 2.0M (~5%) | 6.3M |
| Net revenue | 38.5M | 35.7M |
| Benefit cost per subscriber | Plus S$8, Pro S$25 | Plus S$9, Pro S$30 |
| Benefit costs | 13.95M | 16.2M |
| Subscription gross profit | 24.55M | 19.5M (−5.05M) |

**Discounts in Q2:** regular ~5% = 2.1M; **new** 3-month free trial on Plus, 60k users = 1.8M; **new** annual promo 40% off Plus, 200k subscribers = 2.4M.

**Benefit cost changes:** Plus +S$1 (more cashback use, a new streaming perk). Pro +S$5 (travel season: lounges and insurance claims).

**Subscriber flows (Q2):** 220k joined, 120k left. 70% of joiners came through a promo or trial. 20k Pro subscribers downgraded to Plus (to get the promo); 30k Pro cancelled.

**Unit economics (if asked)**

| | Profit per quarter | Leave each quarter | Value in year 1 | Acquisition cost |
|---|---|---|---|---|
| Promo Plus | S$9 | 10% | ~S$31 | S$45 |
| Full-price Plus | S$21 | 5% | ~S$78 | S$30 |

- Half of promo subscribers renew at full price after year 1; 2-year value ~S$57.
- 40% of trial users convert to paying.
- Marketing spend S$9M (up from 5M); 220k joiners.
- Segments (if asked): of the 200k on the annual promo, ~60k are heavy card and FX users (renew at full price ~80%), 140k light users (~37%).

**Red herring:** FX revenue from subscribers +8% (travel season). Different P&L line.

**Constraints:** list prices are locked this quarter. The partner perk contract runs 12 months (eligibility can change, not the fee).
</details>

<details>
<summary><b>Model answer</b></summary>

**Frame and goal:** profit per subscriber fell ~27% (0.8 ÷ 1.1). Goal: get total profit back to ~S$24.5M a quarter within two quarters (annual promo subscribers are locked in for a year; changes need testing). With 1.1M subscribers, that's ~S$22 each.

**Breakdown**

| Driver | Working | S$ |
|---|---|---|
| More Plus subscribers | +150k × S$30 | +4.5M |
| Fewer Pro subscribers | −50k × S$60 | −3.0M |
| Higher discounts | 6.3 − 2.0 | −4.3M |
| Higher benefit costs | Plus +S$1 × 800k = 0.8; Pro +S$5 × 300k = 1.5 (−0.05 mix) | −2.25M |
| **Total** | | **−5.05M ✓** |

**Hypotheses tested:** the Plus promos pulled customers down from Pro (20k downgrades confirmed). Pro's cost rise is seasonal travel claims, so watch it rather than make it the main fix.

**Is a promo subscriber worth it?** Promo subscribers pay back in ~18 months vs ~5 for full price. They do pay back, slowly, so **change** the promos rather than kill them.

**Fixes**

| Fix | How to size it | Saves per quarter |
|---|---|---|
| Free trial 3 months → 1, card on file | S$20 × 60k | ~1.2M |
| Annual promo only for heavy card/FX users (or 40% → 20%) | ~70% of 2.4M (or S$6 × 200k) | ~1.2–1.7M |
| No Plus promo for existing Pro customers | each downgrade loses S$9 instead of S$21: S$12 × 20k | ~0.24M |
| Travel season ends | S$5 × 300k | ~1.5M (seasonal) |

- **Long-term fix:** a standing rule that promos only run where subscribers pay back within 12 months (when annual subscribers decide whether to renew); a retention offer only for Pro customers who are leaving.
- **Trade-offs:** slower subscriber growth; some Pro customers still downgrade; marketing may push back. Test the shorter trial in one market first.

**Summary:** "Gross profit fell S$5M even though subscribers grew 10%. Two Plus promos cost S$4.3M in discounts and pulled 20k customers down from Pro. Benefit costs rose S$2.25M, mostly seasonal Pro travel claims. Promo subscribers take about 18 months to pay back versus 5 at full price, so I'd change the promos, not kill them: 1-month trials, the annual promo only for heavy card and FX users, and no promo for Pro customers. That recovers about S$3M a quarter, plus about S$1.5M as travel costs ease, close to the whole gap, while we track that growth holds."

**Common mistakes:** a tree that only restates the definition; killing the promo without checking customer value; skipping the benefit-cost branch.
</details>
