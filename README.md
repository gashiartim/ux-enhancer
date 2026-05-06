# ux-enhancer

Claude Code skill. UX/UI refactor specialist for React components. Applies Steve Krug's *Don't Make Me Think* principles — visual hierarchy, scanning-optimized layout, ruthless copy reduction, unambiguous CTAs.

Framework-agnostic: auto-detects whatever design system your project uses (shadcn/ui, Material UI, Chakra, Mantine, Ant Design, or a custom in-house library) and prefers existing components over reinventing primitives.

## What it does

Triggers when you share a React component and want to:

- Improve usability / reduce cognitive load
- Simplify labels and copy
- Clarify navigation and visual hierarchy
- Fix cluttered layouts, instructional paragraphs, ambiguous buttons
- Add proper loading / empty / error states

## Install

Via the [skills.sh](https://skills.sh) CLI:

```bash
npx skills add gashiartim/ux-enhancer
```

Or clone manually:

```bash
git clone https://github.com/gashiartim/ux-enhancer.git ~/.claude/skills/ux-enhancer
```

Then in Claude Code, the skill auto-triggers on UX-related requests, or invoke explicitly:

```
/ux-enhancer
```

## What's inside

- `SKILL.md` — main skill instructions, decision tree, anti-pattern cheat sheet
- `references/copy-rewrite-patterns.md` — lookup table for verbose UI copy → tightened replacements
- `examples/` — full before/after React refactors (form, empty state)

## License

MIT
