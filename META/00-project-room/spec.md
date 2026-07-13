# Qualitative-Comparison Platform · Project Room

> A two-ended platform for running qualitative / case studies fast over **arbitrary resources**. **Production end**: apply tools/scales to a corpus → outputs. **Evaluation end**: side-by-side pairwise comparison of any two resources/outputs, with **semantic** (not textwise) alignment highlighting. Book-distillation auditing is the first user, not the whole scope.

- [`specs/intent-project-001.yaml`](specs/intent-project-001.yaml)

## The two ends

Both ends together are the deliverable (and the potential HCI paper).

## Rooms

- [`01-agreement-workbench`](../01-agreement-workbench/spec.md) — **Evaluation end**. Take any two resources/outputs and convey **how much they agree** (salience-weighted, semantic — not textwise) and where they conflict. Deliberately not a "which is better" ranking (*better* is hard to assess). Serves both book-distillation compare and deep-research compare.
- [`02-generation-workbench`](../02-generation-workbench/spec.md) — **Generation end**. Pick tools/scales/styles × swap corpus → generate a matrix of outputs quickly. Feeds the agreement end.
