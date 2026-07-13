# Room 01 · Agreement Workbench — Evaluation End

> Take any two (or a few) resources/outputs and convey **how much they agree** — a salience-weighted agreement score plus where they align vs conflict, aligned on **meaning, not position**. Deliberately **not** a "which is better" ranking — *better* is hard to assess; *agreement* is tractable and fits our current case.

- **Intent**: [`specs/intent-agreement-workbench-001.yaml`](specs/intent-agreement-workbench-001.yaml)

## Why agreement, not "which is better"

Ranking one output as better than another is subjective and hard to evaluate.
Measuring **how much two outputs agree** (and where they diverge) is tractable,
defensible, and closer to our real case (a distilled product vs its source, or vs
another method). The UI conveys "how different, and where" — as agreement.

## The agreement model (three layers, all borrowed vocabulary)

| Layer | What | Borrowed from |
|---|---|---|
| **1 · Units** | Split each output into typed comparable units: viewpoints/claims, examples, entities/parties | content analysis (*coding/meaning units*); argument mining (claim→premise→evidence) |
| **2 · Relation** | Align units across sides (cosine candidates), label each pair: **Agree** / **Conflict** / **Neutral** / **One-sided** | **NLI** (entailment/contradiction/neutral); stance detection |
| **3 · Weighted score** | Rate each unit 大/中/小; aggregate into a **salience-weighted agreement score** (big units dominate) | RST nucleus/satellite (salience); **weighted Cohen's κ**, **Krippendorff's α**; **concordance** (meta-analysis) |

Always show the score **with its 大/中/小 tier breakdown** — big points agree +
small ones scatter ⇒ still high; small ones agree + big ones differ ⇒ low.

## Views (by decreasing dependence on a shared source)

1. **Semantic relation-colored side-by-side** — MVP / demo core. ≤3 native-structure
   panels; alignment ribbons between matched units, **green=Agree, red=Conflict,
   gray=Neutral/One-sided**. The "colour board", but semantic and relation-typed.
   Header = weighted agreement score + tier bar. Never positional.
2. **Concordance grid** — scalable / N-way. Rows = units grouped by 大/中/小,
   columns = outputs, cells = Agree/Conflict/absent. Big points float to top.
3. **Source-anchored lens** — CONDITIONAL, only when outputs share a source (book
   distillation): coverage heatmap + jump-to-source. Absent when there is no
   common source (e.g. two deep-research answers to different prompts).

## Must serve both customers with one UI

- Book distillation — agreement between a distilled product and its source / another method.
- Deep research (Vert's team) — agreement between different deep-research outputs.

## Belongs here / not here

Belongs: the agreement model (units, relations, score), the comparison views, the
embedding/NLI computation. Does NOT belong: generating the outputs (that is Room
02, the generation end).
