# Course Demo Guide

A design philosophy and customization reference for the Online Course / Coaching Platform demo.

---

## Who This Demo Is For

The Course Demo is designed for **course creators, coaches, educators, consultants, trainers, and experts** who want to sell or organize video-based learning experiences using Videohub360.

Target use cases include:

- Online course creators selling structured video content
- Business coaches offering video lessons plus live coaching sessions
- Educators building a branded learning community
- Consultants or experts packaging their knowledge into a paid member platform
- Training businesses delivering video-based staff or client education

---

## What This Demo Showcases

This demo positions Videohub360 as a **video-first learning and coaching platform**, not as a full LMS.

### Demonstrated capabilities:
- **Video lesson library** — organized, branded access to course content
- **Paid membership tiers** — Free Preview, Course Member, Coaching Plus
- **Live coaching sessions** — group sessions, private calls, workshop replays, member Q&A
- **Learning path** — a clear 3-step structure (Watch → Coaching → Community)
- **Coach/instructor profile** — personal brand identity, bio, credentials, stats
- **Community engagement** — community feed, member discussions
- **Mobile-friendly experience** — responsive layouts for all devices

---

## How This Demo Differs from the Creator Demo

| Feature | Creator Demo | Course Demo |
|---------|-------------|-------------|
| Primary audience | Content creators, streamers | Coaches, educators, course sellers |
| Primary content type | Videos, live streams | Structured courses, coaching sessions |
| Content organization | Video channel | Course library with lessons |
| Coaching emphasis | Minimal | Central feature |
| Learning structure | Not featured | 3-step learning path |
| Instructor profile | Creator "meet" section | Dedicated coach card with credentials |
| Pricing model | Creator membership tiers | Course access + coaching tiers |
| Brand name (demo) | Jay Carter | Jordan Ellis / Creator Academy |
| Demo tone | Personal creator brand | Professional education platform |

Both demos share the same light theme and CSS variable approach, but use independent `.creator-*` and `.course-*` class prefixes so they can coexist without conflicts.

---

## How This Demo Differs from the Healthcare Demo

| Feature | Healthcare Demo | Course Demo |
|---------|----------------|-------------|
| Industry | Medical / virtual care | Education / coaching |
| Primary audience | Patients, caregivers | Students, learners, clients |
| Sections | Provider profiles, services | Courses, coaching, memberships |
| Color accent | Teal | Purple |
| CTA | Book an appointment | Enroll / Start Learning |

---

## Design Language

The Course Demo uses a **clean, premium education/coaching platform** aesthetic:

- Light `#f8fafc` page background
- White (`#ffffff`) card surfaces
- Blue primary (`#2563eb`) for buttons and accents
- Purple accent (`#7c3aed`) used sparingly (badges, gradients)
- Rounded corners (`border-radius: 24px` for cards)
- Soft card shadows
- No dark backgrounds (unlike older Creator demo versions)
- No glassmorphism (unlike older Creator demo versions)

### CSS Variables

```css
:root {
  --course-bg:           #f8fafc;
  --course-surface:      #ffffff;
  --course-surface-soft: #f1f5f9;
  --course-text:         #0f172a;
  --course-muted:        #64748b;
  --course-primary:      #2563eb;
  --course-primary-dark: #1d4ed8;
  --course-accent:       #7c3aed;
  --course-success:      #16a34a;
  --course-warning:      #f59e0b;
  --course-border:       #e2e8f0;
  --course-shadow:       0 18px 45px rgba(15, 23, 42, 0.08);
  --course-radius:       24px;
  --course-max:          1180px;
}
```

---

## Safe Wording Rules

This demo is intentionally scoped to avoid overpromising features that may not exist.

### Use these terms ✅

| Use this | Instead of |
|----------|-----------|
| Video lessons | Courses with automated progress |
| Lesson library | LMS |
| Member-only content | Student tracking |
| Live coaching sessions | Live classes with attendance |
| Community feed | Gradebook |
| Video resources | SCORM compliance |
| Paid membership access | Automatic certificates |
| Coach/instructor profile | Gradebook or assignments |

### Avoid these unless confirmed ❌

- Quizzes or assessments
- Automatic certificates or credentials
- Student grade tracking or gradebooks
- Assignment submission tools
- SCORM compliance
- Automated course completion tracking
- "247 students enrolled" or similar real-time social proof numbers
- "Currently live" or fake urgency indicators

---

## Customization Tips

### Changing the Platform Name
The demo uses "Creator Academy" throughout. Replace it in:
- Header brand name widget
- Footer brand column
- Hero eyebrow badge text (optional)
- Page title

### Changing the Instructor Profile
Replace Jordan Ellis with the real instructor:
1. Update name heading in `course-instructor.json`
2. Update title/role
3. Update bio paragraph
4. Update stat numbers (years, lessons, students)
5. Replace the avatar placeholder image

### Adjusting Pricing Tiers
The 3-tier pricing (Free / $29 / $99) is demo content. To update:
1. Open `course-membership.json` or edit the section in Elementor
2. Update the plan name, price, and feature list for each card
3. Update CTA button text to match your plans

### Adding More Courses
To add more than 4 course cards:
1. Duplicate an existing course card container in Elementor
2. Change the `grid_columns_grid` setting to `repeat(3, 1fr)` or adjust the layout as needed

### Connecting Buttons to Real Pages
All buttons link to `#anchor` placeholders. Before publishing:
1. Update each button link to point to the correct page or section
2. Use Elementor's link picker to select existing pages

---

## Positioning This Demo

When presenting the Course Demo to potential customers, position it as:

> "This is a sample of how you could use Videohub360 to build a branded online course and coaching platform. You can organize your video lessons, offer paid memberships, host live coaching sessions, and give students a community space — all in one place."

Avoid positioning it as:
- A full LMS replacement
- A platform with automated grading or certificate generation (unless confirmed)
- A competitor to Teachable, Kajabi, or Thinkific feature-for-feature
