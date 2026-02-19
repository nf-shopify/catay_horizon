# CATAY Horizon Theme

## Project Overview

CATAY (catay.us) is a multi-brand e-commerce store curating handcrafted jewelry and apparel from Brazilian artisan designers. The store runs on **Shopify's Horizon theme (v3.4.0)** and sells across 15+ brands including Ecran Studios, Azulerde, Ímpar Atelier, Usejoias, Triana, Paolla Falcão, Carolina Gomes, Lilac, Flex.etc, Volta Atelier, and others.

Product categories: Earrings, Necklaces, Chokers, Bracelets, Rings, Hoops, Cuffs, Sunglass Chains, Bags, Button Down Shirts, Dresses, Sarongs, Swim.

## Design Direction

**Tone**: Clean-elevated luxury with Brazilian warmth. Jewelry is the hero; the design frames it with generous negative space, deliberate typography contrast, and a warm gold accent that echoes artisan metalwork.

**Inspiration**: Mejuri, Vrai, Fernando Jorge, Beatriz Werebe, Farm Rio (warmth adapted to luxury restraint), Ana Luisa, Tiffany & Co.

## Typography

| Role       | Font Handle                  | Font Name                 |
| ---------- | ---------------------------- | ------------------------- |
| Heading    | `cormorant_garamond_n7`      | Cormorant Garamond Bold   |
| Accent     | `cormorant_garamond_n4`      | Cormorant Garamond Regular|
| Body       | `raleway_n4`                 | Raleway Regular           |
| Subheading | `raleway_n5`                 | Raleway Medium            |

Serif headings create editorial luxury feel. Raleway body is airy and elegant. Never use Inter, Roboto, Arial, or system fonts.

## Color Schemes

| ID                      | Name              | Background   | Primary Text | Buttons          | Usage                              |
| ----------------------- | ----------------- | ------------ | ------------ | ---------------- | ---------------------------------- |
| `scheme-1`              | Default White     | `#ffffff`    | `#000000`    | Gold `#C5A572`   | Main content, product cards        |
| `scheme-2`              | Warm Cream        | `#FAF7F2`    | `#000000`    | Gold `#C5A572`   | Alternating sections               |
| `scheme-3`              | Sage              | `#eef1ea`    | `#000000`    | Black `#000000`  | Brand story, organic feel          |
| `scheme-4`              | Gold Accent       | `#C5A572`    | `#ffffff`    | Black `#000000`  | Announcement bar, CTA banners      |
| `scheme-5`              | Dark              | `#1A1A1A`    | `#ffffff`    | Gold `#C5A572`   | Footer, dark sections              |
| `scheme-6`              | Transparent Light | transparent  | `#ffffff`    | White `#ffffff`  | Hero overlays on imagery           |
| `scheme-58084d4c-...`   | Transparent Dark  | transparent  | `#000000`    | Black `#000000`  | Transparent header, non-hero pages |

**Accent color**: `#C5A572` (warm gold). Hover state: `#B8965F`.

## Technical Constraints

1. **JSON-only modifications** -- all customization happens via JSON template files and `settings_data.json`. Do NOT edit vendor Liquid files directly.
2. **Horizon upgradability** -- never modify files in `sections/`, `blocks/`, `snippets/`, `layout/`, or `assets/` that ship with the Horizon theme.
3. **Extension points first** -- use theme settings, metafields, and JSON template blocks.
4. **Custom code isolation** -- if custom Liquid is ever needed, create clearly named NEW files (e.g., `sections/custom-catay-*.liquid`), never edit vendor sections.

## File Structure

```
config/settings_data.json    -- Global settings (typography, colors, motion)
templates/index.json         -- Homepage (6 sections)
templates/product.json       -- Product detail page
templates/collection.json    -- Collection / product listing page
sections/header-group.json   -- Header + announcement bar
sections/footer-group.json   -- Footer
```

## Key Horizon Section Types

- `hero.liquid` -- Full-bleed hero banners
- `product-list.liquid` -- Product grids and carousels
- `product-information.liquid` -- Product detail page (has `enable_sticky_add_to_cart`)
- `product-recommendations.liquid` -- Related products
- `media-with-content.liquid` -- Split media + text layouts
- `collection-links.liquid` -- Category navigation strips
- `section.liquid` -- Generic flexible section (email signup, custom content)
- `main-collection.liquid` -- Collection grid with filters

## Key Horizon Block Types

- `accordion` -- Collapsible content (contains `_accordion-row` children)
- `_accordion-row` -- Individual accordion rows (contains nested `@theme` blocks)
- `text` / `_inline-text` -- Rich text content
- `_product-card` -- Product card (contains gallery, title, price sub-blocks)
- `buy-buttons` -- Add to cart + accelerated checkout
- `variant-picker` -- Variant selection UI
- `email-signup` -- Newsletter signup form

## Validation

After editing any theme file, validate using the Shopify dev MCP:
```
validate_theme(conversationId, absoluteThemePath, filesCreatedOrUpdated)
```
