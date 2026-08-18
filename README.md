# Humanized Writing Skill

An agent-agnostic AI writing skill for humanized SEO articles, natural rewriting, aggressive humanization, detector-aware editing, and technical content — without losing facts or search performance.

It teaches an AI agent to write long-form web content that reads like careful human authorship: varied rhythm, concrete detail, a real voice, and structure driven by search intent instead of LLM habits. When asked, it goes further — reducing the statistical and structural patterns commonly associated with machine-generated prose. It works with any tool that supports the portable [Agent Skills](https://agentskills.io) `SKILL.md` convention: Claude Code, OpenAI Codex, Cursor, GitHub Copilot, OpenCode, Windsurf, and others.

## Installation

```bash
npx skills add behzadsp/humanized-writing-skill
```

The Skills CLI lets you choose which installed agent(s) to add the skill to. You can also install manually by copying this repository into your agent's skills directory — everything the skill needs is `SKILL.md` and `references/`.

## Writing modes

The skill reads two independent dimensions from your request and infers both automatically — you never have to name a mode.

**Task type:** create, rewrite, improve, or optimize.

**Humanization mode:**

- **Natural** *(default)* — excellent, readable prose with a strong voice and solid SEO. No deliberate irregularity. This is what "write an article" or "humanize this" gets you.
- **Aggressive humanization** — stronger structural and stylistic variation: sentence structure, paragraph rhythm, openings, transitions, and pacing. Still professional, still correct. Ask for it with "aggressive humanization", "much less AI-like", or "make the structure unpredictable".
- **Detector-aware rewriting** — reduces the linguistic and structural signals that AI detectors key on, and acts on detector feedback when you supply it. Triggered by any mention of AI detection, GPTZero, Originality.ai, Turnitin, or a pasted detector score.

The two combine freely: "write a new SEO article, aggressively humanized" runs create + aggressive; "GPTZero flagged this, rewrite it" runs rewrite + detector-aware.

## Example usage

```text
Write a humanized SEO article targeting "Laravel queue best practices".
Audience: intermediate Laravel developers.
```

```text
Rewrite this article using aggressive humanization while
preserving its SEO keywords and technical accuracy.
```

```text
GPTZero flagged this article as highly AI-generated.
Use detector-aware rewriting and preserve the meaning.
```

```text
Here is the detector output and highlighted text.
Revise only the sections that need it.
```

```text
Write a 2,000-word SEO article about Kubernetes autoscaling.
Use aggressive humanization and an experienced engineering voice.
```

```text
Optimize this blog post for the keyword "managed VPS hosting"
without keyword stuffing or generic SEO language.
```

## Features

- **Natural writing mode** — varied sentence and paragraph structure, concrete mechanisms over vague claims, an actual authorial voice
- **Aggressive humanization** — heavier structural and rhythmic variation while staying professional and correct
- **Detector-aware rewriting** — reduces uniform rhythm, repetitive openings, symmetrical structure, and generic phrasing that drive high AI-probability estimates
- **Detector feedback refinement** — paste a score and highlighted sentences, and the skill diagnoses the underlying patterns and rewrites at the right level (sentence, paragraph, or section) over one or two targeted passes
- **SEO-aware humanization** — search intent, keywords, entities, headings, and direct answers are protected through every rewrite
- **Structural variation** — an internal anti-pattern scan for uniform lengths, repeated openings, over-explicit transitions, and forced three-item lists
- **Semantic preservation** — facts, names, numbers, dates, URLs, code, commands, and technical terminology survive every rewrite unchanged
- **Technical content support** — particularly strong at software engineering articles that respect the reader's expertise and preserve code exactly
- **Author voice adaptation** — supply a writing sample and the skill matches its fingerprint (rhythm, contractions, directness, technical depth) above generic heuristics
- **Agent agnostic** — plain `SKILL.md` + Markdown references; no APIs, no MCP servers, no vendor-specific configuration

## Philosophy

Humanized Writing exists to make AI-assisted writing more natural, useful, specific, and credible. It also supports detector-aware rewriting that reduces formulaic linguistic and structural patterns commonly associated with machine-generated prose. AI detectors are probabilistic systems and frequently disagree, so this project does not promise that content will be classified as human by any specific detector. Writing quality, factual accuracy, reader value, and semantic preservation remain higher priorities than any detector score.

That means the skill never injects typos, wrong facts, broken code, or fake grammatical errors to look human — poor writing is not more human, and detectors aren't fooled by corruption anyway. External detectors (GPTZero, Originality.ai, Turnitin) are optional: the skill uses their output only when you provide it or explicitly ask it to run an available tool, and it never invents scores.

## Repository structure

```text
humanized-writing-skill/
├── SKILL.md                          # Control plane: rules, modes, priority, when to load what
├── README.md
├── LICENSE
└── references/
    ├── human-writing-patterns.md     # AI patterns to avoid + natural-writing model
    ├── detector-aware-writing.md     # Aggressive + detector-aware methodology
    ├── seo-writing.md                # Search intent, keywords, headings, E-E-A-T
    ├── article-workflow.md           # Task type × humanization mode workflows
    ├── quality-checklist.md          # Final QA pass, incl. detector-aware QA
    └── examples.md                   # Before/after examples
```

`SKILL.md` stays compact; agents load the reference files only when the task needs them. Detector-aware guidance loads only for aggressive or detector-aware requests, so ordinary SEO writing keeps context usage low.

## License

[MIT](LICENSE)
