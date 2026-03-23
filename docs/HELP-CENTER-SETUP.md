# Help Center Setup Instructions

Complete setup guide for the Help Center page template in the Videohub360 community and streaming demo package.

---

## Prerequisites

Before you begin, make sure you have:

- [ ] WordPress **6.0 or later** installed
- [ ] **Elementor** (free) plugin installed and activated — version 3.15+
- [ ] **Contact Form 7** (free) plugin installed and activated
- [ ] A theme compatible with Elementor (e.g., Hello Elementor, Astra, OceanWP)
- [ ] Administrator access to your WordPress dashboard

> **Elementor Pro is NOT required.** The Help Center template uses only Elementor Free widgets (Container, Heading, Text Editor, Shortcode, Accordion).

---

## Step 1 — Install Required Plugins

### Contact Form 7

1. Go to **Plugins > Add New**.
2. Search for **Contact Form 7**.
3. Click **Install Now**, then **Activate**.

### Elementor (if not already installed)

1. Go to **Plugins > Add New**.
2. Search for **Elementor Website Builder**.
3. Click **Install Now**, then **Activate**.

---

## Step 2 — Create the CF7 Support Form

1. Go to **Contact > Add New** in your WordPress dashboard.
2. Enter the form name: **Help Center Support Form**
3. In the **Form** tab, delete the default content and paste in the code from:
   ```
   contact-form-7/help-center-form-configuration.txt
   ```
4. Click **Save** and note the form ID shown next to the form title (e.g., `ID: 123`).

---

## Step 3 — Configure the Mail Template

1. In the same form editor, click the **Mail** tab.
2. Set the **To** field to your support email address.
3. Set the **Subject** to:
   ```
   [your-site] Help Center Support Request - [issue-type]
   ```
4. Set **Additional Headers** to:
   ```
   Reply-To: [your-name] <[your-email]>
   ```
5. Replace the **Message body** with the content from `contact-form-7/help-center-mail-template.txt`.
6. Click **Save**.

---

## Step 4 — Import the Help Center Template

1. Go to **Elementor > Templates** in your WordPress dashboard.
2. Click the **Import Templates** button (folder icon) in the top-right corner.
3. Select `templates/help-center/help-center-complete-cf7.json`.
4. Click **Import Now**.
5. The template will appear under **Pages** in the template library.

### Importing Individual Sections

If you prefer to use individual section templates, import each file separately:

| File | Section |
|------|---------|
| `help-center-hero.json` | Hero section |
| `help-center-categories.json` | Support categories grid |
| `help-center-faq.json` | FAQ accordion |
| `help-center-form-cf7.json` | Support request form card |
| `help-center-support-sidebar.json` | Support info sidebar |

Imported sections appear under **Elementor > Templates > Sections**.

---

## Step 5 — Apply the Template to a Page

1. Go to **Pages > Add New** in WordPress.
2. Title the page **Help Center**.
3. Under **Page Attributes**, set the template to **Elementor Canvas** (full-width, no sidebar).
4. Click **Edit with Elementor**.
5. In the Elementor editor, click the **folder icon** (My Templates) in the bottom toolbar.
6. Find **Help Center - Complete Page (Contact Form 7)** and click **Insert**.
7. Confirm any prompts about replacing existing content.

---

## Step 6 — Replace the Form ID Placeholder

The template includes a CF7 shortcode placeholder that must be updated with your actual form ID.

1. In the Elementor editor, scroll down to the **Submit a Support Request** section.
2. Click the **Shortcode** widget inside the form card.
3. In the left panel, locate:
   ```
   [contact-form-7 id="YOUR_FORM_ID" title="Help Center Support Form"]
   ```
4. Replace `YOUR_FORM_ID` with the form ID you noted in Step 2:
   ```
   [contact-form-7 id="123" title="Help Center Support Form"]
   ```
5. Click **Update** to save.

---

## Step 7 — Add the Custom CSS

The Help Center requires CSS from both the base stylesheet and the Help Center-specific stylesheet.

### Method A: Elementor Site Settings (Recommended)

1. In the Elementor editor, click the **hamburger menu** (☰) at the top-left.
2. Go to **Site Settings > Custom CSS**.
3. Paste the contents of each CSS file in this order:
   - `css/healthcare-elementor-styles.css` (base tokens and components)
   - `css/contact-form-styles.css` (CF7 form field styling)
   - `css/help-center-styles.css` (Help Center-specific components)
4. Click **Save Changes**.

> If you have already added the base and contact form CSS for other pages, only add `css/help-center-styles.css`.

### Method B: Enqueue via Child Theme

Add to your child theme's `functions.php`:

```php
function hc_enqueue_help_center_styles() {
    wp_enqueue_style(
        'help-center-styles',
        get_stylesheet_directory_uri() . '/css/help-center-styles.css',
        ['healthcare-elementor-styles'],
        '1.0.0'
    );
}
add_action( 'wp_enqueue_scripts', 'hc_enqueue_help_center_styles' );
```

Copy `css/help-center-styles.css` to `your-child-theme/css/`.

### Method C: Page-Level Custom CSS

1. Open the Help Center page in the Elementor editor.
2. Click **Page Settings** (gear icon at bottom-left).
3. Go to the **Advanced** tab and find **Custom CSS**.
4. Paste the CSS there (applies only to this page).

---

## Step 8 — Update Support Information

Replace the placeholder contact details with your actual support information:

1. Click on the **Support Email** value in the sidebar card.
2. Replace `support@videohub360.com` with your actual support email.
3. Click on the **Response Time** value and update if needed.
4. Click on the **Best For** value and update to match your platform's support areas.
5. Update or remove the **Demo Note** box as appropriate.

---

## Step 9 — Test the Form

1. Click **Publish** (or **Preview**) in the Elementor editor.
2. Fill out all required fields in the support form.
3. Click **Submit Support Request**.
4. Verify the success confirmation message appears.
5. Check your inbox for the notification email from CF7.
6. Test validation by submitting with empty required fields.

---

## Testing Checklist

Before going live, verify:

- [ ] Hero heading and description display correctly
- [ ] All 6 category cards are visible and styled
- [ ] FAQ accordion expands and collapses correctly
- [ ] Support form renders (no shortcode text visible)
- [ ] Form validation works (required fields enforced)
- [ ] Form submission sends an email notification
- [ ] Success message appears after submission
- [ ] Support sidebar information is accurate
- [ ] Page is fully responsive on mobile and tablet
- [ ] Elementor Canvas layout is applied (no sidebar, full width)

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Shortcode text shown instead of form | Replace `YOUR_FORM_ID` in the Shortcode widget with your actual CF7 form ID |
| Form fields are unstyled | Add `css/contact-form-styles.css` to Site Settings > Custom CSS |
| FAQ accordion is unstyled | Add `css/help-center-styles.css` to Site Settings > Custom CSS |
| Category cards show in a single column | Ensure Elementor Flexbox Containers are enabled: **Elementor > Settings > Experiments** |
| Emails not arriving | Check your spam folder; verify the To address in CF7 Mail settings |
| Form not visible | Ensure Contact Form 7 plugin is installed and activated |
| Layout has a sidebar | Set the page template to **Elementor Canvas** in Page Attributes |
| Mobile layout not stacking | Confirm the grid container has `_tablet_container_type: flex` in its responsive settings |

---

## Related Files

| File | Purpose |
|------|---------|
| `templates/help-center/help-center-complete-cf7.json` | Complete Help Center page template |
| `templates/help-center/help-center-*.json` | Individual section templates |
| `contact-form-7/help-center-form-configuration.txt` | CF7 form code |
| `contact-form-7/help-center-mail-template.txt` | Email template settings |
| `css/help-center-styles.css` | Help Center component styles |
| `css/contact-form-styles.css` | CF7 form field styling |
| `css/healthcare-elementor-styles.css` | Base design tokens and components |
| `docs/HELP-CENTER-GUIDE.md` | Help Center structure and customization reference |
