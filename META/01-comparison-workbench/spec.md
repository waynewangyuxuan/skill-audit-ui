# Room 01 · Comparison Workbench — Evaluation End (评测端)

> Take any two (or a few) resources/outputs and compare them side-by-side, aligning on **meaning, not position** — semantic/viewpoint highlighting so a human can do pairwise qualitative study efficiently and in batch. Resource-agnostic.

- **Intent**: [`specs/intent-comparison-workbench-001.yaml`](specs/intent-comparison-workbench-001.yaml)

## The problem

Two outputs read raw, side by side, have no comparability — you can't tell which
parts agree and which diverge. Textwise similarity (the online plagiarism "colour
boards") misses it, because the same viewpoint can be phrased completely
differently. This room's job is **semantic** alignment.

## Three views (all projections over the same content, by decreasing dependency on a shared source)

1. **Semantic pairwise side-by-side** — MVP / demo core. ≤3 native-structure
   panels; hover a chunk → cosine-highlight the semantically-nearest chunks in the
   others (red/yellow). Content-driven, never positional. Works for ANY two outputs.
2. **Claim-normalized grid** — the scalable view. Normalize each output into atomic
   claims (embedding + clustering); matrix of claims × outputs shows agreement /
   unique / conflict. Generalizes to N outputs; still needs no shared source.
3. **Source-anchored lens** — CONDITIONAL, only when the outputs share a source
   (e.g. book distillation): coverage heatmap over the source + jump-to-source
   provenance. Unavailable when there is no common source (e.g. two deep-research
   answers to different prompts).

## Must serve both customers with one UI

- Book distillation — compare what different methods/scales distilled from a book.
- Deep research (Vert's team) — compare deep-research approaches to judge which is better.

## Belongs here / not here

Belongs: the comparison views, the embedding/similarity + claim computation, the
alignment interaction. Does NOT belong: generating the outputs in the first place
(that is Room 02, the production end); source ingest/anchoring mechanics of any
specific pipeline.
