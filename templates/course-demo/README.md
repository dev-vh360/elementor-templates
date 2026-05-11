# Online Course / Coaching Demo Templates

This folder contains Elementor JSON templates for a light, professional online course and coaching platform demo built on **Videohub360**.

---

## Files in This Folder

| File | Description |
|------|-------------|
| `course-homepage-complete.json` | Full homepage combining all 11 content sections |
| `course-header.json` | Sticky navigation header with brand name and CTA |
| `course-hero.json` | Hero section with headline, buttons, and course preview card |
| `course-stats.json` | 4-column stats band (lessons, tracks, sessions, rating) |
| `course-featured-courses.json` | 4-column grid of featured course cards |
| `course-learning-path.json` | 3-step learning path (Watch → Coaching → Community) |
| `course-coaching.json` | Live coaching section with feature list and session preview |
| `course-features.json` | 6-column platform features grid |
| `course-instructor.json` | Instructor/coach profile card with bio and stats |
| `course-membership.json` | 3-tier pricing cards (Free Preview, Course Member, Coaching Plus) |
| `course-testimonials.json` | 3-column testimonial grid |
| `course-cta.json` | Final CTA with gradient background and two buttons |
| `course-footer.json` | Footer with 5 link columns and copyright |

---

## Recommended Setup

1. Import `course-homepage-complete.json` via **Elementor > Templates > Import**.
2. Add `css/course-demo-styles.css` to **Elementor Site Settings > Custom CSS** or enqueue it from your theme.
3. Add the page CSS class **`course-demo-page`** via **Elementor page settings > Advanced > CSS Classes**.
4. Replace sample course titles, coach profile content, images, and pricing with real content.

See [`docs/COURSE-DEMO-SETUP.md`](../../docs/COURSE-DEMO-SETUP.md) for step-by-step instructions.

---

## Design Notes

- **Color palette:** Light blue primary (`#2563eb`), purple accent (`#7c3aed`), clean white cards
- **Body class:** `course-demo-page`
- **CSS prefix:** `.course-*` (independent from `.creator-*` and `.hc-*` classes)
- **Theme:** Light, professional education/coaching platform — not dark, not medical, not generic

---

## Sample Content to Replace

- **Brand name:** "Creator Academy" → your platform name
- **Instructor:** "Jordan Ellis" → real coach/educator name
- **Course titles** → real course names
- **Pricing tiers and prices** → actual pricing (sample shown for demo only)
- **Testimonials** → real student feedback
- **Images** → replace placeholder images with real photos/thumbnails

---

## What This Demo Does NOT Claim

This demo is intentionally scoped to features that Videohub360 actually supports. It does **not** promise:

- Quiz or assessment tools
- Automatic certificates
- Student grade tracking or gradebooks
- SCORM or LMS compliance
- Assignment submission

Focus: **video lessons, live coaching, paid memberships, community engagement, coach profile.**
