# Humanized Writing Skill

An agent-agnostic AI skill for writing natural, high-quality SEO articles and blog content — and for humanizing existing content without losing facts or search performance.

It teaches an AI agent to write long-form web content that reads like careful human authorship: varied rhythm, concrete detail, a real voice, and structure driven by search intent instead of LLM habits. It works with any tool that supports the portable [Agent Skills](https://agentskills.io) `SKILL.md` convention: Claude Code, OpenAI Codex, Cursor, GitHub Copilot, OpenCode, Windsurf, and others.

## Installation

```bash
npx skills add behzadsp/humanized-writing-skill
```

The Skills CLI lets you choose which installed agent(s) to add the skill to. You can also install manually by copying this repository into your agent's skills directory — everything the skill needs is `SKILL.md` and `references/`.

## Example usage

```text
Write a humanized SEO article targeting "Laravel queue best practices".
Audience: intermediate Laravel developers.
```

```text
Humanize this article while preserving its technical accuracy:
[paste article]
```

```text
Optimize this blog post for the keyword "managed VPS hosting"
without keyword stuffing or generic SEO language.
```

```text
Write a 1,800-word guide to Redis caching.
Make it sound like an experienced backend engineer explaining
the topic to another developer.
```

## Features

- **Natural long-form writing** — varied sentence and paragraph structure, concrete mechanisms over vague claims, an actual authorial voice
- **SEO and search-intent optimization** — intent-driven structure, descriptive headings, snippet-friendly answers, natural keyword use
- **Humanized rewriting** — four modes (create, rewrite, improve, optimize), inferred automatically from the request
- **Anti-formulaic writing checks** — a detailed catalog of LLM writing patterns (stock intros, empty transitions, three-item lists, fake enthusiasm, generic conclusions) with an internal critique pass before delivery
- **Semantic preservation** — facts, names, numbers, URLs, code, and technical claims survive every rewrite
- **Technical content support** — particularly strong at software engineering articles that respect the reader's expertise
- **Content brief support** — briefs with keywords, required headings, word counts, and brand voice are treated as authoritative
- **Agent agnostic** — plain `SKILL.md` + Markdown references; no APIs, no MCP servers, no vendor-specific configuration

## Philosophy

This project exists to make AI-assisted writing genuinely better — more useful to readers, more accurate, more natural to read. It is **not** an AI-detector bypass tool. It never instructs an agent to add typos, errors, or artificial noise, and it makes no claims that output will evade GPTZero, Originality.ai, Turnitin, or any similar system. Good writing and detector evasion are different goals; this skill only pursues the first.

## Repository structure

```text
humanized-writing-skill/
├── SKILL.md                          # Control plane: rules, modes, when to load what
├── README.md
├── LICENSE
└── references/
    ├── human-writing-patterns.md     # AI patterns to avoid + natural-writing model
    ├── seo-writing.md                # Search intent, keywords, headings, E-E-A-T
    ├── article-workflow.md           # CREATE / REWRITE / IMPROVE / OPTIMIZE workflows
    ├── quality-checklist.md          # Final QA pass before delivery
    └── examples.md                   # Before/after examples
```

`SKILL.md` stays compact; agents load the reference files only when the task needs them, keeping context usage low for small edits.

## License

[MIT](LICENSE)
