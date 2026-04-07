# Healthcare Platform — Elementor Templates

A complete set of Elementor page templates for a virtual healthcare platform and Videohub360 community/streaming demo. Includes a full homepage template, a complete About page template, a Contact Us page template, a Help Center page template with Contact Form 7 integration, modular section templates, custom CSS, and comprehensive documentation.

---

## What's Included

| Path | Contents |
|------|----------|
| `templates/homepage-complete.json` | Full homepage (all 7 sections) |
| `templates/section-*.json` | 7 individual homepage section templates |
| `templates/about-page/about-page-complete.json` | Full About page (all 7 sections) |
| `templates/about-page/about-*.json` | 7 individual About page section templates |
| `templates/contact-page/contact-page-complete-cf7.json` | Full Contact page with Contact Form 7 integration |
| `templates/contact-page/contact-page-complete-static.json` | Full Contact page with static HTML form (reference) |
| `templates/contact-page/contact-*.json` | 4 individual Contact page section templates |
| `templates/help-center/help-center-complete-cf7.json` | Full Help Center page with Contact Form 7 integration |
| `templates/help-center/help-center-*.json` | 5 individual Help Center section templates |
| `css/healthcare-elementor-styles.css` | Main stylesheet with CSS variables |
| `css/elementor-custom-widgets.css` | Elementor widget-specific overrides |
| `css/about-page-styles.css` | About page-specific component styles |
| `css/contact-form-styles.css` | Contact Form 7 and static form styling |
| `css/help-center-styles.css` | Help Center-specific component styles |
| `contact-form-7/form-configuration.txt` | CF7 form code for Contact page |
| `contact-form-7/mail-template.txt` | Email template configuration for Contact page CF7 |
| `contact-form-7/setup-instructions.md` | Step-by-step CF7 setup guide for Contact page |
| `contact-form-7/help-center-form-configuration.txt` | CF7 form code for Help Center support form |
| `contact-form-7/help-center-mail-template.txt` | Email template configuration for Help Center |
| `contact-form-7/help-center-setup-instructions.md` | Step-by-step Help Center CF7 setup guide |
| `images/README.md` | Image requirements and placeholder guide |
| `docs/README.md` | Overview, color palette, typography |
| `docs/INSTALLATION-GUIDE.md` | Step-by-step setup instructions |
| `docs/DESIGN-SPECS.md` | Full design token reference |
| `docs/CUSTOMIZATION-GUIDE.md` | How to adapt templates to your brand |
| `docs/ABOUT-PAGE-GUIDE.md` | About page structure and customization guide |
| `docs/CONTACT-PAGE-GUIDE.md` | Contact page structure and customization guide |
| `docs/CONTACT-FORM-SETUP.md` | Detailed CF7 setup instructions |
| `docs/ALTERNATIVE-FORM-PLUGINS.md` | WPForms, Elementor Pro, Gravity Forms guides |
| `docs/HELP-CENTER-GUIDE.md` | Help Center structure and customization guide |
| `docs/HELP-CENTER-SETUP.md` | Detailed Help Center setup instructions |

---

## Pages Included

### Homepage Sections (7 sections)

1. **How It Works** — 3-step process with numbered cards
2. **Featured Providers** — 6-provider grid with avatar, badge, and booking button
3. **Services** — 2-column Mental Health / Medical Care split
4. **Why Choose Us** — 4-column feature card grid
5. **Stats Bar** — Gradient bar with 4 key metrics
6. **Testimonials** — 3-column patient quote grid
7. **CTA** — Dark gradient call-to-action box with two buttons

### About Page Sections (7 sections)

1. **Hero** — Two-column layout with H1, eyebrow, lead text, action buttons, and hero card
2. **Stats** — 4 white stat boxes with teal numbers and muted labels
3. **Services** — 2-column split: Mental Health Care and Medical Care with service lists
4. **Benefits** — 3-column grid: Convenience, Comfort, and Connection
5. **Team** — 3-column grid of 6 provider cards with avatar initials
6. **Mission & Vision** — 2-column equal-width cards
7. **CTA** — Blue-to-teal gradient banner with heading and two buttons

### Contact Page Sections (4 templates)

1. **Hero** — Centered H1 and description paragraph
2. **Form Card (CF7)** — Card with Contact Form 7 widget integration
3. **Form Card (Static)** — Card with static HTML form (visual reference)
4. **Info Sidebar** — Contact information card with emergency info box

### Help Center Sections (6 templates)

1. **Hero** — Centered H1 and introduction for the Help Center
2. **Support Categories** — 6-card grid: Account & Login, Profiles & Community, Streaming & Live Sessions, Messages & Notifications, Content & Uploads, Technical Support
3. **FAQ** — Accordion widget with 8 common platform questions
4. **Form Card (CF7)** — Support request form with Contact Form 7 integration
5. **Support Info Sidebar** — Contact information, response time, and demo note
6. **Complete Page** — Full Help Center combining all sections

---

## Quick Start

### Homepage
1. Import `templates/homepage-complete.json` via **Elementor > Templates > Import**
2. Add CSS from `css/healthcare-elementor-styles.css` to **Elementor > Site Settings > Custom CSS**
3. Add provider photos to the Featured Providers section
4. Update all button links to your actual pages

### About Page
1. Import `templates/about-page/about-page-complete.json` via **Elementor > Templates > Import**
2. Add CSS from both `css/healthcare-elementor-styles.css` and `css/about-page-styles.css` to **Elementor > Site Settings > Custom CSS**
3. Update team member names, initials, and descriptions
4. Update all button links to your actual pages

### Contact Page
1. Install the **Contact Form 7** plugin
2. Create a form using the code in `contact-form-7/form-configuration.txt`
3. Import `templates/contact-page/contact-page-complete-cf7.json` via **Elementor > Templates > Import**
4. Add CSS from `css/contact-form-styles.css` to **Elementor > Site Settings > Custom CSS**
5. Select your CF7 form in the CF7 widget settings
6. Update contact information in the sidebar

See [`docs/CONTACT-FORM-SETUP.md`](docs/CONTACT-FORM-SETUP.md) for complete CF7 setup instructions.
See [`docs/CONTACT-PAGE-GUIDE.md`](docs/CONTACT-PAGE-GUIDE.md) for Contact page customization.
See [`docs/ALTERNATIVE-FORM-PLUGINS.md`](docs/ALTERNATIVE-FORM-PLUGINS.md) for WPForms, Elementor Pro, and Gravity Forms guides.

### Help Center
1. Install the **Contact Form 7** plugin
2. Create a form using the code in `contact-form-7/help-center-form-configuration.txt`
3. Import `templates/help-center/help-center-complete-cf7.json` via **Elementor > Templates > Import**
4. Add CSS from `css/contact-form-styles.css` and `css/help-center-styles.css` to **Elementor > Site Settings > Custom CSS**
5. Replace `YOUR_FORM_ID` in the Shortcode widget with your actual CF7 form ID
6. Update support contact information in the sidebar

See [`docs/HELP-CENTER-SETUP.md`](docs/HELP-CENTER-SETUP.md) for complete setup instructions.
See [`docs/HELP-CENTER-GUIDE.md`](docs/HELP-CENTER-GUIDE.md) for Help Center customization.

See [`docs/INSTALLATION-GUIDE.md`](docs/INSTALLATION-GUIDE.md) for full setup instructions.
See [`docs/ABOUT-PAGE-GUIDE.md`](docs/ABOUT-PAGE-GUIDE.md) for About page customization.

---

## Color Palette

| Color | Hex |
|-------|-----|
| Primary | `#2563eb` |
| Primary Dark | `#1d4ed8` |
| Secondary (Teal) | `#0f766e` |
| Text | `#1f2937` |
| Muted | `#6b7280` |
| Background | `#f6f8fb` |
| Surface | `#ffffff` |
| Border | `#e5e7eb` |

---

## Requirements

- WordPress 6.0+
- Elementor (free) 3.15+
- Elementor Pro is **not required**
- Contact Form 7 (free) — required for the CF7 contact page template