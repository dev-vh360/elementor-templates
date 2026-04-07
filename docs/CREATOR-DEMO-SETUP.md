# Creator Demo Platform — Setup Guide

Complete setup instructions for the Creator Demo Elementor templates.

---

## Prerequisites

- WordPress 6.0+
- Elementor (free) 3.15+
- Modern browser with backdrop-filter support (Chrome 76+, Safari 9+, Firefox 103+, Edge 79+)

---

## Step 1: Import Templates

### Option A: Import Complete Homepage

1. In WordPress admin, go to **Elementor > Templates**
2. Click **Import Templates**
3. Upload `templates/creator-demo/creator-homepage-complete.json`
4. The template will appear in your template library

### Option B: Import Individual Sections

Import any of these section templates:

- `creator-header.json` — Sticky navigation header
- `creator-hero.json` — Hero section with creator photo and live stream preview
- `creator-stats.json` — 4-column stats band
- `creator-why.json` — "Why Jay Built This Platform" with 3 feature cards
- `creator-features.json` — "What You Can Do Here" with 2x2 grid
- `creator-meet.json` — "Meet Jay" creator card
- `creator-how-it-works.json` — 3-step process
- `creator-membership.json` — 3-tier pricing cards
- `creator-testimonials.json` — 3-column testimonial grid
- `creator-cta.json` — Final CTA section
- `creator-footer.json` — Footer with links

---

## Step 2: Apply Custom CSS

The Creator Demo templates require custom CSS for the dark theme, glassmorphism effects, and gradient backgrounds.

### Method 1: Elementor Custom CSS (Recommended)

1. Go to **Elementor > Site Settings**
2. Navigate to **Custom CSS**
3. Copy the entire contents of `css/creator-demo-styles.css`
4. Paste into the Custom CSS field
5. Click **Update**

### Method 2: Child Theme

If you're using a child theme:

1. Copy `creator-demo-styles.css` to your child theme's folder
2. Enqueue it in `functions.php`:

```php
function enqueue_creator_demo_styles() {
    wp_enqueue_style(
        'creator-demo-styles',
        get_stylesheet_directory_uri() . '/creator-demo-styles.css',
        array(),
        '1.0.0'
    );
}
add_action('wp_enqueue_scripts', 'enqueue_creator_demo_styles');
```

### Method 3: Simple Custom CSS Plugin

1. Install a plugin like **Simple Custom CSS** or **WP Add Custom CSS**
2. Paste the contents of `creator-demo-styles.css` into the plugin's editor
3. Save changes

---

## Step 3: Set Up Body Background

The multi-layer radial gradient background requires adding a custom class to your page's body element.

### Add Body Class

1. Edit your page in Elementor
2. Click the ⚙️ Settings icon (bottom left)
3. Go to **Advanced** tab
4. In **CSS Classes**, add: `creator-demo-page`
5. Update the page

This applies the dark background with purple/cyan glow effects.

---

## Step 4: Replace Images

### Creator Photo (Hero Section)

- **Current placeholder**: `https://placehold.co/120x120/7c3aed/ffffff?text=JC`
- **Required size**: 120x120px minimum
- **Format**: JPG or PNG with transparent background
- **Style**: Circular crop recommended (border applied via CSS)

### Stream Thumbnail (Hero Section)

- **Current placeholder**: `https://placehold.co/600x450/1e293b/ffffff?text=Live+Stream`
- **Required aspect ratio**: 4:3 (e.g., 600x450px, 800x600px)
- **Format**: JPG or PNG
- **Content**: Screenshot of a live stream or video preview

### Where to Update

1. Edit page in Elementor
2. Click on the Image widget
3. Click **Choose Image**
4. Upload your image or select from Media Library
5. Update the page

---

## Step 5: Customize Creator Name and Branding

### Replace "Jay Carter" with Your Name

Search and replace throughout the template:

1. Hero headline: "Your Direct Line to Jay Carter"
2. Footer brand name: "Jay Carter Live"
3. Meet section heading: "Meet Jay Carter"
4. Creator name in card: "Jay Carter"
5. Copyright notice: "© 2026 Jay Carter Live"

### Update Creator Initials

In the "Meet Jay" section, update the avatar initials:

1. Find the container with gradient background (96x96px)
2. Click the Heading widget showing "JC"
3. Change to your initials
4. Update the page

---

## Step 6: Update Links and CTAs

All buttons currently link to placeholder anchors (`#trial`, `#join`, etc.).

### Update Button Links

1. Edit page in Elementor
2. Click on any Button widget
3. In the **Content** tab, update the **Link** field
4. Common links to update:
   - "Start Free Trial" → Your signup page URL
   - "Join Now" → Your registration page URL
   - "Watch Demo" → Your demo video URL
   - View Pricing" → Your pricing page URL

---

## Step 7: Customize Colors (Optional)

The default color scheme uses purple (#7c3aed) and cyan (#06b6d4). To change:

### Update CSS Variables

In `creator-demo-styles.css`, find these lines:

```css
:root {
  --cd-primary:   #7c3aed;  /* Purple */
  --cd-secondary: #06b6d4;  /* Cyan */
  --cd-accent:    #f59e0b;  /* Amber */
}
```

Replace with your brand colors. Example for blue/green:

```css
:root {
  --cd-primary:   #2563eb;  /* Blue */
  --cd-secondary: #10b981;  /* Green */
  --cd-accent:    #f59e0b;  /* Keep amber or change */
}
```

All gradients, buttons, and accents will update automatically.

---

## Step 8: Customize Pricing Tiers

### Update Tier Names and Prices

1. Edit the "Membership Tiers" section
2. Click on each tier card
3. Update:
   - Tier name (e.g., "Pro Tier" → "Creator Tier")
   - Price number (e.g., "$19" → "$29")
   - Feature list items
   - Button text and link

### "Most Popular" Ribbon

The middle tier (Pro Tier) has an automatic ribbon via CSS. To change which tier is "popular":

1. Find the tier container with `_element_id: "popular"`
2. Move this ID to a different tier container
3. The ribbon will appear on that tier instead

---

## Step 9: Typography (Optional)

The templates use system fonts for maximum compatibility. To use custom fonts:

### Option 1: Elementor Fonts

1. Go to **Elementor > Site Settings > Typography**
2. Set your preferred fonts
3. Elementor will apply them globally

### Option 2: Google Fonts in CSS

Add to the top of `creator-demo-styles.css`:

```css
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap');

body.creator-demo-page {
  font-family: 'Inter', sans-serif;
}
```

Recommended fonts for this design:
- **Inter** — Modern, clean
- **Poppins** — Rounded, friendly
- **Space Grotesk** — Tech-forward
- **DM Sans** — Professional

---

## Step 10: Test Responsive Behavior

Preview your page at different screen sizes:

1. Click the **Responsive Mode** icon in Elementor (bottom left)
2. Test at:
   - Desktop (1920px)
   - Tablet (1024px, 768px)
   - Mobile (375px, 360px)
3. Adjust spacing/padding if needed

### Expected Responsive Behavior

- **Desktop**: All grids as designed
- **Tablet (≤1024px)**: 4-col → 2-col, 3-col → 2-col
- **Mobile (≤760px)**: All grids → 1-col, reduced padding

---

## Step 11: Browser Compatibility Check

The glassmorphism effects use `backdrop-filter`, which requires modern browsers.

### Supported Browsers

- ✅ Chrome 76+
- ✅ Safari 9+ (with -webkit- prefix)
- ✅ Edge 79+
- ✅ Firefox 103+

### Fallback for Older Browsers

Older browsers will still show:
- ✅ Dark background
- ✅ Semi-transparent cards (without blur)
- ✅ Gradients and shadows
- ✅ All layout and content

The blur effect is progressive enhancement—the design works without it.

---

## Step 12: Publish Your Page

1. Click **Update** or **Publish** in Elementor
2. Preview the page in a new tab
3. Test all buttons and links
4. Share with your community!

---

## Troubleshooting

### Background Gradient Not Showing

- ✅ Ensure you added `creator-demo-page` to the body CSS classes
- ✅ Check that custom CSS is applied (view page source, search for "creator-demo-styles")

### Sticky Header Not Sticking

- ✅ Ensure the header container has `position: fixed` (set in Elementor or CSS)
- ✅ Add class `creator-header` to the header container

### "Most Popular" Ribbon Not Showing

- ✅ Check that the tier container has `_element_id: "popular"` or class `popular`
- ✅ Verify CSS is loaded (ribbon is CSS-only, no HTML element)

### Glassmorphism Not Working

- ✅ Test in a modern browser (see supported browsers above)
- ✅ Older browsers will show solid semi-transparent backgrounds instead

### Images Not Loading

- ✅ Replace placeholder URLs with actual uploaded images
- ✅ Ensure image URLs are absolute (start with https://)

---

## Next Steps

- Read [CREATOR-DEMO-GUIDE.md](CREATOR-DEMO-GUIDE.md) for design philosophy and customization tips
- Explore individual section templates to build custom pages
- Join our community for support and updates

---

## Support

For questions or issues:
- Check the documentation in `/docs/`
- Review existing GitHub issues
- Open a new issue with details about your setup

---

**Version**: 1.0.0  
**Last Updated**: April 2026
