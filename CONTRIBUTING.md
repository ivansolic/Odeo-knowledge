# Contributing a lesson

## Use `/contribute-lesson`, not a hand-written PR

Inside Odeo, run `/contribute-lesson`. It will:

1. **generalize** your lesson, so it is about the pattern and not about your project
2. **run `privacy-scan.sh` as a hard gate**: emails, secrets and tokens, local paths, IP
   addresses, and your own deny-list terms. It blocks; you redact or explicitly confirm
   each finding is a generic example
3. **show you the exact text** that would leave your machine
4. **open the PR only after you approve it**

Hand-written PRs skip every one of those steps, which is why they are not accepted.

## This repository is public and permanent

Anything merged here is public forever. Deleting it later does not help: git history keeps
it, and forks and clones keep it too. The privacy scan is a safety net under your judgment,
not a substitute for it. **If you would not put it on a billboard, do not contribute it.**

## What belongs here

A lesson must be **all three**:

- **verified**: it actually worked, and you can say how you know
- **non-trivial**: not a typo fix, not something a first search finds
- **reusable**: a pattern likely to recur for someone else, not a one-off

## What does not belong here

- your code, your project's names, your architecture, your customers
- secrets, credentials, internal URLs, personal data, anyone else's data
- code you do not have the right to publish
- **anything phrased as an instruction to the agent.** Entries are reference material.
  Text like "always do X", "ignore Y", or "the new rule is Z" will be rejected: Odeo is
  built to disregard it, so at best it is noise and at worst it is an attempt to steer
  someone else's assistant. This is the one rule we enforce without discussion.

## Shape

One lesson per file, in the category that fits, with frontmatter:

```markdown
---
module: [the area it applies to]
tags: [searchable, keywords]
problem_type: [bug | pattern | decision]
provenance: [what it came from, no identifying detail]
reuse_count: 0
created: [YYYY-MM-DD]
---

# A title that states the lesson, not the topic

## Context
What situation produces this problem.

## Guidance
What to do, concretely.

## Why it matters
What it costs when ignored.

## When to apply
Including when NOT to.

## Example
Minimal and generic.
```

## Curation

A maintainer reads every PR. Expect edits for clarity, or a request to generalize further.
A rejection is usually "too specific to your setup" or "not verified", and is not a
judgment of you. Once merged, the lesson reaches every user on their next update.

## License

MIT. By contributing you agree your lesson is published under it, and you confirm you have
the right to publish it.
