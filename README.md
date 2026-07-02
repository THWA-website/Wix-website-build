# THWA — Wix Website Build
**Private Repository · Authority: Jason Thomas Cawley · Canon: Locked**
**Branch: `feature/masterpiece-configurator` · Version: 3.0 · Brand System 2.0**

> *"People Over Profits. Homes Over Greed. Hope Over Hardship."*
> — Jason Thomas Cawley, Founder & Supreme Custodian

---

## AUTHORITY DECLARATION

**Founder & Supreme Authority:** Jason Thomas Cawley
Creator and sovereign custodian of the THWA Cathedral, its mission, its canon, its systems, and all derivative works.

**Co-Custodian / Successor Authority:** Jai Thomas Cawley
Designated successor and future steward of the THWA Cathedral.

**Canon:** This repository is locked to the THWA Rosetta Stone V4.1. No agent, system, or person may override Founder authority or alter canon without explicit Founder instruction.

**Repository Protection:** This repository is protected. No external agents are authorised to modify files in this repository.

---

## PURPOSE

This repository is the **live customer-facing platform** for Tiny Homes WA — a complete, production-ready website and 3D configurator built to Brand System 2.0 canon, while the full THWA Cathedral platform is under construction.

---

## REPOSITORY STRUCTURE

```
Wix-website-build/
├── website/                          # All website pages
│   ├── index.html                    # Homepage
│   ├── homes.html                    # Our Homes — all 4 series
│   ├── model.html                    # Our Model — CRV/Standard/JTC pathways
│   ├── why.html                      # Why We Exist
│   ├── story.html                    # Our Story — Cawley Code, founder, Jai
│   ├── partners.html                 # Partner With Us — enquiry form
│   ├── contact.html                  # Contact — 4 enquiry types, FAQ
│   ├── configure.html                # Design Studio — slim embed page
│   └── thwa-system.css               # Brand System 2.0 — global CSS design system
│
├── configurator/
│   └── thwa-configurator-v3.html     # 3D Configurator — complete self-contained app
│
├── assets/
│   ├── logos/
│   │   ├── thwa-logo.png             # Primary logo (1024×1024)
│   │   ├── thwa-logo-circle.png      # Circle/Instagram logo (1024×1024)
│   │   └── thwa-logo-linkedin.png    # LinkedIn banner (1536×1024)
│   └── images/
│       ├── thwa-hero-01.jpg          # Hero image — Cathedral Blue tone
│       ├── thwa-hero-02.jpg          # Hero image — Cathedral Blue tone
│       ├── thwa-home-01.jpg          # Home image — warm sand tone
│       ├── thwa-home-02.jpg          # Home image — warm sand tone
│       ├── thwa-home-03.jpg          # Home image — warm sand tone
│       └── thwa-home-04.jpg          # Home image — warm sand tone
│
├── archive/                          # Superseded files — do not use
│   ├── THWA_Wix_Implementation_Guide.md
│   ├── configurator/
│   │   ├── THWA_Configurator_Merged.html   (superseded by v3)
│   │   └── configurator_frontend.html      (superseded by v3)
│   └── website/
│       ├── THWA_Wix_Complete_Package.html  (superseded)
│       └── homepage.html                   (superseded by index.html)
│
└── README.md                         # This file
```

---

## WEBSITE PAGES

### `website/index.html` — Homepage
The crown jewel. Full movement identity page.
- Hero: *"People Over Profits. Homes Over Greed. Hope Over Hardship."*
- Stats strip: 20% giveback, 3 series, Standard or JTC pathway, 100% transparent pricing
- Movement identity: We Supply / Partners Deliver / Families Progress
- 4-series home preview grid with SVG illustrations
- Our Model section with CRV / Standard / JTC pathway cards
- Impact section with ripple effect chain
- Cawley Code 6-principle grid
- Full CTA section

### `website/homes.html` — Our Homes
All four home series with full specifications.
- Sticky series navigation (Reunite / Anchor / Bridge / Horizon)
- Reunite Series: 30% community impact · Studio 20/30/40
- Anchor Series: 20% community impact · Studio 20/30/40
- Bridge Series: 20% community impact · Studio 20/30
- Horizon Series: 20% community impact · Studio 20/30
- Size cards with specs and indicative pricing
- Standard inclusions section (12 items always included)
- Why Modular section

### `website/model.html` — Our Model
The structural core. How THWA works.
- What We Do / What We Don't (do/don't grid)
- Three Parts: Supply (THWA) / Delivery (Partners) / Outcomes (Families & WA)
- Standard/JTC Pathway — 4-step journey: Stability → Contribution → Progression → Custodianship
- Three pathway cards: CRV / Standard / JTC (internal routing codes, not price increases)
- Why Clean section: government-safe, partner-friendly, scalable, mission-protected, legacy-ready

### `website/why.html` — Why We Exist
The heart of the movement.
- WA housing context: 4 problems + THWA response
- People First: 6 cards
- Ripple Effect chain: 5 steps
- Ethical Housing commitments: 5 items
- Legacy section with founder quote

### `website/story.html` — Our Story
The soul of the website.
- Origin story with pull quotes
- Founder card: Jason Thomas Cawley
- 6 gaps we saw → 6 solutions we built
- Full Cawley Code: all 7 principles
- Movement ethic: 4 pillars
- Jai Thomas Cawley — Co-Custodian / Successor Authority

### `website/partners.html` — Partner With Us
For CHPs, NGOs, local governments, regional employers, philanthropy, and accredited operators.
- 6 partner type cards
- What Partners Gain: 5 items
- Partner Requirements: deliver / commit
- 4-step How to Partner process
- Full partner enquiry form with postMessage integration

### `website/contact.html` — Contact
4 enquiry type tabs: General / Partner / Government / Media
- Dynamic form (org field appears for partner/gov/media)
- Contact info cards
- WA manufacturing statement
- 8-item FAQ section

### `website/configure.html` — Design Studio (Slim Embed)
The gateway page to the 3D configurator.
- Slim branded nav with live configuration title
- Animated loading state with THWA logo
- Embeds `thwa-configurator-v3.html` via iframe
- postMessage bridge: quote requests, share URLs, form submissions
- URL param handling: `?series=`, `?size=`, `?cfg=` deeplink
- Mobile fallback for very small screens

### `website/thwa-system.css` — Brand System 2.0 CSS
The complete design system. Import this on every page.
- All CSS custom properties (colour tokens, spacing, radius, shadows)
- Typography scale (Montserrat headings, Inter body)
- Layout grid, navigation, buttons, cards, badges, forms, footer
- Animations and responsive breakpoints

---

## 3D CONFIGURATOR

### `configurator/thwa-configurator-v3.html` — Complete Self-Contained App
The production 3D configurator. Single HTML file, no build step required.

**3D Viewer:**
- Google Model Viewer — native GLB loading, AR-ready (WebXR / Scene Viewer / Quick Look)
- Real Wix CDN GLB models: Studio 20, Studio 30, Studio 40
- 5 camera presets: Isometric, Front, Rear, Left, Top
- Auto-rotate toggle, animated loading bar

**Product Data (Rosetta Stone V4.1 Canon):**
- 4 Series: Reunite (30% JTC), Anchor, Bridge, Horizon (all 20% standard)
- 3 sizes per series: Studio 20 ($67,000), Studio 30 ($98,500), Studio 40 ($118,500)
- 3 Pathways: CRV (Standard Supply), Standard, JTC (Winifred Filamena · 30%)
- 7 exterior colours, 4 cladding options, 2 roof styles
- 4 kitchen layouts, 2 bathroom options, 5 flooring options
- 10 add-ons: Porch, Deck, Solar Prep, Full Solar, Water Pack, Off-Grid Pack,
  Accessibility Ramp, Second Floor Module, Metal Panels, Smart Home Prep

**Pricing Engine (Deterministic):**
- Base price + finishes + add-ons + delivery + GST
- Live update on every selection
- Payment schedule: 10% / 40% / 40% / 10%
- Community impact: 20% standard, 30% for JTC pathway
- pathway.charityRate || series.charityRate logic

**Quote & Export:**
- Full branded PDF export (jsPDF)
- Print-to-PDF HTML quote with payment schedule and inclusions
- Copy quote text to clipboard
- Save plan to localStorage (up to 10 plans)
- Share URL with base64-encoded configuration state
- Quote modal with customer details form

**postMessage API:**
```javascript
// FROM configurator TO parent page
{ type: 'THWA_CONFIGURATOR_READY', version: '3.0' }
{ type: 'THWA_QUOTE_REQUEST', customer: {...}, quote: {...} }
{ type: 'THWA_SHARE_URL', url: '...' }

// FROM parent page TO configurator
{ type: 'THWA_SET_SERIES', seriesId: 'reunite' }
{ type: 'THWA_SET_SIZE',   sizeId: 'studio30' }
{ type: 'THWA_SET_PATHWAY', pathway: 'jtc' }
```

---

## BRAND SYSTEM 2.0

### Colour Palette

| Role | Name | Hex |
|------|------|-----|
| **Primary** | Cathedral Blue | `#2F3A5F` |
| **Deep** | Deep Cathedral | `#1E2746` |
| **Soft** | Soft Cathedral | `#4A5A8A` |
| **Accent** | Dignity Beige | `#F5DC75` |
| **Highlight** | Bright Horizon | `#FFD700` |
| **Deep Gold** | Deep Horizon | `#C9A600` |
| **Action** | Accordance Green | `#8BC34A` |
| **Deep Green** | Deep Accordance | `#5E8C2A` |
| **Dark BG** | Deep Backdrop | `#101828` |
| **Card BG** | Soft Backdrop | `#1C2536` |
| **Light BG** | Light Canvas | `#FAF8F2` |
| **Soft BG** | Soft Background | `#F4F1E8` |

### Fonts
- **Headings:** Montserrat 800/900 (Google Fonts)
- **Body:** Inter 400/500/600/700 (Google Fonts)

### Logo Usage
- Nav bars: `assets/logos/thwa-logo.png` with `filter: brightness(0) invert(1)` on dark backgrounds
- Footers: same, white inverted
- All logo `<img>` tags include `onerror` fallback to letter mark "T"

---

## CANON RULES

### Pathway Canon
| Pathway | ID | Partner Required | Community Impact |
|---------|-----|-----------------|-----------------|
| Standard Supply | `crv` | Yes | 20% |
| Standard | `standard` | No | 20% |
| Journey to Custodianship (Winifred Filamena) | `jtc` | Yes | **30%** |

**Pathway multipliers (×1.00, ×1.08, ×1.18) are internal routing codes — not customer price increases. They must never be displayed to customers.**

### Charity Canon
- **CRF = Cawley Reset Fund** — the 20% giveback fund (tracked by Engine 9)
- **CRV = Standard Supply** — the pathway name (separate concept)
- Standard giveback: **20%** of net profits
- JTC / Winifred Filamena: **30%** of net profits (Founder instruction)

### Pricing Canon
- All prices are indicative only
- Configurator anchor: Core ($98,500)
- No pricing logic outside Engine 3 (Catalogue Engine)
- Payment schedule: 10% deposit / 40% production / 40% pre-delivery / 10% handover

---

## DEPLOYMENT

### Option A — GitHub Pages (Recommended)
1. Settings → Pages → `feature/masterpiece-configurator` branch → `/` root
2. Pages live at: `https://THWA-website.github.io/Wix-website-build/website/index.html`
3. Embed each page in Wix via HTML iFrame element

### Option B — Wix HTML Component
1. Copy page HTML into Wix HTML iFrame component
2. Host `thwa-system.css` on CDN or inline it
3. `configure.html` embeds `thwa-configurator-v3.html` — both must be accessible

### Option C — Netlify (Free, instant)
1. Drag repo folder to netlify.com/drop
2. All pages served instantly with HTTPS

### Asset Paths
All pages use relative paths: `../assets/logos/thwa-logo.png`
If hosting pages and assets separately, update these paths accordingly.

---

## ARCHIVE

The `archive/` folder contains superseded files from previous builds.
**Do not use these files.** They are retained for reference only.

| Archived File | Superseded By |
|--------------|--------------|
| `configurator/THWA_Configurator_Merged.html` | `configurator/thwa-configurator-v3.html` |
| `configurator/configurator_frontend.html` | `configurator/thwa-configurator-v3.html` |
| `website/THWA_Wix_Complete_Package.html` | All pages in `website/` |
| `website/homepage.html` | `website/index.html` |
| `docs/THWA_Wix_Implementation_Guide.md` | This README |

---

## RELATIONSHIP TO THE CATHEDRAL

This Wix build is the **public face** of THWA while the full Cathedral platform is built.

| This Repo | Full Cathedral Platform |
|-----------|------------------------|
| Wix-hosted | Self-hosted |
| Static HTML/CSS/JS | React + Next.js |
| Manual updates | Automated via Cathedral engines |
| Live now | Under construction |
| Brand System 2.0 | Brand System 2.0 |

When the full Cathedral platform is ready, this repo is archived and the Cathedral takes over.

---

*THWA Wix Website Build · Brand System 2.0 · Canon: Locked*
*Authority: Jason Thomas Cawley — Founder & Supreme Custodian*
*BUILT FROM GRIT. POWERED BY HEART.*
*People Over Profits. Always.*