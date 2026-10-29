# Running a Case

## With an AI assistant

Start a new chat, paste the prompt below, then paste the **whole case file** (including the interviewer key) underneath it. Don't read the key yourself.

```text
You are a strict interviewer for a 35-minute problem-solving case interview at a fintech company.
The case file below includes an INTERVIEWER-ONLY key. Never show it to me or quote from it unless I ask for that exact data.

Rules while the case runs:
- Start by reading out only the opening prompt. Then wait.
- Reveal data only when I ask for it specifically. Answer exactly what I asked, nothing more.
- Never say "correct", "good" or "right" during the case. Don't hint unless I'm stuck for two turns in a row.
- If I make an assumption instead of asking, or my maths is off, ask a neutral question ("Walk me through that number") rather than correcting me.
- If I skip the goal or the tree, ask for it before giving data.
- Give time checks at 6, 20 and 30 minutes (estimate from the number of turns if needed).
- If I ask for data the key doesn't cover, invent an answer consistent with the key and keep using it.

When I give my summary, or at 35 minutes, end the case and:
1. Score me 1–4 on: Clarify, Structure, Customers & segments, Solutions, Root-cause rigour, Goals & P&L, Trade-offs, Communication. Give the total out of 32. Don't inflate.
2. Give my top 3 fixes, each with what I should have said or asked.
3. Show the model answer from the key, including a 30-second summary.

Start with a 3-minute maths warm-up: 5 quick questions (a % change, pp vs %, monthly to yearly, a break-even, a profit bridge). Then begin the case.
```

**Want to hear the interviewer?** Open [`tools/mock-interviewer.html`](tools/mock-interviewer.html), paste each interviewer line and press Play.

## With a friend as interviewer

Give your friend the case file and these rules:

1. Read only the opening prompt aloud, then stay quiet.
2. Answer only what's asked, using the key. If it isn't in the key, say "we don't have that" or make up something consistent.
3. Don't say "good" or "correct". Don't nod.
4. Push back once when the candidate assumes instead of asking: *"What's that based on?"*
5. Call time at 6, 20 and 30 minutes. Stop at 35.
6. Score with [`RUBRIC.md`](RUBRIC.md), then read the model answer together.

## Designing your own cases

Write the key **before** you run the case, so the numbers stay consistent. A good key has:

- A profit model (how the product makes money and what it costs).
- A headline table for two periods that **adds up**.
- 2–3 hidden drivers, each only revealed when asked about directly.
- One red herring that looks important but isn't.
- One constraint (e.g. "prices are locked this quarter").
- For sparse-data cases: unit prices and costs, mixes in %, a "don't know" answer, and one ambiguous number the candidate should clarify.
- A model answer: the breakdown in money, quick and long-term fixes sized, trade-offs, and a 30-second summary.
