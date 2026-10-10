# Workspace UI · design system

Single **enterprise** palette for Personalized Reachout (Zamp PS-3): **slate neutrals** + **one primary blue**. No secondary green/olive tints.

## Principles

- One accent color (`--primary`) for actions, links, active steps, and positive status.
- Neutrals use a cool slate family only (`--foreground`, `--text-secondary`, `--text-tertiary`, `--line`).
- Warnings and errors use dedicated semantic tokens—not mixed with primary.

## Tokens (`style.css`)

| Token | Role |
|-------|------|
| `--primary` / `--primary-hover` | Buttons, links, active UI, ready/confirmed indicators |
| `--primary-soft` / `--primary-muted` | Selected rows, badges, highlights |
| `--foreground` | Headings and primary text |
| `--text-secondary` / `--text-tertiary` | Labels, meta, captions |
| `--surface` / `--surface-muted` / `--surface-hover` | Cards, sidebar, hovers |
| `--line` / `--line-subtle` | Borders and dividers |
| `--warning-*` | Needs-input banners, edge-case tags |
| `--danger` / `--danger-soft` | Errors, delete affordances |
| `--shadow-sm` / `--shadow-md` / `--shadow-card` | Elevation |

Typography: **Inter**. Control radius: **6px** (`--radius`).
