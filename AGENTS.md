# Notes for agents working in `.docs`

Read this before writing or implementing a slice.

## How the user works

- The user plans features as a spec plus short slices. A slice says which files change and what changes in each. Nothing more.
- After a slice is implemented, the user reviews the code and fixes or rewrites what's wrong themselves. Simple, readable code matters more than a complete plan.
- The user wants short, plain answers.

## Writing slices

- Use `.docs/templates/slice.md`. Keep the sections it has. Don't add Acceptance, Impact, Estimate or "From the spec" sections.
- Decide every technical detail yourself from the existing code and its patterns. Record each decision with a one-line reason in the slice's **Decisions** section.
- Treat the **Decisions** section as settled. Don't re-decide, re-ask or rewrite those choices unless the user asks.
- The **Questions** section is only for product or business behavior the code can't answer: what the user sees, what the app should do. One sentence each, plain words, no jargon. Never ask what the codebase already answers.
- Use the terms from `.docs/glossary.md`. A new domain word goes there first.
- Name things after what they do. A method name is a verb that says what happens, not just a direction or a generic word. Do not use Info, Manager or similar words because they have wide responsibility and don't tell what functionality does.

## Implementing slices

- Implement only what the slice describes. Then set `status: implemented` in its frontmatter.
- If the code ends up different from the slice, update the slice's **Changes** and **Decisions** so the doc matches the code.
- Name code with the terms from `.docs/glossary.md`. If code and glossary disagree, rename the code or update the glossary in the same change.
- Read the files you touch first and follow their style. Project conventions are listed in each feature's `slices/README.md`.
- Run the project's lint and test commands before reporting.

## Repository rules

Replace this section with the rules of the project you copy this file into (dependency installation, build commands, temp files, deletion, platform constraints).
