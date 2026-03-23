# Help Center Guide

A complete reference for the Help Center page template included in the Videohub360 community and streaming demo package. This guide covers the page structure, section breakdown, and customization instructions.

---

## Overview

The Help Center provides a structured support experience for users of the Videohub360 platform. It combines a support category grid, an FAQ accordion, and a Contact Form 7-powered support request form — all using only Elementor Free widgets.

The template follows the same card style, color palette, typography, and spacing as the Contact page template, adapted for a community and streaming platform rather than healthcare services.

---

## Page Structure

```
┌────────────────────────────────────────────┐
│  HERO SECTION (centered, full width)       │
│  H1: "Help Center"                         │
│  Supporting description                    │
└────────────────────────────────────────────┘

┌────────────────────────────────────────────┐
│  SUPPORT CATEGORIES (3-column grid)        │
│  Account & Login  │ Profiles & Community   │
│  Streaming        │ Messages               │
│  Content & Uploads│ Technical Support      │
└────────────────────────────────────────────┘

┌────────────────────────────────────────────┐
│  FAQ SECTION (accordion, max-width 820px)  │
│  8 common platform questions               │
└────────────────────────────────────────────┘

┌─────────────────────┬──────────────────────┐
│  SUPPORT FORM       │  SUPPORT SIDEBAR     │
│  (1.2fr)            │  (0.8fr)             │
│  H2 + intro text    │  Email / Response /  │
│  CF7 Shortcode      │  Best For / Demo Note│
└─────────────────────┴──────────────────────┘

┌────────────────────────────────────────────┐
│  FOOTER NOTE (centered, muted text)        │
└────────────────────────────────────────────┘
```

---

## Section Descriptions

### 1 — Hero Section

| Property | Value |
|----------|-------|
| Background | `#f6f8fb` |
| Padding | `70px 16px 40px` |
| Max width | `1100px` (boxed) |
| Alignment | Centered |
| Eyebrow label | "Videohub360 Support" (blue, uppercase) |
| H1 | "Help Center" |
| H1 font size | `3rem`, weight 700 |
| Description max-width | `650px` |
| Description color | `#6b7280` |

**File:** `templates/help-center/help-center-hero.json`

---

### 2 — Support Categories Section

| Property | Value |
|----------|-------|
| Background | `#ffffff` |
| Layout | CSS Grid — 3 columns on desktop |
| Tablet layout | 2 columns |
| Mobile layout | Single column stack |
| Card border radius | `12px` |
| Card padding | `32px 28px` |

**Six support categories:**

| Category | Description |
|----------|-------------|
| Account & Login | Access issues, password resets, profile setup |
| Profiles & Community | Profile settings, connections, activity feed |
| Streaming & Live Sessions | Starting streams, joining rooms, technical issues |
| Messages & Notifications | Direct messages, notifications, alerts |
| Content & Uploads | Uploading content, publishing, media management |
| Technical Support | Browser issues, mobile app, connectivity |

**File:** `templates/help-center/help-center-categories.json`

---

### 3 — FAQ Section

| Property | Value |
|----------|-------|
| Background | `#f6f8fb` |
| Max width | `820px` (boxed) |
| Widget | Elementor Accordion (Free) |
| CSS class | `hc-faq-section` |

**Eight FAQ entries:**

1. How do I start a live stream?
2. Why can't I join a session?
3. How do I update my profile?
4. Why am I not getting notifications?
5. How do I message another member?
6. How do I upload or publish content?
7. What browsers are supported?
8. How do I report a technical issue?

**File:** `templates/help-center/help-center-faq.json`

---

### 4 — Support Request Form (Left Column — 1.2fr)

**Heading:** "Submit a Support Request"  
**Intro text:** "Tell us what issue you're having and our team will review it as soon as possible."

The form uses an Elementor Shortcode widget with a CF7 placeholder:
```
[contact-form-7 id="YOUR_FORM_ID" title="Help Center Support Form"]
```

**Form fields (defined in CF7, not Elementor):**

| Field | Type | Required |
|-------|------|----------|
| Your Name | Text input | Yes |
| Email Address | Email input | Yes |
| Username or Profile Name | Text input | No |
| Issue Type | Select (9 options) | Yes |
| Page or Feature Related To | Select (9 options) | No |
| Describe Your Issue | Textarea | Yes |
| Submit Support Request | Button | — |

**File:** `templates/help-center/help-center-form-cf7.json`

---

### 5 — Support Info Sidebar (Right Column — 0.8fr)

**Heading:** "Support Information"

| Label | Value |
|-------|-------|
| Support Email | support@videohub360.com |
| Response Time | Within 24–48 hours |
| Best For | Account issues, Streaming support, Community assistance, Technical troubleshooting |
| Demo Note | "This is a demo support form. In production, submissions would be routed to your support team." |

**File:** `templates/help-center/help-center-support-sidebar.json`

---

### 6 — Complete Page

Combines all five sections above in a single importable Elementor page template.

**File:** `templates/help-center/help-center-complete-cf7.json`

---

## How to Customize Content

### Updating the Hero Text

1. Open the Help Center page in the Elementor editor.
2. Click the H1 heading widget ("Help Center") and edit the title.
3. Click the description text widget and edit the paragraph.

### Updating Support Categories

Each category card contains three widgets:
- An emoji icon (Heading widget — H3 tag)
- A category title (Heading widget — H3 tag)
- A description paragraph (Text Editor widget)

To update a card:
1. Click on the element you want to change.
2. Edit the text in the left panel.
3. To add or remove cards, duplicate or delete entire card containers in the grid.

### Updating FAQ Questions

1. Click the Accordion widget in the FAQ section.
2. In the left panel, find **Items** — each item has a **Title** (question) and **Content** (answer).
3. Click the pencil icon on any item to edit it.
4. Use the **Add Item** button to add more questions.
5. Drag items to reorder them.

### Updating Support Contact Information

1. Click on the value text below each label in the sidebar card (Email, Response Time, etc.).
2. Edit directly in the Text Editor widget.
3. Click **Save**.

### Changing the Demo Note

1. Click the blue note box container in the support sidebar.
2. Click the text widget inside it.
3. Update the text to reflect your actual support workflow.

---

## Responsive Behavior

| Breakpoint | Layout |
|------------|--------|
| Desktop (>980px) | Three-column category grid; two-column form/sidebar grid |
| Tablet (≤980px) | Two-column category grid; form and sidebar stack vertically |
| Mobile (≤640px) | Single-column layout across all sections |

---

## CSS Classes Reference

| Class | Used on |
|-------|---------|
| `.hc-faq-section` | Accordion widget wrapper (applied via Elementor CSS class) |
| `.hc-help-category-card` | Optional: apply to category card containers for hover effects |
| `.hc-support-info-card` | Optional: apply to sidebar card container |
| `.hc-demo-note` | Optional: apply to demo note box container |
| `.contact-cf7-form` | CF7 Shortcode widget wrapper (inherited from contact page CSS) |

> Note: The Elementor JSON template applies `hc-faq-section` automatically to the accordion widget. Other `.hc-*` classes are available for manual use if you apply them via Elementor's **Advanced > CSS Classes** field on the respective containers.

---

## Color Reference

| Token | Hex | Used for |
|-------|-----|---------|
| `--hc-primary` | `#2563eb` | Eyebrow text, active accordion, demo note border |
| `--hc-secondary` | `#0f766e` | Category section eyebrow, FAQ section eyebrow |
| `--hc-text` | `#1f2937` | Headings, label text |
| `--hc-muted` | `#6b7280` | Descriptions, body text, inactive accordion |
| `--hc-bg` | `#f6f8fb` | Hero, FAQ, and grid section background |
| `--hc-surface` | `#ffffff` | Card backgrounds |
| `--hc-border` | `#e5e7eb` | Card borders |
| `--hc-soft-blue` | `#eff6ff` | Demo note box background |

---

## File Structure

```
templates/
  help-center/
    help-center-complete-cf7.json    ← Full page (all sections combined)
    help-center-hero.json            ← Hero section only
    help-center-categories.json      ← 6 support category cards
    help-center-faq.json             ← FAQ accordion section
    help-center-form-cf7.json        ← Support request form card
    help-center-support-sidebar.json ← Support info sidebar card

contact-form-7/
  help-center-form-configuration.txt  ← CF7 form code
  help-center-mail-template.txt        ← Email template settings
  help-center-setup-instructions.md   ← Step-by-step setup guide

css/
  help-center-styles.css              ← Help Center component styles
```

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Categories section shows a single column | Enable CSS Grid support; ensure Elementor Flexbox Containers are active |
| FAQ accordion not styled | Add `css/help-center-styles.css` to Custom CSS |
| Form shows shortcode text instead of form | Replace `YOUR_FORM_ID` with your actual CF7 form ID |
| Demo note box not blue | Check that `background-color` is set to `#eff6ff` and left border to `#2563eb` in the container settings |
| Mobile layout not stacking | Verify responsive settings on the grid containers |
