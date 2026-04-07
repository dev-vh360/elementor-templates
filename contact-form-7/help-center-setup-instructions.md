# Help Center CF7 Setup Instructions

Step-by-step guide for setting up the Help Center Contact Form 7 form with the Videohub360 community and streaming demo.

---

## Prerequisites

- [ ] WordPress 6.0+ installed
- [ ] Elementor (free) 3.15+ installed and activated
- [ ] Contact Form 7 plugin installed and activated
- [ ] Help Center Elementor template imported (see Step 5)

---

## Step 1 — Install Contact Form 7

1. Go to **Plugins > Add New** in your WordPress dashboard.
2. Search for **Contact Form 7**.
3. Click **Install Now**, then **Activate**.

---

## Step 2 — Create the Help Center Support Form

1. Go to **Contact > Add New** in your WordPress dashboard.
2. Enter the form title: **Help Center Support Form**
3. In the **Form** tab, replace the default form code with the content from `help-center-form-configuration.txt`.
4. Click **Save**.

---

## Step 3 — Configure the Mail Template

1. Click the **Mail** tab in the same CF7 form editor.
2. Set the **To** field to your support email address.
3. Set the **Subject** to:
   ```
   [your-site] Help Center Support Request - [issue-type]
   ```
4. Set **Additional Headers** to:
   ```
   Reply-To: [your-name] <[your-email]>
   ```
5. Replace the **Message body** with the content from `help-center-mail-template.txt`.
6. Click **Save**.

---

## Step 4 — Set Confirmation Messages

1. Click the **Messages** tab in the CF7 form editor.
2. Update **Sender's message was sent successfully** to:
   ```
   Thank you for contacting us! We have received your support request and will respond within 24–48 hours.
   ```
3. Click **Save**.

---

## Step 5 — Import the Help Center Elementor Template

1. Go to **Elementor > Templates** in your WordPress dashboard.
2. Click the **Import Templates** button (folder icon) in the top-right corner.
3. Click **Select File** and choose `templates/help-center/help-center-complete-cf7.json`.
4. Click **Import Now**.
5. The template will appear in your library under **Pages**.

---

## Step 6 — Apply the Template to a Page

1. Create a new page in WordPress (**Pages > Add New**).
2. Name it **Help Center**.
3. Under **Page Attributes**, set the **Template** to **Elementor Canvas** (full-width, no sidebar).
4. Click **Edit with Elementor**.
5. Click the **folder icon** (My Templates) in the bottom toolbar.
6. Find **Help Center - Complete Page (Contact Form 7)** and click **Insert**.

---

## Step 7 — Replace the Form ID

1. In the Elementor editor, locate the **Submit a Support Request** form card in the lower section of the page.
2. Click on the **Shortcode** widget inside the form card.
3. In the left panel, find the shortcode:
   ```
   [contact-form-7 id="YOUR_FORM_ID" title="Help Center Support Form"]
   ```
4. Go back to **Contact > Contact Forms** and find your **Help Center Support Form**.
5. Copy the form ID shown next to the form name (e.g., `ID: 123`).
6. Replace `YOUR_FORM_ID` in the Elementor Shortcode widget with your actual form ID:
   ```
   [contact-form-7 id="123" title="Help Center Support Form"]
   ```
7. Click **Update** in the Elementor editor.

---

## Step 8 — Add the Help Center CSS

1. In the Elementor editor, click the **hamburger menu** (☰) in the top-left corner.
2. Go to **Site Settings > Custom CSS**.
3. Open `css/help-center-styles.css` and paste the contents into the Custom CSS field.
4. If you haven't already added the base stylesheet, also paste the contents of `css/healthcare-elementor-styles.css` and `css/contact-form-styles.css`.
5. Click **Save Changes**.

---

## Step 9 — Test the Form

1. Preview the Help Center page in your browser.
2. Fill out all required fields and click **Submit Support Request**.
3. Verify the confirmation message appears.
4. Check your inbox for the notification email.
5. Test with invalid data to confirm validation messages work correctly.

---

## Optional — Add Spam Protection

### Option A: reCAPTCHA v3
1. Get a reCAPTCHA v3 site/secret key from [google.com/recaptcha](https://www.google.com/recaptcha).
2. In CF7 go to **Contact > Integration** and enter your keys.
3. Add `[recaptcha]` to the form after the last field and before `[submit]`.

### Option B: Honeypot
1. Install the **Contact Form 7 Honeypot** plugin.
2. Add `[honeypot honeypot-field]` anywhere in the form code.

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Form shows "YOUR_FORM_ID" text | Replace the placeholder in the Shortcode widget with your actual CF7 form ID |
| Form not visible on page | Ensure Contact Form 7 is installed and activated |
| Form fields unstyled | Add `css/contact-form-styles.css` and `css/help-center-styles.css` to Custom CSS |
| Emails not received | Check your spam folder; verify the "To" address in CF7 Mail settings |
| Grid layout not showing | Enable Elementor Flexbox Containers: **Elementor > Settings > Experiments** |
| Mobile layout not stacking | Confirm `_tablet_container_type` is set to `flex` in the grid container responsive settings |
| Dropdown not styled | Ensure `contact-form-styles.css` is loaded; the custom chevron uses an SVG background-image |
| Validation errors not showing | CF7 validation messages require the `.wpcf7` wrapper to be present; do not strip it |
