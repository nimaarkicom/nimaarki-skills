# nimaarki-skills

Original prompts and tool skills used on [nimaarki.com](https://nimaarki.com)'s
[Skills page](https://dfnwhah6bfd5t.cloudfront.net/skills/).

One folder per skill, in the same `SKILL.md` format
[Claude Skills](https://docs.claude.com/en/docs/claude-code/skills) use:
YAML frontmatter (`name`, `description`) naming what the skill is and
when to use it, then a plain-markdown body explaining how. Each
`SKILL.md` is self-contained: copy the folder, read it, use it.

## Skills

- [corkboard-network-diagram](corkboard-network-diagram/): turn a set
  of related concepts into a physical pin-and-string corkboard diagram.

Some skills outgrow a folder and get their own repo, since each one
may change on its own schedule:

- [three-pass-prose-repair](https://github.com/nimaarkicom/three-pass-prose-repair):
  fixes writing that reads flat, generic, or obviously AI-written.
  Moved here 2026-09-04 for its own version history, its own research
  reference files, and a real diagnostic script.
