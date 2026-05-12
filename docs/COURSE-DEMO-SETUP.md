# Online Course / Coaching Demo — Setup Guide

## Overview

This guide explains how to import and configure the Online Course / Coaching demo templates for Videohub360.

The demo uses a warm academy-style design (cream / deep green / gold) and is completely independent of the Creator Platform demo and Care / Healthcare demo.

---

## Prerequisites

- WordPress + Elementor Pro installed
- Videohub360 theme active
- Elementor template import permissions

---

## Step 1 — Import the Complete Homepage

1. In WordPress admin, go to **Elementor > My Templates** (or Templates > Library).
2. Click **Import Templates**.
3. Upload `templates/course-demo/course-homepage-complete.json`.
4. The template will appear in your library as:
   **Pathway Academy — Online Course & Coaching Demo**

To use it on a page:
1. Create a new page (or edit an existing one with Elementor).
2. Click the folder icon to open the template library.
3. Search for **Pathway Academy** and insert the template.

---

## Step 2 — Add the Custom CSS

**Option A — Elementor Site Settings (recommended)**

1. Go to **Elementor > Site Settings > Custom CSS**.
2. Paste the contents of `css/course-demo-styles.css`.
3. Click **Save Changes**.

**Option B — Child Theme**

1. Copy `css/course-demo-styles.css` to your child theme directory.
2. In `functions.php`, add:

```php
function enqueue_course_demo_styles() {
    wp_enqueue_style(
        'course-demo-styles',
        get_stylesheet_directory_uri() . '/course-demo-styles.css',
        [],
        '2.0.0'
    );
}
add_action( 'wp_enqueue_scripts', 'enqueue_course_demo_styles' );
```

---

## Step 3 — Add the Required Body Class

1. Open the page in Elementor.
2. Click the hamburger menu (top-left) > **Page Settings**.
3. Go to the **Advanced** tab.
4. In the **CSS Classes** field, add:

```
course-demo-page
```

This class is required. Without it, the cream background and academy-style components will not apply correctly.

---

## Step 4 — Import Individual Sections (Optional)

Each section is also available as a standalone Elementor template:

| Section | File |
|---------|------|
| Header | `course-header.json` |
| Hero | `course-hero.json` |
| Academy Highlights | `course-stats.json` |
| Featured Courses | `course-featured-courses.json` |
| Curriculum Roadmap | `course-learning-path.json` |
| Live Coaching Schedule | `course-coaching.json` |
| Platform Features | `course-features.json` |
| Instructor Profile | `course-instructor.json` |
| Enrollment Options | `course-membership.json` |
| Student Outcomes | `course-testimonials.json` |
| CTA Band | `course-cta.json` |
| Footer | `course-footer.json` |

Import individual sections the same way as the complete homepage (Elementor > My Templates > Import).

---

## Step 5 — Import the Course Catalog Template (Optional)

The Course Catalog is a standalone full-page template that complements the main homepage.

1. In WordPress admin, go to **Elementor > My Templates > Import Templates**.
2. Upload `templates/course-demo/course-catalog.json`.
3. The template will appear in your library as **Course Demo - Course Catalog**.
4. Create a new page (e.g. titled **Courses** or **Course Catalog**) and edit it with Elementor.
5. Insert the **Course Demo - Course Catalog** template.
6. In Elementor page settings > **Advanced > CSS Classes**, add the class:

```
course-demo-page
```

7. Ensure `css/course-demo-styles.css` is loaded globally (see Step 2). The catalog uses the same stylesheet — no additional CSS file is needed.
8. Replace the sample course titles, categories, descriptions, module counts, access labels, and links with your real course content.

### Course Catalog content to replace

- Course card titles, descriptions, module counts, and access type labels (6 cards in the grid)
- Featured learning track title, description, module names, and meta details
- Workshop/coaching session names and descriptions
- Footer brand name (currently **Pathway Academy**) and link columns
- All `#anchor` links to point to real pages or sections

### About the filter and search controls

The filter pills (All Courses, Beginner, Business, etc.) and the search field in the catalog toolbar are **visual demo elements only**. They do not perform live filtering or AJAX search by default.

Site owners can wire them to real filtering functionality — for example, using a query filter plugin, Elementor dynamic content, or custom JavaScript — as needed. This is not required for the demo to look correct.

---

## Step 6 — Customize the Content

Replace all sample content with your own:

### Branding
- Replace **Pathway Academy** with your academy or brand name throughout the templates.
- Update the brand mark (currently the letter "P" in a green square) with your logo.

### Instructor Profile
- Replace **Dr. Jordan Ellis** with the actual instructor name and title.
- Update the bio, credentials, and instructor stats (years teaching, lessons, students).
- Replace the placeholder avatar image with a real instructor photo.

### Course Cards
- Update the 4 featured course titles, descriptions, module counts, and access labels.
- Replace placeholder images with real course thumbnail images.

### Curriculum Modules
- Update the 4 module titles and descriptions to reflect the actual curriculum structure.
- Add or remove module cards as needed.

### Coaching Schedule
- Update the coaching session days, names, and descriptions to reflect the actual schedule.
- Replace "Tuesday / Thursday / Monthly" with the real schedule.

### Enrollment Options
- Update the 3 enrollment plan names, pricing, and feature lists.
- The sample pricing ($0 / $29 / $99) is demo content — replace with actual pricing.

### Testimonials
- Replace the 3 sample testimonials with real student feedback.
- Update reviewer names and roles.

### Contact / Links
- Update all `#anchor` links (e.g., `#curriculum`, `#coaching`, `#enrollment`) to point to real sections or pages.
- Update footer links to point to real pages.

---

## Image Replacement Notes

The hero uses an Elementor icon/widget-based academy preview card instead of a real image, so no hero image replacement is needed.

Course catalog cards use placeholder thumbnails from `placehold.co`. Replace these with actual course images in **Elementor > Edit Image > Choose Image**.

Recommended image formats:
- Course cards: 16:9 ratio, minimum 640×360px
- Instructor avatar: square, minimum 240×240px

---

## CSS Class Reference

| Class | When to Apply |
|-------|-------------|
| `course-demo-page` | Body class on the demo page (required) |
| `course-header` | Header container |
| `course-module-card` | Curriculum module card containers |
| `course-schedule-card` | Coaching schedule card containers |
| `course-cta-band` | CTA section inner container |
| `course-footer` | Footer container |
| `course-btn-primary` | Primary deep green buttons |
| `course-btn-secondary` | Outlined secondary buttons |

---

## Reminder: Sample Content

All course titles, descriptions, instructor names, student testimonials, pricing amounts, and schedule details in this demo are **sample placeholder content**.

Customers should replace all sample content before using this template for a live site.

---

## Design Notes

- **Palette:** Cream background (`#fbf7ef`), deep green primary (`#14532d`), gold accent (`#c47f2c`)
- **No blue/purple gradients** — this demo uses solid green buttons and gold accents
- **Body class required:** `course-demo-page`
- **CSS prefix:** `.course-*` (independent of `.creator-*` and `.hc-*`)
