# NOETIC DHARMA GROUP — Master Reference Document
## Website, Brand, & Technical Specifications
## Created: 14-Dec-2024 | Version 1.0

---

# SECTION 1: BRAND IDENTITY

## Brand Name
**NOETIC DHARMA GROUP** (NDG)
- Display: "NOETIC DHARMA" (primary) + "GROUP" (subdued)
- Abbreviation: NDG

## Tagline
**"Wisdom for an Unstable Age"**

## Core Definitions
| Term | Definition |
|------|------------|
| **Noetic** | Relating to the intellect, intuition, or implicit understanding. Root: noēsis — direct knowing, inner intelligence, the faculty of insight beyond noise. |
| **Dharma** | Duty fulfilled by observance; the principles of cosmic or individual existence. Root: dhr — that which upholds, the structure of reality, moral causality. |

## Mission Statement
The fusion of intellectual clarity and structural alignment: seeing the world as it is, acting in accordance with how it truly works, and executing with precision. **Wisdom operationalized.**

---

# SECTION 2: BRAND COLORS

## Primary Palette
| Color | Hex | Usage |
|-------|-----|-------|
| Deep Space | `#050810` | Primary background |
| Cosmic Navy | `#0a0e1a` | Secondary background |
| Panel Navy | `#0d1220` | Card/panel backgrounds |
| Pure White | `#f2f4f8` | Primary text |
| Muted Silver | `#a8b2c1` | Secondary text |
| NDG Gold | `#d4a84b` | Accent, CTAs, highlights |
| Gold Hover | `#e6ba5a` | Button hover states |

## Secondary/Accent
| Color | Hex | Usage |
|-------|-----|-------|
| Cosmic Blue | `#4a7fb5` | Lightning accents, subtle glow |
| St. Michael Red | `#8B0000` | Moral compass section glow |
| Error Red | `#e63946` | Form validation errors |
| Panel Light | `#f7f4ef` | Light mode panels (rare) |

## CSS Variables
```css
--color-bg-deep: #050810;
--color-bg-cosmic: #0a0e1a;
--color-text-primary: #f2f4f8;
--color-text-muted: #a8b2c1;
--color-accent-gold: #d4a84b;
--color-accent-gold-hover: #e6ba5a;
--color-border-subtle: rgba(212, 168, 75, 0.3);
```

---

# SECTION 3: TYPOGRAPHY

## Font Stack
| Purpose | Font | Fallback |
|---------|------|----------|
| Display/Headings | Cinzel | Times New Roman, serif |
| Body Headings | Cormorant Garamond | Georgia, serif |
| Body Text | Inter | system-ui, sans-serif |

## Font Sizes (Desktop)
| Element | Size | Line Height |
|---------|------|-------------|
| H1 | 48-72px (clamp) | 1.2 |
| H2 | 32-48px (clamp) | 1.2 |
| H3 | 24-32px (clamp) | 1.3 |
| Body | 20px | 1.8 |
| Small/Labels | 12-14px | 1.5 |

## Letter Spacing
- Accent labels: 0.15-0.25em
- Body text: normal
- Navigation: 0.05em

---

# SECTION 4: WEBSITE SECTIONS

## Section Structure
1. **Hero** — Epic Halo Socrates, floating tablet logo, tagline, definitions
2. **Three Pillars** — Noetic Clarity, Dharma Alignment, Execution Velocity
3. **Philosophy** — Noetic/Dharma principles, Socratic Method
4. **The Fourth Turning** — Crisis context, three forces, opportunity
5. **Services** — Capital Advisory + Digital/AI offerings
6. **Principles** — Six guiding principles
7. **Our Guiding Moral Compass** — White header, James quote, moral framework
8. **St. Michael / Armor of God** — Image + biblical quotes
9. **Contact** — Form with First/Last/Email/Phone required
10. **Footer** — Brand, nav links, copyright

---

# SECTION 5: KEY QUOTES & SOURCES

## Socratic/Philosophical
| Quote | Source | Section |
|-------|--------|---------|
| "The unexamined life is not worth living." | Socrates | Hero/Pillars |
| "Wisdom begins in wonder." | Socrates | Available |
| "To find yourself, think for yourself." | Socrates | Available |
| "Excellence is not a singular act, but a habit." | Aristotle | Client Access |

## Biblical/Spiritual
| Quote | Source | Section |
|-------|--------|---------|
| "But be ye doers of the word, and not hearers only, deceiving your own selves." | James 1:22 | Moral Compass |
| "Put on the whole armour of God, that ye may be able to stand against the wiles of the devil." | Ephesians 6:11 | Armor of God |
| "For we wrestle not against flesh and blood, but against principalities, against powers..." | Ephesians 6:12 | Armor of God |
| "Stand therefore, having your loins girt about with truth, and having on the breastplate of righteousness..." | Ephesians 6:14-17 | Armor of God |
| "St. Michael the Archangel, defend us in battle. Be our protection against the wickedness and snares of the devil." | Prayer to St. Michael | Armor of God |
| "Be sober, be vigilant; because your adversary the devil, as a roaring lion..." | 1 Peter 5:8 | Available |

## NDG Original
| Quote | Context |
|-------|---------|
| "The sacred obligation to pursue truth through inner wisdom. The illuminated mind in service of rightful action." | Philosophy synthesis |
| "Insight without action is inert. Wisdom without execution is indulgence." | Execution Doctrine |
| "You cannot control the cycle. You can only position yourself correctly within it." | Fourth Turning |
| "Truth is the ultimate competitive edge." | Principle 01 |
| "Clarity is a form of compassion." | Principle 04 |

---

# SECTION 6: IMAGE ASSETS

## Current Inventory
| Filename | Description | Section(s) |
|----------|-------------|------------|
| epichalo.png | Socrates with orange/blue energy halo | Hero background |
| logotablet.png | Bronze tablet with NDG name | Hero foreground |
| writing.png | Socrates seated, writing with quill | Philosophy (Noetic) |
| reading.png | Socrates seated, holding book | Philosophy (Dharma) |
| orating.png | Socrates with finger raised, teaching | Philosophy (Socratic Method) |
| herocontemplating.png | Socrates in thoughtful pose | Fourth Turning, Client Access |
| stmichael.png | St. Michael defeating demon | Moral Compass section |
| thumbsup.png | Friendly Socrates with thumbs up | Footer |

## Image Specifications
- Format: PNG with transparency
- Positioning: `object-position: center bottom` (anchored at bottom)
- Headspace: 40px margin above highest point
- Shadow: `drop-shadow(0 20px 40px rgba(0,0,0,0.5))`

---

# SECTION 7: TECHNICAL STACK

## Current Production
| Component | Technology | Purpose |
|-----------|-----------|---------|
| Hosting | Vercel | Static site hosting, CDN |
| Repository | GitHub | Version control |
| Domain | www.noeticdharma.com | Primary domain |
| CSS | Vanilla CSS (custom properties) | Styling |
| JS | Vanilla JavaScript | Interactions |
| Fonts | Google Fonts | Typography |

## Planned Integrations
| Component | Recommended Service | Purpose |
|-----------|-------------------|---------|
| Form Backend | Formspree or Resend | Contact form submissions |
| Client Portal DB | Supabase | PIN/user/file storage |
| SMS Verification | Twilio Verify | Client Access auth |
| File Storage | Supabase Storage | Secure document hosting |
| Analytics | Plausible or Vercel | Privacy-friendly analytics |
| Email Marketing | Klaviyo | Newsletter/campaigns |

## Third-Party Apps (Claude Maintains)
| Service | Purpose | Status |
|---------|---------|--------|
| GitHub | Code repository | Active |
| Vercel | Hosting & deployment | Active |
| Formspree | Contact form | To configure |
| Supabase | Client Access backend | Planned |
| Twilio | SMS verification | Planned |
| Klaviyo | Marketing automation | Available |
| Resend | Transactional email | Available |

---

# SECTION 8: FILE NAMING CONVENTIONS

## Standard Format
```
ProjectName-Description_DD-Mon-YYYY.ext
```

## Examples
- `NDG-Website-Hero_14-Dec-2024.png`
- `NDG-Client-Deck_14-Dec-2024.pdf`
- `NDG-Master-Reference_14-Dec-2024.md`

## ZIP Files
Include `_manifest.txt` with:
- Project name
- Contents list
- Creation date

## Code Files
Include header comment:
```
/* © 2025 Noetic Dharma Group, LLC 
   www.noeticdharma.com 
   CONFIDENTIAL & PROPRIETARY 
   Unauthorized use prohibited */
```

---

# SECTION 9: DESIGN PRINCIPLES

## Visual Hierarchy
1. **Socrates-first**: Images anchor to bottom, consistent headspace
2. **Gold accents**: Reserve for CTAs, labels, highlights
3. **62% whitespace**: Generous padding, no cramped layouts
4. **Alternating rows**: Left/right Socrates images for rhythm

## Readability Standards
- Body text: 20px minimum desktop, 18px mobile
- Line length: 65-75 characters max
- Line height: 1.8x for body text
- Contrast: Pure white on deep space (maximum contrast)

## Animation
- Hero float: 8s ease-in-out infinite
- Tablet float: 6s ease-in-out infinite (with rotation)
- Scroll indicator: 2s bounce infinite
- Hover transitions: 0.3s ease

---

# SECTION 10: CONTACT & LOCATIONS

## Primary Office
**Teton Village, Wyoming**

## Affiliate Offices
- Washington DC
- Florida

## Contact Form Fields
| Field | Type | Required |
|-------|------|----------|
| First Name | text | Yes |
| Last Name | text | Yes |
| Email | email | Yes |
| Phone | tel | Yes |
| Area of Interest | select | No |
| Message | textarea | No |

## Area of Interest Options
1. Capital & Strategic Advisory
2. Digital Transformation & AI
3. Licensing Opportunities
4. Strategic Partnership
5. Other

---

# SECTION 11: LEGAL & COMPLIANCE

## Copyright Notice
```
© 2025 Noetic Dharma Group, LLC. All rights reserved.
```

## Confidentiality Footer (for documents)
```
NOETIC DHARMA GROUP™

CONFIDENTIAL & PROPRIETARY © 2025 Noetic Dharma Group, LLC | www.noeticdharma.com

This document contains confidential, proprietary, and trade secret information 
belonging exclusively to Noetic Dharma Group, LLC. Unauthorized review, 
distribution, copying, or disclosure is strictly prohibited.
```

## Console Log Notice
```javascript
console.log('%c© 2025 Noetic Dharma Group, LLC | www.noeticdharma.com | CONFIDENTIAL & PROPRIETARY', 'color: #d4a84b; font-weight: bold;');
```

---

# SECTION 12: FUTURE DEVELOPMENT ROADMAP

## Immediate (This Week)
- [ ] Deploy current website to Vercel
- [ ] Configure Formspree for contact form
- [ ] Test all responsive breakpoints

## Short Term (Next 30 Days)
- [ ] Implement Client Access portal (Supabase + Twilio)
- [ ] Add analytics (Plausible)
- [ ] SEO optimization
- [ ] Performance optimization

## Medium Term (90 Days)
- [ ] Admin dashboard for Client Access
- [ ] PDF watermarking system
- [ ] Email integration (Resend)
- [ ] Newsletter signup (Klaviyo)

## Long Term
- [ ] Client self-service portal
- [ ] Document signing integration
- [ ] Custom client applications
- [ ] Mobile app consideration

---

## DOCUMENT REVISION HISTORY

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 14-Dec-2024 | Claude/NDG | Initial creation |

---

© 2025 Noetic Dharma Group, LLC | CONFIDENTIAL & PROPRIETARY
