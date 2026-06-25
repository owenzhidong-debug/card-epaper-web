# Design System: BOOX Chinese Homepage

> Observed page: https://zh.boox.com/  
> Evidence: live DOM, computed styles, readable stylesheet rules, desktop `1280px` and mobile `390px` layouts, carousel and mobile-menu states. Values marked "inferred" are design guidance rather than source declarations.

## 1. Visual Theme & Atmosphere

BOOX uses a restrained premium-product language built around large, carefully lit device photography. The page does not behave like a dense commerce catalog: it alternates cinematic full-bleed scenes with quiet white editorial bands, then returns to dark, image-backed brand sections. The result is technical enough to explain an e-ink product, but emotionally framed around attention, paper, calm, and long-term use.

Visual density is intentionally low. Product names and editorial claims sit in large open fields, while detailed information is grouped into grids only after the product has been visually established. Corners stay almost square, borders are faint, shadows are rare, and color is used as emphasis rather than decoration.

### Key Characteristics

- Full-screen hero photography with a fixed, translucent navigation layer.
- Warm off-white and near-black form the main contrast; terracotta is the only recurring action accent.
- Serif display type is reserved for product names and important editorial statements; UI copy remains clean sans-serif.
- Sections are wide and unframed, with content capped at `1480px`.
- Product imagery is functional content, not decoration: it carries the color, material, and mood of each block.
- Motion is slow and controlled: fade transitions, modest image zoom, sticky story cards, and no playful bouncing.

## 2. Color Palette & Roles

| Role | Semantic Name | Value | Usage |
| --- | --- | --- | --- |
| Primary action | Terracotta | `#CE643D` | Hero purchase button, active carousel bullet, selected navigation state, accent borders on hover. |
| Primary action hover | Light terracotta | `#E8795A` | Hero CTA hover state. |
| Main ink | Ink black | `#1A1815` | Section headings, dark CTA band, high-contrast UI. |
| Warm canvas | Paper white | `#FEFDF8` | Editorial product and feature sections. |
| Navigation canvas | Stone white | `#F8F7F4` | Solid fixed navigation after hover or non-hero contexts. |
| Image backing | Soft gray | `#F5F5F4` | Product-card image stage. |
| Footer surface | Charcoal brown | `#1B1A16` | Footer and deep brand surface. |
| Secondary text | Warm graphite | `rgba(67, 61, 55, 0.70)` | Navigation and subdued light-surface copy. |
| Hero secondary text | Soft white | `rgba(255, 255, 255, 0.50)` | Hero paragraph copy. |
| Quiet divider | Ink wash | `rgba(0, 0, 0, 0.06)` | Review-card and feature-grid separators. |

### Primary

- `#1A1815` establishes the editorial core. Use it for headings and large dark bands, not for repeated card backgrounds.
- `#CE643D` is sparse and purposeful. It should identify an action, active state, or product highlight rather than fill large decorative areas.

### Interactive

- Hero primary action: `#CE643D`, changing to `#E8795A` over `0.3s`.
- Light-surface outlined action: `1px solid #1A1815` or `#CE643D`; the hover treatment fills the border color and reverses text.
- Hero outlined action: `1px solid rgba(255,255,255,0.25)`; hover only increases border opacity to `0.55`.
- Navigation active state uses a slightly deeper terracotta source color `#C6623F`.

### Neutral Scale

- `#FEFDF8`: warm editorial canvas.
- `#F8F7F4`: navigation and neutral chrome.
- `#F5F5F4`: product-image backing.
- `#F9F6ED`: warm hover wash for feature cells.
- `#1B1A16` and `#1A1815`: near-black surfaces, never cool blue-black.

### Surface & Overlay

- Hero navigation begins as `rgba(31,25,19,0.10)` with `backdrop-filter: blur(3.25px)` and white content.
- On navigation hover, it becomes `#FDFDFB` / stone white, gains a faint bottom border, and switches text and icons back to graphite.
- Hero badges use `rgba(255,255,255,0.12)` with a `2px` radius, not a pill.

### Theme Modes

#### Light Mode

- Background: `#FEFDF8` and white editorial bands.
- Surface: white reviews, `#F5F5F4` image fields, sparse `rgba(0,0,0,0.06)` dividers.
- Text: `#1A1815` with warm-gray secondary copy.
- Accent: `#CE643D`.
- Notes: this is the dominant content mode.

#### Dark Mode

- Background: `#1A1815` / `#1B1A16`, sometimes over a photographic texture.
- Surface: dark transparent or image-backed bands rather than elevated dark cards.
- Text: `#FEFDF8` with white at `80%`, `50%`, `45%`, `30%`, and `15%` opacity for hierarchy.
- Accent: terracotta remains stable.
- Notes: dark is section-level art direction, not a user-toggleable site theme observed on the page.

### Shadows & Depth

- Default sections and product cards are flat. Separation comes from whitespace and color fields.
- Fixed light navigation: `0 1px 3px rgba(0,0,0,0.04)`.
- Review hover: `0 4px 16px rgba(0,0,0,0.08)` plus terracotta-tinted border.
- Sticky story scene: `0 25px 50px -12px rgba(0,0,0,0.18)`.
- The only glass effect is the hero navigation and circular hero arrows.

## 3. Typography Rules

### Font Family

- Primary UI: `Outfit-Medium, MiSans, sans-serif` observed as the page default.
- Serif display: `Playfair Display, Noto Serif SC, Georgia, serif` for product names and editorial titles.
- Chinese fallback: `Noto Serif SC` for serif and `Noto Sans SC` / `MiSans` for sans text.
- Monospace: none used in the visual system.

### Hierarchy

| Role | Font | Size | Weight | Line Height | Letter Spacing | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Hero product name | Serif display | `clamp(44px, 7vw, 80px)` | `700` | `1.05` / `84px` at desktop | normal | White, paired with a small translucent label. |
| Dark CTA title | Sans / serif context | `48px` | `700` | normal | normal | Large but compact, used once per section. |
| Section heading | Sans | `40px` | `700` | `48px` | normal | Wide editorial sections. |
| Value-section heading | Sans | `40px` | `700` | `52px` | normal | Supports a deliberate two-line statement. |
| Product card name | Serif display | `20px` | `700` | `28px` | normal | Sits under image, not over it. |
| Body / description | Sans | `14px` to `16px` | `400` | `20px` to `1.6` | normal | Light density; hero description is limited to `420px`. |
| Navigation | Sans | `13px` | `500` | `1` | `0.03em` | Small, controlled, no oversized menu labels. |
| Label / badge | Sans | `11px` to `12px` | `400` to `600` | `1.5` | `0` to `0.1em` | Labels appear as restrained metadata. |

### Principles

- Use serif display type as contrast, not as the default for all headings.
- Keep Chinese product messaging short and declarative: product name, one sensory line, one practical benefit.
- Avoid condensed tracking and over-styled uppercase. The small uppercase-like treatment is limited to quiet metadata.
- Mobile reduces hero type to `44px` while keeping the hero atmospheric; it hides the longer hero description rather than squeezing it.

## 4. Component Stylings

### Buttons and Links

- **Primary CTA:** minimum width `160px`, padding `14px 32px`, `14px` / `500` text, `2px` radius, white text on `#CE643D`.
- **Hero secondary CTA:** same dimensions, transparent surface, `1px` translucent white border, no fill hover.
- **Light section action:** approximately `120px × 43px`, `11px 24px` padding, `4px` radius, either ink outline or terracotta outline.
- **Links:** plain text links with color change only. Do not introduce underlines, pills, or large arrow containers as the default.
- **Carousel control:** `40px` circular glass button with `blur(4px)`, a translucent white fill, and a one-step brighter hover.

### Cards and Containers

- Product groups are not enclosed in elevated cards. The image is a `3:4` stage with `2px` radius; the information sits as open text beneath.
- Review cards are the exception: white background, `2px` radius, `24px` padding, `1px solid rgba(0,0,0,0.06)`.
- Feature cells use no card fill by default. They are separated by thin vertical rules and gain `#F9F6ED` only on hover.
- Avoid nested surfaces. Use page-wide background changes before introducing a card.

### Inputs and Interactive Controls

- No persistent input field is a homepage focus. Utility icons carry search, profile, and cart actions.
- Selected navigation and carousel state use color, not heavy borders or elevated tabs.
- Mobile menu locks body scrolling and opens a full-height `rgba(8,8,8,0.34)` overlay below the fixed navigation.

### Navigation

- Fixed at the top, `70px` desktop and about `63px` mobile.
- Content max-width is `1480px` with `20px` side padding.
- Hero state is translucent, dark-tinted, blurred, and white; hover flips the entire bar to an opaque warm-white service state.
- Desktop navigation has top-level product categories plus hover-open mega panels. Mega panels are flat `#FCFCFA` fields with a faint bottom border, multi-column link lists, product badges, and no floating rounded container.
- Mobile hides the desktop links, keeps logo and utility actions, and exposes a `36px` menu button.

### Image Treatment

- Use real product photography, material-rich environmental shots, and simple device-focused compositions.
- Hero art is full-bleed and carries its own palette; copy is placed in negative space rather than inside a card.
- Product thumbnail images scale from `1` to `1.05` over `0.7s` on hover.
- Image corners are almost square (`2px` to `4px`) unless a sticky scene module uses a larger `12px` outer radius.

### Distinctive Components

- **Hero carousel:** full viewport, five slides, `fade` effect, `800ms` speed, looping autoplay every `5000ms`, text left, product world right or center, compact line pagination.
- **Editorial product grid:** a calm heading and two text links lead into a three-column set of `3:4` product photographs and open metadata.
- **Sticky scene stack:** successive visual stories use sticky cards with deep shadows, turning scroll into a controlled gallery rather than a conventional card list.
- **Feature stat grid:** four factual benefits presented as high-whitespace cells; icon treatment turns terracotta only on hover.
- **Dark video and CTA bands:** full-width contrast moments that reset the page rhythm before moving into testimonials or the footer.

## 5. Layout Principles

### Spacing System

- Base unit: inferred `4px`.
- Repeated spacing values: `8`, `10`, `12`, `16`, `20`, `24`, `28`, `32`, `40`, `48`, `72`, `80`, `112`, `128`, and `140px`.
- The rhythm deliberately becomes generous at section level: hero top padding `130px`, editorial sections `112px` vertical, dark CTA approximately `140px` vertical at the observed viewport.

### Grid & Container

- Primary container: `max-width: 1480px; margin: 0 auto; padding: 0 20px`.
- Desktop product cards: three equal columns; observed at `1280px`, each group was about `403px` wide.
- Feature grid: four desktop cells, two columns on mobile.
- Mobile product grid collapses to a single `390px` column with `20px` gaps.
- Full-bleed hero, video, CTA, and footer sections deliberately break the content container.

### Whitespace Philosophy

- Let images establish scale first, then let copy breathe in the surrounding field.
- Section titles align with the container edge; primary CTA groups are compact and do not span the page.
- Use band-to-band contrast rather than stacked rounded modules to create segmentation.
- Long copy remains narrow. The hero description is only `420px` wide on desktop and is removed on mobile.

### Border Radius Scale

- Micro: `2px` for hero labels, hero and product image stages, review cards.
- Standard: `4px` for simple outlined buttons and internal story-image clipping.
- Large: `12px` only for the outer sticky story card.
- Pill: `50%` for floating navigation arrows and social controls; do not apply pill shapes to normal CTAs.

## 6. Depth & Elevation

| Level | Treatment | Use |
| --- | --- | --- |
| Flat | Background field, no shadow, no border | Product grids, feature cells, most editorial sections. |
| Divider | `1px` low-opacity ink line | Feature-column separation and review-card outline. |
| Glass | Low-opacity white fill, blur, faint white border | Hero navigation and circular carousel arrows. |
| Card | `2px` corners, small border; shadow only on hover | Testimonials and transient information cards. |
| Story | `0 25px 50px -12px rgba(0,0,0,0.18)` | Sticky image-led scroll scenes. |

### Depth Principles

- Do not use shadow as the default separation tool.
- Use blur only on UI that must float over photography.
- Prefer a single photographic plane or a clean color field behind content.
- The page earns high elevation only where scrolling is intended to feel cinematic.

## 7. Do's and Don'ts

### Do

- Use high-quality, large product or environmental photography as the primary composition tool.
- Pair warm off-white pages with one terracotta action color and near-black editorial text.
- Keep corners sharp-to-soft, not playful or pill-heavy.
- Use large section spacing and let product names carry visual weight.
- Make scroll effects slow, legible, and subordinate to the product story.

### Don't

- Do not replace photographic hero scenes with gradient blobs, generic illustrations, or dashboard tiles.
- Do not turn every content group into a rounded card with a drop shadow.
- Do not spread terracotta across backgrounds, labels, and decorative elements at once.
- Do not use cool blue-gray as the primary neutral; the system is warm and paper-like.
- Do not force long hero explanations into mobile layouts; reduce copy instead.

## 8. Responsive Behavior

### Breakpoints

| Name | Width | Key Changes |
| --- | --- | --- |
| Mobile | Observed `390px` | Navigation becomes `63px`, desktop links disappear, menu opens an overlay, hero becomes full viewport, hero title is `44px`, long hero description is hidden. |
| Tablet | Inferred `768px` to `1023px` | Preserve the hero composition, reduce grid columns and navigation density before mobile menu takes over. |
| Desktop | `1024px+` | `70px` navigation, multi-column mega panels, three-column product layout, four-cell feature grid, full large-type hero. |

### Touch Targets

- Mobile menu and utility buttons use a `36px` box.
- Hero actions retain a `49px` height, providing a clear touch target without looking oversized.
- Carousel arrows remain circular and visually separate from product copy.

### Collapsing Strategy

- Desktop: text navigation, mega panels, visual product grids, and side-by-side image narratives.
- Tablet: preserve sections and imagery but reduce content columns before shrinking text aggressively.
- Mobile: use a menu overlay, single-column product cards, two-column feature statistics, and vertical content flow.
- Keep hero photography full-height. Remove subordinate descriptive copy rather than reduce it below readable density.

## 9. Agent Prompt Guide

### Quick Color Reference

- Primary CTA: `#CE643D`.
- Background: `#FEFDF8` and `#F8F7F4`.
- Heading text: `#1A1815`.
- Body text: `rgba(67,61,55,0.70)` on light; `rgba(255,255,255,0.50)` on dark imagery.
- Border or ring: `rgba(0,0,0,0.06)` on light; `rgba(255,255,255,0.25)` on hero overlays.
- Accent: `#CE643D`, with hover `#E8795A`.

### Quick Summary

Create a premium e-ink product homepage that feels like a calm product editorial, not a SaaS dashboard. Lead with full-screen real photography, a translucent fixed navigation bar, and large serif product names. Alternate warm paper-white editorial sections with near-black image or video bands. Use terracotta only for primary actions and active states. Keep radius very small, shadows scarce, and information density deliberately low. Let wide spacing, material photography, and restrained motion do the work.

### Example Component Prompts

- **Hero:** "Build a full-viewport e-ink device hero with a real product photograph as the entire background, a left-aligned 80px serif product name, 11px translucent label, one short supporting line, and paired 160px outline/terracotta actions. Place a 70px glass fixed nav over it."
- **Card:** "Build an editorial product item with a near-square-corner `3:4` pale-gray image stage, subtle 1.05 hover zoom, then open text below with a 20px serif product name, a one-line descriptor, and two small outlined actions. Avoid a card container or shadow."
- **Navigation:** "Build a 70px fixed nav capped at 1480px. Over hero imagery it is a dark translucent blur with white links; on hover it becomes warm-white and switches icon/text colors. Use flat mega-menu panels with columns, no rounded dropdown shell."
- **Button or badge:** "Use a 160×49 terracotta primary button with 2px radius and `#E8795A` hover, plus a same-size transparent hero outline with only a stronger white border on hover."

### Ready-to-Use Prompt

Design a Chinese product-service homepage in the visual language of BOOX: calm, premium, paper-adjacent and image-led. Use warm off-white `#FEFDF8`, ink `#1A1815`, and a single terracotta action accent `#CE643D`. Start with a full-bleed real product hero and translucent fixed navigation. Use serif display typography only for product names and editorial statements, low-radius surfaces, thin dividers, minimal shadow, spacious `1480px` containers, and slow fade/scroll motion. Avoid dashboard density, card grids, gradients, rounded pills, and decorative blobs.

### Iteration Guide

1. First correct the photographic composition and band sequence before tuning cards or decorative details.
2. Check that terracotta appears only where an action or selected state needs emphasis.
3. Reduce radius, borders, and shadows until the page feels closer to an editorial product catalog than a generic web template.
4. On mobile, preserve the atmosphere with full-height imagery and simplify copy before shrinking type.

## Optional Appendix: Interaction Patterns

- Hero carousel: `fade` effect, `800ms` transition, looping autoplay every `5000ms`, clickable compact line bullets, and explicit previous/next controls.
- Fade-in content: sections begin at `opacity: 0` and `translateY(30px)`, then resolve over `0.6s` when visible.
- Product image hover: scale image to `1.05` over `0.7s`.
- Feature hover: light warm fill, terracotta icon field, and light icon stroke.
- Navigation: hero navigation changes from translucent/dark to warm-white on hover; desktop product entries can open a mega panel. Mobile menu opens an overlay and applies `overflow: hidden` to the document body.

## Optional Appendix: Observed Pages

- https://zh.boox.com/ - Chinese BOOX homepage, inspected on 2026-06-23.
