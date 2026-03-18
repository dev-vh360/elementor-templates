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
templates/homepage-complete.json        (or individual section files)
css/healthcare-elementor-styles.css
css/elementor-custom-widgets.css
```

---

## Step 2 — Import the Template

### Option A: Import the Complete Homepage

1. In your WordPress dashboard, go to **Elementor > Templates**.
2. Click the **Import Templates** button (folder icon) in the top-right corner.
3. In the dialog, click **Select File** and choose `templates/homepage-complete.json`.
4. Click **Import Now**.
5. The template will appear in your library under **Pages**.

### Option B: Import Individual Section Templates

Repeat the import steps above for each section file you want to use:

| File                           | Section                  |
|--------------------------------|--------------------------|
| `section-how-it-works.json`    | How It Works             |
| `section-providers.json`       | Featured Providers       |
| `section-services.json`        | Services                 |
| `section-why-choose.json`      | Why Choose Us            |
| `section-stats.json`           | Stats Bar                |
| `section-testimonials.json`    | Testimonials             |
| `section-cta.json`             | Call to Action           |

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
}
add_action( 'wp_enqueue_scripts', 'hc_enqueue_elementor_styles' );
```

Then copy both CSS files into `your-child-theme/css/`.

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

---

## Step 6 — Update Button Links

All buttons in the templates link to `#` by default. Update them to point to your actual pages:

1. Click a **Button** widget in the Elementor editor.
2. In the left panel under **Content > Link**, replace `#` with the target URL.
3. Common targets to update:
   - "Find a Provider" → your provider directory page
   - "Book Session" / "Book Appointment" → your booking or contact page

---

## Step 7 — Customize Content

Update text content to match your actual platform:

- **Section headings and body text** — click any Heading or Text Editor widget
- **Stats numbers** — update in the Stats Bar section (50+, 1,000+, etc.)
- **Provider names and specialties** — update in the Featured Providers section
- **Testimonial quotes and names** — update in the Testimonials section
- **Service list items** — update in the Services section

---

## Step 8 — Publish

1. Click **Publish** (or **Update**) in the Elementor editor.
2. Preview the page on desktop and mobile to confirm responsive behavior.
3. If needed, regenerate Elementor's CSS cache: **Elementor > Tools > Regenerate CSS**.

---

## Troubleshooting

### Template imports but looks unstyled
- Confirm the custom CSS has been added (Step 4).
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

---

## Enabling Flexbox Containers (Required)

The templates use Elementor's modern **Flexbox Container** system. Enable it if not already active:

1. Go to **Elementor > Settings > Experiments**.
2. Find **Flexbox Container** and set it to **Active**.
3. Save changes.

> Note: In Elementor 3.16+ this feature is enabled by default.
