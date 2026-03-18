# Images — Requirements and Placeholder Guide

This folder contains provider avatar images used by the **Featured Providers** section template.

---

## Required Images

Place your provider images in `images/providers/` using the exact filenames referenced in the templates:

| Filename                  | Provider Name      | Specialty           |
|---------------------------|--------------------|---------------------|
| `james-walker.jpg`        | Dr. James Walker   | Addiction Recovery  |
| `olivia-bennett.jpg`      | Dr. Olivia Bennett | Teen Therapy        |
| `andrew-patel.jpg`        | Dr. Andrew Patel   | Family Medicine     |
| `melissa-grant.jpg`       | Dr. Melissa Grant  | Internal Medicine   |
| `daniel-brooks.jpg`       | Dr. Daniel Brooks  | Couples Therapy     |
| `robert-chen.jpg`         | Dr. Robert Chen    | Cardiology          |

---

## Image Specifications

- **Dimensions:** Minimum 136 × 136 px (displayed at 68 × 68 px at 2× density)
- **Format:** JPEG or WebP (JPEG preferred for photos)
- **Aspect ratio:** 1:1 (square — will be cropped to a circle in the UI)
- **File size:** Keep under 80 KB per image for fast page loads
- **Subject:** Head-and-shoulders portrait with neutral or soft background

---

## Placeholder Images

For demos or development, you can use free placeholder services:

```
https://ui-avatars.com/api/?name=James+Walker&size=136&background=dbeafe&color=2563eb
https://ui-avatars.com/api/?name=Olivia+Bennett&size=136&background=dbeafe&color=2563eb
https://ui-avatars.com/api/?name=Andrew+Patel&size=136&background=dbeafe&color=2563eb
https://ui-avatars.com/api/?name=Melissa+Grant&size=136&background=dbeafe&color=2563eb
https://ui-avatars.com/api/?name=Daniel+Brooks&size=136&background=dbeafe&color=2563eb
https://ui-avatars.com/api/?name=Robert+Chen&size=136&background=dbeafe&color=2563eb
```

Or use a generic placeholder like `https://placehold.co/136x136` for layout testing.

---

## How to Update Images in Elementor

1. Open the page in the **Elementor Editor**.
2. Locate the **Featured Providers** section.
3. Click any **Image** widget inside a provider card.
4. In the left panel, click the image thumbnail and choose **Select Image** to upload from the Media Library.
5. Repeat for each provider card.

---

## License

All production images must be either:
- Original photography you own the rights to
- Licensed stock photography from a provider such as Unsplash, Pexels, or Adobe Stock
- AI-generated images with appropriate commercial usage rights

Do **not** use images scraped from the internet without verifying their license.
