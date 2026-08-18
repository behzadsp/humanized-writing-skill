# Human Writing Patterns

Two halves: patterns to avoid, and the model to follow. Apply both when drafting and when revising.

## Part 1: Formulaic AI patterns to avoid

### Generic introductions

Never open with scene-setting boilerplate:

- "In today's fast-paced digital landscape..."
- "In today's ever-evolving world..."
- "In the rapidly evolving world of..."
- "As technology continues to advance..."
- "In an era where..."

Start with the actual subject: the problem, a useful fact, a concrete observation, or the answer itself. If the first sentence could open an article on any topic, delete it.

### Empty transitions

Furthermore, Moreover, Additionally, Consequently, In addition, "It's important to note", "It's worth mentioning" — these usually decorate rather than connect. A transition earns its place only when it expresses a real relationship between ideas (contrast, cause, exception, consequence). Often the strongest transition is none: let the next idea start.

### Repetitive sentence rhythm

Watch for paragraphs where every sentence has roughly the same length, the same grammatical structure, the same opening pattern, or the same tone. That uniformity is the single strongest formulaic signal. Vary length because meaning varies — a short sentence for emphasis, a longer one when the idea genuinely needs room. Never randomize lengths mechanically; variation must follow meaning.

### Symmetrical structure

Do not force every topic into a template like:

```text
Introduction
3 Benefits
3 Challenges
3 Best Practices
Conclusion
```

Structure should emerge from the subject and the search intent. Some topics need a comparison table, some need a walkthrough, some need one long argument. If two sections have identical internal shapes for no reason, reshape one.

### The three-item reflex

LLMs default to groups of exactly three: three benefits, three examples, three adjectives ("fast, reliable, and scalable"). Use however many items the subject actually has — two, five, one. Triples are fine when the content genuinely comes in threes; suspicious when everything does.

### Generic conclusions

Avoid conclusions that restate the introduction, and avoid the stock openers: "In conclusion...", "Ultimately...", "By understanding...", "As we have seen...", "Whether you're a beginner or an expert...".

A conclusion must add something: a decision rule, a recommendation, a consequence, a next action, or a final insight the body couldn't hold. Some articles need no formal conclusion at all — a tutorial can simply end after the last step works.

### Fake enthusiasm

Revolutionary, game-changing, incredible, powerful, cutting-edge, seamless, robust — banned unless objectively justified in context (a "robust" statistical estimator is fine; a "robust" to-do app is not). Enthusiasm should come from interesting content, not adjectives.

### Em-dash overuse

Em dashes are legitimate punctuation, but LLMs use them as the default connector for every pair of thoughts. If a draft has an em dash in most paragraphs, replace most of them with periods, commas, colons, or restructured sentences.

### Over-explanation

Do not explain what the intended reader already knows. An article for senior Laravel developers doesn't define PHP, MVC, or Composer. Pitching below the audience wastes their time and reads as filler. Explain a concept only when the target reader plausibly needs it or the explanation carries the argument.

### Restating the obvious

```text
Caching can improve performance. This means applications can become faster.
```

The second sentence adds nothing. Cut sentences that paraphrase the previous one. One strong sentence beats a strong sentence plus its echo.

### Fabricated experience

Never pretend to have personally used a product, interviewed someone, run a benchmark, handled a production incident, or spoken with an expert — unless the user supplied that evidence. Adopt the tone of someone experienced without inventing the experiences. "Teams that run Redis at this scale usually hit X" is fine; "When I ran Redis at this scale, I hit X" is fabrication.

## Part 2: The natural-writing model

Optimize these dimensions together, not one at a time.

### Sentence variation

Mix short statements, ordinary explanatory sentences, and occasional longer sentences when an idea genuinely requires the room. The mix should feel like thinking, not like a randomizer.

### Paragraph variation

Paragraph lengths should differ naturally. A single-sentence paragraph is fine occasionally, when it earns the emphasis. A long explanatory paragraph is fine when the idea is genuinely one unit. Uniform four-sentence blocks are the tell.

### Specificity

Prefer mechanism, consequence, and condition over abstraction:

Weak: "Redis can significantly enhance application performance and improve overall efficiency."

Strong: "Redis keeps frequently requested data in memory, which can remove repeated database queries from a hot request path."

Every vague claim in a draft is an opportunity: name the mechanism, give the number, state the condition, or show the example.

### Qualification

Expert writing qualifies claims where reality is conditional:

- "That works well when..."
- "The tradeoff is..."
- "For smaller applications, this may not matter."
- "This becomes important once..."
- "In practice, the answer depends on..."

Qualify where the truth actually depends on circumstances. Do not hedge every sentence — blanket hedging reads as evasive, and unearned certainty reads as marketing. Match confidence to evidence.

### Voice

Sound like a knowledgeable person talking to another person. Not a corporate brochure, not an academic paper (unless requested), not a marketing department, not an AI assistant, not a dictionary. Contractions are fine when the tone allows. First person is fine when the user's voice uses it. Rhetorical questions sparingly, and only when they do work.

### Combining and cutting

Combine closely related thoughts when it improves flow. Cut adjectives and adverbs that don't change the meaning. Cut any sentence whose deletion loses nothing. Avoid saying the same idea twice in different words — pick the better phrasing and keep only it.
