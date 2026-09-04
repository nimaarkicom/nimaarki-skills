# Structural tells: professional documents

Reference material for the `three-pass-prose-repair` skill's non-fiction
route: release notes, PR and issue replies, postmortems, technical
articles, and similar work writing. Fiction's "architecture" problem
shows up here as an information and honesty problem instead: filler
that carries no signal, hedging where a plain judgment was called for,
and structure that ignores what the document is actually for. Same
three-pass order as the fiction route; this file covers the general
checklist plus five domain-specific rule sets.

This is original writing built from the cited sources below, checked
independently against each paper's own numbers. None of it is copied
from any other project's summary of the same research.

## General checklist (Pass 1 + Pass 2, before any domain rules)

### The seven AI-writing artifact types found in professional editing

[Chakrabarty, Laban, Wu (2025), "Can AI Writing be Salvaged? Mitigating
Idiosyncrasies and Improving Human-AI Alignment in the Writing Process
through Edits" ("LAMP"), CHI 2025, arXiv:2409.14509
](https://arxiv.org/abs/2409.14509) had 18 professional (MFA-trained)
writers make 8,035 real edits across 1,057 LLM-written paragraphs, then
categorized every edit. The taxonomy covered all but 10 of those 8,035
edits:

1. **Cliché**: an overused phrase or comparison that has lost its
   impact (the paper's own example: "settled over her like a heavy
   blanket," deleted outright).
2. **Redundant exposition**: restating something already shown or
   already obvious.
3. **Purple prose**: ornamentation that pulls attention to the writing
   itself rather than the content; long, dense, over-modified sentences.
4. **Poor sentence structure**: run-ons and missing transitions; the
   paper's most common fix here was simply splitting one sentence into
   two.
5. **Lack of specificity**: vague, ungrounded statements; the *only*
   category where the professional edit made the passage longer, by
   adding a real, concrete detail.
6. **Awkward word choice**: including one very specific tell: "seemed
   to [verb]" used where the writer isn't actually expressing
   uncertainty ("the sky seemed to hover" → "the sky hovered").
7. **Tense inconsistency**: tense drifting within a single paragraph or
   sentence.

Editors' actual edit mix, measured directly: **74% replacement, 18%
deletion, 8% insertion.** Overwriting was a far more common problem than
underwriting; pieces judged higher quality got *fewer* edits (10.2 edits
on average for the lowest-quality tier versus 2.4 for the
highest-quality tier, a strong negative correlation, r = −0.31). The
two categories most associated with perceived quality were awkward word
choice and cliché: fixing those two mattered more than any other
category.

**Check:** for each of the seven types, does the draft show it? **Fix:**
default to replacing or deleting over adding new material: "if in
doubt, cut it." The paper's own automated experiment found LLM editors
were good at trimming purple prose and splitting run-ons, but
consistently bad at the two things that mattered most for quality:
writing a genuinely fresh replacement for a cliché (they tend to swap
one flat phrase for another) and adding a detail with real specificity
rather than a generic-sounding one.

### The seven-code "slop" taxonomy for factual and semi-formal prose

[Shaib, Chakrabarty, Garcia-Olano, Wallace (2025), "Measuring AI 'Slop'
in Text," arXiv:2509.19163](https://arxiv.org/abs/2509.19163) built a
span-level annotation taxonomy from 19 expert interviews, then had a
professional copy editor mark 150 news articles and 100 short QA answers
against it:

- **Density**: words that carry no real information for this specific
  context (their example: "In today's fast-paced modern world of
  cutting-edge technology…").
- **Relevance**: content that doesn't answer the actual question or
  task at hand.
- **Factuality**: errors, invented specifics, or subtly wrong claims.
- **Bias/subjectivity**: the inverse of the usual worry: writing that
  stays falsely neutral where the venue actually calls for a judgment
  call (a review that only lists facts and never evaluates).
- **Repetition**: the same word or phrase reused past the point of
  intent.
- **Templatedness**: a structural formula repeated sentence after
  sentence (their example: "Dr. X, a researcher at Y, found that…"
  reused across every source cited).
- **Tone**: generic voice with no real personality, or formality
  mismatched to the venue.

Measured findings worth acting on directly: the overall "this reads as
slop" judgment correlated strongly with how many separate spans were
flagged (Spearman ρ = 0.70 for news, 0.51 for short QA). Slop is
cumulative, not a single tripwire. Across their whole dataset, Relevance,
Density, and Tone were the three strongest predictors of a document
being judged low quality. And critically: **the LLMs in their study
could not reliably self-detect their own slop** when handed the full
seven-code guide at once (agreement with the human annotator was close
to zero, and even span-level precision was only 0.13–0.16). Self-review
only worked when it ran one dimension at a time, not as one pass against
the whole list.

**Check, one dimension at a time, not all at once:** does every sentence
answer the actual question asked? Is there a paragraph that would read
the same in any similar document, with no fact specific to this one? Is
there a place where the venue calls for a real opinion and the draft
stays neutral instead? **Fix:** cut anything that fails the Density or
Relevance test outright; those two, plus Tone, were the strongest
predictors of "reads as slop" in the study.

### Sentence- and word-level constructs (do this last, in either route)

[Reinhart, Sultana Farhat, Zhang, Wilson, Reinecke (2025), "Do LLMs
write like humans? Variation in grammatical and rhetorical styles,"
PNAS, arXiv:2410.16107](https://arxiv.org/abs/2410.16107) ran the
66-feature Biber framework (a standard linguistics tool for grammatical
and rhetorical style) over parallel human and LLM continuations of the
same source texts. Their central finding: instruction-tuned models, not
model scale, are the main driver of the gap: a base model without
instruction tuning already writes closer to human style, and going to a
bigger instruct model does not close the distance.

Constructs the LLM outputs used far more than human writing (relative
frequency versus human = 100%): present participial clauses (527%,
e.g. "leaning on his agility, dances around the ring"), 'that'-clauses
as subject (263%), past participial clauses (307%), nominalizations
like development/justification (214%), "a X of Y and Z" phrasal
coordination (194%), and hedging "seem"/"appear" (179%).

Constructs used far less: causal "because" (20% of human frequency),
contractions (60%), first-person pronouns (62%), hedges like "something
like" (63%), discourse particles such as a sentence-opening "well" or
"anyway" (60%), and second-person address (52%).

Specific words the same study flagged as wildly overused relative to
human baselines: *tapestry* (155x human frequency, appearing in 23% of
one model's outputs), *camaraderie* (162x), *intricate* (119x),
*underscore* (107x), *unspoken* (102x), *amidst* (100x, in 27% of
outputs), *palpable* and *solace* (95x each).

**Check:** grep the draft for that word list. Count participial-clause
openers ("Leaning on...", "Having considered..."). **Fix:** cut or
replace flagged vocabulary; convert a participial-clause opener to a
plain subject-verb sentence; restore at least one contraction or
first-person statement if the register allows it. The underused list
above is effectively a checklist of what to add back, not just what to
remove.

### Why word-swaps alone under-perform, even for professional nonfiction

[Russell, Karpinska, Iyyer (2025), "People Who Frequently Use ChatGPT for
Writing Tasks Are Accurate and Robust Detectors of AI-generated Text,"
ACL 2025, arXiv:2501.15654](https://arxiv.org/abs/2501.15654) had five
frequent LLM users label 300 real nonfiction articles; their majority
vote was 99.3% correct, including on a set the researchers had already
run through an AI paraphraser specifically to strip surface style. In
that paraphrased condition, one specific tell (unusual or off-key word
choice) was actually flagged *more* often after paraphrasing than
before (69.8% → 88% of labeled examples). Paraphrasing moved the tell
around rather than removing it. A separate humanized condition (run
through an additional AI "humanizer" pass) was still caught by the
expert majority vote 100% of the time; the tells that survived were
structural, not lexical: fixed three-item lists, uniformly upbeat
conclusions, over-formal quotations, and a near-total absence of any
dark or difficult subject matter.

**Check:** does the piece end on an upbeat, forward-looking note
regardless of what it actually reported? Are there fixed-length lists of
exactly three items in a row? Are quoted statements suspiciously
tidy and complete compared to how people actually talk? **Fix:** let a
postmortem or a technical article's conclusion stay as unresolved as the
actual situation is; vary list length; leave a quote a little rough if
that's how it was actually said.

## Domain-specific rules (Pass 1 + Pass 2, applied on top of the general checklist)

### Release notes and announcements

- Lead with the user-facing effect of the change, not the internal
  process that produced it. A Density violation in the sense above is
  most common here as boilerplate about "our team worked hard to
  deliver."
- Cite the actual PR, ticket, or artifact behind each claim; a claim
  with nothing behind it is exactly the Factuality/specificity gap LAMP
  and the slop taxonomy both flag.
- Cut adjectives that inflate a routine change ("blazing fast,"
  "seamless," "revolutionary") unless a real number backs them.
  This is the Bias/subjectivity code pointed the other way: false
  enthusiasm instead of false neutrality.
- Vary sentence opener and length across entries; a changelog where
  every line starts "Added...", "Fixed...", "Improved..." is exactly
  the templatedness pattern the slop paper measured.

### PR and issue replies, code-review comments

- Answer the actual question in the first sentence; don't rebuild
  context the reader already has.
- Cite `file:line`, not a paraphrase of the code.
- Cut reflexive praise ("Great question!", "This looks great!"). It is
  the Tone-mismatch failure mode, formal warmth applied regardless of
  what's actually being said.
- Match reply length to what's actually at stake, not to how thorough
  it's possible to sound; a one-line fix deserves a one-line reply.

### Postmortems / incident reviews

- Blameless toward the people involved, specific and unsparing about the
  mechanism that failed. Vague, softened cause statements are the
  Density and Bias/subjectivity failures at once: no real information,
  and false neutrality where a plain diagnosis was needed.
- Real timestamps, not "shortly after" or "some time later."
- Include the dead ends that were tried and didn't work, not just the
  fix that succeeded in the end. An inevitable-sounding, linear
  timeline is the same "one tidy causal chain" pattern StoryScope
  measured in fiction, applied to what actually happened.
- Action items need a named owner and a testable condition for done,
  not a passive "we should improve monitoring."

### Technical articles and deep-dive posts

- Open with the actual problem, not scene-setting throat-clearing.
  Russell et al.'s detector-study participants specifically named
  formulaic scene-setting openings ("On a drab November morning...") as
  a top tell, and it applies just as much to a technical piece that
  opens with unearned narrative color instead of the problem itself.
- Include at least one real dead end or wrong turn taken while solving
  the problem, not just the clean path to the final answer.
- Commit to at least one real, arguable opinion rather than staying
  neutral throughout. See Bias/subjectivity above.
- Attach numbers to conditions ("40ms at p99 under X load"), not bare
  claims ("much faster").

## Full source list for this file

- Chakrabarty, Laban, Wu (2025), "Can AI Writing be Salvaged? Mitigating
  Idiosyncrasies and Improving Human-AI Alignment in the Writing Process
  through Edits," CHI 2025, arXiv:2409.14509.
- Shaib, Chakrabarty, Garcia-Olano, Wallace (2025), "Measuring AI 'Slop'
  in Text," arXiv:2509.19163.
- Reinhart, Sultana Farhat, Zhang, Wilson, Reinecke (2025), "Do LLMs
  write like humans? Variation in grammatical and rhetorical styles,"
  PNAS, arXiv:2410.16107.
- Russell, Karpinska, Iyyer (2025), "People Who Frequently Use ChatGPT
  for Writing Tasks Are Accurate and Robust Detectors of AI-generated
  Text," ACL 2025, arXiv:2501.15654.

As with the fiction reference file, every number above is a measured
finding within its own study's sample; the domain-specific rules that
follow from them are this skill's own editorial judgment, not a tested
intervention from any of the papers.
