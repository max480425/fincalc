# UI Coding Standards

## shadcn/ui only

- Every component MUST come from shadcn/ui. Do not hand-roll or add custom components.
- Compose existing shadcn primitives to meet a requirement; do not fork or edit shadcn source to change behaviour.
- Keep changes additive: extend a component via props/wrappers in app code, never by rewriting the shadcn implementation.

## Missing component workflow

If no installed shadcn/ui component fits:

1. Check the local registry first (`src/components/ui`) — it may already be present.
2. If absent, look for a match in the shadcn/ui registry.
3. Install it rather than writing your own:
   - `npx shadcn@latest add <component>`
4. Use the installed component as-is; do not modify it to fit the use case.

Never substitute another UI library, plain HTML elements styled by hand, or a new bespoke component for a missing shadcn component.

## Conventions

- Reuse the project's `cn` class-merging util and existing Tailwind theme tokens (`background`, `foreground`, `muted`, `primary`, `border`, `ring`, etc.) instead of hard-coded colours.
- Variants and `className` are the only knobs for styling; prefer `className` over inline styles or one-off CSS.
- Follow the shadcn file layout and naming: `src/components/ui/<kebab-case>.tsx`, one component per file.
- Match the styling and composition patterns already in `src/components/ui` for new work.
