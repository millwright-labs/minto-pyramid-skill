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

## What this does not establish

Sonnet only. Anthropic's guidance is to test across Haiku, Sonnet and Opus, and restraint instructions are exactly the kind that degrade on a smaller model — a Haiku run is the obvious next check. Eight cases is also a thin benchmark; it covers the failure modes that were actually observed, not the space of possible ones.

