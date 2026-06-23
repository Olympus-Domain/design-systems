# Olympus Component Inventory

> Auto-generated from codebase analysis on 2026-06-22.
> 167 component files across 10 groups.
>
> **Classification key:**
> - **DS** = Design system candidate — generic, props-driven, no API/store/navigation coupling
> - **DS-ready** = Already generic enough to extract with minimal changes
> - **DS-possible** = Could be extracted if store/API deps are lifted to props
> - **App** = App-specific — tightly coupled to business logic, not extractable

---

## GenericComponents (15 files)

The strongest design system candidates. Most are pure presentational with no external dependencies.

| Component | Props | RN Primitives | External Deps | Classification |
|-----------|-------|---------------|---------------|----------------|
| **Checkbox** | `onPress, checked` | View, TouchableOpacity | — | **DS-ready** |
| **FlexibleArrowButton** | `text, onPress` | View, Text, TouchableOpacity | — | **DS-ready** |
| **FlexibleBackButton** | `styling, onPress, size` | TouchableOpacity | @react-navigation/native | **DS-possible** (nav dep for default behavior) |
| **FlexibleChoiceButton** | `onPress, highlighted, label` | TouchableOpacity, Text | — | **DS-ready** |
| **FlexibleHeader** | `backButton, backButtonOnPress, backButtonStyle, text, headerSpacing` | View, StatusBar, Text, Platform | @react-navigation/core | **DS-possible** (nav dep for back button) |
| **FlexibleLargeButton** | `buttonText, onPress, colorScheme, textColorScheme, disabled` | TouchableOpacity, Text | — | **DS-ready** |
| **FlexibleTextInput** | *(complex — see source)* | TextInput, Text, View, Keyboard, TouchableWithoutFeedback, Platform, TouchableOpacity | — | **DS-ready** |
| **LoadingIcon** | `loading` | View, ActivityIndicator, Modal | — | **DS-ready** |
| **MultipleChoice** | `option, selected, onSelect` | View, Text, TouchableOpacity | — | **DS-ready** |
| **PopUpClose** | `onPress` | TouchableOpacity | — | **DS-ready** |
| **PopUpOpen** | *(complex — renders fire icons with streak logic)* | — | — | **App** (contains streak business logic) |
| **SkeletonLoader** | `width, height, borderRadius` | View, Animated, StyleSheet | — | **DS-ready** |
| **ThreeOptionToggle** | *(complex — see source)* | StyleSheet, Text, TouchableOpacity, View | — | **DS-ready** |
| **TwoOptionToggle** | `selectedOption, setSelectedOption, option1, option2` | StyleSheet, Text, TouchableOpacity, View | — | **DS-ready** |
| **UploadPicOrCameraChooser** | `modalVisible, setModalVisible, handleCamera, handlePhotoLibrary` | Text, View, Modal, TouchableOpacity | — | **DS-ready** |

**Summary:** 12 DS-ready, 2 DS-possible (nav dep only), 1 App (PopUpOpen has business logic baked in).

---

## WorkoutComponents (27 files, including hooks)

Domain-specific workout UI. Most components use `NewWorkoutFlowContext` or `ExerciseContext`, making them app-specific. A few presentational ones are extractable.

| Component | Props | Stores/Contexts | Classification |
|-----------|-------|-----------------|----------------|
| **AdditionalSettings1RM** | *(complex)* | — | **App** (workout domain) |
| **AdditionalSettingsBackdownDropdown** | `numSets` | — | **App** (workout domain) |
| **AdditionalSettingsButton** | *(complex)* | — | **App** (workout domain) |
| **CardioInputContainer** | *(complex)* | — | **App** (workout domain) |
| **EndWorkoutHeader** | *(complex)* | NewWorkoutFlowContext | **App** |
| **ExerciseCard** | *(complex)* | — | **App** (workout domain) |
| **ExerciseCardContainer** | `showArrow, previousPage, openExercise` | NewWorkoutFlowContext | **App** |
| **ExerciseSupersetRest** | `handleAddExercise, handleAddSuperset, handleAddCardio, handleRest` | — | **DS-possible** (generic action buttons) |
| **ExerciseView** | *(complex)* | AutosaveContext, ExerciseContext, NewWorkoutFlowContext | **App** |
| **FinishWorkoutButton** | `onPress, template` | NewWorkoutFlowContext | **App** |
| **HyperlinkInput** | *(complex)* | — | **DS-possible** (text input + URL validation) |
| **NotesIcon** | `toggle, notes, videoLinks` | — | **DS-possible** (badge icon) |
| **NotesModal** | *(complex)* | NewWorkoutFlowContext | **App** |
| **PastExerciseSearchBar** | *(complex)* | NewWorkoutFlowContext | **App** |
| **RestTimer** | *(complex)* | NewWorkoutFlowContext | **App** |
| **RestTimerMini** | `initialTime` | — | **DS-possible** (timer display) |
| **RestTimeSlider** | `restTime, setRestTime` | — | **DS-ready** (generic slider) |
| **RPEInput** | `onCloseDropdown, clicked, onPress, onSelect, selectedValue` | — | **DS-possible** (dropdown selector) |
| **SavedModal** | `text='Workout Saved'` | — | **DS-ready** (success modal) |
| **SetInput** | *(complex)* | — | **App** (workout domain) |
| **SetInputContainer** | *(complex, with hooks)* | — | **App** (workout domain) |
| **TagDropdown** | *(complex)* | — | **DS-possible** (dropdown) |
| **TimePicker** | *(complex)* | — | **DS-possible** (time picker) |
| **VideoPlayer** | `uri, onClose` | — | **DS-possible** (media player) |
| **WorkoutInProgressBar** | *(complex)* | NewWorkoutFlowContext | **App** |
| **WorkoutSummaryToggleArrow** | `text, showArrow, onPress` | — | **DS-ready** (expandable section header) |

**Summary:** 3 DS-ready, 7 DS-possible, 17 App.

---

## NewComponents (35 files, including hooks and SearchBar sub-module)

Mixed bag — contains both reusable UI primitives and app-specific features.

### DS Candidates
| Component | Props | Classification | Notes |
|-----------|-------|----------------|-------|
| **BlockedModal** | `text='User Blocked!'` | **DS-ready** | Simple overlay message modal |
| **BottomOfScreenMenu** | *(complex)* | **App** | Deep API + nav + context deps |
| **CoachOrUserChoiceObject** | `role, setRole` | **DS-ready** | Radio-style selector |
| **ExpandProfilePicModal** | `modalVisible, setModalVisible, onToggleModal, profileUrl, userId` | **DS-possible** | Fullscreen image viewer |
| **NavBar** | `selected, disabled, cancel, template, onPressHome, editMode` | **App** | Deep API + nav + context deps |
| **PrivacySettingsObject** | `privacy, setPrivacy` | **DS-ready** | Toggle options component |
| **ScreenContainer** | *(simple wrapper)* | **DS-ready** | Layout wrapper |
| **ScreenHeader** | `title, actions` | **DS-ready** | Header with optional actions |
| **SettingsButton** | `onPress` | **DS-ready** | Icon button |
| **StoredWorkoutSkeleton** | *(no props)* | **DS-ready** | Skeleton placeholder |
| **ToastNotification** | *(complex, has hooks)* | **DS-possible** | Self-contained toast system, but has its own color palette |
| **UserCardWithPropic** | `user, onPress, allowSelect` | **DS-possible** | Card with avatar — nav dep |

### App-specific
| Component | Stores/Contexts | API Deps | Classification |
|-----------|-----------------|----------|----------------|
| **AdditionalAccountInfoModal** | UserContext | — | **App** |
| **BottomCommentActionModal** | UserContext | SocialRequest | **App** |
| **ChooseWorkoutTargetAthleteModal** | UserContext | APIRequest | **App** |
| **ClaimRewardModal** | UserContext | ReferralRequest | **App** |
| **EditableProfilePic** | UserContext | APIRequest | **App** |
| **FollowFollowingButton** | UserContext | SocialRequest | **App** |
| **NotificationBell** | UserContext | SocialRequest | **App** |
| **NotificationObject** | — (nav dep) | — | **App** (notification domain) |
| **ProfilePictureSmall** | — (nav dep) | — | **DS-possible** (avatar component) |
| **ReferralBadge** | — | ReferralRequest | **App** |
| **ReferralBanner** | — | — | **App** (referral domain) |
| **ReferralInfoModal** | — | — | **App** (referral domain) |
| **ReferralStar** | — | — | **App** (referral domain) |
| **RelatedUserCard** | UserContext | — | **App** |
| **RequestedFollowerList** | UserContext | APIRequest, SocialRequest | **App** |
| **SearchBar** | — | — | **DS-possible** (search input, but wired to user search) |
| **SendWorkoutModal** | UserContext | WorkoutRequest | **App** |
| **ShareReferralModal** | — | — | **App** (referral domain) |
| **StoredWorkout** | — | APIRequest | **App** |
| **WorkoutRequestCard** | UserContext | WorkoutRequest | **App** |

**Summary:** 8 DS-ready, 4 DS-possible, 23 App.

---

## AnalyticsComponents (7 files)

Charting and analytics views — mostly app-specific due to `AnalyticsContext` dependency.

| Component | Props | Stores/Contexts | Classification |
|-----------|-------|-----------------|----------------|
| **AnalyticsChart** | *(complex)* | — | **App** (chart config) |
| **AnalyticsSearchBar** | `handleChooseItemFromDropdown, itemList, defaultText` | — | **DS-possible** (autocomplete search) |
| **ExerciseAnalyticsView** | `userId` | AnalyticsContext | **App** |
| **ExerciseOverTimeChart** | `data, datapointOnPress, selectedInstanceOfExercise` | — | **DS-possible** (chart wrapper) |
| **OneRMCalculator** | *(complex)* | — | **App** (fitness domain) |
| **TimeframeSelector** | `timeframes, selectedTimeframe, handleSelectTimeframe` | — | **DS-ready** (segmented control) |
| **WorkoutAnalyticsView** | `userId` | AnalyticsContext | **App** |

**Summary:** 1 DS-ready, 2 DS-possible, 4 App.

---

## HeatmapComponents (2 files)

| Component | Props | Classification |
|-----------|-------|----------------|
| **Heatmap** | `color, thumbnail, customWidth, customHeight` | **DS-possible** (SVG body map — domain-adjacent but reusable) |
| **Muscles** | *(SVG path data)* | **App** (hardcoded muscle SVG paths) |

---

## OCRComponents (4 files)

Workout card scanning — entirely app-specific.

| Component | Props | Classification |
|-----------|-------|----------------|
| **EditableAthleteInfo** | `athleteInfo, updateAthleteInfo` | **App** |
| **EditableExerciseInfo** | `exercise, updateExercise` | **App** |
| **EditableWorkoutHeaderInfo** | *(complex)* | **App** |
| **OCRQueueItem** | `item, onRetry, onDelete, nextRetryAt` | **App** |

---

## SharingComponents (5 files)

Social sharing — app-specific platform integrations.

| Component | Props | Classification |
|-----------|-------|----------------|
| **ShareModal** | `isVisible, setModalVisible, componentRef, openInstagramShareModal` | **App** |
| **ShareToIMessageButton** | `componentRef` | **App** |
| **ShareToInstagramButton** | `componentRef` | **App** |
| **ShareToInstagramModal** | *(complex)* | **App** |
| **ShareToOtherButton** | `componentRef` | **App** |

---

## SocialComponents (16 files, including VideoScreen sub-module)

Social feed components — heavily coupled to UserContext and social API.

| Component | Props | Stores/Contexts | API Deps | Classification |
|-----------|-------|-----------------|----------|----------------|
| **Bookmark** | `workoutId, subjectUser, workoutName` | UserContext | APIRequest, WorkoutRequest | **App** |
| **BottomOfScreenComments** | *(complex)* | UserContext | APIRequest, SocialRequest | **App** |
| **Comment** | *(complex)* | UserContext | APIRequest, SocialRequest | **App** |
| **CommentsSettingsModal** | *(complex)* | UserContext | SocialRequest | **App** |
| **EmptySocialHeader** | — | — | — | **DS-ready** (empty state) |
| **EmptySocialPost** | — | — | — | **DS-ready** (empty state) |
| **Like** | `reaction` | — | APIRequest | **App** |
| **MentionText** | `text` | — | — | **DS-possible** (rich text renderer) |
| **PlusFollowButton** | `subjectUser, subjectPrivacy` | UserContext | SocialRequest | **App** |
| **PostsFeed** | *(complex)* | UserContext | — | **App** |
| **SocialPost** | `dbPostObject, fromProfile, isLoading, fromProfileSubject` | UserContext | MediaRequest | **App** |
| **SocialPostHeader** | *(complex)* | UserContext | APIRequest, SocialRequest, WorkoutRequest | **App** |
| **SocialPostInteractions** | *(complex)* | UserContext | SocialRequest | **App** |
| **SocialPostLocation** | — | — | — | **DS-ready** (location display) |
| **VideoControls** | — | — | — | **DS-ready** (play/pause overlay) |
| **VideoScreen** | `src, width, height` | — | — | **DS-possible** (video player) |
| **VolumeTimePRsBadges** | `volume, duration, tonnageIncrease, setTimeInSeconds` | — | — | **DS-possible** (stat badges) |

**Summary:** 4 DS-ready, 3 DS-possible, 10 App.

---

## StatsComponents (5 files)

| Component | Props | Stores/Contexts | Classification |
|-----------|-------|-----------------|----------------|
| **CalendarView** | `streaks, month, year, dates, datesToWorkoutId` | StatsContext, UserContext | **App** |
| **EditExerciseNameInformationModal** | `closeModal` | — | **DS-ready** (info modal) |
| **EditExerciseNameModal** | `closeModal, selectedExercises, clearScreen` | UserContext | **App** |
| **ProfileStatsView** | `subjectUser` | StatsContext | **App** |
| **StatsSkeleton** | — | — | **DS-ready** (skeleton placeholder) |

**Summary:** 2 DS-ready, 0 DS-possible, 3 App.

---

## TeamsComponents (27 files, including CreateTeamScreen and TeamHomeScreen sub-modules)

Team management UI — heavily coupled to `TeamsContext` and `UserContext`.

### DS Candidates
| Component | Props | Classification |
|-----------|-------|----------------|
| **GenderToggle** | `selected, onSelect` | **DS-ready** (segmented toggle) |
| **TeamCard** | `name, description, members, volume, img, openModal, team, myTeam, goToTeam, is_public` | **DS-possible** (info card with image) |
| **TeamSwitches** | *(switch toggles)* | **DS-possible** (labeled switches — but untokenized colors) |
| **DiscoverableModal** | `hide` | **DS-ready** (simple info modal) |
| **PrivateModal** | `hide` | **DS-ready** (simple info modal) |
| **ViewAddedMembersModal** | `closeModal, members, removeMember` | **DS-possible** (list modal) |

### App-specific (21 files)
All remaining TeamsComponents use `TeamsContext`, `UserContext`, API calls, or navigation — fully app-specific.

**Summary:** 3 DS-ready, 3 DS-possible, 21 App.

---

## Overall Classification Summary

| Classification | Count | Percentage |
|---------------|-------|------------|
| **DS-ready** | 34 | 20% |
| **DS-possible** | 22 | 13% |
| **App** | 111 | 67% |
| **Total** | 167 | 100% |

### DS-Ready Components (34) — Extract First

These are immediately extractable with no code changes:

**Primitives (inputs/buttons/controls):**
- Checkbox, FlexibleArrowButton, FlexibleChoiceButton, FlexibleLargeButton
- FlexibleTextInput, MultipleChoice, RestTimeSlider
- TwoOptionToggle, ThreeOptionToggle, GenderToggle, TimeframeSelector
- CoachOrUserChoiceObject, PrivacySettingsObject, SettingsButton

**Layout/containers:**
- ScreenContainer, ScreenHeader, FlexibleHeader (if nav dep lifted)

**Feedback/modals:**
- LoadingIcon, SavedModal, BlockedModal, DiscoverableModal, PrivateModal
- EditExerciseNameInformationModal, UploadPicOrCameraChooser, ToastNotification

**Content display:**
- SkeletonLoader, StoredWorkoutSkeleton, StatsSkeleton
- EmptySocialHeader, EmptySocialPost, SocialPostLocation
- VideoControls, WorkoutSummaryToggleArrow

### DS-Possible Components (22) — Extract with Refactoring

These need their store/API/nav dependencies lifted to props:
- FlexibleBackButton, FlexibleHeader (nav), HyperlinkInput, NotesIcon
- RestTimerMini, RPEInput, TagDropdown, TimePicker, VideoPlayer
- ExerciseSupersetRest, AnalyticsSearchBar, ExerciseOverTimeChart
- Heatmap, MentionText, VideoScreen, VolumeTimePRsBadges
- ProfilePictureSmall, UserCardWithPropic, TeamCard, TeamSwitches
- ViewAddedMembersModal, ExpandProfilePicModal, SearchBar
