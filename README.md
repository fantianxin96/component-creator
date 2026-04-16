# Component Creator Skill

A universal AI skill for building design-system-driven component libraries.
Works with Cursor, Claude Code, Windsurf, and any tool that supports SKILL.md.
Not tied to any specific design system — works with any token set, any framework.

This skill teaches AI coding tools a three-phase workflow: collect design tokens,
build a reusable component CSS library, and generate new components that stay
consistent with your established foundation.

## Available Skills

| Skill | Description |
|-------|-------------|
| [component-creator](./SKILL.md) | Builds `tokens.css` from designer input, creates reusable `components.css` classes, and generates new components that strictly reference the token system. |

## Installation

> **Cursor**
> ```bash
> mkdir -p .cursor/skills/component-creator
> curl -o .cursor/skills/component-creator/SKILL.md \
>   https://raw.githubusercontent.com/fantianxin96/component-creator/main/SKILL.md
> ```

> **Claude Code**
> ```bash
> mkdir -p .claude/skills/component-creator
> curl -o .claude/skills/component-creator/SKILL.md \
>   https://raw.githubusercontent.com/fantianxin96/component-creator/main/SKILL.md
> ```

> **Windsurf**
> ```bash
> mkdir -p .windsurf/rules/component-creator
> curl -o .windsurf/rules/component-creator/SKILL.md \
>   https://raw.githubusercontent.com/fantianxin96/component-creator/main/SKILL.md
> ```

> **Or clone directly into your project**
> ```bash
> git clone https://github.com/fantianxin96/component-creator.git
> ```

## How It Works

The skill follows three phases:

### Phase 1 — Token Foundation
The AI asks you to paste or describe your tokens (colors, typography, spacing,
radius, shadows). It generates a clean `tokens.css` with only CSS custom
properties — the single source of truth for all visual decisions.

### Phase 2 — Component Library
The AI creates `components.css` with reusable CSS classes (buttons, cards,
badges, forms, etc.) that strictly reference tokens. No hardcoded values allowed.

### Phase 3 — Component Generation
When building new UI, the AI reads the token and component files, maps every
visual decision to an existing token or class, and outputs consistent code.
Any new reusable patterns get added back to `components.css`.

## File Structure

| File | Contains | Rules |
|------|----------|-------|
| `tokens.css` | CSS custom properties only | No classes. No component styles. Values only. |
| `components.css` | Reusable CSS component classes | Every value must reference a token. No raw values. |
| Components | Application-specific UI code | Uses classes from `components.css` + tokens from `tokens.css`. |

## What Makes This Different

- **Framework agnostic** — works with React, Vue, Svelte, plain HTML, or anything else
- **Tool agnostic** — works with Cursor, Claude Code, Windsurf, and any SKILL.md-compatible tool
- **Library agnostic** — not tied to any specific design system; bring your own tokens
- **Designer-friendly** — starts from what the designer already has (Figma exports, brand docs, or verbal descriptions)
- **Self-enforcing** — includes a constraint checklist that prevents hardcoded values from slipping through

## Author

Lilith Fan · UX/UI Designer

## License

MIT
