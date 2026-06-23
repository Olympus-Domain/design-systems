# Olympus Design System

Documentation of the current UI implementation of the Olympus fitness mobile app.
This project captures the emergent design system as it exists today — tokens,
components, patterns, and inconsistencies — for visual documentation purposes.

## Visual Identity

- **Theme:** Dark mode only
- **Primary accent:** Yellow/Gold (`#F5E989`)
- **Background hierarchy:** `#0F0F11` → `#141121` → `#1d1b2a` → `#232329` (darkest to lightest)
- **Text colors:** White for primary, `#8D8D9C` (light grey) for secondary, `#8076AB` (purple-grey) for tertiary
- **Error/destructive:** `#FF6565`
- **Success:** `#54BE98`
- **Typography:** System fonts, Tailwind scale (xs through 3xl)
- **Border radius:** Ranges from `rounded` (4px) to `rounded-full`, with `rounded-lg` and `rounded-xl` most common
- **Shapes:** Pill buttons (`rounded-full`), rounded cards (`rounded-xl`/`rounded-2xl`)

## Color Palette (17 tokens)

| Token | Hex | Role |
|-------|-----|------|
| `midnight-blue` | `#141121` | Primary screen background |
| `navy-bg` | `#1d1b2a` | Secondary background/surfaces |
| `dark-grey` | `#19191C` | Card backgrounds |
| `med-grey` | `#232329` | Elevated surfaces |
| `med-grey-2` | `#282631` | Border dividers |
| `deep-gray` | `#171719` | Unused |
| `black-blue` | `#0F0F11` | Unused |
| `text-box-blue` | `#1C1C24` | Input field borders |
| `light-grey` | `#8D8D9C` | Secondary text |
| `dark-grey-1` | `#717171` | Muted/tertiary text |
| `purple-grey` | `#8076AB` | Accent text, links |
| `light-yellow` | `#F5E989` | Primary accent |
| `yellow` | `#F5E989` | Primary accent (duplicate of light-yellow) |
| `gold` | `#E6C466` | Secondary accent |
| `bright-red` | `#FF6565` | Error/destructive |
| `green` | `#54BE98` | Success |
| `disabled` | `#302D3E` | Disabled state backgrounds |

## Core Components (DS-ready)

These 34 generic components define the app's visual language:

**Buttons:** FlexibleLargeButton (pill, full-width), FlexibleChoiceButton, FlexibleArrowButton (list item with chevron), FlexibleBackButton, SettingsButton (icon)
**Inputs:** FlexibleTextInput, Checkbox, RestTimeSlider, MultipleChoice
**Toggles:** TwoOptionToggle, ThreeOptionToggle, GenderToggle, TimeframeSelector
**Layout:** ScreenContainer, ScreenHeader, FlexibleHeader (with optional back button)
**Feedback:** LoadingIcon (modal spinner), SavedModal, BlockedModal, ToastNotification, SkeletonLoader
**Modals:** UploadPicOrCameraChooser, DiscoverableModal, PrivateModal, EditExerciseNameInformationModal
**Content:** EmptySocialHeader, EmptySocialPost, SocialPostLocation, VideoControls, WorkoutSummaryToggleArrow, StoredWorkoutSkeleton, StatsSkeleton, CoachOrUserChoiceObject, PrivacySettingsObject, PopUpClose

## Screen Patterns

**Form screens** (8 screens): FlexibleHeader → FlexibleTextInput (×N) → FlexibleLargeButton → LoadingIcon
**Browse screens** (6 screens): ScreenContainer → ScreenHeader → [content list] → NavBar
**Detail screens** (4 screens): FlexibleHeader (back) → [content] → NavBar

## Guidelines

See the `guidelines/` folder for detailed audit documents:
- `README.md` — Full current-state overview
- `token-audit.md` — Complete token analysis with inconsistencies
- `component-inventory.md` — All 167 components with props and classification
- `screen-inventory.md` — All 35 screens with dependency maps
