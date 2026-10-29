# 04 · Onboarding Drop-off

**Type:** funnel · **Time:** 35 min · **Main skill:** narrow down step → platform → device → reason

## Opening prompt (read aloud)

> "We're seeing drop-off in Acme's onboarding funnel in Singapore. How would you investigate and resolve this?"

<details>
<summary><b>Interviewer only: data key</b> (don't open if you're the candidate)</summary>

Reveal each item only when asked specifically.

**Context**
- About 40k new sign-ups a month. Revenue per funded user ~S$60 a year. Acquisition cost ~S$25 per sign-up.
- Funnel: sign-up started → personal details → ID scan → selfie/liveness check → KYC decision → approved → funded within 7 days → first card transaction.
- Completion from sign-up to approved fell from 62% to 48–49% over 4 weeks. The drop started ~3.5 weeks ago.

**Step conversion (before → after)**
- Started → details: 90% → 89%
- Details → ID passed: 88% → 87%
- ID → liveness passed: **92% → 74%**
- Liveness → approved: 85% → 85%
- Approved → funded: 70% → 70%; funded → first card transaction: 80% → 80%

**Liveness by platform** (45% iOS / 55% Android)
- iOS 93% → 90%; Android 92% → 61%
- Android flagship 88%, mid/low-end 52%. Mid/low-end is ~65% of Android sign-ups.
- Android failure reasons: poor lighting/image quality 60%, timeout 25%, "spoof detected" 15%.
- After 3 failed attempts, users are locked out for 24h; 70% never come back.
- "Selfie not working" tickets up 4x.

**What changed**
- An app release 3.5 weeks ago upgraded the liveness vendor SDK (stricter matching), requested by Risk/Compliance after a rise in deepfake onboarding fraud. **Compliance won't allow a rollback.**

**Fraud**
- New-account fraud: 0.30% → 0.12% of approved accounts. Average loss ~S$800 per fraudulent account.

**Options if asked**
- Manual video review: ~S$3 each, 10-min turnaround possible under 3k a month.
- Government digital ID (available to ~80% of residents) is integrated for address proof but not identity.

**Red herring**
- A social media acquisition campaign started 2 weeks ago (15% of sign-ups). Those users complete at ~40% vs ~50%; mix explains about 1pp. The drop started before it.

**P&L**
- Lost approvals ≈ 40k × 13pp ≈ 5,200 a month → × 70% funded ≈ 3,640 → × S$60 ≈ S$218k a year per monthly group (~S$2.6M a year run-rate).
- Wasted acquisition cost ≈ 5,200 × S$25 ≈ S$130k a month.
- Fraud saved ≈ S$40k a month.
</details>

<details>
<summary><b>Model answer</b></summary>

- **Root cause:** the new liveness SDK fails on mid/low-end Android cameras, and the 3-attempt lockout turns failures into lost customers.
- **Quick fixes:** on-screen capture guidance and auto-capture; the SDK's lower-resolution mode on low-tier devices; replace the 24h lockout with manual video review (~S$3) for image-quality failures. Keep the strict check for spoof signals.
- **Long-term fixes:** risk-based liveness (strict check only when risk signals say so); government digital ID as the identity route (skips the selfie for ~80%); a second vendor as fallback; a device-tier test gate on SDK releases.
- **Guardrail:** fraud stays ≤0.15%. Goal: completion back to ~60%.
- **Summary:** "Onboarding completion fell from 62% to 48% because the new liveness check fails on cheaper Android phones, and the lockout stops people retrying. We're losing about 5,000 approved customers a month, worth ~S$2.6M a year plus S$130k a month in wasted acquisition. We can't roll back, so: manual review instead of lockout now, then risk-based checks and digital ID. Target ~60% completion with fraud under 0.15%."
- **Common mistakes:** leading with a rollback Compliance already refused; re-applying an overall rate on top of step rates.
</details>
