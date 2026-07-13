# Qualitative-Comparison Platform · Project Room

> A two-ended platform for running qualitative / case studies fast over **arbitrary resources**. **Production end**: apply tools/scales to a corpus → outputs. **Evaluation end**: side-by-side pairwise comparison of any two resources/outputs, with **semantic** (not textwise) alignment highlighting. Book-distillation auditing is the first user, not the whole scope.

- [`specs/intent-project-001.yaml`](specs/intent-project-001.yaml)

## The two ends

Both ends together are the deliverable (and the potential HCI paper).

## Rooms

- [`01-comparison-workbench`](../01-comparison-workbench/spec.md) — **Evaluation end (评测端)**. Take any two resources/outputs and compare them side-by-side; semantic/viewpoint-level alignment highlighting so a human can do pairwise qualitative study efficiently and in batch. Serves both book-distillation compare and deep-research compare.
- [`02-production-workbench`](../02-production-workbench/spec.md) — **Production end (测试端)**. Pick tools/scales/styles × swap corpus → generate a matrix of outputs quickly. Feeds the evaluation end.
