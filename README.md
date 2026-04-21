# geo-schema — JSON-LD for AI Crawlers

> **Copy-paste Schema.org JSON-LD snippets optimized for how ChatGPT, Perplexity, Claude and Gemini read pages.**

Part of [AuraCite](https://auracite.de) — an analytics platform for Generative Engine Optimization.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## Why Schema.org matters for GEO

LLMs rely heavily on structured data to resolve entities, relationships and facts. In traditional SEO, schema is a "nice to have"; for GEO it is close to mandatory: AI engines index entity graphs, not just pages, and JSON-LD is the cleanest signal you can send.

## What is inside

| File | Use case |
| --- | --- |
| [`SoftwareApplication.jsonld`](SoftwareApplication.jsonld) | SaaS products and apps |
| [`Organization.jsonld`](Organization.jsonld) | Company entity (founders, contacts, sameAs) |
| [`FAQPage.jsonld`](FAQPage.jsonld) | Q and A blocks (high GEO signal) |
| [`TechArticle.jsonld`](TechArticle.jsonld) | Technical blog posts |
| [`HowTo.jsonld`](HowTo.jsonld) | Step-by-step guides |
| [`Product.jsonld`](Product.jsonld) | E-commerce products with reviews and price |

Every file is a fully-filled example using a placeholder brand (`ExampleBrand`) so you can see exactly what valid output looks like. Replace the placeholder values with your own.

## How to use

1. Pick the file that matches your page type
2. Replace every `"ExampleBrand"` / `"https://example.com/..."` value with your real data
3. Drop the JSON into a `<script type="application/ld+json">` tag in your `<head>`
4. Validate with [Google Rich Results Test](https://search.google.com/test/rich-results) or [schema.org Validator](https://validator.schema.org/)
5. Verify the page renders the JSON **without JavaScript execution** (AI crawlers often skip JS)

## Tips specific to GEO

- **Always set `sameAs`** on `Organization` — link to LinkedIn, GitHub, Crunchbase, Wikidata. LLMs use this to resolve your entity.
- **Keep `FAQPage` answers short and factual.** LLMs quote them nearly verbatim.
- **Use `TechArticle` instead of `Article`** for developer content. It is a stronger signal for Claude and Perplexity.
- **Fill `aggregateRating` on `Product` and `SoftwareApplication`** only when you actually have ratings. Fake ratings are detected and downranked.
- **For multi-brand pages, nest `Organization` inside `isPartOf`** rather than duplicating entities.

## Contributing

PRs welcome. Please:

1. Keep each file as a single valid JSON-LD object (not an array) so it is copy-pasteable
2. Use `https://schema.org` (https, canonical) as `@context`
3. Validate against [validator.schema.org](https://validator.schema.org/) before submitting
4. No marketing fluff in property values

## License

MIT — use these templates freely for any project, commercial or open-source.

## About AuraCite

- Website: [auracite.de](https://auracite.de)
- Contact: <g@auracite.de>

---

**Star this repo** if it saved you a trip to schema.org docs.