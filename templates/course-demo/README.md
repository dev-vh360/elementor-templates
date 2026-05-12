# Online Course / Coaching Demo Templates

This folder contains Elementor JSON templates for a **warm academy-style** online course and coaching platform demo built on Videohub360.

## Visual Identity

| Token | Value | Use |
|-------|-------|-----|
| Background | `#fbf7ef` | Cream page background |
| Surface | `#fffdf8` | Card / panel background |
| Surface Soft | `#f3eadc` | Muted section backgrounds |
| Primary | `#14532d` | Deep green buttons and labels |
| Accent | `#c47f2c` | Gold/copper module tags and highlights |
| Border | `#e7dccb` | Warm parchment card borders |
| Text | `#1f2933` | Body and heading text |

This palette is completely separate from the Creator Platform demo (blue/purple `#2563eb`, `#7c3aed`) and the Care/Healthcare demo.

## Files

| File | Purpose |
|------|---------|
| `course-homepage-complete.json` | Full homepage — import this to get the complete demo |
| `course-catalog.json` | Full Course Catalog page with filters, featured learning track, course grid, workshops, resources, and CTA |
| `course-header.json` | Sticky navigation header — Pathway Academy branding |
| `course-hero.json` | Academy hero with curriculum module preview |
| `course-stats.json` | Academy highlights strip (solid deep green band) |
| `course-featured-courses.json` | Course catalog grid with level and access labels |
| `course-learning-path.json` | 4-module curriculum roadmap cards |
| `course-coaching.json` | Weekly coaching schedule (Tue / Thu / Monthly) |
| `course-features.json` | Platform learning features (6-card grid) |
| `course-instructor.json` | Dr. Jordan Ellis — faculty/educator profile |
| `course-membership.json` | Enrollment options (Free / Self-Paced / Coaching Program) |
| `course-testimonials.json` | Student outcomes and learning experience testimonials |
| `course-cta.json` | Deep green academy CTA band |
| `course-footer.json` | Dark forest green footer with course links |

## Quick Setup

1. Import `course-homepage-complete.json` into Elementor.
2. Add `css/course-demo-styles.css` to **Elementor > Site Settings > Custom CSS** or enqueue it from your child theme.
3. In Elementor page settings > **Advanced > CSS Classes**, add the class: `course-demo-page`
4. Replace placeholder course titles, instructor name, pricing, and images with real content.

## Body Class

```
course-demo-page
```

This class is required for the CSS styles to apply. See `docs/COURSE-DEMO-SETUP.md` for full setup instructions.

## Design Notes

- Uses `.course-*` CSS class prefix — independent of `.creator-*` and `.hc-*` classes
- No blue/purple gradients; no SaaS-style color scheme
- CTA band uses solid deep green (`#14532d`)
- Module cards use a left gold border accent (`#c47f2c`)
- Coaching section uses a weekly schedule layout, not generic feature cards
- Enrollment section uses education-specific terminology, not creator membership language

## What This Demo Showcases

- Organized video lesson library
- 4-module curriculum roadmap
- Live coaching schedule (group calls, office hours, workshop replays)
- Platform features framed as a learning experience
- Faculty/instructor profile
- Enrollment options (Free Preview, Self-Paced Course, Coaching Program)
- Student outcome testimonials
- Academy-branded footer
- **Course Catalog page** with available courses grid, featured learning track, static filter/search UI, workshops strip, and learning resources

## What This Demo Does NOT Promise

- Quizzes or assessments
- Certificates or credentials
- Gradebooks or progress tracking
- Assignments
- SCORM / LMS compliance
- Student analytics dashboard

See `docs/COURSE-DEMO-GUIDE.md` for safe wording guidelines.
