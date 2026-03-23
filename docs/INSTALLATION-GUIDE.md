# Installation Guide

Step-by-step instructions for setting up the Healthcare Platform Elementor Templates on a WordPress site.

---

## Prerequisites

Before you begin, make sure you have:

- [ ] WordPress **6.0 or later** installed
- [ ] **Elementor** (free) plugin installed and activated — version 3.15+
- [ ] A theme that is compatible with Elementor (e.g., Hello Elementor, Astra, OceanWP, or any block-compatible theme)
- [ ] Administrator access to your WordPress dashboard

> **Elementor Pro is NOT required.** All templates use only Elementor Free widgets (Container, Heading, Text Editor, Image, Button).

---

## Step 1 — Download the Template Files

Clone or download this repository to your local computer. You will need the following files:

```
templates/homepage-complete.json         (or individual section files)
templates/about-page/about-page-complete.json  (or individual about section files)
templates/help-center/help-center-complete-cf7.json  (or individual help center section files)
css/healthcare-elementor-styles.css
css/elementor-custom-widgets.css
css/about-page-styles.css                (required for About page)
css/contact-form-styles.css              (required for Contact and Help Center pages)
css/help-center-styles.css               (required for Help Center page)
```

---

## Step 2 — Import the Template

### Option A: Import the Complete Homepage

1. In your WordPress dashboard, go to **Elementor > Templates**.
2. Click the **Import Templates** button (folder icon) in the top-right corner.
3. In the dialog, click **Select File** and choose `templates/homepage-complete.json`.
4. Click **Import Now**.
5. The template will appear in your library under **Pages**.

### Option B: Import the Complete About Page

1. In your WordPress dashboard, go to **Elementor > Templates**.
2. Click the **Import Templates** button (folder icon).
3. Choose `templates/about-page/about-page-complete.json`.
4. Click **Import Now**.
5. The template will appear in your library under **Pages**.

### Option C: Import the Complete Help Center Page

1. In your WordPress dashboard, go to **Elementor > Templates**.
2. Click the **Import Templates** button (folder icon).
3. Choose `templates/help-center/help-center-complete-cf7.json`.
4. Click **Import Now**.
5. The template will appear in your library under **Pages**.

### Option D: Import Individual Section Templates

Repeat the import steps above for each section file you want to use.

**Homepage sections:**

| File                           | Section                  |
|--------------------------------|--------------------------|
| `section-how-it-works.json`    | How It Works             |
| `section-providers.json`       | Featured Providers       |
| `section-services.json`        | Services                 |
| `section-why-choose.json`      | Why Choose Us            |
| `section-stats.json`           | Stats Bar                |
| `section-testimonials.json`    | Testimonials             |
| `section-cta.json`             | Call to Action           |

**About page sections:**

| File                              | Section                     |
|-----------------------------------|-----------------------------|
| `about-page/about-hero.json`      | Hero (two-column)           |
| `about-page/about-stats.json`     | Stats (white cards)         |
| `about-page/about-services.json`  | Services (split panel)      |
| `about-page/about-benefits.json`  | Benefits (3 cards)          |
| `about-page/about-team.json`      | Team (6 providers)          |
| `about-page/about-mission-vision.json` | Mission & Vision       |
| `about-page/about-cta.json`       | CTA (gradient banner)       |

**Help Center sections:**

| File                                          | Section                          |
|-----------------------------------------------|----------------------------------|
| `help-center/help-center-hero.json`           | Hero (centered H1)               |
| `help-center/help-center-categories.json`     | Support Categories (6-card grid) |
| `help-center/help-center-faq.json`            | FAQ Accordion                    |
| `help-center/help-center-form-cf7.json`       | Support Request Form (CF7)       |
| `help-center/help-center-support-sidebar.json`| Support Info Sidebar             |

Imported sections will appear under **Elementor > Templates > Sections** and can be inserted into any page using the **My Templates** tab in the Elementor editor.

---

## Step 3 — Apply the Template to a Page

1. Create a new page in WordPress (**Pages > Add New**).
2. Click **Edit with Elementor**.
3. In the Elementor editor, click the **folder icon** (My Templates) in the bottom toolbar.
4. Find the imported template and click **Insert**.
5. Confirm any prompts about replacing existing content.

---

## Step 4 — Add the Custom CSS

The CSS files provide the component styles, CSS custom properties, and responsive tweaks that make the templates look their best.

### Method A: Elementor Site Settings (Recommended)

1. In the Elementor editor, click the **hamburger menu** (☰) in the top-left corner.
2. Go to **Site Settings > Custom CSS**.
3. Open `css/healthcare-elementor-styles.css` in a text editor and paste the full contents.
4. Click **Save Changes**.
5. Optionally, also paste the contents of `css/elementor-custom-widgets.css` (you can add it to the same field, below the first file).

**For the About page, also add:**
6. Paste the contents of `css/about-page-styles.css` into the same Custom CSS field (below the other stylesheets).

**For the Contact page or Help Center page, also add:**
7. Paste the contents of `css/contact-form-styles.css` into the same Custom CSS field.

**For the Help Center page, also add:**
8. Paste the contents of `css/help-center-styles.css` into the same Custom CSS field.

### Method B: Enqueue via Child Theme

Add the following to your child theme's `functions.php`:

```php
function hc_enqueue_elementor_styles() {
    wp_enqueue_style(
        'healthcare-elementor-styles',
        get_stylesheet_directory_uri() . '/css/healthcare-elementor-styles.css',
        [],
        '1.0.0'
    );
    wp_enqueue_style(
        'elementor-custom-widgets',
        get_stylesheet_directory_uri() . '/css/elementor-custom-widgets.css',
        ['healthcare-elementor-styles'],
        '1.0.0'
    );
    wp_enqueue_style(
        'about-page-styles',
        get_stylesheet_directory_uri() . '/css/about-page-styles.css',
        ['healthcare-elementor-styles'],
        '1.0.0'
    );
}
add_action( 'wp_enqueue_scripts', 'hc_enqueue_elementor_styles' );
```

Then copy all three CSS files into `your-child-theme/css/`.

### Method C: Elementor Page-Level Custom CSS

For CSS that applies only to one specific page:

1. Open the page in the Elementor editor.
2. Click **Page Settings** (gear icon at the bottom-left).
3. Scroll to the **Advanced** tab and find **Custom CSS**.
4. Paste the CSS there.

---

## Step 5 — Add Provider Images

The Featured Providers section uses placeholder image references. Replace them with real photos:

1. Open the page in the Elementor editor.
2. Click inside the **Featured Providers** section.
3. For each provider card, click the **Image** widget.
4. In the left panel, update the image source to a photo from your WordPress Media Library.

See [images/README.md](../images/README.md) for image size and format specifications.

> **About page team section:** The About page uses text-based avatar initials (not images), so no image uploads are required for the team section.

---

## Step 6 — Update Button Links

All buttons in the templates link to `#` by default. Update them to point to your actual pages:

1. Click a **Button** widget in the Elementor editor.
2. In the left panel under **Content > Link**, replace `#` with the target URL.
3. Common targets to update:
   - "Find a Provider" / "View Providers" → your provider directory page
   - "Book Session" / "Book Appointment" → your booking or contact page
   - "Explore Services" → your services page
   - "Meet Our Providers" → your providers page or About page provider section

---

## Step 7 — Customize Content

Update text content to match your actual platform:

**Homepage:**
- **Section headings and body text** — click any Heading or Text Editor widget
- **Stats numbers** — update in the Stats Bar section (50+, 1,000+, etc.)
- **Provider names and specialties** — update in the Featured Providers section
- **Testimonial quotes and names** — update in the Testimonials section
- **Service list items** — update in the Services section

**About page:**
- **Hero heading and lead text** — click the H1 and Text Editor widgets in the Hero section
- **Stats** — update numbers (2, 8+, 100%, 1) and labels in the Stats section
- **Team member names and descriptions** — update Heading and Text Editor widgets in the Team section
- **Avatar initials** — update the two-letter Heading widget inside each team card
- **Mission and Vision paragraphs** — update Text Editor widgets in the Mission & Vision section
- **CTA heading and description** — update in the CTA section

See [ABOUT-PAGE-GUIDE.md](ABOUT-PAGE-GUIDE.md) for detailed About page customization instructions.

**Help Center:**
- **Hero heading and description** — click the H1 and Text Editor widgets in the Hero section
- **Support category titles and descriptions** — update Heading and Text Editor widgets in each category card
- **FAQ questions and answers** — click the Accordion widget and edit items in the left panel
- **Support request form** — replace `YOUR_FORM_ID` in the Shortcode widget with your actual CF7 form ID
- **Sidebar contact details** — click each value widget (email, response time, best for)

See [HELP-CENTER-GUIDE.md](HELP-CENTER-GUIDE.md) for detailed Help Center customization instructions.
See [HELP-CENTER-SETUP.md](HELP-CENTER-SETUP.md) for Help Center CF7 setup instructions.

---

## Step 8 — Publish

1. Click **Publish** (or **Update**) in the Elementor editor.
2. Preview the page on desktop and mobile to confirm responsive behavior.
3. If needed, regenerate Elementor's CSS cache: **Elementor > Tools > Regenerate CSS**.

---

## Troubleshooting

### Template imports but looks unstyled
- Confirm the custom CSS has been added (Step 4).
- For the About page, also confirm `about-page-styles.css` has been added.
- Clear any caching plugins (e.g., W3 Total Cache, WP Rocket).
- Check that the Elementor Flexbox Containers experiment is enabled: **Elementor > Settings > Experiments > Flexbox Container**.

### Images are missing or broken
- Upload provider images to the WordPress Media Library.
- Update each Image widget to point to the uploaded file (see Step 5).

### Buttons have wrong colors
- Make sure `healthcare-elementor-styles.css` is loaded on the page.
- Check that no other CSS rules are overriding `.elementor-button` styles.

### Grid layout is not responsive
- Ensure Elementor's **Container** layout type is set to **Grid** for the relevant containers.
- The responsive breakpoints are built into the JSON — verify them under **Advanced > Responsive** for each grid container.

### About page avatar initials not centered
- Add `css/about-page-styles.css` to Elementor Site Settings > Custom CSS.
- The avatar circles use `inline-flex` alignment that requires the CSS file to render correctly.

---

## Enabling Flexbox Containers (Required)

The templates use Elementor's modern **Flexbox Container** system. Enable it if not already active:

1. Go to **Elementor > Settings > Experiments**.
2. Find **Flexbox Container** and set it to **Active**.
3. Save changes.

> Note: In Elementor 3.16+ this feature is enabled by default.

