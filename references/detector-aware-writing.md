# Detector-Aware Writing

Read this when the user asks for aggressive humanization, detector-aware rewriting, mentions an AI detector, supplies detector output, or asks to reduce AI-like patterns. This covers AGGRESSIVE and DETECTOR-AWARE humanization. For NATURAL-mode writing, `human-writing-patterns.md` is enough.

## What this is and isn't

Humanization is **not** synonym replacement. Swapping words while keeping the same syntactic skeleton leaves every statistical fingerprint intact and usually reads worse. The signals that mark prose as machine-generated live at the level of structure, rhythm, and predictability — so that's where the editing happens.

AI detectors are probabilistic classifiers trained on different data with different models. They disagree, they update, and they produce false positives on genuine human writing. You cannot guarantee any score, and you must never claim one. What you can do is reduce the patterns that commonly drive high AI-probability estimates, while keeping the writing correct, useful, and readable.

**Never invent measurements.** Do not output "AI probability: 6%", "Perplexity: 87", or "Burstiness: 92" unless a real tool or the user supplied those numbers. Qualitative judgment is fine: "sentence variation: strong", "structural repetition: low".

## The intensity ladder (internal)

Infer intensity from the request; don't expose this scale unless the user asks for configurable intensity.

1. Light editing — touch only what's broken.
2. Natural — the NATURAL-mode default.
3. Strong — noticeable structural rewriting.
4. Aggressive — heavy structural and stylistic variation.
5. Detector-aware maximum — everything below, driven by detector feedback when available.

Higher intensity means more structural rewriting, more sentence variation, less predictable phrasing, more varied paragraph organization, more removed generic prose, and more voice. Factual preservation is mandatory at every level.

## Sentence predictability

Machine prose tends toward statistically predictable continuations — the next word or clause is the "obvious" one. Reduce that by varying, as meaning allows:

- sentence length
- clause structure and clause order
- subject placement (not every sentence opening on the grammatical subject)
- sentence openings
- punctuation
- direct statements vs. explanatory ones
- active vs. passive where passive genuinely reads better
- where a dependent clause sits (front, middle, end)

This is not grammar randomization. Every choice still has to sound intentional. The aim is prose that a careful human editor would sign off on, not prose that's merely unusual.

## Burstiness

Human writing distributes complexity unevenly. A dead giveaway is a paragraph of same-weight sentences:

```text
medium sentence
medium sentence
medium sentence
medium sentence
```

Natural rhythm is uneven — a short punch, an explanatory sentence, a longer one that earns its length, another short one:

```text
short
medium
long
short
```

Don't enforce a numeric sequence; that just trades one mechanical pattern for another. Read the paragraph and let the rhythm follow the ideas.

## Paragraph unpredictability

Avoid every paragraph running the same shape:

```text
topic sentence → explanation → example → summary sentence
```

Let paragraphs vary. Some open with the example. Some open with the consequence, then explain it. Some answer a question outright. Some are one or two sentences. Some raise a qualification or a counterexample instead of a tidy summary. Some transition implicitly, with no closing sentence at all. Structure emerges from what the paragraph is actually doing.

## Sentence-opening diversity

Scan for repeated openings and fix the underlying syntax, not just the first word:

```text
This... This... This...
The... The... The...
Additionally... Furthermore... Moreover...
```

Also watch for repeated frames that hide behind different first words: "This means...", "This allows...", "By doing X...", "Whether you're...", "From X to Y...". Replacing "This means" with "This shows" changes nothing. Restructure the sentence.

## Structural symmetry

Break unnecessary symmetry. Suspicious patterns:

- exactly 3 benefits, 3 drawbacks, 3 examples, 3 best practices
- every section following definition → benefits → example → summary
- parallel section lengths for no reason

Use the structure the information actually needs. If a topic has two real tradeoffs and five genuine steps, write two and five.

## Predictable transitions

Reduce explicit connectors: Furthermore, Moreover, Additionally, Consequently, Therefore, In addition, On the other hand. Don't ban them — use one when the logical relationship genuinely benefits from being named. Human prose transitions through context far more often than through transition words. Frequently the fix is to delete the connector and let the next sentence stand.

## Vocabulary predictability

LLMs over-reach for a small set of words: crucial, robust, seamless, comprehensive, leverage, enhance, optimize, landscape, realm, pivotal, transformative, innovative, effective, efficient, powerful. None are forbidden — use one when it's genuinely the best word. But when they cluster, they read as generated. Prefer context-specific vocabulary: not "leverage caching to enhance performance" but "cache the query results so the page stops hitting the database on every load".

## Excessive polish

AI writing often sounds *too* finished: every sentence grammatically symmetrical, every transition explicit, every paragraph closed neatly, every thought fully explained, every section the same rhetorical shape. In AGGRESSIVE and DETECTOR-AWARE mode, allow natural editorial irregularity that fits the audience:

- a short standalone sentence
- an implied transition
- a deliberate fragment, where it's stylistically right
- conversational phrasing and contractions
- a parenthetical aside
- an occasional rhetorical question
- uneven paragraph length
- a bit of intentional abruptness
- slightly informal phrasing

These must fit the target reader. A professional technical article stays professional — the irregularity is a seasoned author's voice, not sloppiness.

## Natural imperfections — the boundary

The rule is not "add imperfections." It's:

> Never inject obvious mistakes merely to simulate humanity. In aggressive or detector-aware mode, subtle stylistic irregularities may be preserved or introduced when they naturally fit the author's voice, audience, or context.

Acceptable when they fit: contractions, deliberate fragments, mild conversational phrasing, occasional informal constructions, parenthetical asides, slight repetition for emphasis, opening with "And" or "But", occasional rhetorical questions, non-uniform punctuation rhythm.

Never acceptable: misspelled keywords, wrong names, wrong numbers, incorrect URLs, broken code, incorrect technical terminology, factual errors, fake grammatical errors. Correctness always wins.

## Perplexity, honestly

You cannot compute a model's true perplexity without a real tool, so don't claim to. Approximate the *concept* through editing: avoid obvious phrase completion, avoid repeated syntactic templates, replace generic continuation phrases, vary clause order, avoid predictable paragraph endings, use more context-specific language. Describe the result qualitatively if asked — never as a number you didn't measure.

## Semantic and SEO preservation

Detector-aware rewriting preserves, unchanged: factual claims, the primary keyword, useful secondary SEO terminology, names, dates, numbers, URLs, product names, code, commands, quoted material, technical terminology.

It must not damage SEO: keep search intent, topical coverage, primary-keyword relevance, important entities, useful headings, internal links, and clear direct answers. Do not replace correct technical terms just because they look statistically predictable — "PostgreSQL", "idempotent", and "TTL" are the right words even if a detector finds them expected. Do not misspell keywords. Do not blur heading clarity. Meaning is never altered just to make text less predictable.

## Detector feedback workflow

When the user supplies detector output (a score plus, often, highlighted sentences):

1. Treat it as diagnostic information, not absolute truth. Detectors are wrong sometimes.
2. Read the highlighted sections — and their neighbors. The flagged sentence is often fine while the surrounding paragraph carries the repetitive structure that triggered it.
3. Identify the actual patterns: uniform sentence length, repeated openings, symmetrical paragraphs, generic phrasing, predictable transitions.
4. Rewrite those patterns at the right level — sentence, paragraph, or section — not by spinning synonyms into the flagged line.
5. Preserve factual meaning and SEO intent throughout.
6. Recheck the whole piece for consistency (a local rewrite can strand a reference or repeat a point made elsewhere).
7. Return the revised article.

Operate at whichever level the problem lives at. A highlighted sentence with clean neighbors gets a sentence-level fix; a highlighted sentence inside four same-shaped paragraphs needs the paragraphs reworked.

## Multi-pass loop

```text
Original → humanize → detector result → analyze flagged sections
→ targeted rewrite → detector result → optional second targeted rewrite
```

Stop after one or two targeted revisions unless the user explicitly asks to keep going. Repeated rewriting erodes clarity and voice — at some point you're damaging good writing to chase a probabilistic score, which violates the priority hierarchy.

## Detector tools are optional

The skill works with zero external services. If the host agent has a detector tool or browser workflow available **and** the user explicitly asks to use it, you may. Otherwise: don't pretend a detector ran, and don't invent GPTZero / Originality.ai / any scores. If the user pastes results, use them. Never make the core skill depend on any detector API, MCP server, or browser automation.

## Diagnostics mode

When the user wants analysis rather than a rewrite, return concise editorial findings — not hidden reasoning:

```text
Likely AI-like patterns:
- uniform sentence lengths in the middle three paragraphs
- repetitive paragraph openings ("This...")
- excessive explicit transitions (Furthermore, Moreover)
- predictable section structure (every section: definition → benefits → example)
- generic explanatory phrasing ("leverage", "enhance", "robust")
```

Findings, not chain-of-thought. No invented scores.

## Anti-pattern scan (before finalizing AGGRESSIVE / DETECTOR-AWARE output)

Internally sweep for clusters of:

- repeated sentence lengths; repeated sentence openings; repeated paragraph structures
- excessive transitions; predictable lists; excessive three-item sequences
- generic introductions; generic conclusions; repeated adjective pairs/triples
- excessive em dashes; overly formal vocabulary; unnecessary summaries
- formulaic heading patterns
- repeated "This means...", "This allows...", "By...", "Whether...", "From X to Y..."
- overly balanced sentence construction

Fix the meaningful clusters. One focused pass, then stop.

## Don't over-humanize

The failure mode on the other side is destroying good writing to make it statistically odd. Both of these are wrong for a professional technical audience:

```text
Redis, well, it basically kinda stores things super fast you know.
```

```text
Redis stores cached datas and make applications faster.
```

The first is fake-casual noise; the second is just broken grammar. Neither is "more human" — they're worse. Target credible human authorship, appropriate to the reader.

## Author voice takes precedence

If the user supplies a writing sample, match its fingerprint above generic heuristics. Read it for: sentence-length distribution, paragraph length, directness, contraction frequency, first-person use, humor, technical depth, preferred punctuation, rhetorical-question frequency, informality, amount of qualification, typical transitions. Reproduce those traits during rewriting — but capture high-level characteristics, never copy a living author's distinctive phrasing.
