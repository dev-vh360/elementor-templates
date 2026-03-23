# Alternative Form Plugins Guide

This guide explains how to use form plugins other than Contact Form 7 with the Healthcare Platform Contact page template. All options produce the same visual result when paired with `css/contact-form-styles.css`.

---

## Comparison Table

| Plugin | Price | Ease of Use | Spam Protection | Conditional Logic | Best For |
|--------|-------|-------------|-----------------|-------------------|----------|
| **Contact Form 7** | Free | Moderate (shortcode-based) | reCAPTCHA / Honeypot | No (add-on) | Simple forms, minimal setup |
| **WPForms Lite** | Free / Pro | Easy (drag-and-drop) | hCaptcha, reCAPTCHA | Pro only | Beginners, non-technical users |
| **Elementor Pro Forms** | Pro ($59+/yr) | Very Easy (native Elementor) | reCAPTCHA built-in | Yes | Elementor Pro users |
| **Gravity Forms** | $59+/yr | Advanced | reCAPTCHA | Yes (advanced) | Complex workflows, enterprise |

---

## Option 1 — WPForms

### When to Use
- You prefer a visual drag-and-drop form builder
- You want a simpler setup than CF7
- You don't need complex conditional logic

### Installation

1. Go to **Plugins > Add New** and search for **WPForms Lite**.
2. Install and activate the plugin.
3. Go to **WPForms > Add New**.
4. Select the **Simple Contact Form** template.
5. Customize the fields to match the contact form design:
   - Add: Name, Email, Dropdown (care type), Message
   - Set dropdown options: Mental Health Care, Medical Care, General Question, Technical Support
6. In **Settings > Notifications**, configure the email recipient and subject.
7. In **Settings > Confirmations**, set the success message:
   `Thank you for contacting us! We will respond to your inquiry as soon as possible.`
8. Save the form.

### Add to Elementor

1. In the Elementor editor, add a **WPForms** widget (appears after WPForms is installed).
2. Select your form from the dropdown.
3. The form will render inside the card layout.

### CSS Targeting

WPForms uses different wrapper classes. Add the following to your custom CSS alongside `contact-form-styles.css`:

```css
/* WPForms field override */
.wpforms-container input[type="text"],
.wpforms-container input[type="email"],
.wpforms-container select,
.wpforms-container textarea {
  padding: 12px 14px !important;
  border-radius: 10px !important;
  border: 1px solid #e5e7eb !important;
  font-size: 14px !important;
  margin-bottom: 18px !important;
}

.wpforms-container textarea {
  min-height: 130px !important;
}

.wpforms-container .wpforms-submit {
  background: #2563eb !important;
  color: #ffffff !important;
  padding: 14px 20px !important;
  border-radius: 12px !important;
  font-weight: 600 !important;
  border: none !important;
}

.wpforms-container .wpforms-submit:hover {
  background: #1e4fd1 !important;
}
```

---

## Option 2 — Elementor Pro Forms

### When to Use
- You already have Elementor Pro
- You want the tightest integration with the Elementor editor
- You want to style the form entirely within Elementor (no custom CSS needed)

### Setup

1. Upgrade to or install **Elementor Pro**.
2. Open the Contact page template in the Elementor editor.
3. Delete the Contact Form 7 widget from the form card.
4. Search for **Form** in the Elementor widget panel and drag it into the form card container.
5. Configure fields in the **Content > Form Fields** panel:
   - Add: Name (text), Email (email), Select (care type), Message (textarea)
   - For the Select field, set options: Mental Health Care | Medical Care | General Question | Technical Support
6. In **Content > Submit Button**, set label to **Send Message**.
7. In **Actions After Submit**, configure:
   - Add the **Email** action and set the recipient address
   - Add the **Redirect** or **Message** action for the success message

### Styling

Use the **Style** tab in Elementor to style each field:
- Field border radius: `10px`
- Field padding: `12px 14px`
- Field border color: `#e5e7eb`
- Button background: `#2563eb`
- Button border radius: `12px`
- Button hover background: `#1e4fd1`

No additional custom CSS is needed for Elementor Pro forms.

---

## Option 3 — Gravity Forms

### When to Use
- You need advanced conditional logic (show/hide fields based on user input)
- You need to store form entries in the database
- You need to integrate with CRMs, payment gateways, or other third-party services

### Installation

1. Purchase Gravity Forms at [gravityforms.com](https://www.gravityforms.com) (Basic license: $59/yr).
2. Download the plugin zip from your account.
3. In WordPress go to **Plugins > Add New > Upload Plugin** and upload the zip.
4. Activate the plugin and enter your license key in **Forms > Settings**.

### Create the Form

1. Go to **Forms > New Form** and name it **Virtual Health Contact Form**.
2. Add fields:
   - **Name** — Single Line Text (required)
   - **Email** — Email (required)
   - **Select** — Drop Down with options: Mental Health Care, Medical Care, General Question, Technical Support
   - **Message** — Paragraph Text (required)
3. Under **Form Settings > Notifications**, configure the admin email.
4. Under **Form Settings > Confirmations**, add a Text confirmation:
   `Thank you for contacting us! We will respond to your inquiry as soon as possible.`
5. Save the form.

### Add to Elementor

1. Add the **Gravity Forms** widget to the Elementor editor (install the [Elementor Gravity Forms widget](https://wordpress.org/plugins/elementor-gravity-forms-widget/) if not already available).
2. Select your form from the dropdown.

### CSS Targeting

```css
/* Gravity Forms field override */
.gform_wrapper input[type="text"],
.gform_wrapper input[type="email"],
.gform_wrapper select,
.gform_wrapper textarea {
  padding: 12px 14px !important;
  border-radius: 10px !important;
  border: 1px solid #e5e7eb !important;
  font-size: 14px !important;
  margin-bottom: 18px !important;
}

.gform_wrapper textarea {
  min-height: 130px !important;
}

.gform_wrapper input[type="submit"] {
  background: #2563eb !important;
  color: #ffffff !important;
  padding: 14px 20px !important;
  border-radius: 12px !important;
  font-weight: 600 !important;
  border: none !important;
}

.gform_wrapper input[type="submit"]:hover {
  background: #1e4fd1 !important;
}
```

---

## Summary — Which Plugin Should I Use?

| Scenario | Recommended Plugin |
|----------|--------------------|
| I want free and simple | Contact Form 7 |
| I'm not technical and want drag-and-drop | WPForms Lite |
| I already have Elementor Pro | Elementor Pro Forms |
| I need conditional logic or CRM integrations | Gravity Forms |
| I need entries stored in the database | WPForms Pro or Gravity Forms |
| I want invisible spam protection with no keys | CF7 + Honeypot plugin |
