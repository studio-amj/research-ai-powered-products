# Methodology (How This Research Is Built)

## 1) What We Mean by "AI Internalization"

In this research, "internalization" refers to integrating AI capabilities into an organization's software stack and workflows in a way that is repeatable, governed, and scalable.

We split the implementation approach into three buckets:

### A. In-House Model Internalization

Evidence signals:

- Organization trains its own models, or fine-tunes open-source / licensed foundation models.
- Models run on the organization's infrastructure (on-prem, private cloud, or dedicated hosted compute).
- The organization operates parts of the ML/LLM lifecycle: data pipelines, evaluation, safety guardrails, inference/serving, monitoring.

Common motivations:

- Differentiation (domain-specific performance), cost at scale, latency, data residency, IP control, reliability.

### B. Big-Tech / Third-Party AI API Usage

Evidence signals:

- AI features are powered primarily by a hosted API or managed foundation model platform.
- Examples: OpenAI API, Azure OpenAI, AWS Bedrock, Google Vertex AI (managed foundation models), Anthropic API, etc.

Common motivations:

- Fast time-to-market, reduced infra/ML ops burden, access to best frontier models, predictable vendor tooling.

### C. Hybrid

Evidence signals:

- Combination of in-house models for core workloads plus API for edge cases.
- Model routing by cost/latency/risk; self-hosted RAG with external model inference; or staged migration API -> self-host.

## 2) Scope of Each Industry Document

Each industry doc is organized as:

- Market size + outlook: multiple sources where possible; highlight definition differences.
- Current adoption patterns: where AI is deployed in products vs internal tools.
- Use cases and workflow breakdowns: what changes operationally.
- Company 사례: with citations; classify into In-House vs API vs Hybrid (only when evidence supports it).
- Constraints: regulatory, data/IP, workforce, compute, and customer trust.
- Forward view: 12-24 months and 3-5 years; catalysts and blockers.

## 3) Evidence Rules

- No invented numbers. If a statistic is not visible in the source, it is not used.
- Prefer primary sources (company announcements, product docs, regulatory filings) for 사례.
- For market sizing, clearly label:
  - Publisher
  - Publication date
  - Geography
  - Market definition (what is included/excluded)

## 4) Citation Style

- Inline footnotes where possible (Markdown `[^n]`).
- At the end of each doc, include a `## References` section listing:
  - Title, Publisher, Publication date (if available), URL, Access date
