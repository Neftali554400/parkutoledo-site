# ParkUToledo — WordPress Migration Design Assets & Claude Code Prompt

---

## PART 1: DESIGN ASSETS

---

### 1. Brand Colors

These are sourced from the University of Toledo's official brand guidelines. ParkUToledo is UToledo's parking management arm and uses the same institutional palette.

| Role | Name | Hex | Usage |
|------|------|-----|-------|
| Primary | Midnight Blue | `#15397F` | Header, nav, primary buttons, headings |
| Secondary | Gold / Yellow | `#FFDA00` | Accents, CTA highlights, hover states |
| Accent Dark | Dark Blue | `#0D2352` | Footer background, dark sections |
| Support | Light Blue | `#005CB9` | Links, secondary buttons, icon accents |
| Neutral Light | Light Gray | `#BEC6C3` | Borders, dividers, background tints |
| Neutral Mid | Gray | `#A0ACAA` | Body text secondary, captions |
| White | White | `#FFFFFF` | Page backgrounds, card backgrounds |
| Dark | Near Black | `#1A1A1A` | Body text |

**Astra Global Colors to Register:**
```
--color-primary: #15397F
--color-secondary: #FFDA00
--color-accent: #005CB9
--color-dark: #0D2352
--color-text: #1A1A1A
--color-text-light: #A0ACAA
--color-border: #BEC6C3
--color-bg: #FFFFFF
--color-bg-light: #F5F6F8
```

---

### 2. Typography

UToledo's official brand font is **Poppins** (Google Fonts, open source). Use this site-wide.

| Element | Font | Weight | Size (desktop) |
|---------|------|--------|----------------|
| H1 | Poppins | 700 (Bold) | 48px |
| H2 | Poppins | 600 (SemiBold) | 36px |
| H3 | Poppins | 600 (SemiBold) | 24px |
| H4 | Poppins | 500 (Medium) | 20px |
| Body | Poppins | 400 (Regular) | 16px |
| Small / Caption | Poppins | 400 (Regular) | 14px |
| Button | Poppins | 600 (SemiBold) | 15px |
| Nav | Poppins | 500 (Medium) | 15px |

**Google Fonts embed:**
```
https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap
```

---

### 3. Spacing & Layout

| Token | Value | Notes |
|-------|-------|-------|
| Container max-width | 1200px | Standard desktop container |
| Container padding | 20px (mobile), 40px (desktop) | Horizontal gutters |
| Section padding | 80px top/bottom (desktop), 48px (mobile) | |
| Card gap | 24px | Between grid cards |
| Button padding | 14px 32px | Standard CTA |
| Border radius | 8px (cards), 4px (buttons) | |

---

### 4. Component Styles

#### Primary Button
```
Background: #15397F
Text: #FFFFFF
Font: Poppins SemiBold 15px
Padding: 14px 32px
Border-radius: 4px
Hover: background #0D2352, transition 0.2s
```

#### Secondary / Outline Button
```
Background: transparent
Border: 2px solid #15397F
Text: #15397F
Hover: background #15397F, text #FFFFFF
```

#### Gold CTA Button (Hero / High-Emphasis)
```
Background: #FFDA00
Text: #15397F
Font: Poppins Bold
Hover: background #e5c500
```

#### Card / Feature Box
```
Background: #FFFFFF
Border: 1px solid #BEC6C3
Border-radius: 8px
Padding: 32px
Box-shadow: 0 2px 12px rgba(0,0,0,0.07)
Hover: box-shadow 0 4px 20px rgba(0,0,0,0.12), translateY(-2px)
```

#### Alert / Notice Banner
```
Background: #FFF8CC (gold tint)
Border-left: 4px solid #FFDA00
Padding: 16px 20px
Border-radius: 4px
```

---

### 5. Header / Navigation

```
Background: #15397F
Logo: left-aligned (ParkUToledo logo SVG/PNG)
Nav links: Poppins Medium 15px, color #FFFFFF
Nav hover: color #FFDA00
CTA button in nav: Gold button — "Parking Portal"
Mobile: hamburger menu, full-width dropdown
Height: 72px desktop, 60px mobile
Position: sticky
```

**Primary Nav Items:**
- Students
- Faculty & Staff
- Visitors
- Daily / Hourly Parking
- Citations
- Find Parking
- News
- Contact

---

### 6. Footer

```
Background: #0D2352
Text: #FFFFFF
Link color: #BEC6C3
Link hover: #FFDA00
Divider: rgba(255,255,255,0.1)
```

**Footer columns:**
1. ParkUToledo logo + tagline + social icons
2. Quick Links (Students, Faculty, Visitors, Citations, Contact)
3. Contact Info (address, email, phone)
4. External Portal Links (Parking Portal button, ParkMobile link)

**Footer bottom bar:**
```
Background: #091A3A
Text: #A0ACAA 13px
Content: © [Year] ParkUToledo. The University of Toledo.
```

---

### 7. Hero Section (Homepage)

```
Background: Full-width image of UToledo campus parking OR solid #15397F with subtle overlay
Overlay: rgba(13, 35, 82, 0.65) if using image
Headline: Poppins Bold 48px, #FFFFFF
Subheadline: Poppins Regular 20px, #BEC6C3
CTA Buttons: 2 — "Get a Permit" (Gold), "Pay a Citation" (Outline White)
Min-height: 520px desktop, 380px mobile
```

---

### 8. Icon / Visual Style

- Use **outlined icons** (Lucide, Feather, or similar) at 32px for feature cards
- Icon color: `#15397F` on white backgrounds, `#FFDA00` on dark backgrounds
- No filled cartoon-style icons — keep it institutional and clean

---

### 9. Page-Specific Design Notes

| Page | Key Design Elements |
|------|-------------------|
| Home | Hero + 6-card permit type grid + notice banner + news feed section |
| Students | Intro text + portal CTA button + permit types table + FAQ accordion |
| Faculty & Staff | Same structure as Students with faculty-specific content |
| Visitors | Daily permit steps + ParkMobile callout box + hourly info |
| Daily/Hourly | ParkMobile embed or link + map embed + zone info |
| Contractor | Short intro + portal link + permit code info |
| Dept. Event Parking | Event request form embed or WPForms form |
| Patient Visitor | Voluntary form section + info callout |
| Citations | Enforcement hours callout + portal button + appeals steps accordion |
| Rules & Regs | Long-form text page + PDF download button |
| Game Day Info | Structured text + area closures table + key dates |
| News / Blog | Grid of post cards with featured image, date, title, excerpt |
| Contact | Address block + email link + hours + Google Map embed |

---

## PART 2: CLAUDE CODE PROMPT

---

Copy and paste the following prompt into Claude Code to begin the build:

---

```
You are helping rebuild parkutoledo.com as a WordPress site on a Dreamhost staging environment.

STAGING ACCESS:
- URL: https://parkutoledo.dreamsites.io/wp-admin/
- Username: parkutoledo_2btqcg
- Password: lIiXLq!xx4CYsVG38uFpUHzA

ENVIRONMENT:
- WordPress with Astra theme (active)
- Elementor Pro page builder (active)
- All layouts must use Elementor Flexbox CONTAINERS only — never legacy Sections or Columns
- Verify Elementor > Settings > Features > Flexbox Container is ENABLED before building

GOAL:
Rebuild all pages from the live site parkutoledo.com 1:1 into WordPress. This is a migration, not a redesign. Preserve existing content, structure, and user flows exactly.

---

BRAND / DESIGN SYSTEM:

Fonts: Poppins (all weights: 400, 500, 600, 700) — load via Google Fonts

Colors (register in Astra Custom Colors and Elementor Global Colors):
- Primary (Midnight Blue): #15397F
- Secondary (Gold): #FFDA00
- Dark Blue: #0D2352
- Accent Blue: #005CB9
- Light Gray: #BEC6C3
- Mid Gray: #A0ACAA
- Background: #FFFFFF
- Light Background: #F5F6F8
- Text: #1A1A1A

Set these as Global Colors in Elementor before building any pages.

---

ASTRA THEME SETTINGS TO CONFIGURE FIRST:

1. Appearance > Astra Options > Global:
   - Primary font: Poppins
   - Body font size: 16px
   - Heading font: Poppins
   - Primary color: #15397F
   - Link color: #005CB9

2. Header Builder:
   - Logo: Upload ParkUToledo logo (download from parkutoledo.com or use placeholder)
   - Background: #15397F
   - Nav links: white (#FFFFFF), hover: #FFDA00
   - Sticky header: enabled
   - Include a "Parking Portal" CTA button (gold background #FFDA00, text #15397F) linking to https://vpermit.com/parkutoledo/

3. Footer Builder:
   - Background: #0D2352
   - Text: #FFFFFF
   - 3-column layout: Logo+Social | Quick Links | Contact Info
   - Bottom bar: #091A3A, text #A0ACAA

---

PAGES TO BUILD (in order):

Build each page as a new WordPress page using Elementor Containers.

1. HOME (/)
   - Sticky header
   - Hero container: full-width, min-height 520px, background #15397F (or campus image with dark overlay rgba(13,35,82,0.65))
   - Headline: "All Things Parking at The University of Toledo" — Poppins Bold 48px white
   - Subheadline: "Find permits, pay citations, and get parking information" — 20px #BEC6C3
   - Two hero CTA buttons: "Get a Permit" (gold #FFDA00, text #15397F) | "Pay a Citation" (outline white)
   - Below hero: 6-card permit grid (Students, Faculty/Staff, Visitors, Daily/Hourly, Contractors, Dept Events)
   - Each card: white bg, 1px border #BEC6C3, 8px radius, 32px padding, icon top, h3 heading, short description, link button
   - News/Updates section: 3-column post grid from blog category
   - Bottom CTA strip: #15397F background, headline + "Visit Parking Portal" gold button

2. STUDENT PARKING (/student-parking/)
   - Page hero: short, #15397F bg, white headline
   - Intro text about student semester permits, pricing note
   - Primary CTA: "Purchase Student Permit" → https://vpermit.com/parkutoledo/
   - Info cards: Semester Permit, Daily Permit, Monthly Permit
   - Key rules callout box (gold left border #FFDA00)
   - FAQ accordion (use Elementor Accordion widget)

3. FACULTY & STAFF PARKING (/faculty-staff-parking/)
   - Same structure as student page with faculty-specific content
   - Note payroll deduction option
   - CTA → https://vpermit.com/parkutoledo/

4. VISITOR / GUEST PARKING (/visitor-parking/)
   - Steps layout: How to get a daily permit (numbered steps)
   - ParkMobile callout box: blue bg, white text, ParkMobile logo area, download links
   - Pricing info: Daily $5+, hourly via ParkMobile $1.10/hr regular, $2.20/hr premium
   - Portal CTA button

5. DAILY / HOURLY PARKING (/daily-hourly-parking/)
   - ParkMobile section with zone information
   - Meter locations: Areas 11, 12, 13, 18
   - Map embed placeholder (Google Maps iframe of UToledo campus)
   - Link to full parking map at /find-parking/

6. CONTRACTOR PARKING (/contractor-parking/)
   - Short intro: "Contractors and vendors must register all vehicles"
   - Portal link: https://UToledoparking.pmreserve.com
   - Key rules list
   - Contact email: info@parkutoledo.com

7. DEPARTMENT EVENT PARKING (/department-event-parking/)
   - Introduction: event parking request process
   - Peak period notice (callout box): Mon–Thu 7am–4pm
   - Embed or link to event request form
   - Key info: 72-hour advance notice required, staffing fees may apply
   - Contact: info@parkutoledo.com

8. PATIENT / PATIENT VISITOR PARKING (/patient-visitor-parking/)
   - Intro explaining voluntary patient form
   - Green parking area note: enforced 24/7
   - Form embed or link to patient visitor form
   - Info: permit holders must submit documentation each semester

9. CITATIONS (/citations/)
   - Enforcement hours callout (gold bordered box): Mon–Fri 7AM–10PM, Sat–Sun 9AM–5PM
   - "Pay or Appeal a Citation" primary CTA button → https://vpermit.com/parkutoledo/
   - How it works: 3-step process (Receive notice → Log in → Pay or Appeal)
   - Appeals accordion:
     - File within 10 calendar days
     - Log in at ParkUToledo.com
     - Decisions are final
   - Immobilization/Boot section
   - Rules & Regs PDF download button

10. RULES & REGULATIONS (/rules-regulations/)
    - Full text content from Rules & Regs PDF (already extracted — see notes)
    - Formatted as long-form page with anchored section headings:
      1. Parking Permit Requirements
      2. Purchasing a Parking Permit (Student, Faculty, Visitor, Contractor, etc.)
      3. Parking Permit Rules
      4. General Parking Rules
      5. Violations and Fines
      6. Towing
      7. Immobilization/Booting
      8. Collections
      9. Appeals
      10. Special Event Parking
    - Sticky side TOC on desktop (Elementor Table of Contents or manual anchor links)
    - PDF download button at top and bottom: https://content.parkutoledo.com/media/kpbbtlt0/parkutoledo-parking-rules-and-regulations.pdf

11. PERMIT HOLDER INFO — GAME DAYS (/game-day-parking/)
    - Football and basketball sections
    - Area closure table
    - Key instructions for D, C, K permit holders
    - Contact: athleticticketoffice@utoledo.edu for game day questions

12. PARKING NEWS (/parking-news/)
    - WordPress blog archive page
    - Grid layout: 3 columns, post cards with featured image, date, title, excerpt, "Read More" link
    - Category filter if possible

13. CONTACT (/contact/)
    - Address: 2801 W. Bancroft St Mail Stop 107, Toledo, OH 43606
    - Email: info@parkutoledo.com
    - Hours block
    - Google Maps embed (University of Toledo campus)
    - Contact form (WPForms or Contact Form 7): Name, Email, Subject, Message

---

GLOBAL ELEMENTS:

Navigation menu (register in WordPress Menus):
Students | Faculty & Staff | Visitors | Daily/Hourly | Citations | Find Parking | News | Contact

All external portal links should open in a new tab (target="_blank").

---

IMPORTANT RULES:
1. CONTAINERS ONLY — never use legacy Sections. Every layout element must be an Elementor Flexbox Container.
2. Be careful — do not delete or overwrite anything already set up on the staging site. Review what exists before making changes.
3. Make changes incrementally. Build one page at a time and check it before moving to the next.
4. All portal buttons must link to the correct external URLs (listed above).
5. Upload any logos/images to the WordPress Media Library before using in Elementor.
6. Set page titles and meta descriptions for each page (use Rank Math or Yoast if installed).
7. Ensure all pages are fully mobile responsive — test in Elementor's mobile/tablet preview after each build.

---

START WITH:
1. Configure Astra Global Settings (fonts, colors, header, footer)
2. Register Global Colors in Elementor
3. Build the Homepage
4. Then proceed page by page in the order listed above

Report back after each page is complete before starting the next one.
```

---

## PART 3: EXTERNAL PORTAL LINKS REFERENCE

These are the real third-party systems ParkUToledo uses. Do not try to rebuild them — just link to them.

| Action | URL |
|--------|-----|
| Main Parking Portal (permits, citations, account) | https://vpermit.com/parkutoledo/ |
| Contractor/Vendor Permit Portal | https://UToledoparking.pmreserve.com |
| ParkMobile (hourly parking) | https://parkmobile.io or app download |
| Rules & Regs PDF | https://content.parkutoledo.com/media/kpbbtlt0/parkutoledo-parking-rules-and-regulations.pdf |
| Patient Visitor Form | Internal form on live site — recreate with WPForms |
| Event Parking Request | Internal form on live site — recreate with WPForms |

---

## PART 4: PRE-BUILD CHECKLIST FOR CLAUDE CODE

Before writing a single line or touching a page, verify these in wp-admin:

- [ ] Astra theme is active
- [ ] Elementor Pro is active and licensed
- [ ] Elementor > Settings > Features > **Flexbox Container is ON**
- [ ] Poppins font is loading (add via Astra or Elementor custom fonts)
- [ ] Global Colors registered in Elementor
- [ ] Astra header/footer builder is accessible
- [ ] Any existing pages or templates noted before overwriting
- [ ] WPForms or Contact Form 7 installed for contact/event/patient forms
- [ ] Rank Math or Yoast installed for SEO meta fields

---

*Document prepared for Seahawk Media — ParkUToledo WordPress migration project*
*Staging: https://parkutoledo.dreamsites.io*
