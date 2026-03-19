# Contact Form Setup Guide

Complete step-by-step instructions for setting up Contact Form 7 with the Healthcare Platform Contact page template.

---

## Prerequisites

Before you begin, make sure you have:

- [ ] WordPress **6.0 or later** installed
- [ ] **Elementor** (free) plugin installed and activated — version 3.15+
- [ ] Administrator access to your WordPress dashboard
- [ ] An outbound email method configured (default WordPress mail, or WP Mail SMTP)

> **Elementor Pro is NOT required.** The CF7 widget for Elementor Free displays Contact Form 7 forms natively.

---

## Part 1 — Install Contact Form 7

### Step 1.1 — Install the Plugin

1. In your WordPress dashboard go to **Plugins > Add New**.
2. Search for **Contact Form 7**.
3. Click **Install Now** next to the result by Takayuki Miyoshi (the official plugin, 5M+ active installs).
4. Click **Activate** after installation completes.

You will now see a **Contact** menu item in your WordPress dashboard.

---

## Part 2 — Create the Contact Form

### Step 2.1 — Open the Form Editor

1. Go to **Contact > Add New** in your WordPress dashboard.
2. In the **Title** field at the top, enter: **Virtual Health Contact Form**

### Step 2.2 — Paste the Form Code

1. In the **Form** tab, select all existing code and delete it.
2. Paste the following code (also found in `contact-form-7/form-configuration.txt`):

```
<label>Full Name</label>
[text* your-name placeholder "Enter your name"]

<label>Email Address</label>
[email* your-email placeholder "Enter your email"]

<label>What type of care are you looking for?</label>
[select care-type "Mental Health Care" "Medical Care" "General Question" "Technical Support"]

<label>Message</label>
[textarea* your-message placeholder "Tell us how we can help..."]

[submit "Send Message"]
```

> Fields marked with `*` are required. The `placeholder` attribute adds placeholder text.

### Step 2.3 — Save and Note the Form ID

1. Click **Save**.
2. At the top of the form editor you will see the shortcode, e.g.:
   `[contact-form-7 id="123" title="Virtual Health Contact Form"]`
3. Note the **numeric ID** (e.g. `123`). You will need it in Part 4.

---

## Part 3 — Configure Mail Settings

### Step 3.1 — Open the Mail Tab

In the form editor, click the **Mail** tab.

### Step 3.2 — Fill in the Mail Fields

| Field | Value to enter |
|-------|----------------|
| **To** | your-email@yourdomain.com _(replace with your actual email)_ |
| **From** | `[your-name] <[your-email]>` |
| **Subject** | `New Contact Form Submission - [care-type]` |
| **Additional Headers** | `Reply-To: [your-email]` |
| **Message Body** | See below |

**Message Body:**
```
Name: [your-name]
Email: [your-email]
Care Type: [care-type]

Message:
[your-message]
```

### Step 3.3 — Save Mail Settings

Click **Save** in the form editor.

---

## Part 4 — Configure Messages (Success & Errors)

### Step 4.1 — Open the Messages Tab

In the form editor, click the **Messages** tab.

### Step 4.2 — Update the Messages

| Message Key | Recommended Value |
|-------------|-------------------|
| Sender's message was sent successfully | `Thank you for contacting us! We will respond to your inquiry as soon as possible.` |
| Sender's message failed to send | `Something went wrong. Please try again later.` |
| One or more fields have an error | `Please check the form and try again.` |
| This field is required | `Please fill in this field.` |

### Step 4.3 — Save

Click **Save**.

---

## Part 5 — Import the Elementor Template

### Step 5.1 — Import the Contact Page Template

1. In your WordPress dashboard go to **Elementor > Templates**.
2. Click the **Import Templates** button (folder icon, top-right corner).
3. In the file dialog, select `templates/contact-page/contact-page-complete-cf7.json`.
4. Click **Import Now**.

The template will appear under **Pages** in your Elementor template library.

### Step 5.2 — Apply the Template to a Page

1. Create or open a WordPress page (e.g. **Pages > Add New** > title it "Contact Us").
2. Click **Edit with Elementor**.
3. Click the **folder icon** (Add Template) in the Elementor editor.
4. Find your imported Contact page template and click **Insert**.
5. The full Contact page layout will load in the editor.

---

## Part 6 — Connect CF7 Widget to Your Form

### Step 6.1 — Locate the CF7 Widget

1. In the Elementor editor, scroll to the **Send Us a Message** card.
2. Click on the Contact Form 7 widget placeholder.

### Step 6.2 — Select Your Form

1. In the left panel, find **Select Your Form**.
2. Choose **Virtual Health Contact Form** from the dropdown.
3. The form fields will appear in the editor preview.

### Step 6.3 — Save and Preview

1. Click **Save** or **Publish**.
2. Preview the page on the frontend to verify the form appears.

---

## Part 7 — Add Custom CSS

Custom CSS is required to make the CF7 form match the design exactly.

### Step 7.1 — Copy the CSS

Open `css/contact-form-styles.css` from the repository and copy all contents.

### Step 7.2 — Paste into WordPress

**Method A — Elementor Site Settings (recommended)**
1. In your WordPress dashboard go to **Elementor > Site Settings**.
2. Click **Custom CSS** in the left panel.
3. Paste the CSS and click **Save Changes**.

**Method B — WordPress Customizer**
1. Go to **Appearance > Customize**.
2. Click **Additional CSS**.
3. Paste the CSS and click **Publish**.

---

## Part 8 — Test the Form

1. Visit the contact page on the frontend (not in preview mode).
2. Try submitting the form **without filling in required fields** — you should see validation errors.
3. Fill in all fields and click **Send Message**.
4. Verify that the success message appears.
5. Check your email inbox for the notification email.
6. Check your spam/junk folder if the email doesn't arrive within a few minutes.

---

## Spam Protection (Strongly Recommended)

### Option A — Google reCAPTCHA v3 (Invisible)

1. Register your site at [google.com/recaptcha](https://www.google.com/recaptcha) and create a **reCAPTCHA v3** key.
2. In WordPress go to **Contact > Integration**.
3. Scroll to **reCAPTCHA**, enter your Site Key and Secret Key, and click **Save Changes**.
4. reCAPTCHA v3 works automatically without adding any shortcode to the form.

### Option B — Honeypot (No API Required)

1. Install the free **Contact Form 7 Honeypot** plugin.
2. Add `[honeypot honeypot-field]` to your CF7 form code (above the submit button).

### Option C — Turnstile (Cloudflare)

1. Go to **Contact > Integration > Turnstile**.
2. Register a free Turnstile widget at [dash.cloudflare.com](https://dash.cloudflare.com) and paste your keys.

---

## Email Deliverability

If notification emails are not arriving, the most common cause is that WordPress's default `wp_mail()` uses PHP mail, which is often blocked or flagged as spam.

**Recommended fix:** Install **WP Mail SMTP** (free) and connect it to:
- Gmail / Google Workspace
- SendGrid
- Mailgun
- AWS SES
- Or any SMTP server

---

## Troubleshooting

| Problem | Cause | Solution |
|---------|-------|----------|
| Form does not appear | CF7 not installed, or wrong form ID | Install CF7; select correct form in widget |
| Emails not received | PHP mail blocked by host | Install WP Mail SMTP |
| Styles not applied | CSS not added | Paste `contact-form-styles.css` into Custom CSS |
| Validation errors not styled | CSS specificity issue | Check `.wpcf7-not-valid-tip` rule in your CSS |
| Success message not showing | CF7 messages not saved | Re-save the Messages tab in CF7 |
| Page reloads on submit | JavaScript conflict | Enable CF7 AJAX in form settings; deactivate conflicting plugins |
| Select dropdown missing styles | Browser override | Ensure `appearance: none` and custom background SVG arrow are in your CSS |
