# Online Course / Coaching Demo — Guide

## Who This Demo Is For

This demo is designed for:

- Course creators who sell structured video programs
- Coaches and consultants who offer live sessions alongside recorded lessons
- Educators and trainers who want a branded video learning hub
- Experts building paid membership learning experiences
- Online academy founders who need a professional launch page

It is **not** positioned as a full LMS. It showcases what Videohub360 actually supports: organized video content, live coaching sessions, member-only access, and community engagement.

---

## How It Differs From the Creator Platform Demo

| Area | Creator Platform Demo | Course / Coaching Demo |
|------|----------------------|----------------------|
| Visual feel | Creator SaaS / video platform | Warm online academy |
| Color palette | Blue (`#2563eb`) + purple (`#7c3aed`) | Cream + deep green (`#14532d`) + gold (`#c47f2c`) |
| Hero | Video platform card | Curriculum module preview |
| Cards | White SaaS cards | Cream editorial cards with parchment borders |
| Pricing section | Creator membership tiers | Enrollment options |
| Profile section | Creator profile | Instructor / faculty profile |
| Live section | Live streaming / community | Weekly coaching schedule |
| Learning path | 3 generic feature steps | 4-module curriculum roadmap |
| CTA | Blue-purple gradient | Deep green academy band |
| Brand name | Creator Academy | Pathway Academy |

---

## How It Differs From the Care / Healthcare Demo

The Care demo is designed for wellness providers, healthcare services, and appointment-based care businesses. It uses a light clinical palette and appointment booking as its primary CTA.

The Course / Coaching demo is designed for educators, coaches, and course creators. It uses a warm academy palette and enrollment / course access as its primary CTA.

Do not use `.hc-*` CSS classes in the Course demo. The Course demo uses `.course-*` exclusively.

---

## Safe Wording Rules

### Use these terms — they describe real Videohub360 capabilities:

- Video lessons / video library
- Lesson library
- Member-only content
- Live coaching sessions
- Community feed / member community
- Coach profile / instructor profile
- Video resources
- Premium access
- Enrollment
- Organized video content
- Coaching program
- Session replays
- Member-only lessons

### Avoid these terms — they promise LMS features that may not be present:

- Quizzes / assessments
- Certificates / credentials
- Gradebooks
- Student progress tracking
- Assignments
- SCORM
- LMS compliance
- Student analytics dashboard
- Automated drip content (unless it exists)
- Completion badges (unless they exist)

---

## What the Demo Showcases

1. **Curriculum roadmap** — 4-module structure showing how content is organized
2. **Video lesson library** — branded hub for organized course videos
3. **Live coaching schedule** — weekly group sessions, office hours, workshop replays
4. **Platform learning features** — 6-card grid showing core capabilities
5. **Instructor / faculty profile** — Dr. Jordan Ellis profile with credentials and teaching focus
6. **Enrollment options** — Free Preview, Self-Paced Course, Coaching Program
7. **Student outcome testimonials** — realistic, general testimonials about the learning experience
8. **Academy CTA** — deep green band with clear next-step buttons

---

## Positioning Statement

> Use this demo to show buyers that Videohub360 can be used to build a **professional online academy** with organized video courses, live coaching sessions, member-only resources, and community engagement.

This demo helps attract:

- Course creators moving from scattered tools to a branded platform
- Coaches who want to add structured video lessons to their existing coaching business
- Educators launching a paid learning community
- Consultants and trainers building a video-first training library

---

## Color Palette Reference

```css
:root {
  --course-bg:            #fbf7ef;   /* Cream background */
  --course-surface:       #fffdf8;   /* Card surface */
  --course-surface-soft:  #f3eadc;   /* Muted sections */
  --course-text:          #1f2933;   /* Main text */
  --course-muted:         #6b7280;   /* Secondary text */
  --course-primary:       #14532d;   /* Deep green primary */
  --course-primary-dark:  #0f3f23;   /* Footer / dark sections */
  --course-accent:        #c47f2c;   /* Gold/copper accent */
  --course-accent-soft:   #f5dfbd;   /* Soft gold background */
  --course-border:        #e7dccb;   /* Warm parchment border */
}
```

---

## CSS Class Reference

| Class | Purpose |
|-------|---------|
| `.course-header` | Sticky navigation header |
| `.course-highlights-strip` | Solid green stats/highlights band |
| `.course-module-card` | Curriculum module cards with gold left border |
| `.course-schedule-card` | Weekly coaching schedule cards |
| `.course-course-card` | Course catalog cards |
| `.course-feature-card` | Platform feature cards |
| `.course-enrollment-card` | Enrollment option cards |
| `.course-instructor-card` | Faculty/instructor profile card |
| `.course-testimonial-card` | Student outcome testimonial card |
| `.course-cta-band` | Deep green CTA section |
| `.course-footer` | Dark forest green footer |
| `.course-btn-primary` | Deep green primary button |
| `.course-btn-secondary` | Outlined green secondary button |
| `.course-section-eyebrow` | Small green uppercase section label |
| `.course-divider` | Gold accent divider line |

All classes use the `.course-*` prefix, keeping them completely independent of `.creator-*` and `.hc-*` styles.
