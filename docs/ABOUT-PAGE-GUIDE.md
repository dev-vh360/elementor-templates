# About Page Guide

A complete reference for the About Us page templates included in the Healthcare Platform Elementor Templates package. This guide covers the page structure, section-by-section breakdown, and customization instructions.

---

## Overview

The About page consists of seven modular sections that can be used individually or combined into the complete `about-page-complete.json` template. Each section is self-contained and follows the same design system as the homepage templates.

### Sections

| File | Section | Description |
|------|---------|-------------|
| `about-hero.json` | Hero | Two-column layout with H1, lead text, buttons, and a hero card |
| `about-stats.json` | Stats | 4 white stat boxes with teal numbers |
| `about-services.json` | Services | 2-column split: Mental Health + Medical Care |
| `about-benefits.json` | Benefits | 3-column grid: Convenience, Comfort, Connection |
| `about-team.json` | Team | 3-column grid of 6 provider cards with avatar initials |
| `about-mission-vision.json` | Mission & Vision | 2-column equal-width cards |
| `about-cta.json` | CTA | Blue-to-teal gradient banner with two buttons |
| `about-page-complete.json` | Full Page | All 7 sections combined |

---

## Quick Start

1. **Import the full page template** via Elementor > Templates > Import:
   `templates/about-page/about-page-complete.json`

2. **Add CSS** — paste both files into Elementor > Site Settings > Custom CSS:
   - `css/healthcare-elementor-styles.css`
   - `css/about-page-styles.css`

3. **Apply to a page** — create or edit a page, click "Edit with Elementor", insert the imported template from "My Templates".

4. **Update content** — replace placeholder text, names, and button links with your actual content.

---

## Section-by-Section Breakdown

### 1. Hero Section (`about-hero.json`)

**Layout:** Two-column grid (left: content, right: hero card)

**Left column contains:**
- Eyebrow label: "About Our Platform" (pill badge, blue text)
- H1 heading: Platform mission statement
- Lead paragraph: Platform description (muted color, 1.08rem)
- Two action buttons: "Explore Services" (primary blue) + "Meet Our Providers" (white secondary)

**Right column contains (Hero Card):**
- Card with gradient background (white → soft blue, #f0f7ff)
- Border: `1px solid #dce8f8`, border-radius: 28px
- Sub-heading: "What We Offer"
- Short description paragraph
- 2×2 grid of mini-cards (Mental Health, Medical Care, Virtual Visits, Trusted Professionals)

**Responsive behavior:**
- Desktop: 2-column grid
- Tablet (≤1024px): 2-column grid (both columns)
- Mobile (≤760px): Single column, hero card stacks below text

---

### 2. Stats Section (`about-stats.json`)

**Layout:** 4-column grid of white stat boxes

**Each stat box contains:**
- Large number in teal (`#0f766e`) — 2rem, bold
- Label in muted gray — 0.95rem

**Default stats:**
- `2` — Care Categories
- `8+` — Sample Professionals
- `100%` — Virtual Access
- `1` — Connected Care Experience

**Key difference from homepage stats:**
The homepage stats bar uses a blue-to-teal gradient background with white text. The About page stats use white cards with teal-colored numbers — a lighter, more open design.

**Responsive behavior:**
- Desktop: 4 columns
- Tablet (≤980px): 2 columns
- Mobile (≤640px): 1 column

---

### 3. Services Section (`about-services.json`)

**Layout:** 2-column split with equal-width cards

**Section header:** Left-aligned H2 + lead paragraph (max-width 760px)

**Left card (Mental Health Care):**
- Icon: 🧠 (52×52px gradient icon box)
- H3 heading
- Description paragraph
- Bulleted list using `hc-service-list` CSS class:
  - Anxiety, stress, and burnout support
  - Trauma-informed care and emotional wellness
  - Teen and adolescent counseling
  - Addiction recovery and behavioral support
  - Relationship and couples counseling

**Right card (Medical Care):**
- Icon: 🩺 (52×52px gradient icon box)
- H3 heading
- Description paragraph
- Bulleted list:
  - Family medicine and routine checkups
  - Internal medicine consultations
  - Preventive care and screenings
  - Blood pressure and chronic condition guidance
  - Heart health education and cardiology support

**Responsive behavior:**
- Desktop + Tablet: 2 columns
- Mobile: 1 column

---

### 4. Benefits Section (`about-benefits.json`)

**Layout:** 3-column grid of feature cards

**Section header:** Left-aligned H2 + lead paragraph

**Cards:**
1. ⏱️ **Convenience** — Book appointments without commuting
2. 🏠 **Comfort** — Receive care from a familiar setting
3. 🤝 **Connection** — Build meaningful provider relationships

**Card structure:** Icon box (52×52px gradient) + H3 + description paragraph

**Responsive behavior:**
- Desktop: 3 columns
- Tablet: 2 columns
- Mobile: 1 column

---

### 5. Team Section (`about-team.json`)

**Layout:** 3-column grid of 6 provider cards

**Section header:** Left-aligned H2 + lead paragraph

**Each team card contains:**
- Avatar circle: 72×72px, circular (border-radius 50%), gradient background (#dbeafe → #d1fae5)
- Initials text: 24px, bold, primary dark blue (`#1d4ed8`)
- Provider name: H3, 1.2rem
- Description text: muted gray

**Providers featured:**
| Initials | Name | Specialty |
|----------|------|-----------|
| JW | Dr. James Walker | Addiction Recovery Specialist |
| OB | Dr. Olivia Bennett | Adolescent Therapist |
| DB | Dr. Daniel Brooks | Couples Therapist |
| AP | Dr. Andrew Patel | Family Medicine |
| MG | Dr. Melissa Grant | Internal Medicine |
| RC | Dr. Robert Chen | Cardiologist |

**Responsive behavior:**
- Desktop: 3 columns
- Tablet: 2 columns
- Mobile: 1 column

---

### 6. Mission & Vision Section (`about-mission-vision.json`)

**Layout:** 2-column equal-width grid

**Left card (Mission):**
- H2: "Our Mission"
- Two paragraphs describing accessible, virtual-first care

**Right card (Vision):**
- H2: "Our Vision"
- Two paragraphs describing the future-forward care model

**Responsive behavior:**
- Desktop + Tablet: 2 columns
- Mobile: 1 column (Mission card first, Vision card below)

---

### 7. CTA Section (`about-cta.json`)

**Layout:** Full-width gradient box with left-aligned content

**CTA box styling:**
- Background: `linear-gradient(135deg, #1e3a8a 0%, #0f766e 100%)`
- Border-radius: 30px
- Padding: 42px (desktop), 28px (mobile)

**Content:**
- H2 heading: "Support for Mind and Body, Wherever You Are" (white)
- Description paragraph (white, 86% opacity)
- Two buttons: "View Providers" (primary blue) + "Learn More" (white secondary)

**Difference from homepage CTA:**
- Left-aligned content (homepage CTA is centered)
- Different gradient direction (135deg)
- Different heading and button labels

---

## How to Modify Team Member Cards

### Changing a provider's name

1. Open the About page in Elementor
2. Click the team section grid
3. Click the provider card you want to edit
4. Click the Heading widget showing the provider's name
5. Update the **Title** field in the Content tab

### Changing avatar initials

1. Click the Heading widget inside the team card that shows initials (e.g., "JW")
2. Update the **Title** field to the new initials (e.g., "SM" for Sarah Mitchell)
3. The circular gradient background is applied via container settings — the initials will automatically stay centered

### Adding a new team member

1. In Elementor, right-click any existing team card container
2. Select **Duplicate**
3. Update the avatar initials, name, and description in the duplicated card
4. The new card will automatically follow the grid layout

### Removing a team member

1. Click the team card container you want to remove
2. Right-click and select **Delete**
3. The remaining cards will reflow in the grid automatically

---

## How to Customize Stats

Each stat box contains two Heading widgets: one for the number and one for the label.

1. Click the stat box container in Elementor
2. Click the number Heading widget (e.g., "8+")
3. Update the **Title** field with your actual statistic
4. Click the label Heading widget (e.g., "Sample Professionals")
5. Update the **Title** field with your label text

### Changing stat number color

The stat numbers use the teal secondary color (`#0f766e`) by default.

To change the color:
1. Click the stat number Heading widget
2. Go to the **Style** tab
3. Under **Text Color**, set your preferred color
4. Repeat for each stat box, or use a global CSS override:

```css
/* Change all About page stat numbers to a custom color */
/* Add to Elementor Site Settings > Custom CSS */
.hc-about-stat-number {
  color: #your-color !important;
}
```

---

## How to Update Mission/Vision Content

1. Click the Mission or Vision card in Elementor
2. Click each Text Editor widget within the card
3. Update the paragraph content in the editor
4. Save the page

### Adding a third card (e.g., "Our Values")

1. Right-click the Mission card container and select **Duplicate**
2. Move the duplicate to the right using the navigator panel
3. Update the H2 heading and paragraphs with your new content
4. Go to the grid container settings and change **Columns** from 2 to 3

---

## Customizing the Hero Card

The hero card (right column) uses an Elementor container with a gradient background. To change the card's appearance:

**Background gradient:**
1. Click the hero card container (the right column card with gradient)
2. Go to **Style** > **Background**
3. Update Color 1 (currently `#ffffff`) and Color 2 (currently `#f0f7ff`) to your brand colors

**Mini-card backgrounds:**
1. Click any mini-card container
2. Go to **Style** > **Background**
3. Update the **Background Color** (currently `rgba(255, 255, 255, 0.95)`)

**Adding a 5th mini-card:**
1. Right-click an existing mini-card container and select **Duplicate**
2. The 2×2 grid container will automatically expand to accommodate the new card
3. Update the title and text in the duplicated card

---

## CSS Classes Reference

These classes from `about-page-styles.css` can be applied to Elementor elements via the **Advanced > CSS Classes** field:

| Class | Element | Description |
|-------|---------|-------------|
| `hc-about-hero-card` | Container | Hero card with gradient background |
| `hc-mini-card` | Container | Mini-card inside the hero card grid |
| `hc-about-stat-box` | Container | White stat box with teal numbers |
| `hc-about-stat-number` | Heading widget | Large teal stat number |
| `hc-about-stat-label` | Heading widget | Muted stat label |
| `hc-about-avatar` | Heading widget | 72px circular avatar with gradient |
| `hc-about-team-card` | Container | Team card flex column layout |
| `hc-about-cta-box` | Container | About page CTA gradient box |
| `hc-about-hero-wrap` | Container | Hero wrap with 1.15fr/0.85fr columns |
| `hc-service-list` | Text Editor | Bulleted list with colored dot markers |

---

## Responsive Breakpoints

| Breakpoint | Width | Layout changes |
|------------|-------|----------------|
| Desktop | > 1024px | All grid layouts at full column count |
| Tablet | ≤ 1024px | Hero and most grids become 2 columns |
| Mobile | ≤ 760px | All grids collapse to 1 column, reduced padding |

The templates use Elementor's built-in responsive grid settings (`_tablet_grid_columns_grid`, `_mobile_grid_columns_grid`) so no additional CSS is required for basic responsive behavior.

---

## Color Reference

All About page templates use the same color system as the homepage:

| Variable | Value | Usage |
|----------|-------|-------|
| `--hc-bg` | `#f6f8fb` | Page background |
| `--hc-surface` | `#ffffff` | Card backgrounds |
| `--hc-text` | `#1f2937` | Headings and body text |
| `--hc-muted` | `#6b7280` | Descriptive and secondary text |
| `--hc-primary` | `#2563eb` | Buttons, eyebrow labels, bullet dots |
| `--hc-primary-dark` | `#1d4ed8` | Button hover, avatar initials color |
| `--hc-secondary` | `#0f766e` | Stat numbers, gradient endpoints |
| `--hc-border` | `#e5e7eb` | Card borders, secondary button borders |

---

## File Structure

```
templates/
  about-page/
    about-page-complete.json    ← Full page (all 7 sections)
    about-hero.json             ← Hero section
    about-stats.json            ← Stats grid
    about-services.json         ← Services split
    about-benefits.json         ← Benefits grid
    about-team.json             ← Team grid
    about-mission-vision.json   ← Mission & Vision cards
    about-cta.json              ← CTA banner

css/
  healthcare-elementor-styles.css   ← Base styles + About page avatar/stat additions
  about-page-styles.css             ← About page-specific components
```

---

## Troubleshooting

**Avatar initials not centered**
Add `css/about-page-styles.css` to Elementor Site Settings > Custom CSS. The avatar uses fixed width/height and inline-flex to center the text.

**Stat numbers appear in the wrong color**
Ensure `healthcare-elementor-styles.css` is loaded. The stat numbers reference the `--hc-secondary` CSS variable.

**Hero two columns stacking on desktop**
Verify the hero wrap container has **Container Type** set to **Grid** and **Columns** set to 2 in the Layout tab.

**Service list bullets not showing**
Ensure `healthcare-elementor-styles.css` is added to custom CSS. The bullets require the `.hc-service-list` class to be applied to the `<ul>` element inside a Text Editor widget.

**Template imports but appears unstyled**
1. Confirm both CSS files are added to Elementor > Site Settings > Custom CSS
2. Clear Elementor's CSS cache: Elementor > Tools > Regenerate Files
3. Enable Flexbox Containers: Elementor > Settings > Features > Flexbox Container → Active
