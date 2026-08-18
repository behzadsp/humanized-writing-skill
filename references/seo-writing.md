# SEO Writing

Modern SEO writing means satisfying the searcher's intent with genuinely useful content, structured so both readers and search engines can parse it. It does not mean keyword density, padded word counts, or robotic exact-match phrasing.

## Search intent first

Before writing, identify the dominant intent behind the target query:

- **Informational** — the reader wants to understand something ("how do Laravel queues work"). Structure: direct answers, explanations, examples.
- **Commercial investigation** — the reader is comparing options before a decision ("best Linux server monitoring tools"). Structure: honest comparison, criteria, tradeoffs, recommendations for different situations.
- **Transactional** — the reader is ready to act ("buy managed VPS"). Structure: what they get, pricing clarity, how to proceed, objections answered.
- **Navigational** — the reader wants a specific page or brand. Rarely the target of long-form content.

The article's structure must serve the dominant intent. A commercial-investigation query answered with a 1,500-word history of the product category fails the searcher. If the user's brief conflicts with apparent intent, follow the user's explicit requirements.

## Primary keyword

- Use the primary keyword naturally: typically in the title, early in the introduction, and in headings where it genuinely fits.
- Never chase a keyword-density percentage. There is no correct density.
- Avoid awkward exact-match repetition ("best cheap VPS hosting best cheap VPS hosting providers"). If the exact phrase is ungrammatical, use the grammatical form.
- Use variations, synonyms, related entities, and adjacent terminology when they arise naturally from covering the topic well.

## Secondary topics

Cover related subtopics because they help answer the query — not because they contain keywords. The test: would a knowledgeable human writing for readers include this section? If a section exists only to catch a keyword, cut or merge it.

## Titles

- Communicate exactly what the reader will get.
- Front-load the substance; keep it scannable.
- No clickbait unless explicitly requested.
- "Laravel Queue Best Practices for Production Apps" beats "Unlock the Power of Laravel Queues!"

## Introductions

The introduction's job: confirm within two or three sentences that this page answers the reader's query, then get moving. No long generic background. A searcher scanning results decides in seconds whether to stay.

## Headings

- Headings should carry information on their own — a reader scanning only the headings should learn the article's skeleton.
- Avoid vague headings when something specific is available: not "Understanding the Basics" but "How the Queue Worker Processes Jobs"; not "Key Considerations" but "When a Managed Database Costs More Than It Saves".
- Keep heading hierarchy logical (H2 for sections, H3 for subsections). Don't multiply headings to look structured — a heading every two sentences fragments the article.

## Featured-snippet-friendly answers

When a query has a direct answer or definition, give a concise, self-contained answer (one to three sentences) immediately after the relevant heading, then expand. This serves scanning readers and snippet extraction alike. Do not turn the whole article into snippet bait — one or two direct-answer blocks where the queries warrant them.

## Internal links

- If the user supplies internal URLs, a sitemap, or site structure, look for places where a link genuinely helps the reader continue.
- Anchor text should describe the destination naturally.
- Never invent URLs. No supplied URLs means no internal links.

## External evidence

- When browsing or research tools are available and the topic requires current facts (versions, prices, statistics, dates), verify important claims against authoritative sources before asserting them.
- Never invent studies, statistics, citations, quotes, or URLs. If tools are unavailable and a claim can't be verified, either qualify it honestly or omit it.

## E-E-A-T-style quality

Signals of expertise come from the writing itself:

- correct, precise terminology
- concrete examples and realistic scenarios
- honest limitations and tradeoffs ("this approach breaks down when...")
- useful comparisons with real criteria
- practical consequences, not abstract benefits
- appropriate qualification of conditional claims

Never fabricate first-person experience to simulate the "Experience" in E-E-A-T. Depth and accuracy demonstrate expertise better than invented anecdotes.

## What not to do

- No keyword-density targets or stuffing.
- No padding to hit a word count (see the word-count rules in `article-workflow.md`).
- No auto-appended FAQ sections. Add FAQs only when the user asks or when meaningful secondary questions don't fit the article body. Never invent bizarre long-tail questions.
- No "SEO voice": the flat, generic register of mass-produced content is itself a quality problem. Write for the reader; structure for the search engine.
