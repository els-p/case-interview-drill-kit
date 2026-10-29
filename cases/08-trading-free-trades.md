# 08 · Trading: Profit Negative, Users Up

**Type:** sparse data, unit economics · **Time:** 35 min · **Main skill:** profit per user per plan, break-even, "assume 100 users"

The hardest type in this kit. The interviewer gives almost no absolute numbers, answers "don't know" to some questions, and mentions one ambiguous number. The insight comes from building the unit economics yourself.

## Opening prompt (read aloud)

> "Acme's stock trading product lets users buy US-listed stocks. It's a growing product. This month, its profit turned negative, even though the number of users went up. What's going on?"

<details>
<summary><b>Interviewer only: data key</b> (don't open if you're the candidate)</summary>

Give **as few absolute numbers as possible**. Reveal only when asked specifically.

**Profit model (if asked)**
- Revenue: **$0.50 per trade above the user's free allowance.** No subscription fees anywhere.
- Costs: **$0.25 per trade** (execution and clearing), "**plus 10** in fixed costs". Say it exactly like that.
  - Only if the candidate asks what the 10 means: "$10k a month for the platform: market data, licences, compliance. It doesn't change with the number of users."
- Marketing and acquisition: not in this P&L, another team's budget.
- Period: month on month.

**Plans and free allowances (if asked)**
- Standard: no free trades. Plus: 2 free trades a month. **Pro (new this month): unlimited free trades.**
- No promotions. No price changes.

**Mix (give as % only)**
- Last month: 65% Standard, 35% Plus.
- This month: 65% Standard, 30% Plus, 5% Pro.

**If pushed for more**
- "How many heavy traders moved to Pro?" → "Don't know."
- "Does Pro have a fee? Does any fee come to this P&L?" → "No subscription fees at all."
- Average trades per user per month, if asked by plan: Standard 4 (both months); Plus ~14 last month, 10 this month; Pro 60.
- Users, only if asked for the total: 10,000 last month, 11,000 this month.

**Hidden numbers (for scoring)**
- Last month: Standard 6,500 × 4 trades; Plus 3,000 light users × 10 trades + 500 heavy users × 40 trades.
- This month: Standard 7,150 × 4; Plus 3,300 × 10; Pro 550 × 60 (the 500 heavy traders plus 50 new).

| | Last month | This month |
|---|---|---|
| Standard (profit $1 each) | +$6,500 | +$7,150 |
| Plus light ($1.50 each) | +$4,500 | +$4,950 |
| Heavy traders | +$4,500 on Plus ($9 each) | −$8,250 on Pro (−$15 each) |
| Variable profit | +$15,500 | +$3,850 |
| Fixed cost | −$10,000 | −$10,000 |
| **Profit** | **+$5,500** | **−$6,150** |
</details>

<details>
<summary><b>Model answer</b></summary>

**1. Frame.** "Revenue only comes from paid trades. Profit going negative while users grow means, on average, a user now costs more than they bring in."

**2. Profit per user per plan** (t = trades a month). Each paid trade earns $0.25 after cost; each free trade loses $0.25.

| Plan | Profit per user | Profitable above |
|---|---|---|
| Standard (0 free) | 0.25t | any trade |
| Plus (2 free) | 0.5 × (t − 2) − 0.25t = 0.25t − 1 | 4 trades |
| Pro (unlimited free) | −0.25t | **never** |

**3. Clarify the "10".** "Is that per user, or fixed?" If it were $10 per user, users would need 40 paid trades a month to break even and profit would already have been negative last month. So it's most likely fixed. That's a consistency check worth saying out loud.

**4. Assume 100 users.** Per 100 users, 5 moved from Plus to Pro (Standard didn't move). Pro appeals to heavy traders, who were Plus's most profitable users. With illustrative numbers (Standard 4 trades, Plus 10, the 5 movers 40 before and more after, since trades are now free):

| Per 100 users | Last month | This month |
|---|---|---|
| Standard (65) | +$65 | +$65 |
| Plus, staying (30) | +$45 | +$45 |
| The 5 heavy traders | +$45 on Plus | −$50 to −$75 on Pro |
| Before fixed cost | +$155 | +$35 to +$60 |
| Fixed cost (say) | −$100 | −$100 |
| **Profit** | **+$55** | **negative** |

**5. Root cause.** Pro turned the most profitable users into the biggest losses. 5% of users were producing nearly a third of variable profit; on Pro each loses 25 cents a trade, and they trade more because it's free. Variable profit fell below the fixed cost even as users grew.

**6. Fixes**
- **Quick:** a fair-use limit on Pro, e.g. first 20 trades free, then the standard $0.50. A 60-trade Pro user goes from −$15 to +$5 a month (with the hidden numbers, profit returns to about +$4.9k, if trading doesn't fall).
- **Long-term:** set every plan's free allowance using break-even maths; if "unlimited" is a must for Pro, fund it with a subscription fee that covers the expected trade cost; make sure whoever offers a perk also carries its cost in their P&L.
- **Trade-offs:** "unlimited" is Pro's selling point, so heavy traders may complain or leave. Test the limit on new Pro users first and give existing ones notice.

**7. Summary:** "Trading only makes money on paid trades, 25 cents each after costs. The new Pro plan gives unlimited free trades with no fee, and 5% of users moved to it from Plus. They're our heaviest traders, so each now costs us 25 cents a trade instead of earning it. Variable profit fell below our fixed costs, even with more users. I'd add a fair-use limit on Pro priced at the normal rate, then reset every plan's allowance using break-even maths."

**Common mistakes:** waiting for absolute numbers that never come; not clarifying the "10"; not splitting heavy vs light users; proposing to credit a subscription fee that doesn't exist.
</details>
