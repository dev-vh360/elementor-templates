# Design Specifications

Complete reference for all design tokens, spacing values, typography settings, and component specifications used in the Healthcare Platform Elementor Templates.

---

## Color System

### Primary Palette

| Token              | CSS Variable          | Hex Value   | Usage                                |
|--------------------|-----------------------|-------------|--------------------------------------|
| Background         | `--hc-bg`             | `#f6f8fb`   | Page-level background                |
| Surface            | `--hc-surface`        | `#ffffff`   | Cards, light section backgrounds     |
| Text               | `--hc-text`           | `#1f2937`   | Headings and primary body copy       |
| Muted              | `--hc-muted`          | `#6b7280`   | Descriptive / secondary text         |
| Primary            | `--hc-primary`        | `#2563eb`   | Buttons, eyebrows, step numbers, accents |
| Primary Dark       | `--hc-primary-dark`   | `#1d4ed8`   | Button hover states                  |
| Secondary          | `--hc-secondary`      | `#0f766e`   | Gradient endpoints, teal highlights  |
| Soft Blue          | `--hc-soft-blue`      | `#eff6ff`   | Badge backgrounds                    |
| Soft Teal          | `--hc-soft-teal`      | `#ecfeff`   | Subtle teal highlight areas          |
| Border             | `--hc-border`         | `#e5e7eb`   | Card and button borders              |

### Section Background Colors

| Section Type         | Background                                              |
|----------------------|---------------------------------------------------------|
| Light (white)        | `#ffffff`                                               |
| Soft (subtle gradient)| `linear-gradient(180deg, #f8fbff 0%, #f4f8fc 100%)`   |
| Stats bar            | `linear-gradient(135deg, #1e3a8a 0%, #0f766e 100%)`    |
| CTA box              | `linear-gradient(135deg, #0f172a 0%, #1e3a8a 55%, #0f766e 100%)` |

### Icon Box Gradient

Background for icon containers (56 × 56 px):

```css
background: linear-gradient(145deg, #dbeafe 0%, #ccfbf1 100%);
```

---

## Typography

### Font Stack

```css
font-family: Arial, Helvetica, sans-serif;
```

No external web font is required. The system font stack ensures fast load times across all devices.

### Type Scale

| Element          | Size                            | Weight | Line Height | Letter Spacing | Color          |
|------------------|---------------------------------|--------|-------------|----------------|----------------|
| H2 (section)     | `clamp(1.9rem, 2.8vw, 2.8rem)` | 700    | 1.15        | −0.02em        | `#1f2937`      |
| H3 (card title)  | `1.3rem`                        | 700    | 1.3         | normal         | `#1f2937`      |
| Lead / subtitle  | `1.05rem`                       | 400    | 1.65        | normal         | `#6b7280`      |
| Body text        | `1rem` (base)                   | 400    | 1.65        | normal         | `#1f2937`      |
| Muted body       | `1rem`                          | 400    | 1.65        | normal         | `#6b7280`      |
| Eyebrow label    | `13px`                          | 700    | normal      | 0.08em         | `#2563eb`      |
| Badge            | `0.84rem`                       | 700    | normal      | normal         | `#1d4ed8`      |
| Stat number      | `2rem`                          | 700    | 1           | normal         | `#ffffff`      |
| Stat label       | `0.95rem`                       | 400    | normal      | normal         | `rgba(255,255,255,0.86)` |

---

## Spacing System

### Section Padding

| Breakpoint       | Vertical Padding |
|------------------|------------------|
| Desktop (>640px) | `76px` top + bottom |
| Mobile (≤640px)  | `58px` top + bottom |

### Container

| Property         | Value                       |
|------------------|-----------------------------|
| Max width        | `1180px`                    |
| Side padding     | `16px` (prevents edge clipping) |
| Center alignment | `margin: 0 auto`            |

### Section Header Block (centered)

| Property         | Value       |
|------------------|-------------|
| Max width        | `760px`     |
| Bottom margin    | `34px`      |

### Cards

| Property         | Desktop | Mobile (≤640px) |
|------------------|---------|-----------------|
| Padding          | `28px`  | `22px`          |
| Border radius    | `22px`  | `22px`          |
| Border           | `1px solid #e5e7eb` | same |
| Box shadow       | `0 18px 40px rgba(15, 23, 42, 0.08)` | same |

### Grid Gaps

| Usage                  | Gap    |
|------------------------|--------|
| All card grids         | `24px` |
| Button row (CTA)       | `14px` |
| Provider card items    | `14px` |

---

## Border Radius Values

| Element              | Radius        |
|----------------------|---------------|
| Cards                | `22px`        |
| Stats bar container  | `28px`        |
| CTA box              | `30px`        |
| Icon boxes           | `16px`        |
| Step number circles  | `50%` (circle)|
| Avatar images        | `50%` (circle)|
| Buttons              | `14px`        |
| Badges / eyebrows    | `999px` (pill)|

---

## Shadow Specifications

### Card Shadow

```css
box-shadow: 0 18px 40px rgba(15, 23, 42, 0.08);
```

### Avatar Shadow

```css
box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
```

---

## Grid Breakpoints

| Breakpoint  | Max Width | Behavior                                               |
|-------------|-----------|--------------------------------------------------------|
| Desktop     | —         | Full grid layouts (3-col, 4-col, 2-col)                |
| Tablet      | 980px     | 4-col → 2-col; 3-col → 1-col; 2-col → 1-col           |
| Mobile      | 640px     | All grids → 1-col; section padding reduced to 58px    |

---

## Component Specifications

### Eyebrow Label

```
Display:        inline-block
Padding:        8px 14px
Border radius:  999px
Background:     rgba(37, 99, 235, 0.08)
Text color:     #2563eb
Font size:      13px
Font weight:    700
Letter spacing: 0.08em
Transform:      uppercase
Bottom margin:  14px
```

**Inverted (on dark backgrounds):**
```
Background:  rgba(255, 255, 255, 0.12)
Text color:  #ffffff
```

---

### Step Number

```
Width:          42px
Height:         42px
Border radius:  50%
Background:     #2563eb
Text color:     #ffffff
Font weight:    700
Bottom margin:  14px
```

---

### Icon Box

```
Width:          56px
Height:         56px
Border radius:  16px
Background:     linear-gradient(145deg, #dbeafe 0%, #ccfbf1 100%)
Font size:      26px (emoji)
Bottom margin:  16px
```

---

### Provider Avatar

```
Width:          68px
Height:         68px
Border radius:  50%
Object fit:     cover
Border:         2px solid #ffffff
Box shadow:     0 4px 12px rgba(0,0,0,0.08)
```

---

### Specialty Badge

```
Padding:        7px 12px
Border radius:  999px
Background:     #eff6ff
Text color:     #1d4ed8
Font size:      0.84rem
Font weight:    700
```

---

### Buttons

#### Primary Button
```
Min height:     48px
Padding:        0 20px (or 14px 24px for CTA)
Border radius:  14px
Background:     #2563eb
Text color:     #ffffff
Font weight:    700
Border:         1px solid #2563eb
Hover bg:       #1d4ed8
Transition:     0.2s ease
```

#### Secondary Button
```
Min height:     48px
Padding:        0 20px
Border radius:  14px
Background:     #ffffff
Text color:     #1f2937
Font weight:    700
Border:         1px solid #e5e7eb
Hover bg:       #f9fafb
Transition:     0.2s ease
```

---

### Service List Item

```
Padding left:   18px
Margin bottom:  12px
Text color:     #6b7280
Line height:    1.65

Bullet (::before):
  Left:         0
  Top:          11px
  Width:        7px
  Height:       7px
  Border radius: 50%
  Background:   #2563eb
```

---

### Stats Bar

```
Background:     linear-gradient(135deg, #1e3a8a 0%, #0f766e 100%)
Border radius:  28px
Padding:        26px (desktop), 20px (mobile)
Color:          #ffffff

Number:  font-size 2rem, weight 700, line-height 1
Label:   font-size 0.95rem, color rgba(255,255,255,0.86)
```

---

### Testimonial Card

```
Top padding:    42px (extra space for decorative quote)

Decorative quote mark (::before):
  Content:      \201C  (")
  Top:          4px
  Left:         0 (or 28px with card padding offset)
  Font size:    3rem
  Color:        rgba(37, 99, 235, 0.2)
  Font weight:  700
```

---

### CTA Box

```
Background:     linear-gradient(135deg, #0f172a 0%, #1e3a8a 55%, #0f766e 100%)
Border radius:  30px
Padding:        46px 30px
Text align:     center

Heading color:  #ffffff
Body text:      rgba(255,255,255,0.86), max-width 720px
Button gap:     14px
```

---

## About Page — Specific Components

### Hero Card

Right-column card in the About page hero:

```
Background:     linear-gradient(145deg, #ffffff 0%, #f0f7ff 100%)
Border:         1px solid #dce8f8
Border radius:  28px
Padding:        28px
Shadow:         0 18px 40px rgba(15, 23, 42, 0.08)
```

**Mini-cards (2×2 grid inside hero card):**

```
Background:     rgba(255,255,255,0.95)
Border:         1px solid #e5e7eb
Border radius:  18px
Padding:        16px

Title:          1.05rem, weight 700, color #1f2937
Description:    0.9rem, color #6b7280
```

---

### About Page Stat Boxes

Different from the homepage gradient stats bar — uses white cards with teal numbers:

```
Background:     #ffffff
Border:         1px solid #e5e7eb
Border radius:  22px
Padding:        26px 18px
Shadow:         0 18px 40px rgba(15, 23, 42, 0.08)
Text align:     center

Number size:    2rem, weight 700, color #0f766e (secondary/teal)
Label size:     0.95rem, color #6b7280 (muted)
Number margin:  0 0 8px 0
```

---

### Avatar Circles (Team Section)

Text-based initials in a circular gradient badge:

```
Width/Height:   72px × 72px
Border radius:  50% (full circle)
Background:     linear-gradient(145deg, #dbeafe 0%, #d1fae5 100%)
Display:        inline-flex, align-items center, justify-content center

Initials font:  24px, weight 700
Initials color: #1d4ed8 (primary-dark)
```

---

### About Page CTA Box

Left-aligned variant of the CTA (vs. centered on the homepage):

```
Background:     linear-gradient(135deg, #1e3a8a 0%, #0f766e 100%)
Border radius:  30px
Padding:        42px (desktop), 28px (mobile)
Text align:     left

Heading color:  #ffffff
Body text:      rgba(255,255,255,0.86), max-width 760px
Button row:     flex-start, gap 14px, flex-wrap
```

---

### Hero Grid Proportions

The About page hero uses asymmetric column widths:

```
Desktop:   grid-template-columns: 1.15fr 0.85fr
Tablet:    grid-template-columns: 1fr 1fr
Mobile:    grid-template-columns: 1fr
```
