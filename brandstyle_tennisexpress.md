# brandstyle_tennisexpress.md
**Source of truth for all Tennis Express builds. Load this into context before starting any session.**
*Compiled from: Official Brand Guidelines PDF (March 2026) + live site scrape + customer review VOC + tennis_research.pdf avatar analysis.*

---

## 1. Brand Overview

**Client:** Tennis Express
**Website:** TennisExpress.com (always capitalized this way)
**Business type:** Specialty tennis catalog retailer — NOT a DTC direct-response brand. Copy should reflect expertise, selection, and service authority rather than hard-sell persuasion.
**Physical HQ:** Houston, Texas (full-service retail store + global e-commerce)
**Revenue scale:** Multi-7-figures/month total. Shoes are a significant category contributor.
**Primary conversion goal:** Collection page → PDP → ATC → purchase. No single-product funnel logic.
**Core differentiator:** Largest selection of tennis gear online + tennis-specific expertise ("Where We Know Tennis!") + authorized retailer for every major brand.

---

## 2. Color Palette — Confirmed from Official Brand Guidelines PDF

| Token | Hex | Role / Usage |
|---|---|---|
| `--red` | `#EB2128` | Primary brand red · CTAs, buttons, active states, accent elements, sale badges |
| `--black` | `#000000` | Primary text, headings, nav background, dark sections |
| `--blue` | `#265CA8` | Secondary accent · trust badges, informational highlights, occasional section accents |
| `--white` | `#FFFFFF` | Page background, card backgrounds, text on dark sections |
| `--gray-light` | `#F5F5F5` | Section background alternates, card fills, filter bars |
| `--gray-mid` | `#E0E0E0` | Card borders, dividers, pill tag outlines |
| `--gray-text` | `#666666` | Secondary body text, product subtitles, pill tag text |
| `--gray-dark` | `#1A1A1A` | Near-black body text — used instead of pure `#000` for long-form reading |
| `--sale-red` | `#EB2128` | Same as `--red` — sale/clearance badges reuse brand red |
| `--star-gold` | `#F5A623` | Star rating fill color on product cards |

**Color usage rules:**
- Red is for action only — CTAs, sale badges, active filter states, hover underlines on nav
- Black sections are used for full-width editorial moments (hero overlays, pro player sections, "serious player" callout)
- Blue appears sparingly — trust signals, informational callouts, never on CTAs
- Never use red + blue together in the same UI element
- White backgrounds are the default — page should feel clean, not dark

---

## 3. Typography — Confirmed from Official Brand Guidelines PDF

All typography uses **Inter** exclusively. No secondary display font. No serif. No Google Fonts pairing needed.

```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">
```

| Role | Family | Weight | Letter-spacing | Usage |
|---|---|---|---|---|
| H1 / Hero headlines | Inter | 800–900 | `-0.04em` (≈ -20 in brand doc units) | Page title, hero headline |
| H2 / Section heads | Inter | 700–800 | `-0.03em` | Major section headings |
| H3 / Card titles | Inter | 600–700 | `-0.02em` | Product names, sub-section heads |
| Eyebrow labels | Inter | 600–700 | `+0.08em` uppercase | Section category labels, pill tags |
| Body copy | Inter | 400 | `0` | Descriptions, nav text, all body |
| CTA buttons | Inter | 700 | `+0.02em` uppercase | Button labels |
| Price / Data | Inter | 700–800 | `0` | Price display, star counts |
| Fine print | Inter | 400 | `0` | Policies, disclaimers |

**Type scale (desktop):**

| Level | Size |
|---|---|
| H1 | 48–56px |
| H2 | 32–40px |
| H3 | 22–26px |
| Body | 15–16px |
| Small / Label | 12–13px |

**Brand typography rule:** Headings always tight-tracked. Body text normal tracking. No decorative or display fonts — Inter's weight range does the heavy lifting.

---

## 4. Border Radius & Spacing Tokens

```css
--radius-sm:   4px;   /* pill tags, small badges */
--radius:      8px;   /* product cards, filter buttons */
--radius-lg:   12px;  /* section cards, featured editorial blocks */
--radius-pill: 100px; /* fully pill-shaped: NOT used on primary CTAs — TE uses square-ish buttons */
```

**Important distinction from DTC brands:** Tennis Express buttons are **NOT pill-shaped**. They use a modest radius (`6–8px`) consistent with a performance/sporting goods aesthetic — not the rounded softness of wellness/DTC brands.

**Spacing system:**

| Token | Value | Usage |
|---|---|---|
| `--space-xs` | `8px` | Inline gaps, icon-to-text |
| `--space-sm` | `16px` | Within-card padding |
| `--space-md` | `24px` | Between card elements |
| `--space-lg` | `48px` | Section internal padding (desktop) |
| `--space-xl` | `72px` | Section vertical padding (desktop) |
| `--space-xxl` | `96px` | Hero vertical padding |

**Max content width:** `1280px` centered
**Product grid column width:** 4-col desktop / 2-col tablet / 1-col mobile

---

## 5. Button Styles

### Primary CTA (red — main action)
```css
background: var(--red);         /* #EB2128 */
color: #ffffff;
border-radius: 6px;
border: none;
font-family: 'Inter', sans-serif;
font-weight: 700;
font-size: 14px;
letter-spacing: 0.04em;
text-transform: uppercase;
padding: 14px 24px;
```

### Secondary / Outline CTA
```css
background: transparent;
color: var(--black);
border: 2px solid var(--black);
border-radius: 6px;
font-weight: 700;
font-size: 14px;
text-transform: uppercase;
padding: 12px 22px;
```

### Ghost CTA (white on dark section)
```css
background: transparent;
color: #ffffff;
border: 2px solid #ffffff;
border-radius: 6px;
font-weight: 700;
text-transform: uppercase;
```

### "Add to Cart" button (PLP / quick-view)
```css
background: var(--red);
color: #ffffff;
border-radius: 6px;
font-weight: 700;
font-size: 13px;
text-transform: uppercase;
width: 100%;
padding: 12px 16px;
```

### Filter pill (inactive → active)
```css
/* inactive */
background: #ffffff;
border: 1.5px solid var(--gray-mid);
border-radius: var(--radius-sm);
color: var(--gray-text);
font-size: 12px;
font-weight: 600;
text-transform: uppercase;
letter-spacing: 0.06em;
padding: 5px 10px;

/* active */
background: var(--black);
border-color: var(--black);
color: #ffffff;
```

---

## 6. Product Card Anatomy

Based on LP screenshot + mockup image analysis:

```
┌─────────────────────────────────┐
│                                 │
│       [SHOE IMAGE — clean       │
│        white bg, angled]        │
│                                 │
│  [Quick View — hover overlay]   │
│                                 │
├─────────────────────────────────┤
│  [PILL] [PILL] [PILL]           │  ← max 3 performance/use-case tags
│                                 │
│  BRAND NAME (gray, 12px, caps)  │
│  $XX.XX (black, 700, 16px)      │
│  Product Full Name (black, 600) │
│  ★★★★★ 4.8 (star gold + count) │
│                                 │
│  [ADD TO CART ─────────────]    │
└─────────────────────────────────┘
```

**Card border:** `1px solid var(--gray-mid)` with `border-radius: var(--radius)`
**Card shadow:** `0 2px 8px rgba(0,0,0,0.06)` — subtle, not dramatic
**Card background:** `#ffffff`
**Image area background:** `#f8f8f8` (very light gray)
**Quick View:** appears on hover — white overlay bar at bottom of image area

---

## 7. Pill Tag System (New — being introduced in updated PLP)

**Purpose:** Surface key attributes at-a-glance to reduce analysis paralysis and decision friction.

**Taxonomy (standardized across shoe collection):**

| Category | Tags |
|---|---|
| Court Surface | `HARD COURT` · `CLAY COURT` · `ALL-COURT` · `GRASS` · `INDOOR` |
| Fit | `WIDE FIT` · `NARROW FIT` · `TRUE TO SIZE` |
| Performance | `LIGHTWEIGHT` · `MAX STABILITY` · `HIGH DURABILITY` · `SPEED` · `MAX CUSHION` |
| Use Case | `MATCH DAY` · `TRAINING` |
| Editorial | `STAFF PICK` · `BEST SELLER` · `PRO WORN` · `NEW` · `SALE` |

**Pill style rules:**
- Max 3 pills per card
- `PRO WORN` always displays in red (`--red`) background, white text — highest signal tag
- `SALE` and `NEW` badges go in top-left corner of image, not in the pill row
- `STAFF PICK` uses black background, white text
- All others: white background, black border, black text

---

## 8. Section Patterns

| Section Type | Background | Text Color | Usage |
|---|---|---|---|
| Default | `#ffffff` | `--black` | Product grid, standard content |
| Alternate | `#F5F5F5` (gray-light) | `--black` | Trust section, blog section |
| Dark / Editorial | `#000000` | `#ffffff` | Hero overlays, pro player section, featured callout |
| Red accent | `#EB2128` | `#ffffff` | Promotional banner, sale announcement strip |
| Blue accent | `#265CA8` | `#ffffff` | Trust badges, authorized retailer callout |

**Section max-width:** `1280px`
**Section padding:** `72px 40px` desktop / `48px 20px` mobile
**Full-bleed sections** (hero, pro players, dark editorial): no max-width constraint on background

---

## 9. Navigation Structure — Confirmed from Live Site

**Top nav bar:** White background · logo left · utility icons right (search, account, cart) · red "Shop Now" or "Find My Tennis Shoe" CTA button
**Primary nav (desktop):** Horizontal tabs — `Shoes` · `Racquets` · `Apparel` · `Accessories` · `Brands` · `Players` · `Sale`
**Sub-nav for Shoes:** Men's · Women's · Junior · Brands (Nike, Adidas, ASICS, New Balance, Wilson, K-Swiss, On, more) · Clearance · All Shoes

**Shoe brand roster (confirmed from live site):**
Men's: Nike · Adidas · ASICS · New Balance · Wilson · K-Swiss · On · Penguin · Boss · Diadora
Women's: Nike · Adidas · Lacoste · On · Tail · Sofibella · Wilson · K-Swiss · Lija · InPhorm

**Pro player rosters (confirmed from live site):**

*Men's (ATP):* Carlos Alcaraz · Rafa Nadal · Roger Federer · Novak Djokovic · Casper Ruud · Stefanos Tsitsipas · Jannik Sinner · Frances Tiafoe · Taylor Fritz · Alexander Zverev · Ben Shelton · Learner Tien

*Women's (WTA):* Iga Swiatek · Aryna Sabalenka · Elena Rybakina · Jessica Pegula · Ons Jabeur · Coco Gauff · Petra Kvitova · Karolína Muchová · Madison Keys · Paula Badosa

---

## 10. Key Copy — Confirmed Verbatim from Live Site

**Meta description / homepage headline:**
> "Shop at Tennis Express, the best online tennis store with a wide selection of tennis equipment & gear and 2-Day Free Shipping on orders over $50. With gear for players of all skill levels, we have the latest in racquets, shoes, apparel, and more."

**Tagline:** `"Where We Know Tennis!"`
**Mission statement:**
> "Our mission is to inspire and nurture your inner champion by delivering the best consumer experience and providing a broad selection of tennis products and innovative game improvement gear. We will set new standards that others will seek to match."

**Price Match copy (exact, use verbatim):**
> "At Tennis Express we have a Price Match Guarantee so you can shop with confidence. We will gladly match any advertised price, in print or online, by an AUTHORIZED retailer for the exact item that you have purchased within the past 7 days."

**Men's shoes headline (live page):**
> "Whether you're looking for style, comfort, speed, or durability, we've got you covered. With the largest selection of men's tennis shoes, you're sure to find the ideal match for your game and personality."

**Women's shoes headline (live page — use as baseline):**
Similar framing as men's but tone should reflect both performance and style parity.

**About / trust:**
> "Tennis Express is a full-service tennis specialty retailer based in Houston, Texas. For over a decade, we've welcomed customers from all over the world to our retail store, our state of the art website, and to turn the pages of our seasonal catalogs. We were recently named Retailer of the Year by the Tennis Industry in RSI Magazine."

**Retailer accolade:** Named Retailer of the Year by RSI Magazine (pro/specialty) and by Babolat — use as trust proof.

---

## 11. Tone Words — Extracted from Live Site Copy

| Word | How It Shows Up |
|---|---|
| **Confident** | "you're sure to find" / "we've got you covered" — not timid, not hyped |
| **Expert** | "Where We Know Tennis" — stated authority without arrogance |
| **Helpful** | Buyer's guides, spec explainers, "our equipment whiz" phrasing |
| **Enthusiastic** | "candy store" energy — genuine love for the sport |
| **Specific** | Segment-by-segment copy (baseliners, grinders, serve-and-volleyers) |
| **Unpretentious** | No elitist gating — "gear for players of all levels" |
| **Performance-focused** | Power / Control / Spin / Speed / Stability — always tied to play |
| **Trustworthy** | Price match, 90-day returns, authorized retailer — stated plainly |

**Voice summary:** A knowledgeable tennis friend who works at the best tennis shop in the country. Not a brand spokesperson. Not a hard-seller. Talks to you like you already play.

---

## 12. Key Claims — Confirmed, Use Freely

| Claim | Source |
|---|---|
| Largest selection of men's/women's tennis shoes online | Live site copy |
| 2-Day Free Shipping on orders over $50 | Live site / meta |
| Named Retailer of the Year — RSI Magazine | About page |
| Named Retailer of the Year — Babolat | About page |
| Price Match Guarantee — 7 days, authorized retailers | Price match page |
| 90-day return policy for unused products | Customer review aggregation |
| Authorized retailer for Nike, Adidas, ASICS, Wilson, Babolat, Head, Yonex, etc. | Implied across all pages |
| Gear for players of all levels | Homepage meta |
| Houston-based, over a decade in business | About page |
| Free return shipping label included | Customer review aggregation |

---

## 13. Customer Voice — VOC Pulled from Reviews & Research

These are real phrases customers use — use in editorial copy when paraphrasing is needed:

- *"huge selection"*
- *"fast shipping"*
- *"easy to use website"*
- *"improved my backhand"* (outcome-focused, not feature-focused)
- *"can't find this stuff elsewhere"*
- *"like a candy store for tennis players"*
- *"they actually know what they're talking about"*
- *"I was nervous buying online but the return policy made it easy"*

---

## 14. Shoe Collection Page Architecture (Updated Spec)

**Men's and Women's are separate pages.** No gender toggle. Traffic is sent directly to each.

**Page flow:**
1. Hero (gender-specific, existing copy confirmed by team)
2. Brand filter bar + Play Style / Court Surface filter row
3. Product grid (4-col desktop, pill tags, editorial card at row 2)
4. Active Pro Players section (gender-split roster)
5. "Play Like the Legends" section (simplified, existing)
6. "What Kind of Player Are You?" — 3-tile navigator
7. "Shop With Confidence" trust block
8. Expert Guides blog section (renamed from "The Sneaker Blog")
9. Team Outfitting (bottom — B2B only)

**Removed from both pages:** Men's/Women's split CTA section (visitor already self-selected)

---

## 15. Trust Block Copy — Final Approved Version

**Section anchor:**
> "Every reason to buy. Zero reasons to hesitate."

**Three blocks:**

| Icon | Headline | Body |
|---|---|---|
| Shield / Price tag | Price Match Guarantee | Found it cheaper somewhere else? We'll match any authorized retailer's price within 7 days of your purchase — no runaround. |
| Checkmark / Badge | Every Shoe is the Real Thing | We're an authorized retailer for every brand on this page. That means full manufacturer warranty coverage and zero gray-market product. |
| Return arrow | Free Returns. No Stress. | Not the right fit? Returns are free within 90 days on unworn items. We send the label, you drop it off. |

---

## 16. "What Kind of Player Are You?" — 3-Tile Navigator Copy

**Section header:** `"FIND YOUR SHOE"`
**Section sub:** `"Tell us how you play. We'll point you to the right section."`

| Tile | Label | Sub-copy | Link |
|---|---|---|---|
| Left | AGGRESSIVE BASELINER | Max stability. Built for grinding. | `/collections/stability-tennis-shoes` |
| Center | ALL-COURT MOVER | Speed and cushion in one. | `/collections/all-court-tennis-shoes` |
| Right | SERVE & VOLLEY | Lightweight. Quick off the line. | `/collections/lightweight-tennis-shoes` |

---

## 17. Featured Shoe Editorial Card — Spec (In-Grid, Row 2)

Appears as a 2-col-wide editorial card in the 4-col product grid, positioned after the first 4 products.

**Label:** `RIGHT NOW ↗` (small, uppercase, red)
**Headline:** Product-specific — e.g., `"The Fastest Shoe We Carry"`
**Body:** 1–2 line staff voice — e.g., *"Built for aggressive baseline players who need quick first steps without sacrificing lateral support. Our equipment team's current top pick."*
**CTA:** `SHOP THIS SHOE →` + price
**Update frequency:** Monthly or with major new release

---

## 18. Pro Player Section Copy — Non-Corny Framing

**Men's section header:** `"ACTIVE PRO PLAYERS"`
**Men's sub:** `"The pros in this collection play in the same shoes available on this page."`

**Women's section header:** `"ACTIVE PRO PLAYERS"`
**Women's sub:** `"The players in this collection compete in the same shoes available on this page."`

No name-drops in copy. No "Swiatek's feet" phrasing. Let the headshots and names do the association work.

---

## 19. "Play Like the Legends" Section — Simplified Copy

**Header:** `"PLAY LIKE THE LEGENDS"` (existing, keep)
**Body (existing, keep as-is — confirmed by team):** No changes needed unless new assets are added.

---

## 20. Blog Section — Renamed

**Old label:** "The Sneaker Blog" — WRONG, sounds like lifestyle/streetwear
**New label:** `"FROM OUR EQUIPMENT EXPERTS"` or `"TENNIS SHOE GUIDES"`
**Sub:** `"In-depth guides from the team that plays the sport."`

**Editorial article titles for shoe collection (prioritized):**
- "The Fastest Men's Tennis Shoes in 2026"
- "How to Choose the Right Tennis Shoe for Your Game"
- "Speed vs. Stability: Which Type of Tennis Shoe Are You?"
- "The 5 Shoes Our Staff Would Actually Play In"

---

## 21. Team Outfitting Section — Bottom of Page Copy

**Header:** `"Outfitting a Team or Program?"`
**Body:** `"Bulk pricing, custom gear, and dedicated support for clubs, academies, and USTA programs."`
**CTA:** `CONTACT OUR TEAM SALES →`

---

## 22. What NOT to Replicate — Current Site Failures

- **"The Sneaker Blog"** — wrong category signal for a performance tennis retailer
- **Team Outfitting mid-page** — B2B CTA does not belong in individual customer funnel
- **Hero copy serving the wrong visitor** — homepage hero recycled onto collection pages
- **Product cards with zero benefit context** — name + price only, no guidance on who it's for
- **Trust section treated as footer fine print** — three small icons the customer never reads
- **Men's/Women's split CTA on a page that already split** — redundant routing
- **Pro player section with no purchase path** — decoration without conversion intent
- **Corny editorial voice** — "Swiatek's feet and Gauff's ankles" style copy is off-brand; TE speaks plainly and knowledgeably
- **Authorized Retailer badge without explaining why it matters** — credential without consequence
- **Generic category label "shoes" without play style context** — misses the audience's real decision framework (they think in stability/speed/surface, not SKU names)

---

## 23. Shopify / Technical Notes

- **ClawdShip deployment:** `push_page` or `update_page` to Tennis Express store — page ID needed before deploy
- **Store handle:** `tennisexpress.myshopify.com` (confirm before deploying)
- **Image CDN:** Shopify CDN — shoe images pulled from `/collections/` or `/products/` URLs
- **Live support widget:** Red button, bottom-right corner — "Live Support" — do not cover with fixed CTAs
- **Spin to Win popup:** Exists on site — do not add a second email capture popup that conflicts
- **Font loading:** Inter via Google Fonts — already loaded site-wide, reference existing stylesheet

---

*Last updated: March 2026. Compiled from: official Brand Guidelines PDF (March 2026) + live site scrape via search (TennisExpress.com) + tennis_research.pdf customer avatar analysis + Trustpilot/CouponFollow review VOC.*
