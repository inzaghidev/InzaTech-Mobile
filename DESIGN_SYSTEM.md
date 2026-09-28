# InzaTech Mobile --- Design System

## 1. Design Direction

**Product:** InzaTech Mobile

**Style:** - Modern SaaS - Technology-focused - Clean - Professional -
Minimal - Friendly - Spacious - Premium but not excessive

The visual language should feel like a real technology platform rather
than a generic utility app.

Reference direction: - The provided InzaTech Mobile concept screens -
InzaTech Web - Modern SaaS dashboards - Material 3

------------------------------------------------------------------------

# 2. Design Principles

## 2.1 Clarity

Users should immediately understand: - where they are; - what a tool
does; - what action is available; - what content belongs to each
category.

## 2.2 Consistency

The same component should look and behave consistently throughout the
application.

## 2.3 Progressive Disclosure

Do not expose every tool and feature simultaneously.

Use: - categories; - sections; - search; - "See all"; - segmented
controls; - detail pages.

## 2.4 Spaciousness

Avoid dense layouts.

Use sufficient: - padding; - card spacing; - section spacing; - line
height.

## 2.5 Functional Beauty

Visual elements should support usability.

Avoid: - excessive gradients; - unnecessary glassmorphism; - excessive
animations; - decorative elements that compete with content.

------------------------------------------------------------------------

# 3. Navigation

Use exactly five bottom navigation destinations:

``` text
Home
Tools
Explore
Blogs
Profile
```

Recommended icons:

``` text
Home    → home
Tools   → build / construction
Explore → explore / grid_view
Blogs   → article
Profile → person
```

Do not add a separate bottom-navigation item for AI Apps, Portals, or
Widgets.

------------------------------------------------------------------------

# 4. Explore Navigation

Explore combines:

``` text
Portals
Widgets
```

Use:

``` text
┌───────────────┬───────────────┐
│    Portals    │    Widgets    │
└───────────────┴───────────────┘
```

The segmented control should be compact and clearly indicate the active
section.

------------------------------------------------------------------------

# 5. Color System

Use semantic color tokens instead of hard-coding colors throughout
widgets.

## Brand

``` text
Primary
Primary Container
Secondary
Secondary Container
Tertiary
Tertiary Container
```

The visual direction should use an **Indigo / Cyan technology accent**.

Suggested starting values:

``` text
Primary Indigo:       #4F46E5
Secondary Cyan:       #06B6D4
Background Light:     #F8FAFC
Surface Light:        #FFFFFF
Text Primary:         #111827
Text Secondary:       #64748B
Border:               #E2E8F0
Success:              #16A34A
Warning:              #F59E0B
Error:                #DC2626
```

These are starting tokens, not immutable requirements. Centralize them
in the Flutter theme so the palette can be changed globally.

------------------------------------------------------------------------

# 6. Dark Theme

Dark mode should be supported by semantic theme tokens.

Suggested starting values:

``` text
Background Dark:      #0F172A
Surface Dark:         #111827
Elevated Surface:     #1E293B
Text Primary Dark:    #F8FAFC
Text Secondary Dark:  #CBD5E1
Border Dark:          #334155
```

Do not simply invert the light theme.

------------------------------------------------------------------------

# 7. Typography

Preferred fonts:

1.  Inter
2.  Plus Jakarta Sans

Use a clear hierarchy.

``` text
Display
Headline
Title
Body
Label
```

Recommended approximate hierarchy:

``` text
Screen Title:       24–28 px
Section Title:      17–20 px
Card Title:         14–16 px
Body:               13–15 px
Caption:            11–12 px
```

Actual Flutter text styles should be centralized in
`ThemeData.textTheme`.

------------------------------------------------------------------------

# 8. Spacing

Use a consistent spacing scale.

``` text
4   xs
8   sm
12  md-small
16  md
20  lg-small
24  lg
32  xl
40  xxl
```

Prefer multiples of 4.

Common screen padding:

``` text
16 px
```

Large section spacing:

``` text
24–32 px
```

------------------------------------------------------------------------

# 9. Corner Radius

Use moderately rounded surfaces.

``` text
Small controls:      8 px
Buttons:             10–12 px
Cards:               14–18 px
Large containers:    20–24 px
Bottom sheets:       24+ px
```

Avoid extremely rounded cards that make the UI look childish.

------------------------------------------------------------------------

# 10. Elevation and Shadows

Prefer subtle elevation.

Cards should generally use: - light border; - very subtle shadow; - or
tonal surface elevation.

Avoid strong floating shadows.

The UI should feel lightweight.

------------------------------------------------------------------------

# 11. Buttons

Primary button:

``` text
Filled
```

Secondary action:

``` text
Outlined
```

Low-priority action:

``` text
Text button
```

Icon-only buttons should have tooltips where appropriate on larger
platforms and accessible semantics on mobile.

------------------------------------------------------------------------

# 12. Cards

Use cards for: - tools; - AI apps; - portals; - widgets; - blog
articles; - profile settings.

Recommended card anatomy:

``` text
┌──────────────────────────────┐
│ Icon     Category / Label    │
│                              │
│ Title                        │
│ Short description            │
│                              │
│ Optional action / metadata   │
└──────────────────────────────┘
```

Cards should not contain too much text.

------------------------------------------------------------------------

# 13. Tool Cards

Tool cards should prioritize:

``` text
Icon
Tool name
Short description
Category/status
```

Example:

``` text
┌──────────────────────┐
│  ◇  JSON Formatter   │
│     Format JSON      │
└──────────────────────┘
```

Use a grid for compact tools and list cards for tools requiring
descriptions.

------------------------------------------------------------------------

# 14. Home Screen

Recommended order:

``` text
Header
↓
Search
↓
At a Glance
↓
AI Apps
↓
Quick Utilities
↓
Featured Portals
↓
Featured Widgets
↓
Latest Blogs
```

Do not display every feature on Home.

Home is a discovery dashboard, not a complete catalog.

------------------------------------------------------------------------

# 15. Tools Screen

Structure:

``` text
Tools
↓
Search
↓
Categories
↓
Utilities
↓
Calculators
↓
Converters
↓
Generators
↓
Formatters
↓
Developer Tools
↓
AI Apps
```

Use "See all" actions for large categories.

------------------------------------------------------------------------

# 16. AI Apps Screen

AI app cards should have: - recognizable icon; - app name; - concise
description; - category; - action.

Example:

``` text
AI Chatbot
AI Writer
AI Code Generator
AI Image Generator
AI Prompt Library
```

Do not imply that an AI feature is connected to a real provider until it
actually is.

During mock-data development, use labels such as: - Preview; - Demo; -
Coming Soon; where appropriate.

------------------------------------------------------------------------

# 17. Portals Screen

Portal cards should emphasize information architecture.

Example:

``` text
Technology Tutorials
IT Project Lists
Learning Portal
Language Portal
Career Portal
AI Portal
Entertainment Portal
Muslims Portal
```

Each card can contain: - icon; - title; - description; - item count; -
optional badge.

------------------------------------------------------------------------

# 18. Widgets Screen

Widgets should look interactive.

Examples:

``` text
Clock
Calendar
Weather
Countdown
World Time
```

Where possible, local widgets should show real local calculations
without an external API.

For example: - Clock → device time - Calendar → device date - Countdown
→ local timer - World Time → timezone data, if available locally

Weather can remain mock until an API is introduced.

------------------------------------------------------------------------

# 19. Blogs Screen

Blog layout:

``` text
Search
↓
Category Filter
↓
Featured Article
↓
Latest Articles
```

Article cards should contain: - thumbnail; - category; - title; -
date; - short excerpt.

Use consistent aspect ratios for article thumbnails.

------------------------------------------------------------------------

# 20. Article Detail

Structure:

``` text
Back
↓
Hero Image
↓
Category
↓
Title
↓
Metadata
↓
Article Content
↓
Related Articles
```

Provide: - share; - bookmark/favorite; - text readability; - clear
typography.

------------------------------------------------------------------------

# 21. Profile Screen

Structure:

``` text
Profile Header
↓
Account
↓
Favorites
↓
History
↓
Settings
↓
About
↓
Services
↓
Contact
↓
Social Media
```

Use list tiles with: - leading icon; - title; - optional subtitle; -
trailing chevron.

------------------------------------------------------------------------

# 22. Search

Search should be: - prominent; - rounded; - easy to reach; - consistent
across relevant sections.

Use placeholder text such as:

``` text
Search tools, AI apps, portals...
```

Do not create a separate search implementation for every feature if a
shared search component can be reused.

------------------------------------------------------------------------

# 23. Loading States

Use skeletons or lightweight progress indicators.

Avoid blocking the entire application when only one section is loading.

For future API-connected screens:

``` text
Loading
↓
Content
```

or:

``` text
Loading
↓
Error + Retry
```

------------------------------------------------------------------------

# 24. Empty States

Every list-based feature should have a planned empty state.

Example:

``` text
No favorites yet

Save tools, portals, or articles
to find them here later.
```

Include a useful action where appropriate.

------------------------------------------------------------------------

# 25. Error States

Errors should be: - understandable; - actionable; - non-technical where
possible.

Example:

``` text
Unable to load articles.

Please try again.
[ Retry ]
```

Do not expose raw stack traces or API error payloads to users.

------------------------------------------------------------------------

# 26. Accessibility

Maintain: - sufficient contrast; - readable font sizes; - large touch
targets; - meaningful labels; - semantic icons; - logical focus/order
where applicable.

Do not rely only on color to communicate status.

------------------------------------------------------------------------

# 27. Animation

Use subtle motion.

Suitable: - page transitions; - card entrance; - segmented-control
transitions; - loading transitions; - favorite toggles.

Avoid: - excessive bouncing; - long animations; - animation on every
element.

Animation should communicate state or improve perceived responsiveness.

------------------------------------------------------------------------

# 28. Responsive Behavior

Although the initial target is Android phones, components should not
assume one exact screen size.

Test: - small Android phones; - standard phones; - large phones; -
portrait orientation.

Use flexible layouts instead of hard-coded screen widths.

------------------------------------------------------------------------

# 29. Component Library

Create reusable components such as:

``` text
InzaAppCard
InzaToolCard
InzaPortalCard
InzaWidgetCard
InzaBlogCard
InzaSectionHeader
InzaSearchBar
InzaCategoryChip
InzaEmptyState
InzaErrorState
InzaLoadingState
InzaPrimaryButton
InzaIconButton
```

Do not create a reusable component for every single widget unless
repetition justifies it.

------------------------------------------------------------------------

# 30. Design-to-Code Rule

When implementing a screen from Figma/Stitch:

``` text
Design
 ↓
Identify reusable patterns
 ↓
Implement shared components
 ↓
Implement page layout
 ↓
Add local/mock data
 ↓
Test
```

Do not copy visual values into dozens of widgets.

Centralize: - colors; - typography; - spacing; - radius; - component
themes.

------------------------------------------------------------------------

# 31. API Independence

The design system must not depend on API availability.

A screen should remain visually valid when: - the API is unavailable; -
there is no internet; - the response is empty; - mock data is used.

This is particularly important for the first InzaTech Mobile milestone.

------------------------------------------------------------------------

# 32. Final Visual Goal

The application should communicate:

> "One modern technology platform containing tools, AI, resources,
> widgets, and content."

It should feel like one coherent SaaS ecosystem rather than a collection
of unrelated mini-apps.
