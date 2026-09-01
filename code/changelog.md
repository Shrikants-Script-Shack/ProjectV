# V Qatar Website — Changelog

## [0.1.0] — 2026-09-01 — Homepage Foundation

### Project Setup
- **`code/v-qatar/`** — Next.js 16 project (App Router, TypeScript, Tailwind CSS)
- **Framer Motion** + **GSAP** installed for dual animation system
- **Inter** (body) + **Playfair Display** (headings) fonts configured

### Image Assets (`public/images/`)
| File | Description |
|------|-------------|
| `v-hero.webp` | V 600 hero product collection shot |
| `v-300-main.webp` | V 300 product image (50 boxes, 4 ply) |
| `v-600-main.webp` | V 600 product image (32 boxes, 4 ply) |
| `v-2000-main.webp` | V 2000 product image (5 bundles, 5 ply) |
| `v-lifestyle.webp` | V 300 lifestyle / interior shot |
| `favicon.svg` | Brand favicon |

### Homepage Components (`src/components/`)
| Component | File | Purpose |
|-----------|------|---------|
| Header | `Header.tsx` | Announcement bar (rotating on mobile) + glassmorphic sticky nav with mobile menu |
| Hero | `Hero.tsx` | Full-screen hero with GSAP 3D product rotation, parallax scroll, floating badges |
| ProductHighlights | `ProductHighlights.tsx` | 4 glass cards: Pure pulp, Defined layers, Clear packing, Across Qatar |
| Collection | `Collection.tsx` | 3 product cards (V 300, V 600, V 2000) with GSAP scroll-triggered entrances |
| VInPlace | `VInPlace.tsx` | Lifestyle section with parallax image, scroll zoom |
| FormatGuide | `FormatGuide.tsx` | 3-column comparison (sheets, ply, size) — V 600 highlighted |
| HotelsBusiness | `HotelsBusiness.tsx` | Dark panel B2B section with skewed background |
| BuyingJourney | `BuyingJourney.tsx` | 4-step process (payment, address, tracking, carton pack) |
| Footer | `Footer.tsx` | Brand, links (Shop/Service/Information), language switch, copyright |

### Design System (`globals.css`)
- **Color palette:** Burgundy (50–950), Cream (50–300), Warm Gray (100–900)
- **Glass utilities:** `.glass-card`, `.glass-card-dark` (backdrop-blur + borders)
- **Animations:** `.shimmer`, `.animate-float`, `.glow-burgundy`, `.gradient-text`
- **Style direction:** Glassmorphism + bold motion (frosted glass, gradients, 3D rotations)

### Inventive Animations (`src/components/`)
| Component | File | Description |
|-----------|------|-------------|
| FloatingTissues | `FloatingTissues.tsx` | Ambient tissue sheets drift across the page like petals — GSAP-driven, randomized size/speed/rotation/wobble |
| TissuePullHero | `TissuePullHero.tsx` | Scroll-driven: a tissue physically rises out of a CSS tissue box as you scroll the hero — second tissue peeks behind it |
| PlyExploder | `PlyExploder.tsx` | 4 tissue layers stacked → separate on scroll revealing each ply with numbered badges → reassemble. 3D perspective tilt |
| CursorTrail | `CursorTrail.tsx` | Canvas-based: cursor spawns tiny tissue-shaped particles that float, wobble, and fade — speed-reactive, desktop only |

---

## [0.2.0] — 2026-09-01 — Dark Luxury Theme

Full light-to-dark theme conversion across all 14 files.

### Color System Changes (`globals.css`)
- **Body**: `#FEFDFB` (cream) → `#0F0D0C` (warm charcoal)
- **Surfaces**: New `surface-50` to `surface-300` tokens for dark card/panel backgrounds
- **Glass cards**: White-based rgba → dark-based rgba (`rgba(30,27,23,0.6)` + blur)
- **Text**: Flipped — headings now `cream-50`, body now `warm-gray-400`
- **Accent labels**: `burgundy-700` → `burgundy-400` (brighter on dark)
- **Accent lines**: `bg-burgundy-700` → `bg-burgundy-500`
- **Glow**: Intensified `glow-burgundy` with 3 layers for dramatic dark-mode pop
- **Gradient-text**: Brighter burgundy range (500→400→300)
- **Shimmer**: Reduced to `rgba(255,255,255,0.06)` for subtlety on dark

### Component Updates (all 12 components touched)
- All headings: `text-warm-gray-900` → `text-cream-50`
- All body text: `text-warm-gray-500` → `text-warm-gray-400`
- All section labels: `text-burgundy-700` → `text-burgundy-400`
- Collection card gradients: light cream → dark surface tones
- Spec badges: `bg-cream-100` → `bg-surface-200` with `border-warm-gray-800`
- Ply exploder layers: white shades → dark surface shades
- Tissue box (TissuePullHero): light box → dark box, tissues stay white for contrast
- Hotels & Business: `bg-warm-gray-900` → `bg-surface-100` (distinct from body)
- Footer: `bg-warm-gray-900` → `bg-surface-200`
- Floating tissues: Slightly reduced opacity for dark background harmony

### Pages
| Route | File | Status |
|-------|------|--------|
| `/` | `src/app/page.tsx` | Complete homepage (dark theme) |
