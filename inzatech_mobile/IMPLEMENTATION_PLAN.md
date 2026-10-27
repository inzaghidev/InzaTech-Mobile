# InzaTech Mobile --- Implementation Plan

## 1. Objective

Build **InzaTech Mobile** as a Flutter Android application that
complements the InzaTech web platform.

The first milestone is **not** a fully connected production application.

The first milestone is a polished, navigable, API-independent mobile
application using local/mock data.

This approach intentionally reduces: - development complexity; - token
usage when working with AI coding tools; - API quota consumption; -
debugging surface; - dependency on external services; - risk of exposing
API secrets.

------------------------------------------------------------------------

# 2. Product Scope

## Main Navigation

``` text
Home
Tools
Explore
Blogs
Profile
```

## Information Architecture

``` text
InzaTech Mobile
│
├── Home
│
├── Tools
│   ├── Utilities
│   ├── Calculators
│   ├── Converters
│   ├── Developer Tools
│   └── AI Apps
│
├── Explore
│   ├── Portals
│   │   ├── Technology
│   │   ├── IT Projects
│   │   ├── Learning
│   │   ├── Language
│   │   ├── Career
│   │   ├── AI
│   │   ├── Entertainment
│   │   └── Muslims
│   │
│   └── Widgets
│       ├── Clock
│       ├── Calendar
│       ├── Weather
│       ├── Countdown
│       └── World Time
│
├── Blogs
│   ├── Featured
│   ├── Latest
│   ├── Categories
│   ├── Search
│   └── Article Detail
│
└── Profile
    ├── Account
    ├── Favorites
    ├── History
    ├── Settings
    ├── About
    ├── Services
    ├── Contact
    └── Social Media
```

------------------------------------------------------------------------

# 3. Phase 0 --- Project Foundation

## Goal

Create a clean Flutter project and establish the design system before
implementing many screens.

### Tasks

-   [ ] Create/verify Flutter project.
-   [ ] Set Android application ID/package name.
-   [ ] Configure app name: `InzaTech`.
-   [ ] Add application icon later.
-   [ ] Configure Material 3.
-   [ ] Create theme files.
-   [ ] Create core reusable widgets.
-   [ ] Create navigation shell.
-   [ ] Create placeholder pages.

### Initial success state

The application opens and displays:

``` text
Home | Tools | Explore | Blogs | Profile
```

All five tabs navigate correctly.

------------------------------------------------------------------------

# 4. Phase 1 --- Home Screen

## Goal

Create the primary dashboard.

### UI

``` text
Home
│
├── Greeting / Header
├── Search
├── At a Glance
├── AI Apps
├── Quick Utilities
├── Featured Portals
├── Featured Widgets
└── Latest Blog Preview
```

### Initial data

All content is local/mock.

Example:

``` dart
const quickTools = [
  'QR Generator',
  'JSON Formatter',
  'Unit Converter',
];
```

### Do not integrate APIs yet.

------------------------------------------------------------------------

# 5. Phase 2 --- Tools & Utilities

## Goal

Build the main tool discovery interface.

### Categories

``` text
Tools
├── Utilities
├── Calculators
├── Converters
├── Generators
├── Formatters
├── File Tools
└── Developer Tools
```

### First tools to implement

Start with simple client-side tools that do not require APIs:

-   Unit Converter
-   JSON Formatter
-   Text Formatter
-   Base64 Encoder/Decoder
-   Color Converter
-   UUID Generator
-   Timestamp Converter
-   Password Generator
-   QR Generator, if implemented locally

These are ideal early features because the application can perform the
work locally.

------------------------------------------------------------------------

# 6. Phase 3 --- AI Apps UI

## Goal

Build the AI Apps experience without connecting an AI API.

### Categories

``` text
AI Apps
├── AI Chatbot
├── AI Writer
├── AI Code Generator
├── AI Image Generator
├── AI Prompt Library
└── AI Summarizer
```

### Initial behavior

The UI should work with mock responses.

Example:

``` text
User:
Explain React.

Mock response:
React is a JavaScript library...
```

The objective is to validate: - chat layout; - prompt input; - response
cards; - loading state; - error state; - history UI; - copy/share
actions.

### Later API options

Possible future integrations can include Gemini or another suitable
provider, but they are explicitly outside Phase 3.

------------------------------------------------------------------------

# 7. Phase 4 --- Explore / Portals

## Goal

Build the knowledge/resource discovery section.

### UI

Use a segmented control:

``` text
[ Portals ] [ Widgets ]
```

### Portal categories

``` text
Technology
IT Project Lists
Learning
Language
Career
AI
Entertainment
Muslims
```

### Initial data source

Local mock Dart data.

Later it can be replaced by: - Notion API; - a custom backend; - static
JSON; - another CMS.

The UI should not care which data source is used.

------------------------------------------------------------------------

# 8. Phase 5 --- Explore / Widgets

## Goal

Build useful mini-apps.

### First widgets

1.  Digital Clock
2.  Calendar
3.  Countdown
4.  World Time
5.  Weather UI placeholder

Clock/calendar/countdown can work locally.

Weather should initially use mock data.

Later:

``` text
Weather Widget
    ↓
Weather Repository
    ↓
Weather API
```

------------------------------------------------------------------------

# 9. Phase 6 --- Blogs

## Goal

Build the blog experience before connecting Blogger API.

### UI

``` text
Blogs
├── Search
├── Category Filter
├── Featured Article
├── Latest Articles
└── Article Detail
```

### Initial source

Local mock articles.

Example:

``` text
Technology
AI
Web Development
Flutter
Programming
Tutorial
```

### Later

Replace:

``` text
MockBlogRepository
```

with:

``` text
BloggerRepository
```

The UI should remain mostly unchanged.

------------------------------------------------------------------------

# 10. Phase 7 --- Profile & Core Pages

## Goal

Complete the application shell.

### Profile

``` text
Profile
├── Account
├── Favorites
├── History
├── Settings
├── Preferences
├── Notifications
├── About
├── Services
├── Contact
└── Social Media
```

Authentication is not required for the first prototype.

Use a local guest profile initially.

------------------------------------------------------------------------

# 11. Phase 8 --- Local Persistence

After the core UI works, add local persistence for:

-   Favorites
-   History
-   Theme preference
-   Recently used tools
-   User settings

Choose one local storage solution after requirements become clear.

Do not introduce a database simply because the application may need one
someday.

------------------------------------------------------------------------

# 12. Phase 9 --- API Integration

Only after the UI and repository boundaries are stable.

Recommended order:

### 9.1 Gemini / AI

``` text
AI UI
 ↓
AI ViewModel
 ↓
AI Repository
 ↓
Backend/API Service
 ↓
Gemini
```

### 9.2 Notion

``` text
Portal UI
 ↓
Portal ViewModel
 ↓
Portal Repository
 ↓
Notion service/backend
 ↓
Notion API
```

### 9.3 Blogger

``` text
Blog UI
 ↓
Blog ViewModel
 ↓
Blog Repository
 ↓
Blogger API
```

### 9.4 Other APIs

Add only when a feature genuinely requires external data.

------------------------------------------------------------------------

# 13. Phase 10 --- Testing

For every phase:

``` bash
flutter analyze
flutter test
flutter run
```

Test: - navigation; - scrolling; - tap targets; - text overflow; - empty
states; - loading states; - error states; - dark mode if enabled; -
different Android screen sizes.

------------------------------------------------------------------------

# 14. Phase 11 --- Preview Release

Once the first stable prototype exists:

``` text
Flutter
  ↓
flutter build apk
  ↓
APK
  ↓
GitHub Release
  ↓
v0.1.0
```

Use GitHub Releases for public preview.

Use Firebase App Distribution later if private beta testing is required.

------------------------------------------------------------------------

# 15. Phase 12 --- Production

After sufficient testing:

``` text
Flutter
  ↓
Release build
  ↓
Signed Android App Bundle
  ↓
Google Play Console
  ↓
Production
```

Google Play is a later phase, not a prerequisite for initial
development.

------------------------------------------------------------------------

# 16. Recommended Milestones

## Milestone A --- App Shell

-   [ ] Flutter project
-   [ ] Theme
-   [ ] Navigation
-   [ ] Empty pages

## Milestone B --- Core UI

-   [ ] Home
-   [ ] Tools
-   [ ] Explore
-   [ ] Blogs
-   [ ] Profile

## Milestone C --- Functional Local Features

-   [ ] Utilities
-   [ ] Calculators
-   [ ] Converters
-   [ ] Local widgets
-   [ ] Mock AI
-   [ ] Mock portals
-   [ ] Mock blogs

## Milestone D --- API Ready

-   [ ] Repository interfaces
-   [ ] Services
-   [ ] Error handling
-   [ ] Loading states
-   [ ] Configuration management

## Milestone E --- APIs

-   [ ] Gemini
-   [ ] Notion
-   [ ] Blogger
-   [ ] Other required APIs

## Milestone F --- Release

-   [ ] QA
-   [ ] APK
-   [ ] GitHub Release
-   [ ] Beta
-   [ ] Production preparation

------------------------------------------------------------------------

# 17. AI Coding Workflow

When using an AI coding tool, do not ask it to build the entire project
at once.

Prefer:

``` text
Prompt 1:
Create the Flutter project shell and theme.

Prompt 2:
Implement the bottom navigation.

Prompt 3:
Implement Home using mock data.

Prompt 4:
Implement Tools.

Prompt 5:
Implement AI Apps using mock responses.

Prompt 6:
Implement Explore → Portals.

Prompt 7:
Implement Explore → Widgets.

Prompt 8:
Implement Blogs using mock articles.

Prompt 9:
Implement Profile.

Prompt 10:
Refactor shared components.

Prompt 11:
Add API repositories.

Prompt 12:
Integrate APIs one by one.
```

This keeps context/token usage manageable and makes debugging easier.

------------------------------------------------------------------------

# 18. Definition of Version 0.1.0

`v0.1.0` should be considered a **UI/functional preview**, not the final
InzaTech Mobile product.

Target:

-   working navigation;
-   polished Home;
-   Tools;
-   AI Apps mock UI;
-   Portals;
-   Widgets;
-   Blogs mock UI;
-   Profile;
-   local functionality where practical;
-   no required external API.

The application should already feel like a coherent product before
external services are connected.
