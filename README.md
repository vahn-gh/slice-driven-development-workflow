# Spec-driven development workflow

**Simple, readable code by an agent matters more than a complete plan.**

When working with agents, you can spend most of your time planning, going in the wrong direction, and trying to explain to the agent what you want, when you should be spending it on building the feature. This workflow helps you commit more code while keeping it reviewed, tested, and readable.

## Layout to copy into a project

```
AGENTS.md                    # Codex entry point (copy from templates/AGENTS.md)
CLAUDE.md                    # Claude Code entry point (copy from templates/CLAUDE.md)
.docs/
  AGENTS.md                  # shared workflow rules (copy this repo's root AGENTS.md)
  glossary.md                # one word per domain idea (start from templates/glossary.md)
  templates/
    slice.md                 # slice template (copy from this repo)
    glossary.md              # glossary template (copy from this repo)
  features/
    <feature-name>/
      spec.md                # what the feature does and why
      slices/
        README.md            # slice order and project conventions
        01-<name>.md
        02-<name>.md
```

## Agent setup

Copy the entry point for each agent you use. Both entry points use the same workflow rules and glossary under `.docs/`.

- **Codex** loads the root `AGENTS.md` automatically. Copy [`templates/AGENTS.md`](templates/AGENTS.md) to the project root or append its guidance to your existing `AGENTS.md`. It tells Codex to read the shared files before working on specs or slices. [Codex instruction discovery](https://learn.chatgpt.com/docs/agent-configuration/agents-md#how-codex-discovers-guidance)
- **Claude Code** loads the shared files through `@` imports. Copy [`templates/CLAUDE.md`](templates/CLAUDE.md) to the project root or add its imports to your existing `CLAUDE.md`.

If you keep `.docs/` local, put the Claude Code imports in `CLAUDE.local.md` and add that file to `.gitignore`. You can still commit the Codex entry point, which tells Codex to read the shared files when `.docs/` is present.

## Workflow

1. Write `spec.md` for the feature: the goal, the behavior, the main design choices. Add any new domain words to `glossary.md` first, so the spec, slices and code all use the same ones.
2. Split it into slices with `templates/slice.md`. A slice lists the files that change and what changes in each.
3. The agent records its own implementation choices in the slice's **Decisions** section and asks only product questions in **Questions**.
4. Answer the questions and set `status: ready`.
5. The agent implements the slice and sets `status: implemented`.
6. Review the code. Fix or rewrite what's wrong, or send fixes back through the same slice.

## Files

- `AGENTS.md`: shared rules for writing and implementing slices.
- `CLAUDE.md`: loads this repository's rules in Claude Code.
- `templates/slice.md`: the slice template.
- `templates/AGENTS.md`: points Codex to the shared rules and glossary in projects that adopt the workflow.
- `templates/CLAUDE.md`: imports the agent rules and glossary into every Claude Code session.
- `templates/glossary.md`: the glossary template. Each term has a meaning, its names in code and the synonyms to avoid.
