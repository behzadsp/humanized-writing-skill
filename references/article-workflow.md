# Article Workflow

Four modes. Infer the mode from the request; never make the user pick. All analysis, planning, and critique happens internally — output the deliverable, not the process.

## Mode detection

- **CREATE** — "write an article about X", a keyword, a brief, a topic. New content from scratch.
- **REWRITE** — "humanize this", "rewrite this so it sounds natural", "make this sound like an expert wrote it". Existing content, substantial rework, facts preserved.
- **IMPROVE** — "improve this section", "tighten this up", "fix the intro". Targeted changes; most of the text stays.
- **OPTIMIZE** — "optimize this for [keyword]", "make this satisfy search intent", "SEO-improve this post". Existing content, SEO-driven changes.

Mixed requests are common ("rewrite and optimize this") — run the relevant workflows together.

## CREATE

1. Understand the subject well enough to write accurately. Use research tools if available and needed; never fabricate what you can't verify.
2. Determine the intended reader and their expertise level.
3. Determine the likely search intent (see `seo-writing.md`).
4. Identify the primary question or problem the article must answer.
5. Decide which subtopics are necessary to answer it — no more.
6. Choose a structure that fits the subject and intent, not a template.
7. Draft, applying `human-writing-patterns.md` throughout.
8. Run the internal critique pass (below).
9. Check SEO usefulness: intent satisfied, primary topic clear, headings descriptive.
10. Revise the weak sections found.
11. Return the requested deliverable — the article, in clean Markdown, nothing else unless asked.

Do these steps internally. Don't dump the analysis on the user. Don't ask clarifying questions when reasonable assumptions produce a useful result; if the user says "write an SEO article about Laravel Horizon", assume intermediate Laravel developers, informational intent, and write.

## REWRITE

1. Read the source and inventory its factual claims: facts, names, numbers, dates, URLs, product names, commands, code, technical terminology.
2. Identify its audience and intent.
3. Identify the formulaic patterns present (use `human-writing-patterns.md` as the checklist).
4. Rewrite structurally — reorder, merge, split, cut — not synonym-by-synonym. Mechanical paraphrasing produces the same skeleton with worse words.
5. Fix sentence and paragraph rhythm.
6. Remove repetition and filler.
7. Replace vague wording with concrete wording **only where the source supports it**. Never invent specifics to sound concrete.
8. Keep useful SEO terminology naturally in place.
9. Verify against the step-1 inventory that no fact, claim, or required element was lost or altered.

Preserve intended meaning above all. Never silently change a fact to make a sentence flow better. When unsure whether something is factual or stylistic, preserve it. Do not introduce new facts or opinions during a rewrite.

## IMPROVE

Change only what needs changing.

- Diagnose the actual weaknesses first (or fix exactly what the user pointed at).
- Leave strong writing alone — activation of this skill is not a mandate to rewrite everything.
- Respect the existing author's voice when it is already working.
- Same fact-preservation rules as REWRITE.

## OPTIMIZE

1. Determine the likely search intent for the target query.
2. Evaluate honestly whether the article answers it.
3. Find meaningful topic gaps — questions the searcher has that the article skips.
4. Inspect the title and heading structure for clarity and descriptiveness.
5. Remove filler; optimization includes deletion.
6. Improve direct answers near relevant headings (snippet-friendly blocks where warranted).
7. Preserve sections that already work.
8. Integrate the keyword and its variants naturally — no stuffing, no awkward exact-match.
9. Apply changes or recommend them, depending on what the user asked for.

More words are not automatically better. Never expand word count for its own sake.

## Internal critique pass

Before finalizing any substantial long-form piece, sweep the draft for:

- generic introduction; conclusion that adds nothing (or exists unnecessarily)
- repetitive sentence openings; uniform paragraph structure
- keyword stuffing; unnatural exact-match phrases
- repeated ideas; vague or unsupported claims; fake statistics
- excessive transitions, lists, or headings
- three-item pattern abuse; em-dash overuse; fake enthusiasm
- over-explanation for the target audience; irrelevant tangents
- mismatched expertise level; weak search-intent satisfaction

Fix the meaningful problems silently, then stop. **One focused critique-and-revise pass is normally enough.** Do not loop trying to make it perfect.

## Word counts

A requested word count is a target, not a license to pad. Aim reasonably close while prioritizing useful coverage. Never pad by repeating points, adding generic definitions, writing unnecessary summaries, or bolting on irrelevant FAQ questions. If the topic honestly supports 1,400 words and the user asked for 2,000, find genuinely useful additional coverage (examples, edge cases, comparisons) or note the gap — don't dilute.

## Content briefs

When the user supplies a brief (primary keyword, secondary keywords, title, audience, intent, word count, competitors, required headings, internal links, references, CTA, brand voice):

- Explicit brief requirements are authoritative — follow them unless they would force a factual error.
- Required headings go in; required links go in with natural anchors.
- Secondary keywords are coverage hints, not insertion quotas. Work them in where the topic naturally reaches them; skip any that would force awkward prose.

## Technical content

This skill should be excellent at software engineering articles specifically:

- Use terminology correctly and precisely.
- Respect the reader's stated or implied expertise — no explaining PHP to senior Laravel developers.
- Explain mechanisms, not just benefits: *how* it works and *why* that matters.
- Discuss tradeoffs where they exist.
- Include useful, realistic examples.
- Preserve code exactly unless asked to change it.
- Zero marketing fluff.

Prefer:

```text
Laravel queues move slow work such as email delivery or image processing out of the HTTP request lifecycle. The user gets a response without waiting for that work to finish.
```

over:

```text
Laravel queues are a powerful and robust feature that enables developers to significantly enhance application performance and deliver seamless user experiences.
```

## Output format

Default to clean Markdown:

```markdown
# Title

Introduction...

## Descriptive heading

Content...

### Subheading

Content...
```

No metadata tables, SEO scores, or analysis before the article unless requested. If the user asks for the article, return the article. Use bullet or numbered lists only where the information genuinely benefits from scanning — never convert normal prose to lists by reflex.
