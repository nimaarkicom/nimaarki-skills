---
name: corkboard-network-diagram
description: Generate an image that shows a set of related concepts as a physical corkboard pin-and-string diagram, with paper cards, pushpins, and real red string connecting them, and no text rendered anywhere. Use when asked to illustrate a network, a system, or a set of related ideas in a tactile, non-digital style, instead of a flat diagram or icon grid.
---

# Corkboard network diagram

Turns a list of concepts into one image: a physical research-board
diagram, not a flat digital chart. Each concept becomes a small paper
card pinned to a corkboard-style background; real coral-red string
connects the cards as edges.

## When to use this

The user asks for an illustration of a network, a system, or a set of
related concepts, and wants a tactile, hand-assembled look rather than
a clean vector diagram: a detective-board or research-wall aesthetic,
without the clutter that usually implies.

## How to use it

1. List the concepts to illustrate. Use 4 to 6 concepts. More than that
   crowds the frame.
2. Send the prompt below to an image model that supports texture and
   material detail in its prompts (tested against GPT Image 2, through
   AceData). Replace the bracketed list with the real concepts.
3. Ask for a 2:1 landscape ratio for a wide banner, or drop that line
   for a different shape.

```
Create a physical corkboard research-board diagram. Each concept from
this list is a small paper card pinned with a real pushpin: [replace
with your own concepts, e.g. "a server rack, a database, a cloud icon,
a robot arm representing an AI agent, a laptop"].

Real coral-red string connects the pins as edges, denser near the
center, looser toward the edges, forming emergent geometry rather than
random tangles. Include pin shadows, thread tension differences,
natural cross-overlaps, and a warm white paper-texture background.
Generous negative space.

Do not include any text, letters, numbers, words, or hand-written
labels anywhere in the image. Wide landscape orientation, roughly 2:1
aspect ratio.
```

## Result

A dark-mode-friendly counterpart works too. Ask for an exact color
inversion (background to near-black, marks to white or light gray, same
shapes and positions) as a second pass on the result.

## Credit

Inspired by [xxd-panel-087](https://github.com/nevertoday/xxd-panel-087),
which transforms an uploaded photo into a similar pin-and-string style.
This skill is a simpler, from-scratch English prompt for a plain
concept network instead of a photo transform. It shares the aesthetic,
not the source code or the original prompt text.

Tested on [nimaarki.com](https://nimaarki.com), 2026-08-30.
