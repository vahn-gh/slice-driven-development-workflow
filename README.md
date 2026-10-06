# Spec-driven development workflow

**Simple, readable code by an agent matters more than a complete plan.**

When working with agents, you can spend most of your time planning, going in the wrong direction, and trying to explain to the agent what you want, when you should be spending it on building the feature. This workflow helps you commit more code while keeping it reviewed, tested, and readable.

## Layout to copy into a project

```
.docs/
  AGENTS.md                  # rules for agents (copy from this repo)
  templates/
    slice.md                 # slice template (copy from this repo)
  features/
    <feature-name>/
      spec.md                # what the feature does and why
      slices/
        README.md            # slice order and project conventions
        01-<name>.md
        02-<name>.md
```

## Workflow

1. Write `spec.md` for the feature: the goal, the behavior, the main design choices.
2. Split it into slices with `templates/slice.md`. A slice lists the files that change and what changes in each.
3. The agent records its own implementation choices in the slice's **Decisions** section and asks only product questions in **Questions**.
4. Answer the questions and set `status: ready`.
5. The agent implements the slice and sets `status: implemented`.
6. Review the code. Fix or rewrite what's wrong, or send fixes back through the same slice.

## Files

- `AGENTS.md`: how agents write and implement slices.
- `templates/slice.md`: the slice template.
