# Con Corazón — Claude Code Donate Page Brief

## Overview

Build the Donate page for Con Corazón at `/en/donate.html`. This page must match the homepage design system exactly — same nav, same footer, same fonts, colors, and CSS file. The page has one critical functional requirement: the Click & Pledge donation form embed must work correctly. Do not improvise the embed code.

**File to create:** `/en/donate.html`
**Shared CSS:** `../css/styles.css` (already exists — do not modify unless adding donate-specific styles)
**Image file:** `../images/Con_Corazon_Donate.jpg`

---

## Design System (same as homepage — do not change)

```css
--platinum:   #E7ECEF;
--dusk-blue:  #274C77;
--steel-blue: #6096BA;
--icy-blue:   #A3CEF1;
--grey-olive: #8B8C89;
```

**Header font:** Barlow Condensed Bold (Google Fonts)
**Body font:** Poppins (Google Fonts)
**Icons:** Font Awesome 6 Free (CDN)

---

## Navigation

Identical to homepage. Sticky header, Platinum background, logo left, nav links right.

**Nav links:** Casa Hogar | **Donate** (active state — Dusk Blue, slightly bolder) | About | EN / ES

EN links to `../es/donate.html`

---

## Page Sections

---

### Section 1: Page Header with Photo

**Layout:** Full-width photo with dark gradient overlay. Shorter than the homepage hero — approximately 50vh height. Headline text overlaid in the lower portion of the image over the gradient.

**Image:** `../images/Con_Corazon_Donate.jpg`

**Headline (Barlow Condensed Bold, large, white):**
> Every dollar funds the team that cares for Arcatao's seniors.

**CSS guidance:**
- Height: 50vh minimum
- Background-size: cover, background-position: center top
- Overlay: linear-gradient from transparent at top to rgba(0,0,0,0.65) at bottom
- Headline centered in lower third of the image

No CTA button in this section — the donation form is directly below.

---

### Section 2: The Ask — Two Column Layout

**Background:** Platinum (#E7ECEF)
**Layout:** Two equal columns with generous padding. On mobile, stack vertically — copy on top, form below.

**Left column: Copy**

Section header (Barlow Condensed Bold, Dusk Blue):
> Make a Difference Today

Body copy (Poppins, dark text):

> Casa Hogar's local staff provide nursing care, home visits, food assistance, and medical support to over 150 seniors in Arcatao each year. Their salaries are what your donation makes possible.
>
> Saint Joseph's University in Philadelphia funds medical equipment and supplies. Con Corazón funds the people who deliver the care.
>
> Our 2026 staffing goal is $9,378. Every contribution brings us closer.

Trust line (Poppins, smaller, Grey Olive):
> Your donation is tax deductible and processed securely through our fiscal sponsor, the Seattle International Foundation. Funds are managed locally by FUDEMS, a certified nonprofit in El Salvador.

**Right column: Donation Form Embed**

This is the critical functional element. Embed the Click & Pledge donation form exactly as follows — do not modify, wrap, or alter the script tag or div in any way:

```html
<script class="CnP_formloader" src="https://resources.connect.clickandpledge.com/Library/iframe-1.0.0.min.js?637540198539197037" data-guid="6b99a0aa-bf9e-4e99-9cbe-c60d3a71a721"></script>
<div id="CnP_inlineform"></div>
```

The form will render inside the `CnP_inlineform` div automatically when the script loads. Give the right column enough min-height (400px) to accommodate the form rendering. Do not add any border, background color, or padding directly on the CnP_inlineform div itself — let the form render naturally.

---

### Section 3: Trust Signals Strip

**Layout:** Full-width section, Dusk Blue (#274C77) background, white text. Three items displayed horizontally on desktop, stacked on mobile. Each item: Font Awesome icon centered above, short bold phrase below.

**Three trust signals:**

1. Icon: `fa-shield-halved` | Tax-deductible donation
2. Icon: `fa-building-columns` | Fiscally sponsored by Seattle International Foundation
3. Icon: `fa-heart` | 100% supports Casa Hogar staff

Icons in Steel Blue (#6096BA), text in white Poppins.

---

### Footer

Identical to homepage footer. Three columns: logo + tagline + email, mailing list signup, YouTube link. Bottom bar with copyright and SIF fiscal sponsor line.

---

## Responsive Behavior

- **Desktop (1200px+):** Two-column layout for Section 2
- **Tablet (768–1199px):** Two columns if space allows, otherwise stack
- **Mobile (below 768px):** All sections single column. Copy appears above form. Trust signals stack vertically.

---

## Critical Technical Notes

1. **The Click & Pledge embed is the most important element on this page.** Place the script tag in the `<body>` near where the form should render, not in `<head>`. The script self-executes and injects the form into the `CnP_inlineform` div. Both the `<script>` tag and the `<div id="CnP_inlineform">` must appear together in the right column.

2. Do not wrap the embed in any container that uses `overflow: hidden` — this can prevent the form from rendering at full height.

3. The `data-guid` value `6b99a0aa-bf9e-4e99-9cbe-c60d3a71a721` must be preserved exactly — this is the unique identifier for Con Corazón's Click & Pledge account.

4. No em dashes anywhere in copy.

5. Same Google Fonts and Font Awesome CDN links in `<head>` as homepage.

6. Asset paths use `../images/` and `../css/` relative to `/en/` directory.

---

## After Building

Test the donation form by opening the page in a browser and confirming the Click & Pledge form renders inside the right column. If it shows a blank space, the script may need to be placed just before the closing `</body>` tag instead — try both positions if needed.

Add `donate.html` to the nav links on `index.html` and any other pages already built.
