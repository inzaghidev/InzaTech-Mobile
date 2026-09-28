# AGENTS.md --- InzaTech Mobile

## 1. Project Identity

-   **Project:** InzaTech Mobile
-   **Product:** InzaTech Poshaf / InzaTech
-   **Platform:** Android first, Flutter
-   **Language:** Dart
-   **UI:** Flutter + Material 3
-   **Primary goal:** A modular mobile companion to the InzaTech web
    platform.
-   **Repository:** `https://github.com/inzaghidev/InzaTech-Mobile`

InzaTech Mobile combines: - Utilities / Tools - AI Apps - Portals -
Widgets - Blogs - Core pages such as Profile, About, Services, Contact,
and Social Media

The mobile app should evolve incrementally. Do not attempt to implement
the entire product in one pass.

------------------------------------------------------------------------

## 2. Product Navigation

The primary bottom navigation contains exactly five destinations:

1.  **Home**
2.  **Tools**
3.  **Explore**
4.  **Blogs**
5.  **Profile**

`Explore` combines: - Portals - Widgets

`Tools` contains: - Utilities - Calculators - Converters - Developer
Tools - AI Apps

AI Apps may have dedicated detail/list routes, but should remain
accessible from Tools rather than becoming a sixth bottom-navigation
item.

------------------------------------------------------------------------

## 3. Development Strategy

Build the product in small, independently testable increments.

Recommended implementation order:

1.  Project setup
2.  Design system
3.  App shell and bottom navigation
4.  Home
5.  Tools / Utilities
6.  AI Apps UI with local mock data
7.  Explore → Portals
8.  Explore → Widgets
9.  Blogs UI with local mock data
10. Profile and core pages
11. Local persistence / favorites / history where needed
12. API integrations
13. Authentication, if required
14. Release preparation

A screen is considered complete only when: - It compiles. - It works on
an Android emulator/device. - Empty, loading, and error states are
considered where relevant. - It follows `DESIGN_SYSTEM.md`. - It does
not introduce unnecessary dependencies. - Existing screens remain
functional.

------------------------------------------------------------------------

## 4. API Policy for Early Development

### Phase 1: No external API

Do **not** integrate Gemini, Notion, Blogger, weather, finance, or other
external APIs during the initial UI-building phase.

Use: - local Dart model classes; - immutable/static mock data; - local
lists; - fake repository implementations; - local state.

This keeps early development deterministic, fast, and independent
from: - API keys; - quotas; - network failures; - authentication; - rate
limits; - third-party service changes.

### API-ready design

Even without APIs, keep a clean boundary:

``` text
View
  ↓
ViewModel
  ↓
Repository
  ↓
Local Mock Data
```

Later:

``` text
View
  ↓
ViewModel
  ↓
Repository
  ↓
Remote Service
  ↓
Gemini / Notion / Blogger / Other APIs
```

Do not put API calls directly inside widgets.

------------------------------------------------------------------------

## 5. Anti-Vibe-Coding Rules

Avoid generic AI-generated visual patterns:
- random gradients;
- excessive purple/blue neon;
- glowing borders everywhere;
- excessive glassmorphism;
- excessive rounded cards;
- huge meaningless hero sections;
- random icons;
- inconsistent card/button styles;
- inconsistent spacing/font sizes;
- excessive shadows/animation;
- dashboard cards where a simple content layout is more appropriate.

Visual effects must have a product or hierarchy purpose.

------------------------------------------------------------------------

## 6. Architecture Rules

Use a practical feature-first structure inspired by Flutter's
recommended separation of concerns.

Preferred conceptual layers:

``` text
Presentation
  Views
  ViewModels

Data
  Repositories
  Services
  Models
```

For simple features, do not create unnecessary domain/use-case layers.

Recommended feature structure:

``` text
features/
  home/
    presentation/
    data/

  tools/
    presentation/
    data/

  ai_apps/
    presentation/
    data/

  explore/
    presentation/
    data/

  blogs/
    presentation/
    data/

  profile/
    presentation/
    data/
```

Shared UI belongs under:

``` text
core/
  theme/
  widgets/
  routing/
  constants/
  utils/
```

------------------------------------------------------------------------

## 7. Coding Rules

### Dart / Flutter

-   Prefer clear, readable Dart over clever abstractions.
-   Use `const` wherever practical.
-   Keep widgets small and composable.
-   Avoid giant `build()` methods.
-   Do not place business/data logic in UI widgets.
-   Use descriptive names.
-   Keep files focused on one responsibility.
-   Prefer reusable components for repeated cards, buttons, section
    headers, and list items.

### State

Use a consistent state-management approach throughout the project.

For a growing application, Riverpod is acceptable as the project
state-management layer. If the project has not adopted it yet, do not
add it solely for a trivial static screen.

### Navigation

Keep navigation centralized and predictable.

Do not duplicate route definitions across many widgets.

------------------------------------------------------------------------

## 8. UI Rules

The UI must follow `DESIGN_SYSTEM.md`.

Core principles: - Mobile-first. - Material 3 compatible. - Clean SaaS
aesthetic. - Spacious layout. - Rounded cards. - Subtle
elevation/shadows. - Strong visual hierarchy. - Accessible touch
targets. - Consistent iconography. - Avoid excessive decoration. - Avoid
crowded bottom navigation. - Avoid unnecessary gradients.

Use the existing InzaTech visual direction rather than inventing a new
visual language for every screen.

------------------------------------------------------------------------

## 9. Mock Data Rules

Mock data should look realistic but must be clearly separated from
production data.

Example:

``` text
features/tools/data/mock_tools.dart
features/portals/data/mock_portals.dart
features/blogs/data/mock_blog_posts.dart
```

Mock repositories should expose the same conceptual interface that a
future remote repository can implement.

------------------------------------------------------------------------

## 10. API / Secret Security

Never commit: - API keys - OAuth secrets - Notion integration secrets -
Gemini API keys - Blogger credentials - Supabase service-role keys -
Firebase private credentials - signing keys - passwords - production
`.env` files

A public Flutter APK cannot be treated as a secure place for server-side
secrets.

If an API requires a secret, prefer:

``` text
Flutter
  ↓
InzaTech Backend
  ↓
Third-party API
```

------------------------------------------------------------------------

## 11. Git Rules

Use small, meaningful commits.

Examples:

``` text
feat: add home screen
feat: add tools categories
feat: add portals explore screen
feat: add widgets screen
feat: add mock AI apps
fix: correct bottom navigation state
refactor: extract reusable tool card
docs: update implementation plan
```

Do not mix unrelated features in one commit.

------------------------------------------------------------------------

## 12. Testing Expectations

Before marking a feature complete:

``` bash
flutter analyze
flutter test
flutter run
```

For release builds:

``` bash
flutter build apk
```

Test at minimum: - Android emulator - one physical Android device when
available - light/dark theme if supported - small and large phone
layouts - long text - empty states - navigation back behavior

------------------------------------------------------------------------

## 13. Definition of Done

A feature is complete when:

-   [ ] UI matches the design direction.
-   [ ] Navigation works.
-   [ ] Local/mock data works.
-   [ ] No secrets are present.
-   [ ] `flutter analyze` passes.
-   [ ] Relevant tests pass.
-   [ ] No obvious overflow/layout errors.
-   [ ] Documentation is updated if architecture changed.
-   [ ] The feature does not unnecessarily depend on external APIs.

------------------------------------------------------------------------

## 14. Important Principle

**Do not build the whole InzaTech Mobile application at once.**

Prioritize a working UI foundation and add functionality incrementally.

The initial objective is:

> Build a polished, navigable, API-independent InzaTech Mobile prototype
> first.

External APIs should be introduced only after the corresponding UI and
repository boundaries are stable.
