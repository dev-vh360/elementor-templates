# Customization Guide

This guide explains how to adapt the Healthcare Platform Elementor Templates to match your brand and content.

---

## Changing Colors

### Method 1: Update CSS Variables (Recommended)

All colors are defined as CSS custom properties at the top of `css/healthcare-elementor-styles.css`. To change the primary blue to another color, simply update the value:

```css
:root {
  --hc-primary:      #2563eb;   /* ← change this to your brand color */
  --hc-primary-dark: #1d4ed8;   /* ← change this to a darker shade */
}
```

This single change will cascade to buttons, step numbers, eyebrow labels, badge backgrounds, and bullet points.

### Method 2: Elementor Global Colors

1. Go to **Elementor > Site Settings > Global Colors**.
2. Add your brand colors there.
3. In each widget, replace the hardcoded color with your global color.

> **Tip:** Use Method 1 for bulk changes and Method 2 for fine-grained control inside the Elementor editor.

---

## Changing Fonts

The templates use the system font stack (`Arial, Helvetica, sans-serif`) by default. To use a custom font:

### Using Google Fonts

1. Go to **Elementor > Site Settings > Custom Fonts** (or use the Theme's font settings).
2. Add your Google Font and assign it as the default body/heading font.

Alternatively, add this to the top of the Custom CSS field:

```css
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap');

body,
.elementor-widget-heading .elementor-heading-title,
.elementor-widget-text-editor {
  font-family: 'Inter', Arial, sans-serif !important;
}
```

Replace `Inter` with any Google Font of your choice.

---

## Updating Section Content

### Headings and Body Text

Click any **Heading** or **Text Editor** widget in the Elementor editor and update the content directly in the left panel. No code changes needed.

### Eyebrow Labels

The eyebrow labels (e.g., "How It Works", "Services") are Heading widgets styled via inline settings. Click the widget and change the **Title** field.

### Testimonials

1. Click inside a testimonial card.
2. Click the **Text Editor** widget to change the quote text.
3. Click the **Heading** widget below it to change the patient name.

### Stats Numbers

1. Click inside the Stats Bar section.
2. Click each stat's number Heading widget and update the **Title** field.

### Provider Cards

For each provider card:
1. Click the **Image** widget → update photo.
2. Click the provider name **Heading** → update name.
3. Click the specialty **Heading** (badge) → update specialty.
4. Click the **Text Editor** → update description.
5. Click the **Button** → update link URL.

---

## Adding or Removing Sections

### Removing a Section

In the Elementor editor, right-click on the outer container of any section and select **Delete**. Confirm the deletion.

### Duplicating a Section

Right-click the outer container and select **Duplicate**. Then edit the duplicated section's content.

### Adding a New Provider Card

1. Click on an existing provider card container.
2. Right-click and choose **Duplicate**.
3. Update the image, name, badge, description, and button in the new card.
4. The grid will automatically accommodate the new card.

### Adding a New Testimonial

Same process as adding a provider card — duplicate an existing testimonial card and update its content.

---

## Adjusting the Grid Layout

### Changing Column Count

1. Click on a grid container (the one holding the cards).
2. In the left panel, go to **Layout**.
3. Adjust **Columns** under the Grid settings.

Common grid values:
- 3 columns: How It Works, Providers, Testimonials
- 4 columns: Why Choose Us, Stats Bar
- 2 columns: Services

### Adjusting Responsive Breakpoints

The templates include responsive overrides for tablet (≤980px) and mobile (≤640px). To customize:

1. Switch to the Tablet or Mobile breakpoint at the bottom of the Elementor editor.
2. Adjust the column count or padding for that breakpoint specifically.

---

## Modifying the Stats Bar

The stats bar uses a gradient background. To change the gradient:

1. Click the inner stats container (the colored bar).
2. Go to **Style > Background**.
3. Change the gradient colors.

Suggested alternative gradients:

```css
/* Purple to blue */
background: linear-gradient(135deg, #4f46e5 0%, #0ea5e9 100%);

/* Orange to red */
background: linear-gradient(135deg, #f97316 0%, #dc2626 100%);

/* Green */
background: linear-gradient(135deg, #16a34a 0%, #0d9488 100%);
```

---

## Modifying the CTA Section

The CTA box uses a dark multi-stop gradient. To change it, click the CTA box container and update the **Background** gradient under the **Style** tab.

You can also change the button arrangement — the two buttons are inside a Flex container with `flex-wrap: wrap` so they will stack on narrow screens automatically.

---

## Replacing Emoji Icons with SVG or Font Icons

The icon boxes use emoji characters (🧠, 🩺, 🌍, etc.) for simplicity. For a more polished look, replace them with SVG icons or icon fonts:

### Using SVG Icons

1. Click the icon heading widget (the one with the emoji).
2. Replace it with an **Image** widget.
3. Upload your SVG to the Media Library and insert it.
4. Set width and height to 32–40px.

### Using Font Awesome (requires Elementor Pro or a separate icon plugin)

1. Remove the heading widget containing the emoji.
2. Add an **Icon** widget (available in Elementor Pro).
3. Choose your icon from the Font Awesome library.
4. Apply the `hc-icon` CSS class to the widget for consistent sizing.

---

## Changing Section Spacing

To increase or decrease vertical padding for any section:

1. Click the outer container of the section.
2. Go to **Advanced > Margin and Padding**.
3. Adjust the **Top** and **Bottom** padding values.

Default values:
- Desktop: 76px top and bottom
- Mobile: 58px top and bottom (set in the responsive CSS)

---

## Saving Your Customizations as a Template

After making changes, save your customized version as a new Elementor template:

1. Click the **Save** dropdown (arrow next to the Save button) in the Elementor editor.
2. Choose **Save as Template**.
3. Give it a name (e.g., "Healthcare Homepage — My Brand") and click **Save**.

This lets you reuse your customized template on other pages.

---

## About Page Customization

The About page has several unique components that differ from the homepage. For full About page customization instructions, see [ABOUT-PAGE-GUIDE.md](ABOUT-PAGE-GUIDE.md).

### Quick Reference — About Page Unique Elements

**Changing team member avatars:**
The avatar circles use Heading widgets with a circular gradient background. To update:
1. Click the Heading widget showing the initials (e.g., "JW")
2. Update the **Title** field with the new initials
3. The gradient background and circular shape are container settings — they remain unchanged

**Changing stat numbers and labels:**
The About page stats are white cards (not a gradient bar). Each stat box contains two Heading widgets:
1. Click the large number Heading widget and update the **Title** (e.g., change "8+" to "20+")
2. Click the label Heading widget and update the **Title**

**Adding or removing team members:**
- To add: Right-click any team card container → **Duplicate**, then edit the content
- To remove: Click the team card container → Right-click → **Delete**

**Updating the hero card mini-cards:**
The hero card contains a 2×2 grid of mini-cards. Click any mini-card's Heading or Text Editor widget to edit the title and description.

---

## Performance Tips

- **Optimize provider images** before upload — aim for under 80 KB per avatar.
- **Enable Elementor's CSS Print Method** (External File) under **Elementor > Settings > Advanced** to reduce inline styles.
- **Use a caching plugin** such as WP Rocket or W3 Total Cache to speed up page loads.
- **Defer non-critical CSS** using your caching plugin's settings or a performance plugin.
