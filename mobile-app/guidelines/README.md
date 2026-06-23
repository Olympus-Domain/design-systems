# Olympus Design System — Current State

> Last updated: 2026-06-22
>
> This folder documents the current UI implementation of the Olympus mobile app
> as-is, without proposing changes. It serves as the baseline for understanding
> what exists before extracting a formal design system.

---

## What This Is

Olympus is a React Native / Expo fitness app that was built without a prior
design system. Over time, a visual language emerged organically — a dark-themed
palette, a set of reusable generic components, recurring screen layout patterns,
and a Tailwind (NativeWind) token config. This folder captures that emergent
system as it stands today.

## App at a Glance

| Dimension | Count |
|-----------|-------|
| Screens | 35 across 7 groups |
| Components | 167 across 10 groups |
| Tailwind color tokens | 17 (15 active, 2 unused) |
| Untokenized colors in use | ~8 recurring + ~20 one-offs |
| Height tokens | 3 (header, button, input) |
| Spacing tokens | 1 (screenHorizontalPadding) |

## Tech Stack

- **Framework:** React Native + Expo
- **Styling:** NativeWind (Tailwind CSS for React Native) + inline StyleSheet objects
- **Language:** JavaScript (no TypeScript)
- **Navigation:** React Navigation
- **State:** React Context (UserContext, NewWorkoutFlowContext, StatsContext, TeamsContext, and others)
- **Package manager:** npm

## Component Classification

Of the 167 components, a triage based on external dependencies (stores, API
calls, navigation) produces three tiers:

| Tier | Count | Description |
|------|-------|-------------|
| **DS-ready** | 34 (20%) | Generic, props-driven, no API/store/nav coupling. Extractable today. |
| **DS-possible** | 22 (13%) | Could be extracted if store/API/nav dependencies are lifted to props. |
| **App-specific** | 111 (67%) | Tightly coupled to business logic. Not design system material. |

The highest-impact DS-ready components — the ones that define how most screens
look — are:

- `FlexibleHeader` (used in 19 screens)
- `LoadingIcon` (13 screens)
- `FlexibleLargeButton` (13 screens)
- `FlexibleTextInput` (10 screens)
- `ScreenContainer` (7 screens)
- `ScreenHeader` (5 screens)

## Screen Layout Patterns

Three recurring compositions appear across the app:

**Form Screen** (login, signup, account, profile editing):
`FlexibleHeader → FlexibleTextInput (×N) → FlexibleLargeButton → LoadingIcon`

**List/Browse Screen** (workout select, home, new workout/template/program):
`ScreenContainer → ScreenHeader → [content] → NavBar`

**Detail/Summary Screen** (workout detail, single post, profile):
`FlexibleHeader (with back) → [domain content] → NavBar`

## Token Coverage

The Tailwind config provides a color palette and a few sizing tokens. The token
audit found three categories of gaps:

1. **Token bypass** — colors that have tokens but are frequently used as raw hex
   values in style objects (e.g., `#F5E989` has 101 inline uses despite being
   tokenized as `light-yellow`).

2. **Missing tokens** — recurring colors with no token at all (e.g., `#969696`
   appears 38 times with no name).

3. **Inconsistencies** — the same visual intent implemented with different
   values across components (e.g., modal overlays use 6 different semi-transparent
   backgrounds, "dark surface" backgrounds use 9 different hex values).

## Audit Documents

| Document | What it covers |
|----------|----------------|
| [token-audit.md](token-audit.md) | Every design token — declared in Tailwind, hardcoded in components/screens, and isolated inconsistencies traced to source files |
| [component-inventory.md](component-inventory.md) | All 167 components grouped by folder, with props, dependencies, and DS classification |
| [screen-inventory.md](screen-inventory.md) | All 35 screens with component usage, context dependencies, layout patterns, and a most-used-components ranking |
