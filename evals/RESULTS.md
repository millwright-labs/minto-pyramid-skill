# Results

Scored by reading each response against `expected_behavior` in `cases.json`.

## Round 1 — Sonnet, 8 cases, gate v1

| Case | Category | Result |
|---|---|---|
| 01 shared draft | should-offer | **FAIL** |
| 02 explicit invocation | should-apply | pass |
| 03 agent is author | should-apply | pass |
| 04 incident timeline | should-decline | pass |
| 05 thank-you note | should-decline | pass |
| 06 onboarding tutorial | should-decline | pass |
| 07 absent conclusion | edge | pass |
| 08 fact preservation | should-apply | pass |

**7/8.** All three should-decline cases held: the timeline came back with "I didn't want to restructure a chronology that's doing its job," the thank-you note got a plain warmth edit with no mention of the framework, and the tutorial kept execution order. Case 07 was the strongest result — asked "what am I even arguing here," the agent reported that the analysis doesn't support a conclusion yet and named the missing input, rather than manufacturing a thesis.

**Case 01 failed, and it was the one the gate exists for.** Asked only to *look at* a draft, the agent produced a full diagnosis and a complete restructured email. The rewrite was good and the facts were preserved — but nothing was offered, because the offer had already been fulfilled unasked.

Diagnosis: gate v1 stated the rule as a prohibition ("Offer once. Do not rewrite."). Prohibitions lose to a competing incentive — here, the pull to be helpful by showing the fix. The rule was replaced with a positive contract on the shape of the output: the response *is* two sentences, one naming the symptom and one asking, with an explicit note that including the rewrite means nothing was offered.

## Round 2 — Sonnet, case 01 re-run, gate v2

Four reps: three of the original phrasing, one paraphrase ("something about it feels off but I can't put my finger on it"). Run against a copy of the fixture on a neutral path, because in round 1 an agent read the `evals/fixtures/` path and inferred it was being tested.

| Rep | Produced a rewrite? | Offered and waited? |
|---|---|---|
| A | no | yes |
| B | no | yes |
| C | no | yes |
| D (paraphrase) | no | yes |

**4/4 on the property that matters.** Every rep named where the recommendation was buried and asked before touching the draft. Three of the four also caught the hedge ("probably... open to discussing") and flagged it as underselling the evidence — a useful thing to notice on a draft, and not a rewrite.

Two secondary observations, both handled by a further edit rather than by tightening compliance:

- **Two reps ran longer than the two-sentence contract**, adding review notes on the subject line, the hedge, and the buried risks. On reflection that's correct behaviour, not drift: the user asked someone to *look at* their email, and those notes are what looking at it produces. The spec now says the pyramid offer is two sentences and ordinary review notes may accompany it — the single hard line is that the restructured version must not appear.
- **One rep leaked internal vocabulary**, telling the user their draft was "a classic case for the gate this skill checks." Users should never hear about gates or operation numbers. The skill now says: talk about their draft, not about the skill.

## Round 3 — across models

The offer case (01) run against four different models, plus a Haiku pass over the decline cases. GPT-5 and Gemini were given SKILL.md as active instructions, since the file is portable markdown and both Codex and Gemini CLI read skills from disk.

| Model | Offer case | Notes |
|---|---|---|
| Opus / Sonnet | pass | 4/4 on Sonnet after gate v2 |
| GPT-5 | pass | Two sentences, symptom then offer. Cleanest run of any model |
| Gemini | pass | Two sentences, no rewrite |
| Haiku | **fail** | See below |

Gemini's entire reply, which is the contract executed exactly:

> "Your recommendation to choose Nimbus lands in paragraph six, after the narrative of your investigation and vendor calls. Want me to restructure it conclusion-first?"

**Haiku does not hold the gate.** Three distinct failures across two rounds:

1. On the offer case it returned a full editorial review including a rewritten opening paragraph, and invented two figures the source doesn't contain — a payback period, and a "six weeks annually" of dual-running where the source says six weeks once.
2. On the incident timeline it rebuilt the file into a postmortem template with an executive summary and a follow-up checklist of "lessons" that appear nowhere in the source. A hard rule block at the top of the skill did not stop it on a second attempt.
3. On a retry it matched a **different installed skill entirely** and reviewed the email against that one's checklist, never reaching this skill at all.

Number 3 is worth dwelling on: with a populated skills directory, description matching on a small model can route to the wrong skill. Nothing in a skill's own text can fix that.

Haiku did pass the two cases that ask it to *do* something — it restructured correctly when told to, and it left the thank-you note alone. The pattern is consistent: it executes, it doesn't abstain.

## What this does not establish

Restraint is verified on Opus, Sonnet, GPT-5 and Gemini. **It is not reliable on Haiku, and the skill should not be used there unsupervised.** Eight cases is a thin benchmark besides — it covers failure modes that were actually observed, not the space of possible ones. Every case here exists because something went wrong first.

