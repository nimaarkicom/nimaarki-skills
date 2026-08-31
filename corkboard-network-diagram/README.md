# Corkboard network diagram

An image-generation prompt that turns a set of concepts into a physical
pin-board diagram: paper cards, pushpins, and real red string connecting
them, on a warm paper texture. No text is ever rendered into the image.

Inspired by [xxd-panel-087](https://github.com/nevertoday/xxd-panel-087),
adapted into English and simplified for a plain concept network instead
of a photo-to-diagram transform.

## How to use it

1. Copy `prompt.md`.
2. Replace the bracketed concept list with your own subject.
3. Send it to an image model that supports style/texture prompts (tested
   against GPT Image 2, through AceData).

Tested on nimaarki.com, 2026-08-30.
