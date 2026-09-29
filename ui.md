# UI Standards

## Components
- Use shadcn/ui components for all UI. Do not hand-roll or create custom components.
- Composition is fine: assemble layouts from existing shadcn components and Tailwind utilities.
- Import via the `@/components/ui/...` alias.

## Adding a component
1. Check `src/components/ui/` for an existing match.
2. If missing, search the shadcn registry (`npx shadcn@latest add <component>`) and install the closest component — prefer the primitive (e.g. `button` over a custom `IconButton`).
3. Only compose new files when a reusable pattern is needed; keep them thin wrappers around shadcn components.
4. Never edit files in `src/components/ui/` by hand to change styling for one usage site — pass `className` instead.

## Styling
- Tailwind utilities only. No inline `style` objects, CSS modules, or new global CSS.
- Reuse theme tokens (`bg-background`, `text-muted-foreground`, `text-destructive`, etc.); never hardcode colors or spacing values.
- Add new tokens to the shadcn theme in `globals.css`, not inline.

## Conventions
- Server Components by default; add `"use client"` only when state, effects, or event handlers require it.
- Use `cn()` from `@/lib/utils` for conditional classes.
- Client-only shadcn primitives (Dialog, Select, Tabs, etc.) must be rendered inside a client boundary.
- Follow the installed variant/size patterns of neighbouring shadcn components.
