---
name: three-pass-prose-repair
description: Fix AI-flavored writing at the structural level first — plot or document architecture, then discourse flow and pacing, then word choice last — instead of just swapping vocabulary. Two operations, review (diagnose only) and repair (apply the fix), each routed to a reference file: fiction and narrative essays load references/structural-tells.md, professional documents (release notes, PR replies, postmortems, technical articles) load references/professional-docs.md. Use when a draft reads competent but flat, formulaic, or "obviously AI-written," and a word-level pass alone hasn't fixed it.
---

# Three-pass prose repair

Most editing passes start and stop at the sentence level: cut the clichés,
vary the vocabulary, trim the em-dashes. That helps a little, but the
research this skill is built on found the strongest tell sits one layer up
— in the *shape* of the piece, not the words filling it in. This skill
routes a request to the right reference file, then walks it through the
same order of operations every time: architecture first, flow second,
words last.

It covers two kinds of writing, because the failure mode is different in
each:

- **Fiction and narrative essays** — the tell is architectural: a plot
  that resolves too cleanly, emotion rendered only as physical sensation,
  a theme the narrator explains rather than lets emerge.
- **Professional documents** — release notes, PR/issue replies,
  postmortems, technical articles — the tell is informational: filler
  that carries no signal, hedging where a plain judgment was needed,
  one-size-fits-all structure that ignores what the document is for.

This is a writing-craft skill. The goal is prose that reads as genuinely
well-built and specific to its own situation, for a human reader's
benefit — not formulaic, not generic. It makes no claim about defeating
any detector and should never be framed that way; it fixes the actual
structural habits that make writing feel thin, which happens to be the
same habits the cited research measured as distinguishing AI writing
from human writing.

## Operations

| Operation | Contract |
|---|---|
| **review** | Diagnose only — no edits. Read the routed reference file(s), walk the draft against each check, and report findings with the specific line or passage that triggered each one. Stop there; apply nothing until asked. |
| **repair** | Apply the fix, in order: Pass 1 architecture, Pass 2 flow, Pass 3 surface word choice. Do the passes in sequence — don't start with Pass 3, since that's the layer the underlying research found moves least on its own. |

Both operations load the same reference material; `review` reads it as a
checklist to score against, `repair` reads it as edit instructions.

## Routing

| Text type | Load |
|---|---|
| Fiction, short stories, narrative essays | `references/structural-tells.md` |
| Release notes, changelogs, announcements | `references/professional-docs.md` §Release notes |
| PR replies, issue replies, code-review comments | `references/professional-docs.md` §PR and issue replies |
| Incident postmortems / RCAs | `references/professional-docs.md` §Postmortems |
| Technical articles, deep-dive blog posts | `references/professional-docs.md` §Technical articles |
| Anything else non-fiction | `references/professional-docs.md`, general checklist section only |

## Pass order (applies to both routes)

1. **Architecture** — the plot's causal structure, or the document's
   argument structure: what claims it makes, in what order, and how it
   resolves. Fixed first because it is the most expensive to retrofit
   and the layer word-level editing does not reach.
2. **Flow** — pacing, paragraph rhythm, where information is revealed
   versus withheld, whether the piece is uniform end to end or varies
   the way a single author's attention naturally would.
3. **Surface** — clichés, repeated sentence templates, vocabulary,
   register. Real and worth doing, but last, and it should not be
   allowed to stand in for the first two passes.

## Calibration

Don't apply every check in the reference files to every piece — that
just trades one formula for another. The measured human baseline for
almost every feature below sits at a moderate value, not an extreme one;
overshooting a check as far as possible in the opposite direction creates
its own detectable pattern. Fix what the draft actually shows, leave the
rest, and never invent a specific (a name, a number, a date, a citation)
to satisfy a "be more specific" check — a confident wrong detail is worse
than a generic true one.

## Credit and sources

This skill is inspired by [sepia](https://github.com/Nanako0129/sepia)
(Nanako0129, MIT license), a portable Agent Skill that runs the same
architecture-first idea as a full multi-file plugin — routing, four
operations, per-model fingerprints, and its own much larger reference
library. This is an independent, from-scratch rebuild of the same
underlying idea and research base as a smaller two-operation skill: own
wording throughout, own choice of which findings to surface and how,
crediting sepia for the shape of the idea rather than copying its files.

The research base is listed in full, with real per-finding citations, in
`references/structural-tells.md` and `references/professional-docs.md`.
The anchor study for the fiction route is
[StoryScope](https://arxiv.org/abs/2604.03136) (Russell, Rajendhran,
Pham, Iyyer, Wieting — arXiv:2604.03136, submitted 2026-04-03, latest
revision v6 2026-08-10): 61,608 stories from human authors and five
frontier LLMs, 304 narrative-structure features, 93.2% macro-F1
human-vs-AI detection from structure alone, holding at 93.9% (down from
95.5%) after a full surface-style rewrite of the AI stories.

Tested on [nimaarki.com](https://nimaarki.com), 2026-09-03.
