# Structural tells: fiction and narrative essays

Reference material for the `three-pass-prose-repair` skill's fiction
route. Each check below names the study it came from, the actual
measurement, and what to do about it. Treat every "human vs. AI" number
as a moderate target, not a pole to invert toward. See Calibration in
the main `SKILL.md`.

This file is original writing built from published, cited sources. It
does not reproduce any other skill's text; the numbers and quotes below
are pulled directly from the papers named, independently of how any
other project may have summarized them.

## Pass 1: architecture

### 1. The narrator explains the theme instead of trusting the plot

[StoryScope](https://arxiv.org/abs/2604.03136) (Russell, Rajendhran,
Pham, Iyyer, Wieting, arXiv:2604.03136) measured "Narratorial Thematic
Commentary" (the narrator or a character stepping outside the story to
state its lesson) at 77% of AI-written stories versus 52% of
human-written ones, across 61,608 stories written from the same 10,272
prompts. Dialogue used as a vehicle for philosophical debate followed
the same pattern: 59% AI versus 34% human.

**Check:** does any line say, in effect, what the story is "about"?
Does a conversation exist mainly to state a position rather than move
the scene forward? **Fix:** cut the line; let the reader infer meaning
from what happened, not from being told.

### 2. One tidy causal chain, no subplot, no loose thread

StoryScope again: "Subplot Integration → no subplots" at 79% AI versus
57% human; a single continuous cause-and-effect chain from opening to
close ("Causal Chain Continuity") scored 4.20/5 for AI versus 3.92/5 for
human raters.

Independently, [Xu, Xu, Chen, Wells, Ruth, He, Zhang, Hu, Yang, Awadalla
(2025), "Echoes in AI: Quantifying Lack of Plot Diversity in LLM
Outputs," PNAS Nexus, arXiv:2501.00273](https://arxiv.org/abs/2501.00273)
measured how *inevitable* a plot turn is by resampling the same prompt
20 times and checking how often the same twist reappears (their "Sui
Generis" score, and a companion "drop ratio" for turns that occur nearly
every time). Human continuations of the same seed text scored roughly
13–14 on Sui Generis with a 3.7% drop ratio; GPT-4 scored roughly 8–9
with an 11.3% drop ratio. A plot turn is seven to nine times more
likely to be forced by the prompt alone in the AI condition. In one test
case, five separate continuations of a Kafka fragment all resolved the
same way (a police officer helpfully gives directions), never once
reaching anything like the source's colder irony.

**Check:** if you regenerated this scene from the same premise several
times, would the same turn show up every time? Is there a second thread
that doesn't resolve, or doesn't resolve through the main plot? **Fix:**
add a subplot that stays thematically related but is not causally
required by the main line; let at least one thread stay open.

### 3. Emotion shown only as physical sensation

StoryScope: "Emotional Expression → embodied" (a tightening chest, cold
sweat, a dimming room, standing in for the feeling itself) at 81% AI
versus 38% human. The inverse (a plain emotional label such as "she was
afraid") appeared in 29% of human stories and only 8% of AI ones.

**Check:** read every emotional beat. Is it always rendered as a bodily
sensation or environmental mirror, never once stated directly? **Fix:**
state at least one emotion plainly somewhere in the piece. "Show don't
tell" applied to literally every beat is itself a tell, not good craft.

### 4. No reference to anything real

StoryScope: "Intertextual Strategy → explicit named reference" (a real
book, film, artist, brand, or place named outright) at 47% human versus
24% AI. Human authors name real things at roughly twice the rate.
[Beguš (2024), "Experimental Narratives: A Comparison of Human
Crowdsourced Storytelling and AI Storytelling," arXiv:2310.12902
](https://arxiv.org/abs/2310.12902), comparing 250 crowdworker stories
against 80 GPT-3.5/GPT-4 stories written from the same Pygmalion-themed
prompt, found the AI stories converge on generic invented settings. Phrases
close to "a bustling metropolis teeming with innovation" or "the
vibrant city of Elysia" recur across unrelated generations, rather than
a real, specific place.

**Check:** does the piece name a single real person, place, brand, or
work, or does every setting read as an invented composite? **Fix:** name
something real and specific where it would plausibly come up; a
made-up-sounding place name in an otherwise realistic story is a signal
worth removing.

### 5. Endings resolved too neatly, through the protagonist's own growth

StoryScope: "Resolution Mode → internal understanding" (the story ends
because the protagonist reaches acceptance or insight) at 47% AI versus
27% human; "Agency in Resolution → protagonist choice" (the ending turns
entirely on what the protagonist decides, with no outside force) at 69%
AI versus 46% human.

Beguš's same comparison found AI endings converge on a small set of
moralizing closing lines: phrasing close to "love knows no boundaries"
or "love transcends artificiality" recurs across generations regardless
of what the story was actually about, alongside a near-total absence of
darker material: betrayal, manipulation, and real loss are rare in the
AI condition and common in the human one.

**Check:** does the ending resolve because the protagonist personally
grows or accepts something? Is there a tidy moral in the last line that
would fit almost any story, not just this one? **Fix:** let an outside
event, not personal insight, force the resolution, or leave the ending
short of fully resolved. Consider letting something genuinely bad
happen and stay unrepaired.

### 6. Repeated names and stereotyped surface diversity

Beguš's comparison also found heavy convergence on a small set of
character names across unrelated AI generations (their sample recorded
"Ava" ten times, plus repeated "Victor," "Adam"/"Eve," "Eliza," and
"Amelia"), and, even where cast composition looked demographically
varied on the surface, adjective choice stayed stereotyped underneath
(women described through beauty, grace, kindness; men through
intelligence and competence).

**Check:** would this character's name show up if you generated the
scene five more times? Do the adjectives describing each character
still sort by a stereotype once you look past who they are on paper?
**Fix:** pick a name deliberately, not a default; check adjective choice
against the character's actual role in the plot, not their demographic.

### 7. Character network too dense and too friendly

[Nonaka and Perry (2025), "Evaluating LLM Story Generation through
Large-scale Network Analysis of Social Structures," arXiv:2510.18932
](https://arxiv.org/abs/2510.18932) built signed character-interaction
networks (who interacts with whom, and whether the relationship reads
positive or negative) across more than 1,200 stories from four LLMs
against a human-written corpus. LLM-generated casts formed denser
networks (0.338–0.470 density versus 0.182 for human stories) with
relationship sentiment skewed almost entirely positive (average edge
weight +0.24 to +0.66, versus a slightly negative −0.061 for human
stories), and antagonistic sub-networks that were both smaller and less
internally connected than the protagonist's circle.

**Check:** does every character in the cast know and like the
protagonist? Does the antagonist (if any) exist in isolation, with no
allies or history of their own? **Fix:** keep some characters only
indirectly connected to each other; let overall relationship sentiment
run neutral-to-negative rather than uniformly warm; give an antagonist
their own real relationships.

## Pass 2: flow

### 8. The middle sags while the opening and closing are polished

[Tripto, Laban, Chakrabarty, and Wang (2025), "Beyond Checkmate:
Exploring the Creative Chokepoints in AI Text," EMNLP 2025,
arXiv:2501.19301](https://arxiv.org/abs/2501.19301) compared human and
AI writing segment by segment (introduction, body, conclusion) and found
the two diverge most in the *body*: openings and closings are where AI
writing most closely imitates human patterns, and the middle is the
"choke point" where quality and originality drop off. The same study
found human writing varies its own rhythm and word choice across
paragraphs noticeably more than AI writing does. A human author's
"burstiness" fluctuates section to section, where AI prose stays close
to one register the whole way through, including at the start, where an
unusually polished, standard-feeling opening is itself a signal worth
noticing rather than reassurance.

**Check:** read the middle third on its own. Does energy and specificity
drop compared to the opening and closing? Does the register stay
perfectly even across the whole piece? **Fix:** put the most work into
the middle section specifically; deliberately vary sentence length and
density from section to section rather than holding one steady rhythm.

### 9. Discourse structure follows the same template every time

[Namuduri, Chen, Zhang, Iyyer (2025), "QUDsim: Quantifying Discourse
Similarities in LLM-Generated Text," COLM 2025, arXiv:2504.09373
](https://arxiv.org/abs/2504.09373) modeled each paragraph as answering
an implicit Question Under Discussion (QUD) and measured how often
consecutive AI-generated texts reuse the same sequence of question
types. LLM outputs reused the same discourse-move sequence at 0.8–1.2
similarity across generations, versus 0.3–0.4 for pairs of human texts.
AI text follows one template far more consistently than humans follow
any template. The paper's own descriptive read of a common reused
sequence: lay out the situation, justify or excuse a choice, describe
the social consequence, close on the weight of responsibility, repeated
almost regardless of topic. Sequential and procedural question-answer
moves were heavily overused; comparative and verification moves (a later
paragraph revisiting or challenging what an earlier one claimed) were
almost absent.

**Check:** list, in order, what question each paragraph or scene answers:
is it a straight line of one-thing-then-the-next? Does anything in the
piece revisit or complicate an earlier claim? **Fix:** if the outline is
perfectly linear, reorder so at least one later section forces a
re-read of an earlier one; add a passage that compares or verifies
something stated before, rather than only adding new information
forward.

## Pass 3: surface (do this last)

The clichés-and-vocabulary layer is real but is the layer StoryScope
found moves *least* on its own: a full surface-style rewrite of the AI
stories in that study only took detection from 95.5% down to 93.9%. Use
`references/professional-docs.md`'s cross-domain checklist for the
concrete word- and sentence-level items (overused constructs, specific
vocabulary to check for, cliché phrasing); the same surface patterns
show up in fiction and in professional prose alike, and are catalogued
once there rather than twice.

## Self-test worth running before calling a piece finished

Borrowed directly from Xu et al.'s method above, as a manual check
rather than a resampling experiment: pick the one plot turn you're least
sure about, and ask honestly whether five other reasonable continuations
of this exact scene would land on the same turn. If yes, it's a tell,
not a choice. Change it or cut it.

## Full source list for this file

- Russell, Rajendhran, Pham, Iyyer, Wieting (2026), "StoryScope:
  Investigating idiosyncrasies in AI fiction," arXiv:2604.03136.
- Beguš (2024), "Experimental Narratives: A Comparison of Human
  Crowdsourced Storytelling and AI Storytelling," arXiv:2310.12902.
- Xu et al. (2025), "Echoes in AI: Quantifying Lack of Plot Diversity in
  LLM Outputs," PNAS Nexus, arXiv:2501.00273.
- Tripto, Laban, Chakrabarty, Wang (2025), "Beyond Checkmate: Exploring
  the Creative Chokepoints in AI Text," EMNLP 2025, arXiv:2501.19301.
- Namuduri, Chen, Zhang, Iyyer (2025), "QUDsim: Quantifying Discourse
  Similarities in LLM-Generated Text," COLM 2025, arXiv:2504.09373.
- Nonaka, Perry (2025), "Evaluating LLM Story Generation through
  Large-scale Network Analysis of Social Structures," arXiv:2510.18932.

All findings above are reported as measured associations within each
study's own sample and method. None of the "fixes" listed were
themselves tested as interventions by these papers; they are this
skill's own editorial inference from what was measured, same as any
style guide built on descriptive research.
