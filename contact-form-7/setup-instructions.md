# Contact Form 7 — Setup Instructions

This guide walks you through installing, configuring, and connecting Contact Form 7 with the Contact page Elementor template.

---

## Prerequisites

- WordPress 6.0 or later
- Elementor (free) 3.15 or later
- Contact Form 7 plugin installed and activated
- Administrator access to your WordPress dashboard

---

## Step 1 — Install Contact Form 7

1. In your WordPress dashboard go to **Plugins > Add New**.
2. Search for **Contact Form 7**.
3. Click **Install Now** next to the plugin by Takayuki Miyoshi.
4. Click **Activate** once installation completes.

---

## Step 2 — Create the Contact Form

1. Go to **Contact > Add New** in your WordPress dashboard.
2. Give the form a name, e.g. **Virtual Health Contact Form**.
3. In the **Form** tab, delete all default content and paste the code from `contact-form-7/form-configuration.txt`.
4. Click **Save**.
5. Note the shortcode shown at the top of the form editor (e.g. `[contact-form-7 id="123" title="Virtual Health Contact Form"]`). You will need the numeric **ID** in Step 4.

---

## Step 3 — Configure the Mail Template

1. In the same form, click the **Mail** tab.
2. Set the fields using the values from `contact-form-7/mail-template.txt`:
   - **To** — your recipient email address
   - **From** — `[your-name] <[your-email]>`
   - **Subject** — `New Contact Form Submission - [care-type]`
   - **Message Body** — paste the message body from `mail-template.txt`
3. Click **Save**.

---

## Step 4 — Configure Success & Validation Messages

1. Click the **Messages** tab in the form editor.
2. Update the messages to match your design tone:
   - **Sender's message was sent successfully** → `Thank you for contacting us! We will respond to your inquiry as soon as possible.`
   - **Sender's message failed to send** → `Something went wrong. Please try again later.`
   - Required field validation → `Please fill in this field.`
3. Click **Save**.

---

## Step 5 — Import the Elementor Template

1. In your WordPress dashboard go to **Elementor > Templates**.
2. Click **Import Templates** (folder icon, top-right).
3. Select `templates/contact-page/contact-page-complete-cf7.json`.
4. Click **Import Now**.

---

## Step 6 — Update the Shortcode in Elementor

The template includes a **Shortcode** widget (built into Elementor Free) pre-filled with a placeholder shortcode. You must update it with your actual form ID.

1. Open the imported Contact page template in the Elementor editor.
2. In the left-column form card, click on the **Shortcode** widget. It displays the placeholder text:
   `[contact-form-7 id="YOUR_FORM_ID" title="Virtual Health Contact Form"]`
3. In the widget settings panel on the left, replace `YOUR_FORM_ID` with the numeric ID of the form you created in Step 2 (e.g. `123`). The shortcode should look like:
   `[contact-form-7 id="123" title="Virtual Health Contact Form"]`
4. Click **Save** and publish the page.

> **Where to find your form ID:** Go to **Contact > Contact Forms**. The ID is shown in the form list or in the shortcode at the top of the form editor (e.g. `[contact-form-7 id="123" ...]`).

---

## Step 7 — Add Custom CSS

To make the CF7 form match the design exactly:

1. Copy the contents of `css/contact-form-styles.css`.
2. In your WordPress dashboard go to **Elementor > Site Settings > Custom CSS** (or **Appearance > Customize > Additional CSS**).
3. Paste the CSS and save.

---

## Step 8 — Test the Form

1. Visit the contact page on the frontend.
2. Fill in all fields and submit.
3. Verify you receive the notification email.
4. Check that the success message appears.

---

## Spam Protection (Recommended)

### Option A — reCAPTCHA v3

1. Go to [google.com/recaptcha](https://www.google.com/recaptcha) and register your site for **reCAPTCHA v3**.
2. Copy your Site Key and Secret Key.
3. In WordPress go to **Contact > Integration > reCAPTCHA**.
4. Paste both keys and save.
5. Add `[recaptcha]` to the CF7 form code (above the submit button).

### Option B — Honeypot (No API key required)

Install the **Contact Form 7 Honeypot** plugin and add `[honeypot honeypot-field]` to your form.

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Form does not appear | Verify the Shortcode widget contains your correct CF7 shortcode with the right form ID |
| Emails not received | Check spam folder; verify server mail settings; install **WP Mail SMTP** plugin |
| Styles not applying | Confirm `contact-form-styles.css` is added to Site Settings > Custom CSS |
| Form submits but page reloads | Enable AJAX in CF7 form settings or check for JS conflicts |
| Select dropdown not styled | Ensure `.wpcf7 select` rules are in your custom CSS |
| Success message not showing | Check CF7 Messages tab; clear page/CF7 caches |
