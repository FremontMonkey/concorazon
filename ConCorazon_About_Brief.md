# Con Corazón — Claude Code About Page Brief

## Overview

Build the About page for Con Corazón at `/en/about.html`. This page must match the homepage design system exactly — same nav, same footer, same fonts, colors, and CSS file. Do not create a new CSS file unless adding about-specific styles that don't conflict with existing rules.

**File to create:** `/en/about.html`
**Shared CSS:** `../css/styles.css`
**Placeholder images:** Use a styled placeholder div (background: #A3CEF1, centered grey-olive text saying "Photo coming soon") wherever images are marked as PLACEHOLDER.

---

## Design System (same as homepage)

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

**Nav links:** Casa Hogar | Donate | **About** (active state) | EN / ES

EN/ES toggle links to `../es/about.html`

---

## Page Sections

---

### Section 1: Page Header

**Layout:** Full-width section, Dusk Blue (#274C77) background, centered text, generous padding. No photo needed.

**Headline (Barlow Condensed Bold, large, white):**
> About Con Corazón

**Subheadline (Poppins, white, lighter weight):**
> Supporting locally led community development in Arcatao and Nueva Trinidad, El Salvador since 2020.

---

### Section 2: Our Story

**Layout:** Single column, centered, max-width 800px, generous padding. Platinum (#E7ECEF) background.

**Section header (Barlow Condensed Bold, Dusk Blue):**
> Our Story

**Body copy (Poppins):**

> Con Corazón grew out of a long-standing sister parish relationship between St. Joseph Catholic Church in Seattle and San Bartolome Parish in Arcatao. Recognizing that community needs exceeded what the parish relationship could address, co-founders Brian Bonet and Sam Kennedy established Con Corazón in 2020 as a non-denominational nonprofit dedicated to supporting locally led development in Arcatao and Nueva Trinidad.
>
> Con Corazón's first project was an immediate response to the COVID-19 pandemic. In 2020, over 50 donors contributed more than $20,000 to support nearly 5,000 residents of Arcatao and Nueva Trinidad — providing masks, medicines, food, and emergency health care funds to those most in need, including the elderly and families in hard-to-reach communities.
>
> Today, Con Corazón's flagship project is Casa Hogar San Romero de América, an elder care program serving seniors in Arcatao whose families have been displaced by migration and the legacy of El Salvador's 12-year civil war.

**Map embed (place directly below the body copy):**

Embed an interactive Google Map centered on Arcatao, El Salvador using this iframe. Width 100%, height 350px, with a small border-radius to match the site's card style:

```html
<iframe
  src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d15502.!2d-88.9!3d14.08!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8f63b7c8e4b1b1b1%3A0x1234567890abcdef!2sArcatao%2C+El+Salvador!5e0!3m2!1sen!2sus!4v1234567890"
  width="100%"
  height="350"
  style="border:0; border-radius: 8px;"
  allowfullscreen=""
  loading="lazy"
  referrerpolicy="no-referrer-when-downgrade">
</iframe>
```

Note to Claude Code: The embed URL above is a placeholder structure. Generate a proper Google Maps embed URL centered on Arcatao, Chalatenango, El Salvador (approximately 14.08°N, 88.90°W). Use the standard Google Maps embed format. The map should be zoomed to show Arcatao in regional context — visible enough to show its position near the Honduras border.

**Map caption (Poppins, small, Grey Olive, centered below map):**
> Arcatao is located 32 km east of Chalatenango, at the border with Honduras, in a small valley between the mountains La Cañada and Caracol.

---

### Section 3: How We Work

**Layout:** Two columns on desktop, stacked on mobile. Platinum background with a Steel Blue (#6096BA) left border accent on each column for visual separation.

**Section header (Barlow Condensed Bold, Dusk Blue, full width above columns):**
> How We Work

**Left column header:** Our Model

**Left column copy (Poppins):**
> Con Corazón supports locally led work from the United States through fundraising, donor relations, and financial oversight. We do not deliver programs directly. Instead, we fund and support the local team in Arcatao who does.
>
> Donations are processed through our fiscal sponsor, the Seattle International Foundation, who transfers funds to FUDEMS. FUDEMS then manages and disburses those funds to Casa Hogar.

**Right column header:** Our Partners

**Right column copy (Poppins):**
> FUDEMS is an officially registered nonprofit in Arcatao that provides essential organizational infrastructure — managing funds, overseeing program activity, and handling accounting and financial auditing. As a certified local NGO in El Salvador, FUDEMS makes it possible for funds to flow legally and transparently from the United States to El Salvador.
>
> Saint Joseph's University in Philadelphia, a formal partner of Con Corazón, funds medical equipment and supplies for Casa Hogar residents — wheelchairs, canes, medicines, and oxygen. Donor contributions fund the Casa Hogar staff who deliver care every day.

---

### Section 4: Our Team

**Layout:** Two subsections. First: US Team. Second: El Salvador Team. Each uses a card grid layout.

**Section header (Barlow Condensed Bold, Dusk Blue, centered, full width):**
> Our Team

---

#### US Team

**Layout:** Two cards side by side on desktop, stacked on mobile. Icy Blue (#A3CEF1) background for this subsection.

**Subsection label (Barlow Condensed Bold, Dusk Blue, small caps style):**
> Con Corazón — United States

**Card 1: Brian Bonet**
- Photo: PLACEHOLDER (square, 200x200px placeholder div)
- Name: Brian Bonet (Barlow Condensed Bold, Dusk Blue)
- Title: Director, Con Corazón (Poppins, Steel Blue)
- Bio: Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation. (Poppins, body size)

**Card 2: Sam Kennedy**
- Photo: PLACEHOLDER (square, 200x200px placeholder div)
- Name: Sam Kennedy (Barlow Condensed Bold, Dusk Blue)
- Title: Co-Founder and Project Consultant, Con Corazón (Poppins, Steel Blue)
- Bio: Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation. (Poppins, body size)

---

#### El Salvador Team

**Layout:** Four cards in a 2x2 grid on desktop, single column on mobile. Platinum background.

**Subsection label (Barlow Condensed Bold, Dusk Blue, small caps style):**
> Con Corazón — El Salvador

**Card 1: Silvia Menjívar**
- Photo: PLACEHOLDER
- Name: Silvia Menjívar
- Title: Con Corazón Liaison, El Salvador
- Description (Poppins): Business Administration degree. Involved with community projects in Arcatao since the early days of the sister parish relationship.
- Quote (Poppins italic, Steel Blue):
  Spanish: *"El Proyecto Casa Hogar es un espacio que nos llena el corazón, reconocer la importancia que tienen nuestros abuelos y valorar la memoria histórica que hay en esta semilla que han formado comunidades enteras."*
  English: *"Casa Hogar is a space that fills our hearts — recognizing the importance of our elders and honoring the historical memory that built entire communities."*
- Attribution: — Silvia Menjívar

**Card 2: Yessenia Monge**
- Photo: PLACEHOLDER
- Name: Yessenia Monge
- Title: Nurse, Casa Hogar
- Description (Poppins): Nursing technician. Community leader and president of the women's association in Arcatao.
- Quote:
  Spanish: *"Mis aspiraciones es que Casa Hogar pueda acoger a adultos mayores en estado de abandono y con problemas de salud mental que tengan un espacio permanente en Casa Hogar donde puedan llegar y sentirse libres y acogidos."*
  English: *"My aspiration is for Casa Hogar to welcome elders who have been abandoned or are struggling with mental health — a permanent space where they can arrive and feel free and embraced."*
- Attribution: — Yessenia Monge

**Card 3: María Santos Navarrete**
- Photo: PLACEHOLDER
- Name: María Santos Navarrete
- Title: Social Worker, Casa Hogar
- Description (Poppins): Degree in Social Work. Active in community organizing with experience working with older adults.
- Quote:
  Spanish: *"Proyecto una Casa Hogar llena de vida, amor, alegría — un espacio libre sin límites para el adulto mayor, un lugar de encuentro intergeneracional donde siempre hayan sonrisas, amor y generosidad."*
  English: *"I envision a Casa Hogar full of life, love, and joy — a free and limitless space for older adults, an intergenerational meeting place where there are always smiles and generosity."*
- Attribution: — María Santos Navarrete

**Card 4: Guadalupe Bonilla**
- Photo: PLACEHOLDER
- Name: Guadalupe Bonilla
- Title: Administrator, Casa Hogar (since 2022)
- Description (Poppins): Business Administration technician. Community leader.
- Quote:
  Spanish: *"Es increíble comprender que nosotros los hacemos felices. Mis aspiraciones es que Dios siga bendiciendo a cada uno de los donantes para seguir creciendo en la Casa Hogar."*
  English: *"It is incredible to understand that we make them happy. My aspiration is that God continues blessing every donor so we can keep growing at Casa Hogar."*
- Attribution: — Guadalupe Bonilla

---

### Section 5: Partners

**Layout:** Centered header, single horizontal row of logos on Platinum background. Each logo links to partner website. Greyscale by default, full color on hover. Same as homepage partners section.

**Header (Barlow Condensed Bold, Dusk Blue):**
> Our Partners and Supporters

**Partners (in this order):**
1. Seattle International Foundation — https://seaif.org/
2. Saint Joseph's University — https://www.sju.edu/
3. FUDEMS — no URL, display logo placeholder text if no logo file available
4. EC Tours El Salvador — https://www.ectourselsalvador.com/
5. Cloud City Coffee Roasters — https://www.cloudcitycoffeeroasting.com/
6. Sustainable Livelihoods Initiative — no URL, display logo only

Note: If a FUDEMS logo file is provided later, it will be saved as `../images/fudems-logo.png`. Use a styled text placeholder for now.

---

### Footer

Identical to homepage footer.

---

## Responsive Behavior

- **Desktop (1200px+):** Two columns for How We Work, 2-card row for US Team, 2x2 grid for El Salvador Team
- **Tablet (768–1199px):** Stack How We Work columns, 2-card row for teams where space allows
- **Mobile (below 768px):** All single column, all cards stacked

---

## Technical Notes

- No em dashes anywhere in copy. Use commas or periods instead.
- Staff quotes display Spanish first, English translation immediately below in slightly smaller or lighter text.
- Photo placeholders: styled div, background #A3CEF1, height equal to width (square), centered text "Photo coming soon" in Grey Olive (#8B8C89), Poppins.
- Same Google Fonts and Font Awesome CDN links in `<head>` as homepage.
- Asset paths use `../images/` and `../css/` relative to `/en/` directory.
- Add `about.html` to nav links on all other pages already built.

---

## Content Still to Add (after brief)
- Brian Bonet bio (replace Lorem Ipsum)
- Sam Kennedy bio (replace Lorem Ipsum)
- Photo of Brian and Sam together or individually
- Photos of Yessenia, María Santos, Guadalupe, and Silvia
- FUDEMS logo (save as `../images/fudems-logo.png`)
