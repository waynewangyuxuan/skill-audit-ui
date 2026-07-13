# Room 02 · Production Workbench — Production End (测试端)

> Pick different tools / scales / styles and apply them to a corpus → a matrix of outputs, quickly. Corpus swappable, scales swappable: **scale × corpus → output**. Feeds the evaluation end (Room 01).

- **Intent**: [`specs/intent-production-workbench-001.yaml`](specs/intent-production-workbench-001.yaml)

## What lives here

The generation half of the platform. Room 01 compares outputs; something has to
produce them under controlled variation — that is this room.

- Pick a corpus (any resource — book, article set, prompt).
- Pick one or more tools/scales/styles to apply (composable).
- Run → outputs. Vary either axis and re-run to build an output matrix fast.

The "tool" is a book-distillation method in one case and a deep-research pipeline
in another — same shape.

## Contract with Room 01

Output artifacts here are the direct inputs to the evaluation end. Define that
artifact contract early so production → evaluation is a clean handoff.

## Open questions (confirm with Frederick)

- What is a "scale"/"style" as a selectable, parameterizable unit? How are tools registered?
- How much backend orchestration do we own vs. call out to existing pipelines? The
  backend is the hard part; the UI is comparatively simple.

## Not here

Comparing/viewing outputs (that is Room 01). This room only produces them.
