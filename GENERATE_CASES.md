# Generating a New Case Every Day

The 9 cases in [`cases/`](cases/) are worked examples. Once you've done a few, use the prompts below to get a **fresh case every day**, in the same format, aimed at your weak spots.

## Why two chats

An AI interviewer needs the hidden numbers (the key) before the case starts, but you mustn't see them. So:

1. **Chat 1, the case writer**, writes a complete case file: opening prompt, hidden key and model answer.
2. **Chat 2, the interviewer**, gets that file and runs the case with you. Copy it across **without reading it**.

## Step 1: the case writer prompt

Fill in the three lines under "Today's case", then paste into a new chat.

```text
You write practice cases for 35-minute problem-solving case interviews at fintech and product companies. The candidate is told something like "profit fell while users grew" and must frame it, find the cause, size it in money and recommend fixes.

Write ONE new case as a single markdown file in exactly this structure:
- Title line: "# [short name]"
- A line with Type, Time (35 min) and Main skill
- "## Opening prompt (read aloud)": 2-4 sentences, as an interviewer would say them, with only the headline facts
- A collapsed section "<details><summary><b>Interviewer only: data key</b></summary>" containing: the profit model; a two-period headline table; 2-3 hidden drivers, each revealed only when asked about directly; one red herring; one constraint; and answers to the follow-up questions a strong candidate would ask
- A collapsed section "<details><summary><b>Model answer</b></summary>" containing: frame and goal (money target and deadline, with a reason); a breakdown table in money that adds up to the total change; hypotheses and how each is tested; quick and long-term fixes, each sized; trade-offs and a test or rollout; a 30-second summary (problem, cause, fix, impact); common mistakes
An example of the format: https://raw.githubusercontent.com/els-p/case-interview-drill-kit/main/cases/07-checkout-profit.md

Today's case:
- Type: [rotate | operational root cause | pricing and P&L bridge | cannibalisation | funnel drop-off | risk vs growth | customer value vs acquisition cost | sparse-data unit economics | unfamiliar industry]
- Product or industry: [e.g. digital bank, crypto exchange, telco, streaming, food delivery, airline; or "surprise me"]
- My recent weak spots: [paste the last 3 rows of your log, or "none yet"]

Rules:
- Use a fictional company. Use round numbers so the maths can be done on paper.
- Make the numbers reconcile: the headline table, the hidden drivers and the breakdown must add up exactly. Check this before you output anything.
- The obvious first explanation should be incomplete. The full answer should need both the revenue and the cost side.
- Make the case target my weak spots where possible.
- If the type is "rotate", pick a different type from my last case, and choose "sparse-data unit economics" at least every other day.
- For sparse-data unit economics: give unit prices and unit costs, plan tiers with free allowances or perks, mixes in % rather than absolute numbers, a "don't know" answer to 1-2 questions, and one ambiguous number the candidate should clarify (e.g. "plus 10 in fixed costs"). The insight should come from profit per user per plan, the break-even, heavy vs light users, or which team's P&L carries the cost. The model answer must include a profit-per-user-per-plan table, the break-even and a "per 100 users" illustration.

Output only the case file. No commentary before or after it.
```

## Step 2: run it

1. Open a **new** chat.
2. Paste the interviewer prompt from [`COACH_PROMPT.md`](COACH_PROMPT.md).
3. Paste the case file underneath it, without reading it. (If your app can attach files, save it as a `.md` file and attach it instead.)
4. Practise for 35 minutes, then let the interviewer score you.

## If you'd rather use one chat

This works, but the AI is more likely to drift from its own numbers. Paste the case writer prompt, then add:

```text
Change of output: don't show me the case file. Output only the opening prompt in plain text, plus the whole case file encoded in base64 inside a code block labelled KEY, so I can't read it. Then act as my interviewer following these rules: [paste the interviewer prompt from COACH_PROMPT.md]. Use only the facts in the KEY for every answer. When the case ends, decode the KEY and show the model answer.
```

## Keep a short log

After each case, add one row. Paste the last 3 rows into the case writer prompt so new cases aim at your weak spots.

| Date | Case | Type | Score /32 | Top 3 fixes |
|---|---|---|---|---|
| | | | | |

## Make it daily

If your AI app supports scheduled tasks or reminders, schedule the case writer prompt with Type set to "rotate" and a fixed time each day. If it can't hide the key from you in a scheduled run, schedule a reminder instead and run the two chats yourself.
