# Con Corazón — Claude Code Homepage Brief
## Project Overview

Build the homepage for **Con Corazón** (concorazon.org), a U.S.-based nonprofit that supports Casa Hogar San Romero de América, a locally led elder care program in Arcatao, El Salvador. The site is static HTML and CSS only — no React, no frameworks. Font Awesome for icons. Hosted on Netlify or GitHub Pages.

**Tone:** Warm, human, dignified. This is a community-led story, not a corporate charity. The photography and the people are the heroes. Design should feel editorial and warm — not clinical or generic nonprofit.

**Key messaging principle:** Casa Hogar's local staff do the work. Con Corazón supports and funds them. Credit always goes to Casa Hogar staff. Con Corazón enables their work.

---

## Directory Structure

The site is bilingual (English and Spanish). Each language lives in its own directory. Images and CSS are shared at the root level.

```
/concorazon/
  /en/
    index.html          ← Build this first
    casa-hogar.html
    about.html
    donate.html
    team.html
  /es/
    index.html          ← Spanish version, built after English is approved
    casa-hogar.html
    about.html
    donate.html
    team.html
  /images/
    Con_Corazon_Hero.jpg
    [partner logo files]
  /css/
    styles.css
  index.html            ← Root redirect to /en/
```

**Important:** All HTML files in `/en/` and `/es/` reference shared assets using relative paths:
- Images: `../images/filename.jpg`
- CSS: `../css/styles.css`

**Root redirect:** The root `index.html` should contain a simple meta redirect to `/en/index.html`:
```html
<!DOCTYPE html>
<html>
  <head>
    <meta http-equiv="refresh" content="0; url=/en/index.html">
  </head>
</html>
```

**Build order:** Build and approve `/en/index.html` first. The Spanish `/es/index.html` will be created afterward as a separate task once the English version is approved.

---

## Design System

### Colors
```css
--platinum:   #E7ECEF;   /* page background */
--dusk-blue:  #274C77;   /* primary text, headers, nav, buttons */
--steel-blue: #6096BA;   /* accents, links, logo heart */
--icy-blue:   #A3CEF1;   /* stat card section background */
--grey-olive: #8B8C89;   /* secondary text, dividers */
```

### Typography
- **Headers:** Barlow Condensed Bold (Google Fonts — free)
- **Body:** Poppins (Google Fonts — free)
- Import both from Google Fonts at the top of the CSS file

### Logo
Render the Con Corazón logo as inline SVG in the nav. Use exactly this code:

```svg
<svg width="220" height="50" viewBox="0 0 680 80" role="img">
  <title>Con Corazón logo</title>
  <g transform="translate(95, 40)">
    <path d="M0,-28 C0,-28 -6,-38 -16,-38 C-28,-38 -37,-29 -37,-18 C-37,-7 -28,4 -16,13 C-8,19 0,25 0,25 C0,25 8,19 16,13 C28,4 37,-7 37,-18 C37,-29 28,-38 16,-38 C6,-38 0,-28 0,-28 Z" fill="#6096BA"/>
    <path d="M0,-16 C0,-16 -3,-22 -9,-22 C-16,-22 -21,-17 -21,-10 C-21,-3 -16,3 -9,8 C-4,12 0,15 0,15 C0,15 4,12 9,8 C16,3 21,-3 21,-10 C21,-17 16,-22 9,-22 C3,-22 0,-16 0,-16 Z" fill="#E7ECEF"/>
  </g>
  <text x="143" y="53" font-family="'Barlow Condensed', sans-serif" font-weight="700" font-size="42" letter-spacing="3" fill="#274C77">CON CORAZÓN</text>
</svg>
```

### Icons
Use Font Awesome 6 Free (CDN). Include this in the `<head>`:
```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
```

---

## Navigation

Sticky header. Platinum (#E7ECEF) background. Logo on the left. Nav links on the right in Barlow Condensed Bold, Dusk Blue (#274C77).

**Nav links:** Casa Hogar | Donate | About | **EN / ES**

The EN/ES toggle links between language versions:
- From `/en/index.html` the ES link points to `../es/index.html`
- From `/es/index.html` the EN link points to `../en/index.html`
- The currently active language displays in Dusk Blue, the inactive one in Grey Olive (#8B8C89)

On mobile the nav collapses to a hamburger menu (minimal JavaScript toggle).

---

## Page Sections

---

### Section 1: Hero

**Layout:** Full-bleed photo. Text overlaid directly on the image. Dark gradient overlay at the bottom third of the image so text is legible. No separate colored band below the photo.

**Image file:** `../images/Con_Corazon_Hero.jpg`

**Headline (Barlow Condensed Bold, large, white):**
> In Arcatao, El Salvador, too many elders grow old alone. Con Corazón helps change that.

**CTA Button:** "Support Casa Hogar" — links to `donate.html`. Styled in Steel Blue (#6096BA) background, white text, Barlow Condensed Bold.

**CSS guidance:**
- Hero height: 90vh minimum
- Background-size: cover, background-position: center
- Overlay: linear-gradient from transparent at top to rgba(0,0,0,0.6) at bottom
- Headline positioned in lower third of hero over the gradient

---

### Section 2: The Problem

**Layout:** Centered text, single column, generous padding. Platinum (#E7ECEF) background.

**Header (Barlow Condensed Bold, Dusk Blue):**
> Why This Work Matters

**Body copy (Poppins, dark text):**
> In rural El Salvador, it is tradition for adult children to care for their aging parents. But in Arcatao, migration and the legacy of a 12-year civil war have left roughly 200 seniors without that support. Casa Hogar was created by local leaders to fill that void, and Con Corazón helps fund their work.

---

### Section 3: What Is Casa Hogar

**Layout:** Two columns, equal width. Left column: senior center. Right column: home visits. Each column has a short header, one paragraph of copy, and an embedded YouTube video below the text.

**Section header (Barlow Condensed Bold, Dusk Blue, centered above columns):**
> How Casa Hogar Serves the Community

**Left column header:** The Senior Center

**Left column copy (Poppins):**
> Casa Hogar's senior center in Arcatao is a gathering place where older adults come together for health workshops, exercise classes, aerobics, physiotherapy, and social activities. Medical checkups are offered onsite. Health fairs take place every two months, serving 35 seniors at a time with dental, nutritional, and medical care.

**Left column video embed:**
```
https://youtu.be/SIsuUfi-Hgg?si=e2BkGzDbCmsVnCAQ
```
Use YouTube iframe embed. Width 100%, aspect ratio 16:9.

**Right column header:** Home Visits

**Right column copy (Poppins):**
> For seniors who cannot travel, Casa Hogar's nurse visits them at home, checking blood pressure, reviewing medications, and delivering food, adult diapers, and essential supplies. Among those served is Juana Echeverría, 104 years old, who receives regular visits from the Casa Hogar team. Her daughter cares for her with dedication, and the family is grateful for every visit.

**Right column video embed:**
```
https://youtu.be/_XHFitrFmFE?si=_-ZXjhpwuQ6X63RZ
```
Use YouTube iframe embed. Width 100%, aspect ratio 16:9.

---

### Section 4: Impact — Stat Cards

**Layout:** Row of cards on Icy Blue (#A3CEF1) background. On desktop: 3 cards per row, 2 rows. On tablet: 2 per row. On mobile: 1 per column. Each card: white or platinum background, Font Awesome icon centered at top (Dusk Blue), large bold number or short phrase in Dusk Blue (Barlow Condensed Bold), one-line description below in Poppins.

**Section header (Barlow Condensed Bold, Dusk Blue, centered):**
> Casa Hogar by the Numbers

**The six cards:**

1. Icon: `fa-house` | **150+** | Elderly residents visited annually
2. Icon: `fa-calendar-check` | **45** | Seniors attend the center each month
3. Icon: `fa-heart-pulse` | **25** | Seniors in serious health situations assisted
4. Icon: `fa-basket-shopping` | **40** | Seniors receive food assistance
5. Icon: `fa-wheelchair` | **60** | Seniors provided with medical equipment
6. Icon: `fa-person-walking` | **20** | Seniors join monthly group walks

**Note:** These numbers are confirmed from the 2026 FUDEMS budget document. Display as shown.

---

### Section 5: Hear From the Community

**Layout:** Pull quote centered at top, large display text. Three video embeds below in a row on desktop, stacked on mobile.

**Section header (Barlow Condensed Bold, Dusk Blue):**
> In Their Own Words

**Pull quote (large Barlow Condensed Bold, Steel Blue, centered):**
> "Together it is better to walk. Our pain decreases."
> — Casa Hogar seniors, Arcatao

**Three testimonial video embeds (YouTube iframes, equal width, 16:9):**
1. María Magdalena: `https://youtu.be/TL18-cvgX3M?si=smNOC1PHBNoUbisK`
2. Rogelio: `https://youtu.be/rssezX01cHo?si=IQnP6AGwfBnOvoHu`
3. María: `https://youtu.be/4YFCZ-IVtp0?si=RdDFsjAe5aDXiquC`

**Background:** Platinum (#E7ECEF)

---

### Section 6: How We Work

**Layout:** Single column, centered, Dusk Blue (#274C77) background, white text. Creates a strong visual break before the donate CTA.

**Section header (Barlow Condensed Bold, white):**
> Locally Led. Donor Funded.

**Body copy (Poppins, white):**
> Casa Hogar is led and operated by a dedicated local team of women in Arcatao. Con Corazón supports their work from the United States through fundraising, donor relations, and financial oversight. Funds are transferred through our fiscal sponsor, the Seattle International Foundation, to FUDEMS, a local nonprofit partner in Arcatao. Saint Joseph's University in Philadelphia funds medical equipment and supplies. Together, we make sure Casa Hogar's staff have what they need to serve the elders of their community.

---

### Section 7: Donate CTA

**Layout:** Full-width section, Steel Blue (#6096BA) background, white text, centered.

**Header (Barlow Condensed Bold, white, large):**
> Fund the People Who Make It Possible

**Body copy (Poppins, white):**
> Casa Hogar's local staff are the heart of everything you have seen. Their salaries are what donor support makes possible. Our 2026 staffing goal is $9,378. Every contribution brings us closer.
>


**CTA Button:** "Donate Now" — links to `donate.html`. White background, Dusk Blue text, Barlow Condensed Bold. Prominent size.

---

### Section 8: Partners

**Layout:** Centered header, then a single horizontal row of partner logos on Platinum background. Each logo links to the partner's website. Logos displayed in greyscale, full color on hover.

**Header (Barlow Condensed Bold, Dusk Blue):**
> Our Partners and Supporters

**Partners (in this order):**
1. Seattle International Foundation — https://seaif.org/
2. Saint Joseph's University — https://www.sju.edu/
3. EC Tours El Salvador — https://www.ectourselsalvador.com/
4. Cloud City Coffee Roasters — https://www.cloudcitycoffeeroasting.com/
5. Sustainable Livelihoods Initiative — no URL available, display logo only

Use the existing logo image files from the current Squarespace site where possible, or create styled text placeholders if image files are not available.

---

### Footer

**Layout:** Dark background (Dusk Blue #274C77), white text, three columns.

**Column 1:**
Logo (SVG, white version — change heart fill to #A3CEF1 and text fill to white)
Tagline in Poppins:
> Supporting locally led elder care in Arcatao, El Salvador
Email: info@concorazon.org

**Column 2: Stay Informed**
> Join our mailing list to receive updates on Casa Hogar and Con Corazón's work.
Simple email signup form: First Name, Last Name, Email Address, Sign Up button.
(Form submission functionality TBD — use a placeholder action for now)

**Column 3: Watch Our Videos**
Link to Con Corazón YouTube channel.
Icon: `fa-youtube` Font Awesome icon beside the link.

**Bottom bar:**
> © 2026 Con Corazón
Centered, smaller Poppins text.

---

## Responsive Breakpoints

- **Desktop:** 1200px and above — full layouts as described
- **Tablet:** 768px–1199px — two-column layouts where applicable
- **Mobile:** below 768px — all sections stack to single column. Stat cards: 1 per row. Videos: stacked. Nav collapses to hamburger menu.

---

## Technical Notes

- Static HTML/CSS only. No JavaScript frameworks. Minimal JS only where needed (hamburger menu toggle).
- All YouTube embeds use standard iframe embed format with `width="100%"` and a 16:9 aspect ratio wrapper div.
- No em dashes anywhere in copy. Use commas or periods instead.
- Smooth scroll behavior: `scroll-behavior: smooth` on html element.
- Google Fonts import for Barlow Condensed and Poppins at top of CSS file.
- Font Awesome 6 Free via CDN in `<head>`.
- All asset paths from `/en/` directory use `../images/` and `../css/`.

---

## Before You Start — Local Setup Checklist

Create this folder structure on your computer before running Claude Code:

```
/concorazon/
  /en/        ← empty, Claude Code builds here
  /es/        ← empty, built later
  /images/
    Con_Corazon_Hero.jpg   ← add this file now
  /css/       ← empty, Claude Code builds here
```

Save partner logo image files to `/images/` as you collect them from the current Squarespace site.

---

## Pages Still to Build (not in this brief)
- `en/casa-hogar.html`
- `en/about.html`
- `en/donate.html` (requires SIF donation embed code)
- `en/team.html`
- All `/es/` versions (built after English versions are approved)
