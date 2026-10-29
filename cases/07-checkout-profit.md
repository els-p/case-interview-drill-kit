# 07 · Checkout Profit Down, Volume Up

**Type:** commercial · **Time:** 35 min · **Main skill:** check every branch before solving

## Opening prompt (read aloud)

> "Acme Pay is our checkout product for online merchants in Singapore. Last quarter, Acme Pay gross profit fell about 20%, even though the value of transactions we processed grew about 20%. The Head of Merchant Payments wants to know why, and what we should do."

<details>
<summary><b>Interviewer only: data key</b> (don't open if you're the candidate)</summary>

Quarterly, S$. Reveal only when asked specifically.

**Profit model:** gross profit = merchant fees (transaction value × fee rate) − processing costs (card scheme fees paid to Visa/Mastercard, % of value) − fraud and chargeback losses. Sales costs sit elsewhere.

**What changed (if asked):** five large merchants signed last quarter on a lower fee rate; Visa and Mastercard raised scheme fees from 1 April; **no change to fraud rules or the chargeback process** (losses did change; the candidate has to ask about losses separately).

**Headline**

| | Q1 | Q2 |
|---|---|---|
| Transaction value | 250M (all existing merchants) | 300M (250M existing + 50M from 5 new large merchants) |
| Fee rate | existing 2.0% | existing 2.0%, large 1.0% |
| Merchant fees | 5.0M | 5.5M |
| Processing cost rate | 0.8% | 0.9% (market-wide rise) |
| Processing costs | 2.0M | 2.7M |
| Fraud & chargeback losses | ~0 | 0.4M |
| Gross profit | 3.0M | 2.4M (−0.6M) |

**Fraud detail:** ~90% (0.36M) at one new large merchant, a consumer electronics retailer: card testing and stolen cards buying phones. ~80% of the cards issued abroad, many banks, both schemes. Pattern: a never-seen card makes several tiny test payments, then buys phones within minutes. **3DS is switched off there** because Sales agreed a frictionless checkout. Existing merchants: ~0.04M, normal.

**If asked**
- 3DS on high-risk transactions only would stop ~75% of this fraud, with ~2% fewer completed purchases on those transactions.
- Existing merchant contracts can be repriced with 30 days' notice; ~10% are price-sensitive (a competitor charges 1.8%). Large merchant contracts are fixed for 12 months, renewing in 6; their fraud clause allows checks on high-risk transactions.
- Large merchants bring 20k new app sign-ups a quarter; 25% stay active; an active user is worth ~S$15 a quarter; normal acquisition cost S$40 per active user.
- Transaction count +30% with a smaller average ticket (lots of small food orders). **Red herring.**
</details>

<details>
<summary><b>Model answer</b></summary>

**Frame and goal:** profit per dollar processed fell a third (0.8 ÷ 1.2). Goal: back to ~S$3M a quarter within one to two quarters, keeping the growth.

**Breakdown**

| Driver | S$ |
|---|---|
| New large merchants: fees +0.5M − processing at the old rate 0.4M | +0.1M |
| Scheme fee rise: 0.1pp × 300M | −0.3M |
| Fraud, mostly one merchant | −0.4M |
| **Total** | **−0.6M ✓** |

**Insights:** the large merchants pay 1.0% while the scheme cost is now 0.9%, so they make almost nothing, and lose money once fraud is counted. They do bring sign-ups, so keep them but reprice at renewal.

**Fixes**
- **Quick:** 3DS for high-risk, never-seen cards at the electronics merchant (~75% of 0.36M ≈ **0.27M**); pass the scheme rise to existing merchants with notice (250M × 0.1% ≈ **0.25M**), phased for price-sensitive merchants.
- **Long-term:** risk scoring at every merchant; a minimum price plus a fraud review before signing large deals; reprice large merchants at renewal with volume tiers and fraud liability.
- **Trade-offs:** some genuine shoppers fail 3DS (fewer completed purchases); the merchant relationship (they were promised frictionless checkout); some small merchants may leave over the price rise. Test 3DS on high-risk transactions only.

**Summary:** "Gross profit fell S$0.6M, or 20%, while transaction value grew 20%, so profit per dollar processed fell by a third. There are three causes. S$0.36M is fraud at one new electronics merchant, where we switched off 3DS to give them a frictionless checkout. S$0.3M is the scheme fee rise, which we absorbed. And our growth came from large merchants priced at 1%, which barely covers the new 0.9% cost. Now: switch on 3DS for high-risk, never-seen cards at that merchant, and pass the scheme rise on to existing merchants with notice. Long term: risk scoring at every merchant, and a minimum price plus a fraud review before large deals. That recovers about S$0.5M, close to 90%, within a quarter."

**Common mistakes:** striking off fraud because "the process didn't change"; assuming 3DS stops 100% and costs nothing; passing on the whole 0.7M processing rise (only 0.3M is the rate rise).
</details>
