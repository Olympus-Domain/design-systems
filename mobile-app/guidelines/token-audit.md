# Olympus Design System — Token Audit

> Auto-generated from codebase analysis on 2026-06-22.
> Covers `components/` and `screens/` directories.

---

## 1. Currently Tokenized (in `tailwind.config.js`)

### Colors
| Token name       | Value     | Usage count (bg/text/border) |
|------------------|-----------|------------------------------|
| `midnight-blue`  | `#141121` | 101 / 31 / 0 = **132**      |
| `light-yellow`   | `#F5E989` | 29 / 32 / 25 = **86**       |
| `yellow`         | `#F5E989` | 22 / 36 / 11 = **69**       |
| `light-grey`     | `#8D8D9C` | 0 / 79 / 24 = **103**       |
| `navy-bg`        | `#1d1b2a` | 29 / 0 / 0 = **29**         |
| `purple-grey`    | `#8076AB` | 0 / 27 / 7 = **34**         |
| `bright-red`     | `#FF6565` | 2 / 12 / 3 = **17**         |
| `dark-grey`      | `#19191C` | 7 / 5 / 2 = **14**          |
| `text-box-blue`  | `#1C1C24` | 0 / 0 / 11 = **11**         |
| `green`          | `#54BE98` | 1 / 8 / 0 = **9**           |
| `med-grey`       | `#232329` | 5 / 0 / 3 = **8**           |
| `disabled`       | `#302D3E` | 1 / 4 / 3 = **8**           |
| `gold`           | `#E6C466` | 0 / 0 / 1 = **1**           |
| `deep-gray`      | `#171719` | 0 / 0 / 0 = **0** (unused) |
| `med-grey-2`     | `#282631` | 0 / 0 / 4 = **4** (border dividers) |
| `dark-grey-1`    | `#717171` | 0 / 5 / 0 = **5** (muted text on profile) |
| `black-blue`     | `#0F0F11` | 0 / 0 / 0 = **0** (unused) |

### Spacing
| Token name               | Value  | Notes                      |
|--------------------------|--------|----------------------------|
| `screenHorizontalPadding`| `16px` | Screen-level horizontal pad|

### Height
| Token name | Value  | Notes            |
|------------|--------|------------------|
| `header`   | `56px` | Header height    |
| `button`   | `48px` | Button height    |
| `input`    | `40px` | Input height     |

---

## 2. Hardcoded Values That Should Be Tokenized

### 2a. Colors — Used via inline Tailwind `[#hex]` syntax (bypassing tokens)

These colors are used directly with `bg-[#hex]`, `text-[#hex]`, or `border-[#hex]` instead of going through a token. Many are duplicates or near-duplicates of existing tokens.

| Hex value   | Occurrences | Equivalent token?            | Suggested token name  |
|-------------|-------------|------------------------------|-----------------------|
| `#1d1b2a`   | 26 (bg)     | **Yes** — `navy-bg`          | Already exists, use it|
| `#969696`   | 38 (style)  | No                           | `grey-400`            |
| `#8d8d9c`   | 31 (style)  | **Yes** — `light-grey`       | Already exists, use it|
| `#ffffff`   | 20 (style)  | No (Tailwind default `white`)| Use `white`           |
| `#262433`   | 7 (bg)      | No                           | `surface-dark`        |
| `#1a1a2e`   | 2 (bg)      | No                           | `surface-deep`        |
| `#3b3651`   | 6 (border)  | No                           | `border-subtle`       |
| `#1f1b2f`   | 5 (bg)      | No                           | `surface-elevated`    |
| `#d3d3d3`   | 7 (style)   | No                           | `grey-300`            |
| `#54be98`   | 7 (mixed)   | **Yes** — `green`            | Already exists, use it|
| `#8076AB`   | 16 (style)  | **Yes** — `purple-grey`      | Already exists, use it|
| `#F63737`   | 2 (text)    | Near-dupe of `bright-red`    | Consolidate           |
| `#FF6363`   | 3 (style)   | Near-dupe of `bright-red`    | Consolidate           |
| `#4a4466`   | 2 (mixed)   | No                           | `purple-muted`        |
| `#262626`   | 2 (border)  | No                           | `border-dark`         |

### 2b. Colors — Used in StyleSheet/inline style objects

| Hex value   | Occurrences | Notes                                 |
|-------------|-------------|---------------------------------------|
| `#F5E989`   | 101         | Same as `light-yellow`/`yellow` token — heaviest inline usage in the codebase |
| `#969696`   | 38          | Untokenized grey, very frequent       |
| `#1d1b2a`   | 34          | Same as `navy-bg` token               |
| `#8d8d9c`   | 31          | Same as `light-grey` token            |
| `#ffffff`   | 20          | White — should use Tailwind default   |
| `#141121`   | 20          | Same as `midnight-blue` token         |
| `#FF6565`   | 18          | Same as `bright-red` token            |
| `#232329`   | 13          | Same as `med-grey` token              |

### 2c. Typography — Font Sizes

**Tokenized (via Tailwind scale):**
| Class      | Approx value | Occurrences |
|------------|-------------|-------------|
| `text-xs`  | 12px        | 17          |
| `text-sm`  | 14px        | 60          |
| `text-base`| 16px        | 71          |
| `text-lg`  | 18px        | 122         |
| `text-xl`  | 20px        | 48          |
| `text-2xl` | 24px        | 11          |
| `text-3xl` | 30px        | 1           |

**Hardcoded (inline Tailwind or style objects):**
| Value   | Occurrences | Notes                                   |
|---------|-------------|-----------------------------------------|
| `16px`  | 17          | Duplicate of `text-base` — should use it|
| `30px`  | 12          | Duplicate of `text-3xl` — should use it |
| `18px`  | 1 + 6       | Duplicate of `text-lg`                  |
| `12px`  | 1           | Duplicate of `text-xs`                  |
| `50px`  | 1           | Outlier — hero/display text?            |
| `45px`  | 1           | Outlier — hero/display text?            |
| `20px`  | 4           | Duplicate of `text-xl`                  |
| `14px`  | 1           | Duplicate of `text-sm`                  |
| `10px`  | 1           | Below scale — caption/micro?            |
| `17px`  | 1           | Off-scale — normalize to 16 or 18      |

### 2d. Typography — Font Weights

| Value    | Occurrences | Notes                              |
|----------|-------------|------------------------------------|
| `bold`   | 5           | Should use `font-bold` class       |
| `600`    | 1           | Semi-bold — `font-semibold`        |
| `500`    | 1           | Medium — `font-medium`             |
| `normal` | 1           | Default — `font-normal`            |

> No custom `fontFamily` values found — the app uses system fonts throughout.

### 2e. Border Radius

**Tokenized (Tailwind scale):**
| Class         | Occurrences |
|---------------|-------------|
| `rounded-full`| 59          |
| `rounded-lg`  | 42          |
| `rounded-xl`  | 34          |
| `rounded`     | 28          |
| `rounded-2xl` | 19          |
| `rounded-md`  | 13          |
| `rounded-3xl` | 7           |

**Hardcoded (inline or style objects):**
| Value  | Occurrences | Closest token     |
|--------|-------------|-------------------|
| `20`   | 10          | `rounded-xl` (12) or `rounded-2xl` (16) — off-scale |
| `15px` | 9 (tw)      | `rounded-xl` (12) — off-scale     |
| `999`  | 7           | `rounded-full` — should use it    |
| `10`   | 7           | `rounded-lg` (8) — close          |
| `50`   | 5           | `rounded-full` — should use it    |
| `80`   | 2           | `rounded-full` — should use it    |
| `8`    | 4           | `rounded-lg` — should use it      |
| `5`    | 2           | `rounded` (4) — close             |
| `4px`  | 3 (tw)      | `rounded` — should use it         |
| `3px`  | 2 (tw)      | `rounded-sm` (2) — close          |

### 2f. Spacing (padding/margin in style objects)

Most-repeated hardcoded values:
| Value | Property uses     | Occurrences | Notes                    |
|-------|-------------------|-------------|--------------------------|
| `10`  | margin/padding    | ~24         | Most common spacing unit |
| `5`   | margin/padding    | ~8          | Second most common       |
| `20`  | padding           | ~7          | Screen-level spacing     |
| `8`   | padding           | ~6          | Component internal       |
| `0`   | various           | ~9          | Resets                   |
| `16`  | padding           | ~3          | Matches `screenHorizontalPadding` |

### 2g. Opacity

| Value | Occurrences | Suggested token      |
|-------|-------------|----------------------|
| `0.5` | 12 (rgba+opacity) | `overlay-medium` |
| `0.8` | 4           | `overlay-heavy`      |
| `0.7` | 2           | `overlay-medium-heavy`|
| `0.2` | 2           | `overlay-light`      |

### 2h. Shadows

Only 3 components use shadows, all with `shadowColor: '#000'`. Not yet a pattern worth tokenizing — revisit if shadow usage grows.

---

## 3. Isolated Style Inconsistencies

These are values used in isolation that contradict the dominant patterns in the codebase — the kind of drift a design system would prevent.

### 3a. Modal Overlays — 6 Different Backgrounds for the Same Purpose

Every modal needs a semi-transparent overlay. The codebase uses **6 different implementations** for this single pattern:

| Value                          | Files using it                                                     |
|--------------------------------|---------------------------------------------------------------------|
| `bg-black/70`                  | SavedModal, NotesModal, BlockedModal, ExpandProfilePicModal, EditExerciseNameModal, EditExerciseNameInformationModal, SelectLeaderboardExerciseModal, AddLeaderboardExerciseModal, MyInvitesModal, ViewAddedMembersModal (10) |
| `rgba(0,0,0,0.5)`             | JoinTeamWithCodeModal, DiscoverableModal, PrivateModal, LeaveTeamModal, DeleteTeamModal, TeamInfoModal (6) |
| `rgba(0, 0, 0, 0.7)`          | ShareReferralModal (1)                                              |
| `rgba(0, 0, 0, 0.6)`          | AdditionalAccountInfoModal (1)                                      |
| `rgba(20,18,32,0.9)`          | ClaimRewardModal, ReferralInfoModal (2)                              |
| `rgba(7,7,25,0.8)`            | WorkoutCardSubmissionScreen (1)                                      |

**Verdict:** One token needed — e.g. `overlay-backdrop`. The `bg-black/70` pattern has the most usage and would be the natural standard.

### 3b. Placeholder Text Color — 4 Different Values

| Value     | Files                                                              | Count |
|-----------|--------------------------------------------------------------------|-------|
| `#8D8D9C` | FlexibleTextInput, AnalyticsSearchBar, SelectLeaderboardExerciseModal, PastExerciseSearchBar, ExercisesStatsScreen, VolumeStatsScreen | 6 |
| `#F5E989` | SetInput (×2), CardioInputContainer (×3)                           | 5     |
| `#8076AB` | HyperlinkInput, NotesModal, LocationSearchModal                    | 3     |
| `#999999` | BottomOfScreenComments                                             | 1     |
| `#6e7191` | SearchBar                                                          | 1     |

**Verdict:** `#8D8D9C` (`light-grey`) is the dominant pattern for search/text inputs. `#F5E989` is used specifically for workout numeric inputs (intentional contrast). `#8076AB` (`purple-grey`) for notes/links may be intentional. But `#999999` and `#6e7191` are one-offs that should align with `#8D8D9C`.

### 3c. Profile Picture Border Radius — Inconsistent "Circle" Implementation

Three components render circular profile pictures using **three different radius values**:

| Component                  | Small style | Medium style | Large style |
|----------------------------|-------------|-------------|-------------|
| `EditableProfilePic`       | `50`        | `50`        | `80`        |
| `TeamEditableProfilePicture` | `50`     | `50`        | `80`        |
| `ProfilePictureSmall`      | `999`       | `50`        | `999` (×5)  |

**Verdict:** `borderRadius: 999` and `borderRadius: 50` and `borderRadius: 80` all mean "circle" — should all use `rounded-full` or a single `avatar-radius` token. The varying values only work because the image happens to be small enough — they'll break at different sizes.

### 3d. Streak Fire Colors — Hardcoded Color Ramp, Duplicated Across 2 Files

The streak fire icon uses a 5-level color ramp, copy-pasted identically into `ShareToInstagramModal` and `SocialPostHeader`:

| Streak level | Color     | Semantic meaning |
|-------------|-----------|------------------|
| ≤1          | `#3B7FDF` | Blue (low)       |
| 2           | `#3EE37C` | Green            |
| 3           | `#CEDA71` | Yellow-green     |
| 4           | `#D79029` | Orange           |
| ≥5          | `#FA3C05` | Red (hot)        |

**Verdict:** This is a semantic color ramp with no token representation and duplicated logic. Should be a `streakColors` map or token set, consumed from one place.

### 3e. Toast Notification Colors — Isolated Color System

`ToastNotification.js` defines its own private color palette that exists nowhere else:

| Key       | Value     | Nearest token          |
|-----------|-----------|------------------------|
| `error`   | `#CC3333` | `bright-red` (`#FF6565`) — different red |
| `alert`   | `#E6B800` | `gold` (`#E6C466`) — different gold      |
| `success` | `#4D8C2E` | `green` (`#54BE98`) — different green     |
| `info`    | `#2E7FCC` | No token                                  |
| bg        | `#1e1a32` | Near `navy-bg` (`#1d1b2a`) — different   |

**Verdict:** The toast component reinvented the color palette rather than using existing tokens. Every color is a near-miss of an existing token — close enough to look intentional but different enough to create visual inconsistency.

### 3f. Surface/Background Colors — "Dark Background" Has ~8 Variants

Components that need a dark background each picked their own shade:

| Value     | File                            | Semantic role        |
|-----------|---------------------------------|----------------------|
| `#1D1A2B` | BottomCommentActionModal        | Modal body           |
| `#1e1a32` | ToastNotification               | Toast background     |
| `#211c3b` | ShareToInstagramModal           | Modal body           |
| `#1a1a1a` | VideoPlayer                     | Video container      |
| `#2c2c2e` | SkeletonLoader                  | Skeleton placeholder |
| `#1d1b2a` | (token: `navy-bg`)              | Screen background    |
| `#141121` | (token: `midnight-blue`)        | Screen background    |
| `#19191C` | (token: `dark-grey`)            | Card background      |
| `#1f1b2f` | Multiple screens                | Section background   |

**Verdict:** These are all doing the same job — "container darker than the screen" — with 9 different hex values. A design system would have 2-3 surface levels: `surface-primary`, `surface-elevated`, `surface-sunken`.

### 3g. Switch Track Colors — Consistent but Untokenized

All `Switch` components use the same pattern — but none through tokens:

```
trackColor={{ false: '#767577', true: '#F5E989' }}
ios_backgroundColor="#3e3e3e"
```

Used in: `TeamSwitches` (×2), `TeamSettingsScreen` (×2). Consistent, but `#767577` and `#3e3e3e` have no tokens and don't match any existing token.

### 3h. Icon Tint Color — Inconsistent Greys

| Value     | File                   | Usage                   |
|-----------|------------------------|-------------------------|
| `#D9D9D9` | FlexibleArrowButton    | Chevron icon            |
| `#D9D9D9` | ExerciseCard           | Drag handle icon        |
| `#5e5e5e` | ReferralStar           | Disabled/loading icon   |
| `#5e5e5e` | Muscles (heatmap)      | Inactive muscle SVG     |

**Verdict:** `#D9D9D9` is used for "decorative/secondary" icons, `#5e5e5e` for "inactive/disabled" icons — both are valid semantic roles but neither has a token.

### 3i. Off-Scale Typography

| Value         | File                       | Context                      | Should be         |
|---------------|----------------------------|------------------------------|--------------------|
| `fontSize: 50`| RestTimer.js               | Timer countdown display      | Custom `display-xl` token |
| `fontSize: 45`| RestTimer.js               | Timer countdown (smaller)    | Custom `display-lg` token |
| `fontSize: 10`| EndWorkoutScreen.js        | Micro label in workout summary| `text-xs` (12) or custom `text-micro` |
| `fontSize: 17`| BottomCommentActionModal.js| **Commented out** — dead code| Remove             |

### 3j. Off-Scale Spacing

| Value           | File                                   | Context                           |
|-----------------|----------------------------------------|-----------------------------------|
| `padding: 35`   | BottomCommentActionModal               | Modal body padding — non-standard |
| `paddingLeft: 34`| AdditionalSettingsBackdownDropdown     | Pixel-nudge alignment             |
| `paddingBottom: 100` | ExerciseAnalyticsView             | Scroll overrun — not a design token |
| `paddingBottom: 50`  | WorkoutAnalyticsView              | Scroll overrun — different value  |
| `paddingTop: 30` | ToastNotification                     | Status bar clearance              |
| `marginLeft: 55` | ReferralInfoModal                     | Manual horizontal centering hack  |

### 3k. `borderWidth: 120` — RestTimer.js

Used to create a thick circular border as a visual ring around the rest timer. This is a layout/visual trick, not a border token — but it's the kind of magic number that should be extracted into the component's own constant with a name.

---

## 4. Key Findings

### What works
- **Color palette** is defined and heavily used (586 total tokenized color class usages).
- **Typography scale** via Tailwind is dominant (330 uses of `text-*` classes).
- **Border radius** scale is mostly followed (202 tokenized vs ~45 hardcoded).
- **Component heights** (header/button/input) are defined.

### Token gaps (patterns that repeat but have no token)

1. **Token bypass is the #1 issue.** The same colors that ARE tokenized are frequently used as raw hex values — especially `#F5E989` (101 inline uses), `#1d1b2a` (60 inline uses), `#8d8d9c` (34 inline uses). A theme change wouldn't propagate to these.

2. **~8 colors in active use have no token at all.** `#969696` (38 uses) is the worst offender. `#262433`, `#3b3651`, `#1f1b2f` are background/surface variants without tokens.

3. **Near-duplicate reds.** `#FF6565`, `#FF6363`, `#F63737`, `#FF6666`, `#FF3B30`, `#CC3333`, `#e70300` — seven shades of red used where one or two tokens would suffice.

4. **`yellow` and `light-yellow` are the same value** (`#F5E989`). One should be removed or differentiated.

5. **2 tokens are truly unused**: `deep-gray` and `black-blue` — safe to remove. `med-grey-2` (4 uses as border dividers) and `dark-grey-1` (5 uses as muted text) are low-usage but active.

6. **No semantic naming.** Current tokens are named by appearance (`light-grey`, `midnight-blue`) not by role (`text-secondary`, `surface-primary`). This makes theming impossible without renaming everything.

7. **Font sizes** are mostly on the Tailwind scale, but 31 inline uses bypass it — usually with values that already have a Tailwind equivalent.

8. **Border radius** has 15px and 20px as recurring hardcoded values that sit between the Tailwind scale stops — suggests a custom scale stop is needed.

### Inconsistencies (isolated values that break the pattern)

9. **Modal overlays** use 6 different semi-transparent backgrounds for the same purpose. One token needed.

10. **Placeholder text colors** vary across 5 values — 2 are one-offs that should align with the dominant `#8D8D9C`.

11. **Profile picture "circle" radius** uses 3 different values (`50`, `80`, `999`) that all mean the same thing — `rounded-full`.

12. **Streak fire colors** are a semantic 5-level ramp hardcoded and copy-pasted into 2 files with no token or shared source.

13. **Toast notification** invented its own parallel color system — each color is a near-miss of an existing token (`#CC3333` vs `bright-red`, `#4D8C2E` vs `green`), creating subtle visual inconsistency.

14. **Dark backgrounds** use ~9 different hex values for "container darker than screen" — needs 2-3 surface-level tokens.

15. **Switch track colors** are consistent (`#767577`/`#3e3e3e`) but exist outside the token system entirely.

16. **Icon tint greys** (`#D9D9D9`, `#5e5e5e`) serve clear semantic roles (decorative vs inactive) but have no tokens.

---

## 4. Recommended Token Categories for Design System

| Category         | Current state               | Action needed                          |
|------------------|-----------------------------|----------------------------------------|
| **Colors**       | 17 tokens, ~8 missing       | Add missing, add semantic aliases      |
| **Typography**   | Using Tailwind defaults      | Define explicit scale + weights         |
| **Spacing**      | 1 token (`screenHorizontalPadding`) | Define 4px-based scale          |
| **Border Radius**| Using Tailwind defaults      | Add custom stops for 15px, 20px        |
| **Heights**      | 3 tokens                    | Good — extend as needed                |
| **Shadows**      | None                         | Low priority — only 3 uses             |
| **Opacity**      | None                         | Define overlay scale                   |
