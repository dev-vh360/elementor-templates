# Healthcare Platform — Elementor Templates

A complete set of Elementor page templates for a virtual healthcare platform. The package includes a full homepage template, a complete About page template, fifteen modular section templates, custom CSS stylesheets, and comprehensive documentation.

---

## What's Included

```
/templates/
  homepage-complete.json        ← Full homepage (all sections combined)
  section-how-it-works.json     ← "How It Works" 3-step section
  section-providers.json        ← Featured Providers grid
  section-services.json         ← Mental Health & Medical services split
  section-why-choose.json       ← Why Choose Us feature cards
  section-stats.json            ← Stats bar (blue-to-teal gradient)
  section-testimonials.json     ← Patient testimonials grid
  section-cta.json              ← Call-to-Action dark gradient box

  /about-page/
    about-page-complete.json    ← Full About page (all sections combined)
    about-hero.json             ← Hero section (two-column layout + hero card)
    about-stats.json            ← Stats grid (white cards, teal numbers)
    about-services.json         ← Care services split (Mental Health + Medical)
    about-benefits.json         ← Why Virtual Services Matter (3 cards)
    about-team.json             ← Team grid (6 providers with avatar initials)
    about-mission-vision.json   ← Mission & Vision 2-column cards
    about-cta.json              ← CTA gradient banner

  /help-center/
    help-center-complete-cf7.json    ← Full Help Center page with CF7
    help-center-hero.json            ← Hero section
    help-center-categories.json      ← 6 support category cards
    help-center-faq.json             ← FAQ accordion section
    help-center-form-cf7.json        ← Support request form card
    help-center-support-sidebar.json ← Support info sidebar

/contact-form-7/
  form-configuration.txt             ← CF7 form code for Contact page
  mail-template.txt                  ← Email template for Contact page
  setup-instructions.md              ← CF7 setup guide for Contact page
  help-center-form-configuration.txt ← CF7 form code for Help Center
  help-center-mail-template.txt      ← Email template for Help Center
  help-center-setup-instructions.md  ← CF7 setup guide for Help Center

/css/
  healthcare-elementor-styles.css    ← Main stylesheet (CSS variables + components)
  elementor-custom-widgets.css       ← Elementor-specific widget overrides
  about-page-styles.css              ← About page-specific components
  contact-form-styles.css            ← CF7 and static form styling
  help-center-styles.css             ← Help Center component styles

/images/
  README.md                          ← Image requirements & placeholder guide

/docs/
  README.md                          ← This file
  INSTALLATION-GUIDE.md              ← Step-by-step setup instructions
  DESIGN-SPECS.md                    ← Colors, typography, spacing reference
  CUSTOMIZATION-GUIDE.md             ← How to adapt the templates
  ABOUT-PAGE-GUIDE.md                ← About page structure & customization
  CONTACT-PAGE-GUIDE.md              ← Contact page structure & customization
  CONTACT-FORM-SETUP.md              ← Detailed CF7 setup for Contact page
  ALTERNATIVE-FORM-PLUGINS.md        ← WPForms, Elementor Pro, Gravity Forms
  HELP-CENTER-GUIDE.md               ← Help Center structure & customization
  HELP-CENTER-SETUP.md               ← Help Center setup instructions
```

---

## Quick Start

### Homepage
1. **Import** `templates/homepage-complete.json` via Elementor > Templates > Import
2. **Add CSS** from `css/healthcare-elementor-styles.css` to Elementor > Site Settings > Custom CSS
3. **Add provider images** to the Featured Providers section
4. **Update links** on all buttons to point to your actual pages

### About Page
1. **Import** `templates/about-page/about-page-complete.json` via Elementor > Templates > Import
2. **Add CSS** — paste both `css/healthcare-elementor-styles.css` and `css/about-page-styles.css` to Elementor > Site Settings > Custom CSS
3. **Update team members** — edit avatar initials, names, and descriptions in the Team section
4. **Update links** on all buttons to point to your actual pages

### Help Center
1. **Install Contact Form 7** plugin
2. **Create form** — paste code from `contact-form-7/help-center-form-configuration.txt` into a new CF7 form named **Help Center Support Form**
3. **Import** `templates/help-center/help-center-complete-cf7.json` via Elementor > Templates > Import
4. **Add CSS** — paste `css/contact-form-styles.css` and `css/help-center-styles.css` to Elementor > Site Settings > Custom CSS
5. **Replace form ID** — update `YOUR_FORM_ID` in the Shortcode widget with your actual CF7 form ID
6. **Update sidebar** — replace placeholder contact details with your support email and information

See [HELP-CENTER-SETUP.md](HELP-CENTER-SETUP.md) for full step-by-step instructions.
See [HELP-CENTER-GUIDE.md](HELP-CENTER-GUIDE.md) for Help Center customization.

See [INSTALLATION-GUIDE.md](INSTALLATION-GUIDE.md) for full step-by-step instructions.
See [ABOUT-PAGE-GUIDE.md](ABOUT-PAGE-GUIDE.md) for About page customization.

---

## Color Palette

| Token             | Hex       | Usage                         |
|-------------------|-----------|-------------------------------|
| `--hc-bg`         | `#f6f8fb` | Page background               |
| `--hc-surface`    | `#ffffff` | Card and section backgrounds  |
| `--hc-text`       | `#1f2937` | Primary body text             |
| `--hc-muted`      | `#6b7280` | Secondary / descriptive text  |
| `--hc-primary`    | `#2563eb` | Buttons, accents, step numbers |
| `--hc-primary-dark`| `#1d4ed8`| Button hover states           |
| `--hc-secondary`  | `#0f766e` | Gradient endpoints, teal tones |
| `--hc-soft-blue`  | `#eff6ff` | Badge backgrounds             |
| `--hc-soft-teal`  | `#ecfeff` | Subtle teal highlight areas   |
| `--hc-border`     | `#e5e7eb` | Card borders                  |

---

## Typography

- **Font family:** Arial, Helvetica, sans-serif (system font stack — no web font required)
- **H2 headings:** `clamp(1.9rem, 2.8vw, 2.8rem)`, weight 700, letter-spacing −0.02em
- **H3 headings:** `1.3rem`, weight 700
- **Body / lead text:** `1.05rem`, color `#6b7280`, line-height 1.65
- **Eyebrow labels:** `13px`, weight 700, letter-spacing 0.08em, uppercase
- **Badges:** `0.84rem`, weight 700

---

## Image Requirements

Provider avatar images are not included. See [images/README.md](../images/README.md) for specifications and placeholder options.

---

## Requirements

| Requirement       | Version      |
|-------------------|--------------|
| WordPress         | 6.0 or later |
| Elementor (free)  | 3.15 or later |
| Elementor Pro     | Not required  |
| PHP               | 7.4 or later |

---

## License

These templates are provided for use on your own WordPress/Elementor projects. All design assets, copy, and code in this repository are original and may be freely customized for commercial or personal use.
