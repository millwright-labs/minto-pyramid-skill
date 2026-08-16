# minto-pyramid

An Agent Skill that makes your coding agent write the way consultants are taught to write: **answer first, then the reasons, then the evidence.**

Works in Claude Code, Claude Desktop, and anything else that reads Agent Skills. One file, no dependencies.

## Install

```bash
git clone https://github.com/millwright-labs/minto-pyramid-skill ~/.claude/skills/minto-pyramid
```

Windows (PowerShell):

```powershell
git clone https://github.com/millwright-labs/minto-pyramid-skill "$env:USERPROFILE\.claude\skills\minto-pyramid"
```

Or hand the repo URL to your agent and ask it to install the skill. Or download `SKILL.md` and drop it in `~/.claude/skills/minto-pyramid/SKILL.md`. Restart your session and it's live.

## Use

It triggers on its own when you ask for a recommendation, proposal, memo, exec summary, or a "make this clearer" edit. To force it:

```
Use the minto-pyramid skill on this draft.
```

Five operations are defined inside — restructure, buried-lede test, reason audit, so-what pass, email version. Ask for one by name, or hand it a draft and let it start with the restructure.

## What it actually does

The default order for a model is narrative: background, then findings, then the point — because that's the order most prose is written in. It buries the one line your reader needed. This skill inverts the order, enforces Minto's grouping rules on the middle layer, and bars the model from inventing facts while it tightens.

It is deliberately narrow. It declines incident timelines, runbooks, tutorials, and anything where chronology is the content, because forcing a pyramid onto those makes them worse.

## Provenance and fact-check

The idea came from [an Instagram post by @thewizeai](https://www.instagram.com/p/DcG_kY2lYSN/) (16 Aug 2026). The five prompts in that post are the seed of the five operations here. The framing around them had some slippage, so everything was checked before it was written down, and the skill was then reviewed by three other models and tested against a control.

**Checks that held**

- Barbara Minto joined McKinsey in 1963 in Cleveland and moved to the London office in 1966. ([Wikipedia](https://en.wikipedia.org/wiki/Barbara_Minto), secondary)
- Minto says she coined MECE. ([McKinsey alumni interview: "MECE: I invented it, so I get to say how to pronounce it"](https://www.mckinsey.com/alumni/news-and-events/global-news/alumni-news/barbara-minto-mece-i-invented-it-so-i-get-to-say-how-to-pronounce-it) — her own account, not independent confirmation)
- The pyramid's rules: every idea summarizes the ideas grouped below it, each group answers the question its parent raises, ideas in a grouping are the same kind of idea and in a logical order.
- MECE tests **inductive** groupings. It does not test a deductive chain, where premises force the conclusion jointly. Most short summaries of Minto blur the two.

**Corrections made**

- **"Exactly three reasons."** The post hard-codes three; so does most of the internet. It isn't one of Minto's rules — the logic determines the count. Forcing three is what manufactures the filler reason.
- **SCQA and the grouping rules are missing from the post entirely.** They're the part that makes the middle layer hold up, so both are here.
- **"The first woman McKinsey hired into consulting."** The documented claim is narrower — the first female MBA McKinsey hired. The skill makes no biographical claim at all, so this correction lives here rather than there.
- **Publication date: unsettled, so the skill doesn't state one.** Minto's own site says the book "was written in 1987 and re-issued by the publisher unchanged in 2002" ([barbaraminto.com](https://www.barbaraminto.com/)); earlier editions circulated from 1981; Wikipedia's 1985 doesn't match either. The expanded *Minto Pyramid Principle* is 1996.
- No primary source is cited above. The book itself was not consulted; these are author statements and secondary summaries, labelled as such.

**Tested**

The same messy 400-word recommendation email was rewritten twice: once by an agent with this skill, once by an identical agent without it. Both led with the recommendation — a capable model already does that much. With the skill, the three-week investigation narrative was cut as process rather than evidence, the reasons were grouped as reasons instead of listed as vendors, and the risks survived in their own section. The skilled run also sharpened one of the source's facts into something stronger than the original said, while the control left it alone — which is why "invent nothing" is now written into every operation, and why the worked example was rebuilt so both versions carry identical facts.

Expect the gain to be largest on long documents and weaker models, and smallest on a short email in a frontier model that was already going to lead with the ask.

## License

MIT — Millwright Labs.
