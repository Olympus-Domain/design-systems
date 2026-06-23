# Olympus Screen Inventory

> Auto-generated from codebase analysis on 2026-06-22.
> 35 screen files across 7 groups.
>
> This document maps which components each screen uses, to trace the dependency
> graph and understand which design system components will have the widest impact.

---

## LoginScreens (5 screens)

| Screen | Components Used | Stores/Contexts | API Deps |
|--------|----------------|-----------------|----------|
| **WelcomeScreen** | — | — | — |
| **LoginScreen** | FlexibleHeader, FlexibleLargeButton, FlexibleTextInput, LoadingIcon | — | APIRequest, newAPI |
| **SignupScreen** | Checkbox, FlexibleHeader, FlexibleLargeButton, FlexibleTextInput, LoadingIcon | UserContext | APIRequest |
| **ForgotPassScreen** | FlexibleHeader, FlexibleLargeButton, FlexibleTextInput | — | APIRequest |
| **ConfirmPasswordScreen** | FlexibleHeader, FlexibleLargeButton, FlexibleTextInput, LoadingIcon | UserContext | APIRequest |
| **CheckLoginScreen** | — | AutosaveContext, UserContext | APIRequest, services, newAPI |

**Pattern:** Login flow is built almost entirely from GenericComponents — `FlexibleHeader` + `FlexibleLargeButton` + `FlexibleTextInput` + `LoadingIcon` is the standard form screen template.

---

## ProfileAndAccountScreens (7 screens)

| Screen | Components Used | Stores/Contexts | API Deps |
|--------|----------------|-----------------|----------|
| **ProfileHomeScreen** | BottomOfScreenMenu, ExpandProfilePicModal, FlexibleBackButton, FollowFollowingButton, NavBar, NotificationBell, PostsFeed, ProfilePictureSmall, ProfileStatsView, SettingsButton, StoredWorkout, StoredWorkoutSkeleton, ThreeOptionToggle | UserContext | APIRequest, WorkoutRequest |
| **EditProfileScreen** | EditableProfilePic, FlexibleHeader, FlexibleLargeButton, FlexibleTextInput, LoadingIcon, PrivacySettingsObject | UserContext | APIRequest |
| **CreateProfileScreen** | AdditionalAccountInfoModal, CoachOrUserChoiceObject, EditableProfilePic, FlexibleHeader, FlexibleLargeButton, FlexibleTextInput, LoadingIcon, PrivacySettingsObject | AutosaveContext, UserContext | APIRequest, ReferralRequest, newAPI |
| **AccountScreen** | FlexibleHeader, FlexibleLargeButton, FlexibleTextInput, LoadingIcon | UserContext | APIRequest |
| **ChangePasswordScreen** | FlexibleHeader, FlexibleLargeButton, FlexibleTextInput | UserContext | APIRequest |
| **SettingsScreen** | FlexibleArrowButton, FlexibleHeader, FlexibleLargeButton, LoadingIcon, ProfilePictureSmall | UserContext | — |
| **CommunityGuidelinesScreen** | FlexibleHeader | — | — |
| **SignupScreen** | *(listed under LoginScreens)* | | |

**Pattern:** Form screens reuse the same GenericComponents template. `ProfileHomeScreen` is the most component-heavy screen (13 components).

---

## WorkoutScreens (8 screens + sub-components)

| Screen | Components Used | Stores/Contexts | API Deps |
|--------|----------------|-----------------|----------|
| **WorkoutSelectScreen** | FlexibleArrowButton, NavBar, ScreenContainer, ScreenHeader | UserContext | WorkoutRequest |
| **NewWorkoutScreen** | ChooseWorkoutTargetAthleteModal, FlexibleLargeButton, FlexibleTextInput, NavBar, PopUpOpen, RestTimeSlider, ScreenContainer, ScreenHeader, TwoOptionToggle | AutosaveContext, NewWorkoutFlowContext, UserContext | MediaRequest, APIRequest |
| **NewTemplateScreen** | FlexibleLargeButton, FlexibleTextInput, NavBar, RestTimeSlider, ScreenContainer, ScreenHeader, TwoOptionToggle | NewWorkoutFlowContext | — |
| **NewProgramScreen** | FlexibleLargeButton, FlexibleTextInput, NavBar, ScreenContainer, ScreenHeader | NewProgramFlowContext | — |
| **WorkoutSummaryScreen** | ExerciseCardContainer, ExerciseSupersetRest, ExerciseView, FinishWorkoutButton, LoadingIcon, NavBar, RestTimer, SavedModal, ScreenContainer, WorkoutInProgressBar | AutosaveContext, NewWorkoutFlowContext, UserContext, WorkoutStore | WorkoutRequest |
| **EndWorkoutScreen** | EndWorkoutHeader, FlexibleLargeButton, FlexibleTextInput, LoadingIcon, LocationPicker, NavBar, PopUpClose, PopUpOpen, ScreenContainer | AutosaveContext, NewWorkoutFlowContext, UserContext, WorkoutStore | WorkoutRequest, MediaRequest, SocialRequest |
| **DetailedWorkoutView** | FlexibleHeader, FlexibleLargeButton, MultipleChoice, NavBar, PopUpOpen, SocialPostHeader, VolumeTimePRsBadges | UserContext | WorkoutRequest, MediaRequest |
| **LocationPicker** | — | — | — |
| **LocationSearchModal** | PopUpClose | — | LocationRequest |
| **SocialPostMedia** | — | WorkoutStore | — |

**Pattern:** Workout creation screens use the `ScreenContainer` + `ScreenHeader` + `NavBar` shell. The workout flow context (`NewWorkoutFlowContext`) threads through most of these screens.

---

## SocialScreens (4 screens)

| Screen | Components Used | Stores/Contexts | API Deps |
|--------|----------------|-----------------|----------|
| **HomeScreen** | NavBar, NotificationBell, PostsFeed, ReferralInfoModal, ScreenContainer, ScreenHeader | ReferralContext, UserContext | APIRequest, ReferralRequest |
| **SinglePostScreen** | FlexibleHeader, Heatmap, LoadingIcon, SocialPost | UserContext | — |
| **NotificationScreen** | FlexibleHeader, LoadingIcon, NotificationObject, RequestedFollowerList, WorkoutRequestCard | UserContext | APIRequest, SocialRequest, WorkoutRequest |
| **RelatedUsersScreen** | FlexibleHeader, LoadingIcon, RelatedUserCard, RequestedFollowerList, SearchBar | UserContext | APIRequest |

---

## StatsScreens (4 screens)

| Screen | Components Used | Stores/Contexts | API Deps |
|--------|----------------|-----------------|----------|
| **DayWorkoutsScreen** | FlexibleHeader, NavBar | UserContext | WorkoutStatsRequest |
| **ExercisesStatsScreen** | EditExerciseNameModal, FlexibleHeader, NavBar, PopUpOpen | StatsContext, UserContext | — |
| **StreakStatsScreen** | CalendarView, FlexibleBackButton, FlexibleHeader, NavBar, PopUpOpen | StatsContext | — |
| **VolumeStatsScreen** | FlexibleHeader, NavBar | StatsContext, UserContext | — |

**Pattern:** All stats screens use `FlexibleHeader` + `NavBar`. `StatsContext` provides the data layer.

---

## TeamsScreens (6 screens)

| Screen | Components Used | Stores/Contexts | API Deps |
|--------|----------------|-----------------|----------|
| **TeamHomeScreen** | *(delegates to TeamHomeScreen component)* | — | — |
| **CreateTeamScreen** | *(delegates to CreateTeamScreen component)* | — | — |
| **TeamScreen** | LeaderboardView, LoadingIcon, NavBar, PostsFeed, TeamHeader | TeamsContext | — |
| **TeamMembersScreen** | MembersView, TeamMembersHeader | — | — |
| **TeamSettingsScreen** | DeleteTeamModal, DiscoverableModal, FlexibleTextInput, LeaveTeamModal, LoadingIcon, PrivateModal, TeamEditableProfilePicture, TeamSettingsHeader | TeamsContext, UserContext | APIRequest |
| **AddMembersScreen** | FlexibleHeader, FlexibleLargeButton, LoadingIcon, SearchBar, ViewAddedMembersModal | UserContext | APIRequest |

---

## OCRScreens (3 screens)

| Screen | Components Used | Stores/Contexts | API Deps |
|--------|----------------|-----------------|----------|
| **WorkoutCardSubmissionScreen** | FlexibleHeader, FlexibleLargeButton, LoadingIcon, NavBar, OCRQueueItem, PopUpClose | UserContext, OCRUploadContext | ConfigRequest |
| **EditableOCRResultsScreen** | EditableAthleteInfo, EditableExerciseInfo, EditableWorkoutHeaderInfo, FlexibleHeader, FlexibleLargeButton, LoadingIcon, NavBar | UserContext | WorkoutRequest, APIRequest, OCRRequest |
| **OCRTemplateConfig** | — | — | — |

---

## AnalyticsScreens (1 screen)

| Screen | Components Used | Stores/Contexts | API Deps |
|--------|----------------|-----------------|----------|
| **AnalyticsHomeScreen** | ExerciseAnalyticsView, FlexibleHeader, NavBar, WorkoutAnalyticsView | — | — |

---

## Most-Used Components Across Screens

These components appear in the most screens — they define the app's visual language and are the highest-impact design system candidates.

| Component | # Screens Used In | Group | DS Classification |
|-----------|-------------------|-------|-------------------|
| **FlexibleHeader** | 19 | GenericComponents | DS-possible |
| **NavBar** | 14 | NewComponents | App |
| **LoadingIcon** | 13 | GenericComponents | DS-ready |
| **FlexibleLargeButton** | 13 | GenericComponents | DS-ready |
| **FlexibleTextInput** | 10 | GenericComponents | DS-ready |
| **ScreenContainer** | 7 | NewComponents | DS-ready |
| **ScreenHeader** | 5 | NewComponents | DS-ready |
| **PopUpOpen** | 5 | GenericComponents | App |
| **PopUpClose** | 3 | GenericComponents | DS-ready |
| **FlexibleArrowButton** | 2 | GenericComponents | DS-ready |
| **FlexibleBackButton** | 2 | GenericComponents | DS-possible |
| **SearchBar** | 2 | NewComponents | DS-possible |
| **TwoOptionToggle** | 2 | GenericComponents | DS-ready |
| **RestTimeSlider** | 2 | WorkoutComponents | DS-ready |
| **ProfilePictureSmall** | 2 | NewComponents | DS-possible |

---

## Screen Layout Patterns

Three recurring screen compositions emerge across the app:

### Pattern 1: Form Screen
Used by: LoginScreen, SignupScreen, ForgotPassScreen, ConfirmPasswordScreen, AccountScreen, ChangePasswordScreen, EditProfileScreen, CreateProfileScreen
```
FlexibleHeader
  └─ FlexibleTextInput (×N)
  └─ FlexibleLargeButton
  └─ LoadingIcon
```

### Pattern 2: List/Browse Screen
Used by: WorkoutSelectScreen, ExercisesStatsScreen, HomeScreen, NewWorkoutScreen, NewTemplateScreen, NewProgramScreen
```
ScreenContainer
  └─ ScreenHeader
  └─ [content]
  └─ NavBar
```

### Pattern 3: Detail/Summary Screen
Used by: DetailedWorkoutView, SinglePostScreen, WorkoutSummaryScreen, ProfileHomeScreen
```
FlexibleHeader (with back button)
  └─ [domain content]
  └─ NavBar
```

---

## Dependency Graph: Contexts → Screens

| Context | Screens |
|---------|---------|
| **UserContext** | 22 screens (almost universal) |
| **NewWorkoutFlowContext** | NewWorkoutScreen, WorkoutSummaryScreen, EndWorkoutScreen, NewTemplateScreen |
| **StatsContext** | ExercisesStatsScreen, StreakStatsScreen, VolumeStatsScreen |
| **TeamsContext** | TeamScreen, TeamSettingsScreen |
| **AutosaveContext** | CheckLoginScreen, CreateProfileScreen, NewWorkoutScreen, WorkoutSummaryScreen, EndWorkoutScreen |
| **ReferralContext** | HomeScreen |
| **NewProgramFlowContext** | NewProgramScreen |
| **OCRUploadContext** | WorkoutCardSubmissionScreen |
| **WorkoutStore** | WorkoutSummaryScreen, EndWorkoutScreen, SocialPostMedia |
