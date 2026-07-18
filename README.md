# Analytics

Historical usage analytics for your whole fleet — spend, tokens, sessions, and time agented, sliceable by day, model, project, and provider.

A [workspacer](https://github.com/DJTouchette/workspacer) hub plugin (webview). It replaces the app's former built-in Analytics pane, reading the same session-history store through the hub bus.

## What it does

- **Stat tiles** — sessions, total spend, tokens in/out, tool calls, and total agented time for the selected window.
- **Daily spend** — bar chart with hover details, 7d / 30d / 90d / all-time ranges.
- **Breakdowns** — top models, projects, and providers by spend, with session and token counts.
- **Recent sessions** — the raw table: agent, project, branch, model, duration, tokens, cost.
- **Provider filter** — everything above sliceable to Claude / Codex / OpenCode / Pi.

Data comes from the `analytics.summary` and `analytics.recent` capabilities (the desktop's SQLite session history). Live in-flight spend is the [Cost HUD](https://github.com/DJTouchette/workspacer-plugin-cost-hud) plugin's job — this one is the historical record.

## Install

Command palette → **Install Plugin…** → `DJTouchette/workspacer-plugin-analytics`

## Permissions

| Capability | Why |
|---|---|
| `analytics.summary` | totals + by-day/model/project/provider buckets |
| `analytics.recent` | the recent-sessions table |

No filesystem access, no events consumed, no network, no sidecar process.
