# Contribution Guidelines

Thanks for wanting to add to **awesome-creative-agentic-coding**. The bar for this list is intentionally high — please read this before opening a PR.

## Scope

This list is for resources at the intersection of **agentic AI** (LLMs in a loop, with tools, memory, autonomy) and **creative coding for media art** (generative art, music, visuals, installations, audio-reactive media).

A resource fits if it satisfies *both* of:

1. **Agentic** — there is a meaningful agent loop, tool use, or autonomy. Pure text-to-image / text-to-music models are *not* in scope (they belong on [vibertthio/awesome-machine-learning-art](https://github.com/vibertthio/awesome-machine-learning-art) or [filipecalegario/awesome-generative-ai](https://github.com/filipecalegario/awesome-generative-ai)).
2. **Creative** — the application is media art, generative art, music, performance, or another creative-coding domain. Pure-engineering agentic tooling without a clear creative-coding through-line belongs on [e2b-dev/awesome-ai-agents](https://github.com/e2b-dev/awesome-ai-agents).

When in doubt, mention in the PR which axis you think the resource hits and why.

## Quality bar

- **Verify the URL works** before submitting. Broken links are removed without warning.
- Prefer **canonical** sources — the project's main repo or the artist's own site, not a fork or mirror.
- The resource should be **useful right now** — not a vague tweet, a 404'd talk page, or a paper with no code/recording.
- For artist projects: a real public artifact (repo, project page, recorded performance) is required. Press articles alone are not enough.

## Format

Each entry is a single line:

```
- [Name](url) — One-sentence description in active voice.
```

Conventions:

- Em-dash (—) between the link and the description, not a hyphen.
- Description is one sentence (under ~150 characters), ending in a period.
- Where ownership/lineage matters, put it in the description (e.g., "ahujasid's reference Ableton MCP").
- For papers, link to the canonical project page or arXiv abstract, not the PDF.

## What gets rejected

- Personal blog posts that are restatements of [Building Effective Agents](https://www.anthropic.com/engineering/building-effective-agents) without new insight.
- "AI art" projects with no agent loop (e.g., one-shot Midjourney generations).
- Defunct projects, archived repos with no replacement, or sites that 404.
- Self-promotion without a working artifact.
- Lists of tweets, threads, or anything reliant on a brittle screenshot.

## How to submit

1. Fork this repo.
2. Add your entry in the most-fitting section, alphabetically *unless* the section already has an opinionated ordering (e.g., Coding Agents is roughly ordered by ecosystem influence).
3. Verify your URL with `curl -sIL` or `gh repo view`.
4. Open a PR with the title `Add: <name>` or `Update: <name>` and a one-sentence justification — including which scope axis it hits.

Thanks for keeping the bar high.
