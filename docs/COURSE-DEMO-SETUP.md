# Course Demo Setup Guide

Step-by-step instructions for importing and configuring the Online Course / Coaching Platform demo templates.

---

## Prerequisites

- WordPress 6.0+
- Elementor (free) 3.15+
- No additional plugins required for this demo

---

## Step 1 — Import the Complete Homepage

1. In WordPress admin, go to **Elementor > Templates > Saved Templates**.
2. Click **Import Templates** (or use the upload icon).
3. Select `templates/course-demo/course-homepage-complete.json`.
4. Click **Import Now**.
5. Create or open a page, click **Edit with Elementor**, then insert the template.

**Alternatively**, import individual sections by repeating the above steps for any `course-*.json` file.

---

## Step 2 — Add the CSS

The templates require `css/course-demo-styles.css` to render correctly.

**Option A — Elementor Site Settings (recommended):**
1. In Elementor editor, click the hamburger menu → **Site Settings**.
2. Under **Custom CSS**, paste the full contents of `css/course-demo-styles.css`.
3. Click **Save Changes**.

**Option B — Child theme (developer):**
1. Copy `css/course-demo-styles.css` to your child theme's `/css/` folder.
2. Enqueue it in `functions.php`:

```php
add_action( 'wp_enqueue_scripts', function() {
    wp_enqueue_style(
        'course-demo-styles',
        get_stylesheet_directory_uri() . '/css/course-demo-styles.css',
        [],
        '1.0.0'
    );
} );
```

---

## Step 3 — Add the Page Body Class

The CSS is scoped to `body.course-demo-page` to avoid conflicts with other templates.

1. Open the page in Elementor.
2. Click the hamburger menu → **Page Settings** (or click the gear icon at the bottom left).
3. Go to the **Advanced** tab.
4. In the **CSS Classes** field, type: `course-demo-page`
5. Click **Update / Publish**.

---

## Step 4 — Replace Placeholder Images

The templates use placeholder images from `placehold.co`. Replace these with real images:

| Section | Image | Recommended Size |
|---------|-------|-----------------|
| Hero | Course preview thumbnail | 560 × 315 px (16:9) |
| Featured Courses | Course card thumbnails (×4) | 480 × 270 px (16:9) |
| Live Coaching | Session preview card | 520 × 290 px (16:9) |
| Instructor | Coach/instructor headshot | 160 × 160 px (square) |

To replace images in Elementor:
1. Click the image widget.
2. In the left panel, click the image thumbnail.
3. Upload or select your replacement image.

---

## Step 5 — Customize Sample Content

Replace all placeholder content with real information:

### Brand Name
Search for `Creator Academy` in the Elementor editor and replace with your platform name.

### Instructor Profile
- Replace `Jordan Ellis` with the real instructor name.
- Replace `Course Creator & Business Coach` with real title.
- Update bio text, stats (years, lessons, students).
- Replace the avatar placeholder with a real photo.

### Course Cards
Replace the 4 sample course titles and descriptions with real courses:
- Creator Business Foundations
- Launch Your Paid Community
- Video Content Strategy
- Live Coaching Masterclass

### Pricing Tiers
Replace the 3 sample plans with real pricing:
- Free Preview ($0/month)
- Course Member ($29/month)
- Coaching Plus ($99/month)

> **Note:** These are sample prices for demonstration only. They do not reflect actual Videohub360 pricing.

### Testimonials
Replace the 3 sample testimonials with real student feedback.

### Navigation Links
Update the header nav links and footer link columns to point to real page URLs.

---

## Step 6 — Import Individual Sections (Optional)

If you want to use individual sections rather than the complete homepage:

1. Import the specific `course-*.json` file (e.g., `course-hero.json`).
2. In your Elementor page, click **Add Template** and insert the imported section.
3. Repeat for each section you need.

Available individual sections:
- `course-header.json`
- `course-hero.json`
- `course-stats.json`
- `course-featured-courses.json`
- `course-learning-path.json`
- `course-coaching.json`
- `course-features.json`
- `course-instructor.json`
- `course-membership.json`
- `course-testimonials.json`
- `course-cta.json`
- `course-footer.json`

---

## Troubleshooting

**Cards not showing correct styles?**
Confirm the `course-demo-page` body class is set and the CSS file has been added to Elementor Site Settings.

**Images showing as grey placeholders?**
Replace placeholder image URLs with your own hosted images.

**Font sizes look different on mobile?**
The templates include responsive font size settings. Verify you are previewing in Elementor's responsive mode.

**Do not use the `creator-demo-page` or `hc-page-bg` classes for this page.** Those classes are for the Creator Demo and Healthcare demo respectively.
