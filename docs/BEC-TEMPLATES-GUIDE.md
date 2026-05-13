# BEC Templates Guide

A complete reference for the Biblical Exposition Conference (BEC) Promo Block templates included in this repository. This guide covers the block structure, individual section files, and instructions for importing, styling, and customizing the templates in Elementor.

---

## Overview

The BEC Promo Block is a self-contained conference marketing section designed to be dropped into any Elementor page. It promotes the Biblical Exposition Conference (BEC) with a hero announcement, a two-column mission/details layout, and a full-width registration rates section.

The block is styled entirely through the `css/bec-styles.css` file using CSS custom properties defined on `.bec-block`, making it fully self-contained — no base stylesheet dependency.

---

## Files in This Template Set

| File | Contents |
|------|----------|
| `bec-templates/bec-promo-hero.json` | Hero section — kicker badge, H2 title, lead paragraph |
| `bec-templates/bec-promo-grid.json` | Two-column grid — Mission card (left) + Conference Details card (right) |
| `bec-templates/bec-promo-registration.json` | Registration rates — full-width card with three pricing tiers |
| `bec-templates/bec-promo-complete.json` | Complete single-import template combining all three sections |
| `css/bec-styles.css` | All BEC Promo Block styles (self-contained) |

---

## Quick Start

1. **Add the CSS** — paste the contents of `css/bec-styles.css` into:
   **Elementor > Site Settings > Custom CSS**
   (or enqueue via your child theme's `functions.php`)

2. **Import the complete template** via **Elementor > Templates > Import**:
   `bec-templates/bec-promo-complete.json`

3. **Apply to a page** — create or edit a WordPress page, click **Edit with Elementor**, then insert the imported template from **My Templates**.

4. **Update content** — replace placeholder dates, location, hotel details, and the registration URL with your actual conference information.

> **Tip:** You can also import the three individual section files (`bec-promo-hero.json`, `bec-promo-grid.json`, `bec-promo-registration.json`) separately and assemble them on any page.

---

## CSS Setup

The BEC Promo Block uses a single standalone stylesheet with no external dependencies.

### Option A — Elementor Site Settings (recommended)

1. Go to **Elementor > Site Settings > Custom CSS**.
2. Paste the full contents of `css/bec-styles.css`.
3. Click **Save Changes**.

### Option B — Child Theme `functions.php`

```php
function enqueue_bec_styles() {
    wp_enqueue_style(
        'bec-styles',
        get_stylesheet_directory_uri() . '/css/bec-styles.css',
        [],
        '1.0.0'
    );
}
add_action( 'wp_enqueue_scripts', 'enqueue_bec_styles' );
```

### Option C — Elementor Page CSS

For a single-page scope, paste the CSS into the page's **Advanced > Custom CSS** panel inside Elementor.

---

## Customization

### Conference Dates
Open `bec-promo-complete.json` (or `bec-promo-grid.json`) in Elementor and locate the **Conference Details** card. Update the `bec-value` text-editor widget for the **Conference Dates** row.

### Location
In the same **Conference Details** card, update the `bec-value` text-editor widget for the **Location** row.

### Hotel / Group Rate
Update the `bec-value` text-editor widget for the **Book Your Room** row. Replace `GRMGRMG` with the actual group rate ID and add the hotel name above it.

### Registration URL
In the **Our Mission** card (left column), select the **Register Today** button widget and update the link URL. The current default is:
```
https://becchicago.com/registration/
```

### Registration Prices & Dates
Locate each tier container (`bec-tier`) inside the **Registration Rates** card and update the date range (`bec-tier-sub`) and price (`bec-tier-price`) widgets accordingly.

### Colors & Design Tokens
Override any of the CSS custom properties on `.bec-block` in your site's custom CSS after `bec-styles.css` has loaded:

```css
.bec-block {
  --accent: #your-brand-color;
  --accent2: #your-secondary-color;
}
```

---

## Registration Rates Reference

| Tier | Dates | Price |
|------|-------|-------|
| Early Registration | 4/18/2026 – 2/28/2027 | $265.00 |
| Standard Registration | 03/01/2027 – 03/30/2027 | $325.00 |
| Onsite Registration | 04/01/2027 – 04/30/2027 | $375.00 |

---

## Design Tokens

All visual tokens are defined as CSS custom properties on `.bec-block`:

| Property | Default Value | Usage |
|----------|---------------|-------|
| `--bg` | `#f1f5f9` | Section background (gradient mesh base) |
| `--card` | `#ffffff` | Card background |
| `--border` | `#e2e8f0` | Card border color |
| `--text` | `#0f172a` | Primary text color |
| `--muted` | `#475569` | Secondary / muted text color |
| `--accent` | `#4f46e5` | Primary accent (indigo) — button, Standard tier, detail borders |
| `--accent2` | `#16a34a` | Secondary accent (green) — Early tier, button gradient end |
| `--accent-light` | `#eef2ff` | Light indigo tint — kicker badge background, Mission card background |
| `--accent2-light` | `#dcfce7` | Light green tint |
| `--gold` | `#d97706` | Amber accent — Onsite tier and registration rates card top bar |
| `--gold-light` | `#fef3c7` | Light amber tint |
| `--shadow-sm` | `0 2px 8px rgba(2,6,23,.06)` | Subtle tier card shadow |
| `--shadow` | `0 8px 28px rgba(2,6,23,.10)` | Standard card shadow |
| `--shadow-lg` | `0 20px 48px rgba(2,6,23,.14)` | Card hover-lift shadow |
| `--radius` | `20px` | Card border radius |
| `--radius-sm` | `14px` | Inner element border radius |

---

## Requirements

| Requirement | Version |
|-------------|---------|
| WordPress | 6.0 or later |
| Elementor (free) | 3.15 or later |
| Elementor Pro | Not required |
| PHP | 7.4 or later |
