# minto-pyramid

An Agent Skill that makes Claude write the way McKinsey trains consultants to write: **answer first, then the reasons, then the evidence.**

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

It triggers on its own when you ask for an email, memo, update, proposal, exec summary, or a "make this clearer" edit. To force it:

```
Use the minto-pyramid skill on this draft.
```

Five operations are defined inside — restructure, buried-lede test, reason audit, so-what pass, email version. Ask for one by name, or hand it a draft and let it pick.

## What it actually does

Claude's default is narrative order: background, then findings, then the point. That's how prose reads and how prose was trained. It buries the one line your reader needed. This skill inverts the order and enforces Barbara Minto's grouping rules on the middle layer.

## Provenance and fact-check

The idea came from [an Instagram post by @thewizeai](https://www.instagram.com/p/DcG_kY2lYSN/) (16 Aug 2026). The prompts in that post are good; the framing has some slippage, so this skill was checked against primary sources before being written down.

**Verified**

- Barbara Minto joined McKinsey in 1963, in Cleveland, and moved to the London office in 1966. ([Wikipedia](https://en.wikipedia.org/wiki/Barbara_Minto))
- *The Pyramid Principle: Logic in Writing and Thinking* was published in 1985; the expanded *The Minto Pyramid Principle: Logic in Writing, Thinking and Problem Solving* in 1996.
- Minto coined MECE. ([McKinsey alumni interview: "MECE: I invented it, so I get to say how to pronounce it"](https://www.mckinsey.com/alumni/news-and-events/global-news/alumni-news/barbara-minto-mece-i-invented-it-so-i-get-to-say-how-to-pronounce-it))
- The rules of the pyramid: each idea summarizes the ideas grouped below it; ideas in a grouping are the same kind of idea; ideas in a grouping are logically ordered. ([overview](https://modelthinkers.com/mental-model/minto-pyramid-scqa))
- MECE tests **inductive** groupings — separate reasons of the same kind. It does not apply to deductive chains, where each step depends on the last. The skill keeps the two apart; most short summaries of Minto blur them.

**Corrected**

- The post says Minto was "the first woman McKinsey hired into consulting." The documented claim is narrower: the first **female MBA** McKinsey hired. This skill states it that way.
- The post hard-codes **exactly three reasons**. That's a consulting convention, not one of Minto's rules — her constraint is MECE, not a count. Forcing three is what produces the filler reason everyone can smell. The skill asks for however many the case actually has, typically two to four.
- The post omits **SCQA** and the three grouping rules, which are the parts that make the middle layer hold up. Both are included here.

## License

MIT — Millwright Labs. Use it, fork it, ship it.
