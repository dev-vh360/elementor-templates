# Contact Page Guide

A complete reference for the Contact Us page templates included in the Healthcare Platform Elementor Templates package. This guide covers the page structure, section breakdown, and customization instructions.

---

## Overview

The Contact page provides a clean two-column layout with a contact form on the left and contact information on the right. It is designed to match the overall healthcare platform design system — using the same card style, color palette, typography, and spacing as the Homepage and About page templates.

Two complete template variants are provided:

| File | Description |
|------|-------------|
| `contact-page-complete-cf7.json` | Primary version — uses Contact Form 7 widget |
| `contact-page-complete-static.json` | Backup/reference version — uses static HTML form |

---

## Quick Start

### CF7 Version (Recommended)
1. Import `templates/contact-page/contact-page-complete-cf7.json` via **Elementor > Templates > Import**
2. Create a Contact Form 7 form using the code in `contact-form-7/form-configuration.txt`
3. Add CSS from `css/contact-form-styles.css` to **Elementor > Site Settings > Custom CSS**
4. In the Elementor editor, update the CF7 widget to point to your new form
5. Update contact information in the sidebar card
6. Publish the page

### Static Version (Reference)
1. Import `templates/contact-page/contact-page-complete-static.json`
2. Add CSS from `css/contact-form-styles.css` to Custom CSS
3. Note: The static form does not process submissions; connect a form plugin to make it functional

See [`../contact-form-7/setup-instructions.md`](../contact-form-7/setup-instructions.md) for full CF7 setup instructions.

---

## Page Structure

The Contact page is composed of three sections:

```
┌────────────────────────────────────────────┐
│  HERO SECTION (centered, full width)       │
│  H1: "Contact Our Care Team"               │
│  Description paragraph (max-width 650px)  │
└────────────────────────────────────────────┘

┌─────────────────────┬──────────────────────┐
│  FORM CARD          │  INFO SIDEBAR        │
│  (1.2fr)            │  (0.8fr)             │
│  H2 + intro text    │  H2 heading          │
│  CF7 or HTML form   │  Email / Phone /     │
│                     │  Hours / Services    │
│                     │  Info box (blue)     │
└─────────────────────┴──────────────────────┘

┌────────────────────────────────────────────┐
│  FOOTER NOTE (centered, muted text)        │
└────────────────────────────────────────────┘
```

---

## Section Breakdown

### 1 — Hero Section

| Property | Value |
|----------|-------|
| Background | `#f6f8fb` |
| Padding | `70px 16px 40px` |
| Max width | `1100px` (boxed) |
| Alignment | Centered |
| H1 font size | `3rem` (design spec: `clamp(2.2rem, 4vw, 3rem)`) |
| H1 color | `#1f2937` |
| Description max-width | `650px` |
| Description color | `#6b7280` |
| Description font size | `1.05rem` |

**Files:**
- `templates/contact-page/contact-hero.json` (individual section)

---

### 2 — Two-Column Grid

| Property | Value |
|----------|-------|
| Layout | CSS Grid — `1.2fr 0.8fr` |
| Column gap | `30px` |
| Row gap | `30px` |
| Padding | `40px 16px 80px` |
| Mobile (≤850px) | Single column stack |

Both columns use the shared card style:

| Card Property | Value |
|---------------|-------|
| Background | `#ffffff` |
| Border | `1px solid #e5e7eb` |
| Border radius | `22px` |
| Box shadow | `0 18px 40px rgba(0,0,0,0.08)` |
| Padding | `28px` |

---

### 3 — Form Card (Left Column — 1.2fr)

**Heading:** "Send Us a Message"  
**Intro text:** "Fill out the form below and our team will respond as soon as possible."

The form includes:

| Field | Type | Required |
|-------|------|----------|
| Full Name | Text input | Yes |
| Email Address | Email input | Yes |
| What type of care are you looking for? | Select (4 options) | No |
| Message | Textarea (min-height 130px) | Yes |
| Send Message | Submit button | — |

**Dropdown options:**
- Mental Health Care
- Medical Care
- General Question
- Technical Support

**Files:**
- `templates/contact-page/contact-form-section-cf7.json`
- `templates/contact-page/contact-form-section-static.json`

---

### 4 — Contact Information Sidebar (Right Column — 0.8fr)

**Heading:** "Contact Information"

**Contact items:**

| Label | Value |
|-------|-------|
| Email | support@virtualhealthdemo.com |
| Phone | (800) 555‑2038 |
| Virtual Office Hours | Monday – Friday, 9:00 AM – 6:00 PM |
| Platform Services | Mental Health Therapy, Medical Consultations, Virtual Appointments |

**Info box (bottom of sidebar):**

| Property | Value |
|----------|-------|
| Background | `#eef6ff` |
| Border | `1px solid #dbeafe` |
| Border radius | `16px` |
| Padding | `18px` |
| Margin top | `30px` |
| Heading | "Need Immediate Help?" |
| Text color | `#6b7280` |

**Files:**
- `templates/contact-page/contact-info-sidebar.json`

---

### 5 — Footer Note

Centered muted text below the grid:
> "Demo platform connecting patients with mental health and medical professionals through virtual care."

---

## How to Update Contact Information

All contact details are stored in **Text Editor** widgets inside the sidebar card. To update them:

1. Open the Contact page in Elementor editor
2. Click on the value text below each label (Email, Phone, etc.)
3. Edit directly in the text editor widget
4. Click **Save**

---

## How to Change the Info Box Color

1. Click on the blue info box container in Elementor
2. Go to **Style > Background**
3. Change the background color (default: `#eef6ff`)
4. Change the border color in **Style > Border** (default: `#dbeafe`)

---

## Responsive Behavior

| Breakpoint | Layout |
|------------|--------|
| Desktop (>850px) | Two-column grid (1.2fr 0.8fr) |
| Tablet / Mobile (≤850px) | Single column, form card stacks above info sidebar |

On mobile, all form fields remain full-width. The button expands to full width via the custom CSS media query.

---

## CSS Classes Reference

| Class | Used on |
|-------|---------|
| `.contact-cf7-form` | CF7 widget wrapper (set via Elementor CSS class) |
| `.contact-static-form` | Static HTML form element |
| `.wpcf7` | Default CF7 form wrapper |
| `.wpcf7-submit` | CF7 submit button |
| `.wpcf7-not-valid` | Invalid field state |
| `.wpcf7-mail-sent-ok` | Success message |
| `.wpcf7-mail-sent-ng` | Error message |

---

## Color Reference

| Token | Hex |
|-------|-----|
| Primary | `#2563eb` |
| Primary hover | `#1e4fd1` |
| Secondary (teal) | `#0f766e` |
| Text | `#1f2937` |
| Muted | `#6b7280` |
| Background | `#f6f8fb` |
| Card | `#ffffff` |
| Border | `#e5e7eb` |
| Info box background | `#eef6ff` |
| Info box border | `#dbeafe` |

---

## File Structure

```
templates/
  contact-page/
    contact-page-complete-cf7.json    ← Full page with CF7 widget (recommended)
    contact-page-complete-static.json ← Full page with static HTML form
    contact-hero.json                 ← Hero section only
    contact-form-section-cf7.json     ← Form card with CF7 widget
    contact-form-section-static.json  ← Form card with HTML form
    contact-info-sidebar.json         ← Contact info sidebar card

contact-form-7/
  form-configuration.txt             ← CF7 form code to paste
  mail-template.txt                  ← Email template settings
  setup-instructions.md              ← Step-by-step setup guide

css/
  contact-form-styles.css            ← CF7 + static form styling
```

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Grid does not show two columns | Ensure the page uses Elementor Flexbox Containers; enable in **Elementor > Settings > Features** |
| CF7 form not visible | Install and activate the Contact Form 7 plugin; update the widget's form ID |
| Form fields unstyled | Add `css/contact-form-styles.css` to Custom CSS |
| Info box not blue | Check that the container background color is `#eef6ff` |
| Mobile layout not stacking | Confirm the responsive overrides in the grid container settings |
