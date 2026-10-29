# 05 · Card Fraud Losses Double

**Type:** risk vs growth · **Time:** 35 min · **Main skill:** weigh a growth win against its full cost

## Opening prompt (read aloud)

> "At Acme UK, fraud losses on online card payments rose from 4 to 9 basis points of online card volume over 8 weeks. What's going on, and what would you do?"

<details>
<summary><b>Interviewer only: data key</b> (don't open if you're the candidate)</summary>

Reveal each item only when asked.

**Baseline**
- Online card volume ~£2.0B a month, +3% over the period.
- Revenue: interchange ~0.2% of volume ≈ £4M a month.
- Liability: if Acme approves without a 3DS challenge (or grants an exemption), Acme eats the fraud. If the merchant skipped 3DS, Acme can charge it back.
- Net fraud losses: £0.8M → £1.8M a month.

**Where**
- 80% of the extra loss is on transactions Acme approved **without a challenge**, so it can't be recovered.
- Challenge rate fell **18% → 9%**. Approval rate rose **93.0% → 94.2%**.

**Segments**
- Gift cards / digital vouchers: 6% of volume but **65%** of new losses. Marketplaces 15%.
- £50–£250, many back-to-back transactions on one card within minutes.
- Mostly cards older than 6 months (real customers' cards, not mule accounts).

**What changed**
- **Week 0:** the risk team shipped a new 3DS threshold to cut friction (growth goal: approval rate +1pp). No guardrail by merchant category.
- **Week 2:** victims mention a fake "parcel delivery fee" text-message phishing campaign. Industry-wide; other banks' losses rose less.

**Customer / ops**
- Fraud disputes 2.1x. ~30k extra support contacts a month at ~£6 = **£180k a month**.
- ~15k extra victims a month; their 90-day churn 12% vs 4%. Value ~£90 → **~£108k a month**.

**P&L**
- Gain: +1.2pp approvals × £2B = £24M × 0.2% = **+£48k a month**.
- Costs: fraud **−£1.0M**, support −£180k, churn −£108k.
- Net ≈ **−£1.24M a month**. The growth win is ~25x smaller than its cost.
</details>

<details>
<summary><b>Model answer</b></summary>

- **Root cause:** a loosened no-challenge threshold let phished cards through on gift-card merchants. An external trigger, made much worse by an internal change.
- **Quick fixes:** bring back challenges for high-risk categories above ~£50 and for rapid repeat payments (3+ within 10 minutes); block known phishing merchant names; reissue compromised cards; in-app phishing warning. Recovers ~70% of the extra loss for ~0.3pp of approvals (≈ −£12k interchange).
- **Long-term fixes:** challenge decisions based on expected fraud loss vs friction cost, by merchant category; fraud basis points as a mandatory guardrail on any approval-rate goal, with automatic alerts; tokenised card numbers on virtual cards; share phishing intelligence with the industry.
- **Summary:** "Fraud losses doubled because we loosened our challenge threshold just as a phishing campaign hit, and stolen cards went through on gift-card merchants. The approval gain is worth £48k a month; the cost is about £1.24M. Re-tighten challenges on high-risk categories now, recovering ~£0.9M a month for ~£12k of interchange, then move to cost-based challenge decisions with fraud guardrails."
</details>
