---
slice: NN
title: Short title of the slice
status: draft # draft | ready | implemented
depends_on: [] # e.g. [01, 02]
spec: ../spec.md
---

# Slice NN: Short title of the slice

## Goal

One or two sentences: what this slice adds and why, in plain words.

## Changes

### `path/to/ExistingFile.ts` (edited)

- What changes in this file, one fact per bullet.
- Use the names that will appear in code (classes, methods, fields).

### `path/to/NewFile.ts` (new)

- What the file contains and what each public method does.
- Follow the existing patterns of the codebase.

### `path/to/NewFile.test.ts` (new)

- What the tests check, as plain statements.

## Decisions

Implementation choices the agent made itself, each with a one-line reason. Settled: don't re-decide them without the user. See `.docs/AGENTS.md`.

- Choice: reason.

## Questions

Only product or business-logic questions the code can't answer. Delete this section when there are none.

**Q1. Question in one sentence?**
Answer:

## Out of scope

- What this slice deliberately doesn't do, and which slice does it.
