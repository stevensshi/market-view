# marketView — demo site

**Live:** https://stevensshi.github.io/marketview-demo

An autonomous market-intelligence product: every morning an LLM pipeline
reads the market firehose (Bloomberg news mail, research newsletters such as
Apollo's Daily Spark, web search, viral social) and synthesizes it into
ranked, evidence-linked investment theses across six asset classes,
rendered as a single self-contained HTML dashboard.

## Pipeline

firehose → EXTRACT (budget LLM tier) → CLUSTER + SYNTHESIZE (per-sector
fan-out + market-wide ROLLUP, frontier LLM) → VERIFY (every claim needs a
source) → RANK (materiality signals) → RENDER (static HTML).

Design decisions worth reading the views for:

- **Event families**: theses driven by one underlying event (e.g. a Hormuz
  supply shock) are grouped under a family rail and hub card — but never
  merged, because opposite-direction logics are different trades.
- **Consensus ↔ contrarian**: for/against evidence bars per thesis keep the
  minority view visible instead of averaging it away.
- **Trust layer**: unverifiable claims are flagged, social items pass an
  engagement gate, research-newsletter content is republished only as short
  excerpts linking to public permalinks.

## What's in this repo

Only rendered output: `latest/`, dated `views/`, `manifest.json`, and this
page. The pipeline source lives in a private repo; happy to walk through it —
contact via GitHub profile.

*Personal research project. Not investment advice.*
