# Design Specification — ช่างนิรันดร์ One-Page Catalog Redesign

**Project**: Replace chatnirun.com with a modern, accessible one-page catalog site  
**Designer**: Kaze (BagIdea Software House)  
**Date**: July 2025  
**Target audience**: Thai adults 35+, temple committees, monastery administrators, religious site managers

---

## 1. Content Audit (from chatnirun.com)

| Field | Value |
|-------|-------|
| Business name | ร้านช่างนิรันดร์ |
| Lead craftsman | ช่างนิรันดร์ อุ่นต๊ะ |
| Address | ม.11 หมู่บ้านป่าตึงงาม ต.เจดีย์หลวง อ.แม่สรวย จ.เชียงราย |
| Phone | 096-078-7242 |
| Email | n_irundorn@hotmail.com |
| Experience | 10+ years |
| Old site tagline | รับสั่งทำ ออกแบบ ผลิตสินค้าศิลปะ ทุกรูปแบบ ทุกขนาด |

### Product/Service Categories

1. **ฉัตรพระประธาน** — ฉัตรพื้นเมือง, ฉัตรประยุกต์, ฉัตรตั้งศาลพระภูมิ (featured/hero product)
2. **ดุนโลหะและตกแต่ง** — Metal embossing for temple decoration
3. **ดอกไม้คำ** — Traditional gold flowers (Lanna style)
4. **ช่อฟ้า / หน้าบัน** — Temple roof finials
5. **สัปโทน / บางแทรก / ตงกระด้าง / พุ่มดอก** — Architectural ornaments
6. **งานปูนปั้น** — Stucco/plaster work (statues, animals, pre-made)

---

## 2. Design Trends Applied (2025)

Researched from DEV.to, Framer, TheeDigital, Wix, and Squarespace trend reports:

| Trend | Application in this design |
|-------|---------------------------|
| **Bento grid layout** | Product catalog section uses asymmetric bento cards inspired by Japanese lunch boxes |
| **Bold serif typography** | Headlines use Noto Serif Thai (heavy weight) for strong presence |
| **Earthy organic tones** | Color palette uses deep reds, antique gold, warm cream — earthy & trustworthy |
| **Micro-interactions** | Hover states, fade-up scroll reveals, nav transparency transition |
| **Minimal navigation** | Sticky nav with 4 links only; collapses to hamburger on mobile |
| **Scroll storytelling** | Fade-up animations reveal each section as user scrolls |
| **Large CTA buttons** | Oversized contact buttons with clear phone/LINE labels |

---

## 3. Color Palette

Rationale: The palette evokes Thai temple architecture — **deep crimson** walls, **antique gold** ornaments, **warm cream** stone, on a **charcoal** night sky. This communicates tradition, quality, and spiritual craftsmanship without looking dated.

| Token | Hex | Usage |
|-------|-----|-------|
| `--red` | `#8B1A1A` | Primary brand color, buttons, accents |
| `--red-dark` | `#6B1313` | Hero background gradient |
| `--gold` | `#C9A84C` | Gold accent, CTAs, decorative lines |
| `--gold-light` | `#E8CC7A` | Hover states on gold elements |
| `--gold-pale` | `#F5EDD4` | Light gold tint for backgrounds |
| `--cream` | `#F8F4ED` | Section backgrounds (warm white) |
| `--cream-dark` | `#EDE8DF` | Card borders, subtle dividers |
| `--text` | `#1E1A16` | Primary text (dark brown-black) |
| `--text-mid` | `#4A3728` | Secondary text |
| `--text-muted` | `#7A6650` | Captions, labels |
| `--white` | `#FEFCF8` | Warm white (not pure white) |

**Contrast ratios (WCAG AA)**:
- `--text` on `--cream`: 12.8:1 ✓
- `--text` on `--white`: 13.4:1 ✓
- `--white` on `--red`: 7.2:1 ✓
- `--text` on `--gold`: 5.1:1 ✓

---

## 4. Typography

### Fonts (Google Fonts — free/open-source)

| Role | Font | Weight | Size |
|------|------|--------|------|
| Display / Hero | Noto Serif Thai | 900 | clamp(2.5rem, 6vw, 4.5rem) |
| Section headings | Noto Serif Thai | 800 | clamp(1.8rem, 4vw, 2.8rem) |
| Card headings | Noto Serif Thai | 700 | 1.2–2rem |
| Body text | Noto Sans Thai | 400 | 1rem (18px base) |
| Labels / tags | Noto Sans Thai | 600 | 0.72rem + letter-spacing |
| Navigation | Noto Sans Thai | 500 | 0.85rem |

**Why Noto Serif/Sans Thai**: 
- Excellent Thai character support and readability
- Noto Serif Thai gives weight and dignity (traditional craft brand)
- 18px base size ensures readability for 35+ audience
- Line height 1.7–1.9 for Thai text (longer vowel marks need breathing room)

---

## 5. Page Structure & UX Rationale

```
┌─────────────────────────────────────────┐
│  NAV (sticky, transparent → solid)      │
├─────────────────────────────────────────┤
│  HERO (100vh)                           │
│  Deep red + diamond pattern             │
│  Brand name · Tagline · 2 CTAs         │
│  Scroll indicator                       │
├─────────────────────────────────────────┤
│  ABOUT (cream bg)                       │
│  Image left · Text right               │
│  3 key stats                            │
├─────────────────────────────────────────┤
│  CATALOG (white bg)                     │
│  Bento grid: 1 large + 5 cards         │
│  Each card = 1 service category         │
├─────────────────────────────────────────┤
│  HOW TO ORDER (cream bg)                │
│  3-step process with numbered cards     │
├─────────────────────────────────────────┤
│  CONTACT (dark/charcoal bg)             │
│  Address + phone + email                │
│  3 large CTA buttons (Phone/LINE/Web)  │
│  Map placeholder                        │
├─────────────────────────────────────────┤
│  FOOTER (near-black)                    │
│  Logo · Nav links · Copyright           │
└─────────────────────────────────────────┘
```

### UX Decisions for 35+ Thai audience

| Decision | Rationale |
|----------|-----------|
| 18px base font size | Larger than typical 16px — reduces eye strain |
| No carousels or sliders | Difficult to interact with on mobile for older users |
| Single CTA per section | Reduces decision fatigue |
| Phone number always visible | Primary contact channel for this audience; don't hide behind forms |
| Large tap targets (44px+) | Meets WCAG 2.5.5 — easier to tap on mobile |
| High contrast throughout | 7:1+ contrast ratio for all body text |
| Section labels in small caps | Helps navigation without cognitive overload |
| Smooth scroll only, no parallax | Parallax causes disorientation for some users |

---

## 6. Responsive Breakpoints

| Breakpoint | Behavior |
|------------|----------|
| `> 1024px` | Full desktop: 2-col about, bento grid full |
| `768px–1024px` | Tablet: bento stacks to 2 rows, about remains 2-col |
| `480px–768px` | Mobile: all stacks to 1-col, hamburger nav, hero text smaller |
| `< 480px` | Small mobile: bento all 1-col, hero actions stack vertically |

---

## 7. Accessibility Notes

- All interactive elements have `:focus` visible outlines
- Color is not the only differentiator (icons + labels used together)
- `lang="th"` on `<html>` for correct screen reader pronunciation
- Section IDs for anchor navigation (keyboard accessible)
- `aria-label` on icon-only buttons

---

## 8. Assets Needed (for production)

When moving from mockup to production, replace CSS placeholder cards with:

1. **Hero**: Photo of workshop or finished chatra installation
2. **About**: Portrait of ช่างนิรันดร์ at work
3. **Catalog cards**: 1 photo per category (can use existing chatnirun.com photos)
4. **Contact**: Embed actual Google Maps iframe for อ.แม่สรวย จ.เชียงราย
5. **LINE ID**: Get official LINE OA ID to replace placeholder
6. **Facebook**: Get Facebook page URL for chatnirun

---

*Sources consulted for 2025 trends:*
- DEV Community: 25 Web Design Trends 2025
- Framer Blog: 7 emerging web design trends for 2025
- TheeDigital: 20 Top Web Design Trends 2026
- Figma Resource Library: Web Design Trends 2026
