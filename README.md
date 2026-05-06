# ux-enhancer

Claude Code skill. UX/UI refactor specialist for React components. Applies Steve Krug's *Don't Make Me Think* principles — visual hierarchy, scanning-optimized layout, ruthless copy reduction, unambiguous CTAs.

Originally built for [Reliva](https://reliva.app) (a dental practice SaaS), but the core UX rules apply to any task-driven web app. The Design System section is Reliva-specific — adapt it to your own component library.

## What it does

Triggers when you share a React component and want to:

- Improve usability / reduce cognitive load
- Simplify labels and copy
- Clarify navigation and visual hierarchy
- Fix cluttered layouts, instructional paragraphs, ambiguous buttons
- Add proper loading / empty / error states

## Install

```bash
git clone https://github.com/gashiartim/ux-enhancer-skill.git ~/.claude/skills/ux-enhancer
```

Then in Claude Code, the skill auto-triggers on UX-related requests, or invoke explicitly:

```
/ux-enhancer
```

## Customize

Edit `SKILL.md` and replace the **Reliva Design System** section with your own DS components (e.g. shadcn/ui, Material, your custom library). The principles above that section are framework-agnostic.

## License

MIT
