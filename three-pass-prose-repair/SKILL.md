---
name: three-pass-prose-repair
description: "Fixes writing that reads flat, generic, or obviously AI-written. Most fixes only swap out words, which barely helps. This fixes the bigger problem first: how the piece is built, then the flow, then the words last. Two modes: review (says what's wrong) and repair (fixes it step by step). Works on fiction and on everyday documents (release notes, PR replies, postmortems, technical articles)."
---

# Fix writing that sounds like AI

**In plain terms:** most tools that try to fix AI-sounding writing just swap
out a few words. That barely helps. The bigger problem is usually how the
piece is put together: a story that wraps up too neatly, or a report that
buries the point in filler. This fixes that first, before touching a single
word.

It covers two kinds of writing, because the problem shows up differently in
each:

- **Fiction and narrative essays**: a plot that resolves too cleanly,
  feelings shown only as a racing heart or a tight chest instead of
  something real, a theme the narrator just states instead of letting the
  reader feel it.
- **Everyday documents** (release notes, PR/issue replies, postmortems,
  technical articles): filler that says nothing, hedging where a plain
  answer was needed, the same shape used for every document regardless of
  what it's actually for.

This is a writing-craft tool. The goal is writing that reads like it was
actually built for its own situation (not formulaic, not generic), for
the reader's benefit. It is not about beating any detector, and should
never be described that way; it fixes the real habits that make writing
feel thin, which happen to be the same habits the research below measured.

## Operations

| Operation | Contract |
|---|---|
| **review** | Diagnose only. Do not edit anything. Read the routed reference file(s). Walk the draft against each check. Report findings, and cite the specific line or passage that triggered each one. Stop there; apply nothing until asked. |
| **repair** | Apply the fix in order: Pass 1 architecture, Pass 2 flow, Pass 3 surface word choice. Do the passes in sequence. Do not start with Pass 3; the underlying research found that layer moves least on its own. |

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

1. **Architecture**: the plot's causal structure, or the document's
   argument structure, meaning what claims it makes, in what order, and
   how it resolves. It comes first because it is the most expensive to
   retrofit, and it is the layer word-level editing does not reach.
2. **Flow**: pacing, paragraph rhythm, where information is revealed
   versus withheld, whether the piece is uniform end to end or varies
   the way a single author's attention naturally would.
3. **Surface**: clichés, repeated sentence templates, vocabulary,
   register. This is real and worth doing, but it comes last, and it
   should not stand in for the first two passes.

## Calibration

Don't apply every check in the reference files to every piece; that
just trades one formula for another. The measured human baseline for
almost every feature below sits at a moderate value, not an extreme one;
overshooting a check as far as possible in the opposite direction creates
its own detectable pattern. Fix what the draft actually shows, leave the
rest, and never invent a specific (a name, a number, a date, a citation)
to satisfy a "be more specific" check. A confident wrong detail is worse
than a generic true one.

## Credit and sources

This skill is inspired by [sepia](https://github.com/Nanako0129/sepia)
(Nanako0129, MIT license), a portable Agent Skill that runs the same
architecture-first idea as a full multi-file plugin: routing, four
operations, per-model fingerprints, and its own much larger reference
library. This is an independent, from-scratch rebuild of the same
underlying idea and research base as a smaller two-operation skill: own
wording throughout, own choice of which findings to surface and how,
crediting sepia for the shape of the idea rather than copying its files.

The research base is listed in full, with real per-finding citations, in
`references/structural-tells.md` and `references/professional-docs.md`.
The anchor study for the fiction route is
[StoryScope](https://arxiv.org/abs/2604.03136) (Russell, Rajendhran,
Pham, Iyyer, Wieting, arXiv:2604.03136, submitted 2026-04-03, latest
revision v6 2026-08-10): 61,608 stories from human authors and five
frontier LLMs, 304 narrative-structure features, 93.2% macro-F1
human-vs-AI detection from structure alone, holding at 93.9% (down from
95.5%) after a full surface-style rewrite of the AI stories.

Tested on [nimaarki.com](https://nimaarki.com), 2026-09-03.
