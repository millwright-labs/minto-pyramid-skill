# Evaluations

`cases.json` follows the eval structure in [Anthropic's skill authoring best practices](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/best-practices): a query, optional input files, and a list of expected behaviours. There is no official runner — this is a rubric, scored by reading the output.

## What is being tested

Most of these cases test **restraint, not capability.** The interesting failure for this skill is not "can it build a pyramid" — any capable model can. It is:

1. **Over-firing** — imposing conclusion-first structure on a timeline, a tutorial, or a thank-you note, where it makes the writing worse.
2. **Acting unasked** — returning a rewrite of someone's draft when they only asked you to look at it.
3. **Inventing** — sharpening a source's facts while compressing.
4. **Manufacturing a conclusion** — forcing a thesis onto analysis that doesn't support one yet.

Three of the eight cases (04, 05, 06) are expected to produce **no pyramid at all**. A version of this skill that "passes" by restructuring everything has failed.

## How to run

Start a fresh session with the skill installed, paste one case's `query` (with its file), and let the agent respond as it normally would. Do not tell it that it is being evaluated, and do not mention the skill unless the query itself does — cases 02 and 08 name it deliberately, the rest do not. Score the response against `expected_behavior`.

Anthropic's guidance is to test across Haiku, Sonnet and Opus, since a skill is an addition to a model and weaker models need more explicit guidance. Restraint instructions are the ones most likely to degrade on a smaller model, so the gate is worth re-checking whenever you change it.

## Known limitation of this harness

Running the cases through subagents is not identical to a real user session: the request arrives as a task rather than as conversation, and an agent asked to "respond as you normally would" is aware it is producing a specimen. Worse, **the fixture path leaks the test** — in a trial run, one agent read the path `evals/fixtures/` and correctly guessed it was being checked for whether the skill fires on tutorial content. It still behaved correctly, but that result is contaminated. Copy fixtures somewhere neutral before scoring a case you care about.

Treat these results as a strong signal about the gate, not a certificate. The most reliable check is still using the skill for a week and noticing when it annoys you.
