# Tiny Homes WA — Wix Implementation Guide
## Complete Website + Configurator Setup (Babylon.js Edition)

---

## WHAT YOU NOW HAVE

The configurator uses **Babylon.js with real mesh-level control**.
Your GLB models have named meshes that map directly to configurator options.
When a user selects "Sloping Roof", the `RoofSlopingUpgrade` mesh appears in 3D.
When they select "Premium Panels", `ExteriorPanelsPremium` appears.
This is a true production-grade configurator — not a placeholder.

### Mesh Map (from your manifests)

| User Selection | Mesh Name in GLB |
|---------------|-----------------|
| Sloping Roof | `RoofSlopingUpgrade` |
| Premium Panels | `ExteriorPanelsPremium` |
| Large Windows | `WindowsLargeUpgrade` |
| SPC Flooring | `FloorSPCUpgrade` |
| Premium Kitchen | `KitchenCabinetryPremium` |
| Premium Benchtop | `KitchenBenchtopPremium` |
| Premium Bathroom | `BathroomFixturesPremium` |
| Terrace/Deck | `TerraceDeck` |
| Solar Prep | `SolarPrep` |
| Smart Home | `SmartHomePrep` |

---

## PART 1 — ACTIVATE THE 3D MODELS (Most Important Step)

Your GLB files are on your desktop:
```
C:\Users\tinyh\Desktop\blender GLB review\Full production\Studio20_Production.glb
C:\Users\tinyh\Desktop\blender GLB review\Full production\Studio30_Production.glb
C:\Users\tinyh\Desktop\blender GLB review\Full production\Studio40_Production.glb
```

### Step 1 — Host your GLB files (choose one option)

**Option A: Wix Media Manager (Easiest)**
1. Go to Wix Dashboard → Media Manager
2. Upload each GLB file
3. Right-click → Get URL
4. Copy the URL (looks like `https://static.wixstatic.com/3d/...`)

**Option B: CloudFlare R2 (Best performance, free egress)**
1. Sign up at cloudflare.com → R2 Storage
2. Create bucket: `thwa-models`
3. Upload the 3 GLB files
4. Enable public access → copy URLs

**Option C: GitHub (Free, simple)**
1. Create repo: `thwa-models` (public)
2. Upload GLB files
3. Use raw URL: `https://raw.githubusercontent.com/THWA-website/thwa-models/main/Studio20_Production.glb`

### Step 2 — Update the HTML file

Open `THWA_Wix_Complete_Package.html` in Notepad.
Find these 3 lines and replace the empty `glb_url: ''` values:

```javascript
{ id: 'studio20', glb_url: 'YOUR_STUDIO20_URL_HERE', ... }
{ id: 'studio30', glb_url: 'YOUR_STUDIO30_URL_HERE', ... }
{ id: 'studio40', glb_url: 'YOUR_STUDIO40_URL_HERE', ... }
```

Example:
```javascript
{ id: 'studio20', glb_url: 'https://static.wixstatic.com/3d/studio20.glb', ... }
```

---

## PART 2 — ADD TO WIX

### Step 1 — Add HTML iFrame element
1. Open Wix Editor
2. Click **+** → **Embed & Social** → **HTML iFrame**
3. Click **Enter Code**
4. Paste the ENTIRE contents of `THWA_Wix_Complete_Package.html`
5. Set iFrame height: **1500px** (desktop), **2000px** (mobile)
6. Click **Apply**

### Step 2 — Connect to Wix Velo (receive quotes)
Add this to your Wix page's Velo code:

```javascript
$w.onReady(function () {
  window.addEventListener('message', function(event) {
    if (event.data && event.data.type === 'thwaConfiguratorQuote') {
      const quote = event.data;
      
      // Option 1: Save to Wix CRM
      wixCrm.createContact({
        name: { first: 'Configurator', last: 'Lead' },
        emails: [{ tag: 'main', email: '' }],
        customFields: {
          'model': quote.model.label,
          'total_aud': quote.total_aud,
          'build_summary': JSON.stringify(quote.selections)
        }
      });
      
      // Option 2: Show confirmation on page
      $w('#confirmationBox').show();
      $w('#quoteModel').text = quote.model.label;
      $w('#quoteTotal').text = `AUD $${quote.total_aud.toLocaleString('en-AU')}`;
    }
  });
});
```

---

## PART 3 — WIX WEBSITE STRUCTURE

### Pages to Create in Wix

| Page | Slug | Content Source |
|------|------|---------------|
| Home | `/` | Hero Identity Section |
| Our Homes | `/our-homes` | Master Catalogue |
| Configurator | `/configurator` | This HTML embed |
| Our Model | `/our-model` | Our Model section docs |
| Why We Exist | `/why-we-exist` | Why We Exist docs |
| Our Story | `/our-story` | Our Story docs |
| Partner With Us | `/partner` | Partner docs |
| Contact | `/contact` | Contact form |

---

## PART 4 — HERO SECTION (Home Page — Copy/Paste Ready)

**Headline:**
> People Over Profits. Homes Over Greed. Hope Over Hardship.

**Sub-identity:**
> Tiny Homes WA breaks the mold by proving that ethical margins don't weaken a business — they strengthen a nation. When greed is removed from housing, the ripple effect of good becomes measurable: more homeowners, more taxpayers, more stability, more dignity, and a stronger Western Australia.

**Supporting line:**
> This is housing done right. This is how we build a stronger WA.

**Primary button:** `Start Your Build` → `/configurator`
**Secondary button:** `Explore Our Homes` → `/our-homes`

---

## PART 5 — THWA THEME SETTINGS (Wix)

### Colours
```
Primary:   #003C71  (THWA Navy)
Accent:    #FFC72C  (THWA Gold)
Secondary: #001F3F  (Dark Navy)
Light:     #F4F4F4  (Neutral Grey)
White:     #FFFFFF
```

### Fonts
- **Headings:** Montserrat ExtraBold (800)
- **Body:** Open Sans Regular (400)
- **Quotes:** Playfair Display Italic

### Buttons
- Primary: Fill `#003C71`, white text, 8px radius
- Hover: Fill `#FFC72C`, text `#003C71`
- Secondary: Outline `#003C71`, hover fills gold

---

## PART 6 — PRICING REFERENCE

| Model | Code | Base AUD |
|-------|------|---------|
| Studio 20 | THWA-20 | $108,585 |
| Studio 30 | THWA-30 | $118,000 |
| Studio 40 | THWA-40 | $128,150 |

| Upgrade | Mesh Activated | Price |
|---------|---------------|-------|
| Sloping Roof | RoofSlopingUpgrade | +$17,000 |
| Premium Panels | ExteriorPanelsPremium | +$8,500 |
| Large Windows | WindowsLargeUpgrade | +$4,500 |
| Premium Kitchen | KitchenCabinetryPremium | +$6,500 |
| Premium Bathroom | BathroomFixturesPremium | +$4,800 |
| SPC Flooring | FloorSPCUpgrade | +$3,200 |
| Terrace/Deck | TerraceDeck | +$9,000 |
| Solar Prep | SolarPrep | +$2,200 |
| Full Solar | — | +$8,500 |
| Smart Home | SmartHomePrep | +$3,500 |
| Water-Saving | — | +$1,250 |
| Off-Grid | — | +$12,000 |
| Second Floor | — | +$25,000 |
| Metal Panels | — | +$3,800 |

---

## PART 7 — LAUNCH CHECKLIST

- [ ] Host GLB files (Wix Media / CloudFlare R2 / GitHub)
- [ ] Update 3 `glb_url` values in the HTML
- [ ] Paste HTML into Wix iFrame element
- [ ] Set iFrame height to 1500px+
- [ ] Set Wix theme colours to THWA palette
- [ ] Set Wix fonts to Montserrat + Open Sans
- [ ] Create 8 pages per navigation structure
- [ ] Add Hero copy to Home page
- [ ] Add Velo quote receiver code
- [ ] Test PDF download
- [ ] Test on mobile
- [ ] Test quote send button
- [ ] **Go live** 🏗️

---

## YOUR GLB FILES (confirmed locations)

```
Studio 20: C:\Users\tinyh\Desktop\blender GLB review\Full production\Studio20_Production.glb
Studio 30: C:\Users\tinyh\Desktop\blender GLB review\Full production\Studio30_Production.glb
Studio 40: C:\Users\tinyh\Desktop\blender GLB review\Full production\Studio40_Production.glb

Base models:
Studio 20: C:\Users\tinyh\Desktop\blender GLB review\Base models\Studio20_Base.glb
Studio 30: C:\Users\tinyh\Desktop\blender GLB review\Base models\Studio30_Base.glb
Studio 40: C:\Users\tinyh\Desktop\blender GLB review\Base models\Studio40_Base.glb
```

Use the **Production** versions — they include all upgrade meshes.

---

*People Over Profits. Always.*
*Tiny Homes WA — tinyhomeswa.com.au*