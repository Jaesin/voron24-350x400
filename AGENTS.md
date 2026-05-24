# Voron 2.4 Gantry Project — GitHub Tracking Approach

## Overview

This project uses **GitHub's free tools** (Issues, Projects, Milestones, Labels) for managing the Voron 2.4 gantry assembly. All GitHub interactions must go through the **GitHub MCP** (`@github` tools) rather than manual API calls or CLI.

## Tools

| Tool | Purpose |
|------|---------|
| **GitHub Issues** | Individual tasks — one issue per concrete action |
| **GitHub Projects** | Kanban board with columns: To Do → In Progress → Done |
| **Milestones** | Group issues for major phases (e.g., "Gantry Complete") |
| **Labels** | Categorize tasks for filtering and assignment |
| **GitHub MCP** | All GitHub operations (create/update issues, manage project boards, query status) |

## Dashboard

Live at **https://voron24.mulenex.org/** — static React dashboard deployed via GitHub Pages from `docs/index.html`. Updates on every push to `main`. Background image sourced from `https://vorondesign.com/images/voron2.4.jpg`.

Project board: **https://github.com/users/Jaesin/projects/2**

## Task Workflow

1. **Create an issue** for each task with a clear title and description (see template below)
2. **Add labels** for area, type, and priority
3. **Add to Project board** in the "To Do" column
4. **Assign** to yourself or your son
5. **Move to "In Progress"** when actively working
6. **Close the issue** and move to "Done" when complete
7. **Reference the issue** in git commit messages (`#issue_number`)

## Issue Template

Every issue should include:

```
**Description**: What needs to be done
**Estimated Time**: e.g., 45min, 2h
**Prerequisites**: #issue_number (if any)
**STL Files**: path/to/file.stl (if applicable)
**Hardware Required**: Screws, rails, bearings, etc.
**Acceptance Criteria**: How to verify it's done
**Manual Reference**: Assembly manual section/page
```

## Label Conventions

| Label | Usage |
|-------|-------|
| `area: gantry` | Gantry-specific tasks |
| `area: frame` | Frame-related tasks |
| `area: electronics` | Wiring, controllers, firmware |
| `area: skirts` | Skirts and enclosure |
| `area: panels` | Panel mounting, doors |
| `type: print` | 3D printing task |
| `type: assembly` | Physical assembly task |
| `type: wiring` | Electrical/wiring task |
| `type: config` | Firmware config or tuning |
| `priority: high` | Blocking other work |
| `priority: medium` | Normal priority |
| `priority: low` | Nice-to-have or optional |
| `good first issue` | Tasks suitable for onboarding your son |

## Milestones

Track progress toward major completion points:
- **Gantry Complete** — all gantry components printed, assembled, and installed
- **Electronics & Wiring** — controllers mounted, wired, configured
- **Panels & Enclosure** — panels cut, mounted, doors installed
- **First Print** — printer operational, calibrated, producing prints

## GitHub MCP Usage

All GitHub operations must use the `@github` MCP tools:

- `@github issues create` — create a new issue
- `@github issues update` — change title, body, labels, assignees
- `@github issues list` — query open issues with filters
- `@github projects items create` — add issue to project board
- `@github projects items update` — move card between columns
- `@github projects items list` — view board state

Do **not** use `gh` CLI directly or GitHub REST API calls — always use the MCP tools so state is tracked in the conversation context.
