---
name: InzaTech Mobile
colors:
  surface: '#fcf8ff'
  surface-dim: '#dcd8e5'
  surface-bright: '#fcf8ff'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#f5f2ff'
  surface-container: '#f0ecf9'
  surface-container-high: '#eae6f4'
  surface-container-highest: '#e4e1ee'
  on-surface: '#1b1b24'
  on-surface-variant: '#464555'
  inverse-surface: '#302f39'
  inverse-on-surface: '#f3effc'
  outline: '#777587'
  outline-variant: '#c7c4d8'
  surface-tint: '#4d44e3'
  primary: '#3525cd'
  on-primary: '#ffffff'
  primary-container: '#4f46e5'
  on-primary-container: '#dad7ff'
  inverse-primary: '#c3c0ff'
  secondary: '#00687a'
  on-secondary: '#ffffff'
  secondary-container: '#57dffe'
  on-secondary-container: '#006172'
  tertiary: '#005338'
  on-tertiary: '#ffffff'
  tertiary-container: '#006e4b'
  on-tertiary-container: '#67f4b7'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#e2dfff'
  primary-fixed-dim: '#c3c0ff'
  on-primary-fixed: '#0f0069'
  on-primary-fixed-variant: '#3323cc'
  secondary-fixed: '#acedff'
  secondary-fixed-dim: '#4cd7f6'
  on-secondary-fixed: '#001f26'
  on-secondary-fixed-variant: '#004e5c'
  tertiary-fixed: '#6ffbbe'
  tertiary-fixed-dim: '#4edea3'
  on-tertiary-fixed: '#002113'
  on-tertiary-fixed-variant: '#005236'
  background: '#fcf8ff'
  on-background: '#1b1b24'
  surface-variant: '#e4e1ee'
typography:
  display-lg:
    fontFamily: Inter
    fontSize: 32px
    fontWeight: '700'
    lineHeight: 40px
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Inter
    fontSize: 24px
    fontWeight: '600'
    lineHeight: 32px
    letterSpacing: -0.01em
  headline-md:
    fontFamily: Inter
    fontSize: 20px
    fontWeight: '600'
    lineHeight: 28px
  title-lg:
    fontFamily: Inter
    fontSize: 18px
    fontWeight: '600'
    lineHeight: 24px
  title-md:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '500'
    lineHeight: 24px
  body-lg:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '400'
    lineHeight: 24px
  body-md:
    fontFamily: Inter
    fontSize: 14px
    fontWeight: '400'
    lineHeight: 20px
  label-lg:
    fontFamily: Inter
    fontSize: 14px
    fontWeight: '500'
    lineHeight: 20px
  label-md:
    fontFamily: Inter
    fontSize: 12px
    fontWeight: '500'
    lineHeight: 16px
    letterSpacing: 0.01em
  headline-lg-mobile:
    fontFamily: Inter
    fontSize: 22px
    fontWeight: '600'
    lineHeight: 28px
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  base: 4px
  xs: 4px
  sm: 8px
  md: 16px
  lg: 24px
  xl: 32px
  gutter: 16px
  margin-mobile: 16px
  margin-tablet: 24px
---

## Brand & Style

The design system is a premium, mobile-first SaaS aesthetic that prioritizes clarity, performance, and trust. It utilizes a **Modern Minimalist** style with strong influences from **Material 3**, characterized by logical elevation, spacious layouts, and high-quality functional typography. The goal is to create an interface that feels invisible yet highly efficient, allowing the technology platform's data and actions to take center stage. 

The visual language focuses on depth created through subtle shadows and tonal layering rather than heavy lines, ensuring the UI feels light and responsive on high-density mobile displays.

## Colors

The palette is rooted in a professional "Indigo" primary, supported by "Cyan" and "Emerald" for secondary and tertiary actions. This ensures a broad range of semantic possibilities for data visualization and status indicators within the SaaS environment.

- **Primary**: Used for the most important actions, active states, and brand presence.
- **Secondary/Tertiary**: Used for highlights, category distinctions, and secondary feature paths.
- **Surface & Background**: Utilizes a cool Slate-based greyscale to reduce eye strain and maintain a premium, clean feel.
- **Text**: Employs high-contrast Slate 900 for readability and Slate 500 for auxiliary information to maintain clear information hierarchy.

## Typography

The design system exclusively uses **Inter** to leverage its exceptional legibility and systematic weight distribution. 

- **Hierarchy**: Use `display-lg` and `headline-lg` sparingly for key landing areas.
- **Readability**: `body-md` is the workhorse for content. All body text should maintain a 1.5x line height ratio to ensure breathing room between lines of text.
- **Interactive Elements**: Use `label-lg` for buttons and `label-md` for small tags or micro-copy. 
- **Scale**: On mobile devices, ensure any headline larger than 24px scales down to the `headline-lg-mobile` token to prevent excessive wrapping.

## Layout & Spacing

This design system follows a **Fluid Grid** model with an 8px base unit. 

- **Mobile Layout**: Use a standard 4-column grid with 16px margins and 16px gutters.
- **Tablet/Desktop**: Transition to a 12-column grid. Margins increase to 24px or 32px depending on screen density.
- **Rhythm**: All vertical spacing between elements should be a multiple of 4 (e.g., 8, 16, 24, 32). Large card containers should typically use `lg` (24px) padding to maintain the "spacious" requirement.

## Elevation & Depth

Hierarchy is established through **Ambient Shadows** and tonal separation. 

- **Level 0 (Background)**: `#F8FAFC`. Used for the main canvas.
- **Level 1 (Cards/Surface)**: `#FFFFFF`. Elevated with a soft, diffused shadow: `0px 1px 3px rgba(0, 0, 0, 0.05), 0px 10px 15px -3px rgba(0, 0, 0, 0.05)`.
- **Level 2 (Modals/Overlays)**: Elevated with a deeper shadow to pull it forward: `0px 20px 25px -5px rgba(0, 0, 0, 0.1)`.
- **Active States**: Subtle 1px borders using `border_color` are used on Level 1 elements to ensure definition against the background when shadows are disabled for performance.

## Shapes

The design system adopts a "Rounded" philosophy to appear approachable and modern.

- **Standard Cards**: Use `rounded-xl` (24px) for major dashboard cards and containers.
- **Secondary Cards**: Use `rounded-lg` (16px) for nested elements or list items.
- **Buttons**: Use 8px (rounded-md) or fully pill-shaped (rounded-full) depending on the context of the action.
- **Input Fields**: 12px roundedness to sit comfortably between the button and card styles.

## Components

### Bottom Navigation
- **Structure**: 5 tabs max.
- **Style**: Fixed at the bottom of the screen with a Blur (Glassmorphism) effect or pure White background. 
- **Active State**: Primary color icon + label. Inactive uses Secondary Text color. Use a 2px top-border or an indicator pill on the active icon for Material 3 clarity.

### Segmented Controls
- **Style**: A container with `#F1F5F9` background and `rounded-lg`.
- **Selected Item**: White background with a subtle shadow (Level 1 elevation), mimicking a physical slider moving across the options.

### Rounded Cards
- **Style**: Background `#FFFFFF`, border-radius 24px, padding 24px.
- **Interactions**: On tap, apply a scale transform (98%) to provide tactile feedback.

### Buttons
- **Primary**: Solid Indigo `#4F46E5` with white text.
- **Outline**: 1.5px border of Indigo with Indigo text.
- **Ghost**: No background/border, used for "Cancel" or low-priority actions.

### Input Fields
- **Background**: `#FFFFFF`.
- **Border**: 1px `#E2E8F0` resting; 2px `#4F46E5` focused.
- **Labels**: Always visible, positioned above the field using `label-md`.

### Chips & Tags
- **Style**: Soft background tints (e.g., Emerald at 10% opacity for Tertiary status) with high-contrast text. Pill-shaped (rounded-full).