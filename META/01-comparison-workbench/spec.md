# Room 01 · Comparison Workbench

> Compare, over one corpus, what multiple distillation methods (book2skill / 女娲 / DSL) distilled — via one tripartite graph rendered as three lenses.

- **Intent**: [`specs/intent-comparison-workbench-001.yaml`](specs/intent-comparison-workbench-001.yaml)

## What lives here

The core comparison UX. The distillation products are **heterogeneous**
(book2skill = method cards + playbook with anchors; 女娲 = holistic
methodology; DSL = structured representation) — different structure,
different length — so they cannot be aligned by position. This room's
job is to find the shared axes to hang comparison on.

Backbone data model — one tripartite graph:

    source span ──consumed-by──▶ product fragment ──expresses──▶ claim

Three lenses = three pivots on that graph:
1. **Source-anchored** (pivot on source) — MVP, method-agnostic, only
   needs Layer-2 anchors. Coverage heatmap over the book.
2. **Product-anchored side-by-side** (pivot on product) — the spec's
   ≤3-panel view; alignment is cosine-similarity-driven, not positional.
3. **Claim-normalized grid** (pivot on claim) — normalize each product
   into atomic claims, render an agreement/unique/conflict matrix. The
   real scalable "compare the distillates directly".

Belongs here: comparison views, the graph data model, coverage/claim
computation. Does NOT belong here: single-book ingest/anchoring
mechanics (source project pipelines), the Layer-1 answer-routing
"trace drawer" (deferred, likely its own room later).
