# 01 · Card Top-ups Drop

**Type:** operational root cause · **Time:** 35 min · **Main skill:** confirm the mechanism before solving

## Opening prompt (read aloud)

> "Acme is a digital bank in Singapore. Successful card top-ups, where customers fund their Acme account from an external debit or credit card, fell 18% week on week. App sessions are flat. What's going on, and what would you do?"

<details>
<summary><b>Interviewer only: data key</b> (don't open if you're the candidate)</summary>

Reveal each item only when the candidate asks a question that would get it.

**Baseline**
- Card top-ups are free to the user; Acme pays ~1.2% acquiring cost.
- Other funding: PayNow/FAST (~S$0.05 per transaction), bank transfer.
- Last week: 400k successful card top-ups, average S$120 (S$48M). This week: 328k (S$39.4M).
- Monetisation: funded money is spent on the Acme card. Revenue ~0.9% of card spend. About 80% of funded money is spent within 30 days.

**Funnel (attempts vs success)**
- Attempts: 470k → 465k (flat). Success rate 85% → 70.5%. A conversion problem, not demand.

**Segments**
- iOS and Android down equally. No app release this week.
- Visa and Mastercard both down; debit and credit both down.
- Issuer: **Bank A** (~35% of attempts) success 86% → 42%. Other issuers stable at 84–86%.
- Bank A on **desktop web**: 84%. Bank A **in-app**: 38%.
- 30% of failures are users in their first 7 days.

**Failure detail (decline codes / 3DS)**
- Bank A failures aren't issuer declines. 3DS completion fell 92% → 45%; error "authentication timeout".
- Bank A switched 3DS to approval in its own banking app on Tuesday and told customers by SMS.
- In the Acme app, 3DS runs in a WebView. After approving in Bank A's app, the deep link doesn't return the user to the WebView session, so it times out. On desktop the browser polls, so it works.
- Support tickets "top-up failed" +240% week on week.

**What happens to users who fail**
- 55% fund another way within 24h; 45% don't fund that week.
- New users whose first top-up fails: 90-day retention 38% (vs 71%). Lifetime value of a retained user ~S$60.
- ~12k new users a week hit a failure.

**P&L a strong candidate works out**
- Lost volume: 72k × S$120 ≈ S$8.6M a week.
- Acquiring cost not paid: S$8.6M × 1.2% ≈ **+S$103k a week** (a "saving").
- Unfunded 45% = S$3.9M × 80% spent × 0.9% ≈ **−S$28k a week**.
- New-user value at risk: 12k × 33pp × S$60 ≈ **−S$238k a week**. This dominates.
- Net ≈ −S$165k a week, plus support cost.
- Bonus: card top-up acquiring costs ~S$576k a week. Shifting 30% to PayNow saves ~S$170k a week.
</details>

<details>
<summary><b>Model answer</b></summary>

- **Root cause:** one issuer's 3DS change (approve in their banking app) breaks the return to the Acme in-app WebView, so authentication times out. Desktop is fine.
- **Quick fixes (days):** for Bank A cards in-app, open 3DS in the system browser or extend the timeout with a "return to Acme" prompt; offer PayNow as a one-tap fallback on failure; escalate to Bank A and the 3DS vendor; in-app message and support macro.
- **Long-term fixes (weeks):** native 3DS SDK with proper app-to-app handling; success-rate alerts per issuer (a 44pp drop should page someone within hours); make PayNow the default funding method (cheaper and more reliable).
- **Trade-off:** PayNow-first cuts cost but doesn't help users who only have a card.
- **Summary:** "Card top-ups fell 18% because one issuer's new 3DS flow breaks in our app. It's costing about S$165k a week, mostly from new users who never get started. Fix the redirect now, steer people to PayNow, and add per-issuer monitoring. That protects about S$200k a week."
- **Common mistake:** calling it "user education" before asking for the app vs web split.
</details>
