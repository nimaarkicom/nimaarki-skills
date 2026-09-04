---
name: three-pass-prose-repair
description: Self-review checklist that fixes AI-flavored writing at the structural level first — plot/document architecture, then pacing and flow, then word choice last — instead of just swapping vocabulary. Use when a draft (fiction or a professional document like release notes, a PR reply, or a postmortem) reads competent but flat, formulaic, or "obviously AI-written," and word-level fixes alone haven't helped.
---

# Three-pass prose repair

Most editing passes start and end at the sentence level: cut the clichés,
vary the vocabulary, trim the em-dashes. That helps a little, but it treats
the symptom. The actual research on what makes AI-written fiction read as
AI-written found the tell sits one layer up, in the *shape* of the story
itself — the plot's causal chain, how emotion gets rendered, how the ending
resolves — not in which words fill it in.

This skill is a three-pass order of operations: fix the architecture first,
then the flow, and only then the words. It also includes a lighter version
of the same idea for professional documents, where the equivalent problem
is filler, hedging, and one-size-fits-all structure rather than plot.

This is a writing-craft tool. The goal is prose that reads as genuinely
well-built and specific to its own story or situation — not formulaic,
not generic — for a human reader's benefit. It is not a tool for evading
any particular detector, and it does not claim to make anything
undetectable; it makes writing better by fixing the actual structural
habits that make it feel thin.

## Why structure first

[StoryScope](https://arxiv.org/abs/2604.03136) (Russell et al., 2026 —
UMD + Google DeepMind) trained a classifier on 61,608 stories: 10,272
prompts each written once by a human author and once by five frontier
LLMs (Claude, GPT, Gemini, DeepSeek, Kimi). Using *only* 304 narrative-
structure features — no vocabulary, no sentence-level style at all — the
classifier told human from AI fiction at 93.2% macro-F1. When the same AI
stories were then given a full surface-style rewrite (LAMP-style editing:
new vocabulary, new syntax, clichés removed), detectability barely moved:
95.5% down to 93.9%. The structural tells survive a wording pass almost
untouched.

The paper's own qualitative read of what those 304 features amount to:
AI fiction over-explains its own theme, keeps a single tidy causal chain
with few subplots, renders emotion almost entirely as physical sensation,
avoids naming anything from the real world, and resolves endings through
the protagonist's internal acceptance or growth far more often than human
writing does. None of that is a vocabulary problem, so no vocabulary fix
touches it.

## How to use it

Paste the checklist below along with your draft into a model, or walk
through it yourself as a human editor. Work the passes **in order** —
don't jump to Pass 3 first, that's the part that changes least.

```
Review this draft in three passes, in this order. Do not skip ahead to
Pass 3 before finishing Pass 1 and Pass 2.

PASS 1 — ARCHITECTURE (plot / document structure)
Look for these specific patterns and flag or fix each one you find:
- Does the narrator or writer explain the theme, moral, or takeaway
  directly, instead of letting it emerge from what happens? Cut the
  direct statement; trust the reader to get there.
- Is there one single, tidy causal chain from start to end with no
  subplot, no dead end, no loose thread? Add one that doesn't resolve,
  or braid in a second thread that's thematically related but not
  causally tidy.
- Is emotion shown only through physical sensation (tight throat, cold
  sweat, a dimming room) and never once stated plainly ("she was
  afraid")? Mix both modes in — don't let "show don't tell" become a
  rule applied to every single beat.
- Are there zero references to anything real — no named place, work,
  person, or brand? Name something real and specific where it would
  plausibly come up.
- Does the ending resolve cleanly through the protagonist's own internal
  growth or acceptance? Consider an ending that resolves through outside
  circumstance instead, or one that stays a little unresolved.
- Was a main character introduced with an external description dump
  (appearance, backstory, a summary of who they are)? Introduce them
  through action or dialogue instead and let the reader infer the rest.

PASS 2 — FLOW (pacing / discourse structure)
- Does every paragraph or section follow the same template (state a
  fact, then reflect on it, then move on)? Break the pattern in at
  least a few places — vary paragraph length and rhythm on purpose.
- Is all the context front-loaded early, with nothing held back? Move
  at least one piece of context later, so the reader has to reinterpret
  something they already read.
- Does the middle sag with even, undifferentiated pacing? Compress the
  parts that matter least, slow down for the one or two moments that
  matter most.
- Does the opening over-explain the setting before anything happens?
  Cut it down; let location emerge through action.

PASS 3 — SURFACE (word choice — do this last, not first)
- Clichés and stock phrases ("delve into," "tapestry of," "a testament
  to").
- Repeated sentence templates — read three consecutive sentences aloud;
  if they scan with the same rhythm and shape, rebuild one.
- Vocabulary or register that doesn't match the voice established
  elsewhere in the piece.

CALIBRATION
Don't apply every fix everywhere — that just trades one formula for
another. Pick the 3-5 changes that matter most for this specific piece
and leave the rest. The goal is prose that reads like it was built for
this one story or document, not prose that scores well against a
checklist.
```

## Adapting this for professional documents

Fiction's "architecture" problem shows up in professional writing as a
structure and honesty problem instead: filler that carries no real
information, hedging where a plain judgment was called for, and a
one-size-fits-all shape that ignores what the document is actually for.
Same three-pass order, lighter checklist:

- **Release notes / announcements** — lead with the user-facing impact,
  not the internal work. Cite the actual PR, ticket, or artifact behind
  each claim. Cut marketing inflation ("blazing fast," "seamless") that
  isn't backed by a number.
- **PR / issue replies** — answer the actual question first. Cite
  `file:line`, not a paraphrase. Drop reflexive praise ("Great question!",
  "This looks great!"). Match reply length to how much is actually at
  stake, not to how thorough it's possible to sound.
- **Postmortems** — blameless toward the people involved, blunt about the
  mechanism that failed. Include real timestamps, the dead ends that were
  tried and didn't work, and action items with a named owner, not a
  passive "we should."
- **Tickets / work orders** — title states the outcome, not the task.
  Acceptance criteria that can actually be tested. Link to related
  context instead of re-explaining it inline.

## Credit

This skill is inspired by [sepia](https://github.com/Nanako0129/sepia)
(Nanako0129, MIT license) — a portable Agent Skill that runs the same
architecture-first idea as a full multi-file plugin, with per-model
fingerprints, a 30-feature diagnosis rubric, and domain-specific rule
sets for professional prose. This is a from-scratch, single-file
distillation of the same underlying research into one copy-pasteable
checklist — it does not copy sepia's text, its packaging, or its
per-model calibration data, only the three-pass ordering idea and the
research it's grounded in.

The research itself is [StoryScope](https://arxiv.org/abs/2604.03136)
(Russell, Rajendhran, Pham, Iyyer, Wieting — 2026, arXiv:2604.03136,
UMD + Google DeepMind): 61,608 stories, human and 5 frontier LLMs,
304 narrative-structure features, 93.2% macro-F1 detection from
structure alone, 95.5% → 93.9% after a full surface-style rewrite. The
specific checklist items above (theme over-explanation, single causal
chain, embodied-only emotion, no real-world references, growth/
acceptance endings) are the paper's own named findings, not sepia's or
this skill's invention.

Tested on [nimaarki.com](https://nimaarki.com), 2026-09-03.
