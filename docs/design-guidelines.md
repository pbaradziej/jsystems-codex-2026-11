# ING homepage design reference

Source: [ING Bank Śląski](https://www.ing.pl/). Captured on 2026-11-05 using Playwright CLI 0.1.23 and a visible Chrome window with a dedicated persistent profile. Desktop viewport: 1440 x 1000 CSS pixels. Optional cookies were rejected; the consent dialog was confirmed absent and the full-page screenshot was visually inspected.

This is an observed homepage reference, not an official ING specification. Campaign content can change. Measurements describe the default desktop state; responsive breakpoints, interaction states and form validation were not established. Null tokens mean unknown, not transparent. No application code was changed.

## Assets

| File | Purpose |
| --- | --- |
| [design-tokens.json](../assets/design-tokens.json) | Structured tokens, source URLs, original font-face declarations and measurement scope |
| [homepage.png](../assets/homepage.png) | Full-page reference without overlays |
| [logo.svg](../assets/logo.svg) | Original header wordmark: navy ING and orange lion |
| [favicon.ico](../assets/favicon.ico) | Original site favicon |

All downloaded font files are linked in the typography table below. Existing repository assets are outside this extraction.

## Colors

| Token | Hex | Observed usage |
| --- | --- | --- |
| brand.primary | #FF6200 | Hero panel and orange brand accents |
| brand.accent | #7724FF | Hero CTA pseudo-element |
| background.default | #FFFFFF | background / default |
| background.light | #F0F0F0 | background / light |
| background.warm | #F7F4F1 | background / warm |
| background.lavender | #F0E8FE | Account-plan section |
| background.promo | #F1E9FF | Mortgage promo panel |
| background.service | #EDEDF5 | Service information section |
| text.primary | #0D0804 | text / primary |
| text.secondary | #696969 | text / secondary |
| text.muted | #767676 | text / muted |
| text.link | #525199 | Utility and editorial links |
| text.onDark | #FFFFFF | text / onDark |

The wordmark contains its own navy color; retain its source artwork. Error, success and overlay colors were not verified and remain null. Do not assign semantic validation roles to campaign colors.

## Typography

Body: `INGme, Helvetica, Arial, sans-serif`. Display headings: `"ING Display", INGme, Helvetica, Arial, sans-serif`. INGme regular 400 and bold 700 were loaded. ING Display is a variable font declared for weights 400-900; observed headings use 700. The original text faces use normal style and font-display: swap. ProximaNova is declared in the source CSS but was not loaded for this homepage; it is not the primary font.

| Downloaded file (repository path via link) | Family and weight |
| --- | --- |
| [INGdisplay-VAR.2c99c41224fafbfb8699.woff2](../assets/fonts/ing-display/INGdisplay-VAR.2c99c41224fafbfb8699.woff2) | ING Display, variable 400-900 |
| [INGMe-Bold.5c73399898ab77d6f1c7.woff](../assets/fonts/ingme/INGMe-Bold.5c73399898ab77d6f1c7.woff) | INGme, 700 |
| [INGMe-Regular.31ed947193fd3b0e0466.woff](../assets/fonts/ingme/INGMe-Regular.31ed947193fd3b0e0466.woff) | INGme, 400 |
| [ProximaNova-bold.9ff94b872c7bdcb65dbb.woff](../assets/fonts/proximanova/ProximaNova-bold.9ff94b872c7bdcb65dbb.woff) | ProximaNova, 700, declared but not loaded in the observed page |
| [ProximaNova-Light.84d721b3abc43bd990f7.woff](../assets/fonts/proximanova/ProximaNova-Light.84d721b3abc43bd990f7.woff) | ProximaNova, 300, declared but not loaded in the observed page |
| [ProximaNova-regular.4523679e932bedc39f2e.woff](../assets/fonts/proximanova/ProximaNova-regular.4523679e932bedc39f2e.woff) | ProximaNova, 400, declared but not loaded in the observed page |
| [web-fonts.woff](../assets/fonts/web-fonts/web-fonts.woff) | web-fonts, icon glyphs; not a text family |

Verify the license of every downloaded font before use or redistribution. For local @font-face rules, use the linked file, its declared family, normal style, swap display and its actual weight (400/700 for INGme, 400 900 for ING Display). Use woff format for .woff and woff2 for .woff2. The web-fonts asset is an icon font; do not apply it to prose.

| Role | Size / line height | Weight |
| --- | --- | --- |
| Legal/footer small text | 12px / varies by element | 400 |
| Supporting text | 14px / varies by element | 400 |
| Body | 16px / 20px | 400 |
| Navigation and card titles | 16px / 24px | 400 / 700 |
| Hero CTA | 19px / 23.75px | 700 |
| Section heading | 24px / 32px | 700 |
| Mortgage promo heading | 32px / 32px | 700 |
| Hero heading | 80px / 80px | 700 |

The hero is an h2 in the source; no visible h1 was found. Use a suitable accessible heading hierarchy in the application rather than copying the source semantics blindly.

## Spacing and layout

A 4px base unit is an inferred normalization, supported by observed 4, 8, 12, 16, 24 and 32px values. It is not a recovered official scale. Navigation links have 12px padding. Account cards have 32px 24px 8px padding; their observed width is 290px with a 24px horizontal gap. Treat these dimensions as desktop reference values, not fixed mobile dimensions. Hero content uses a two-column split; sections below use four-card grids and paired editorial columns.

## Border radius

| Token | Value | Context |
| --- | --- | --- |
| none | 0px | Default blocks and hero CTA element |
| sm | 4px | Search control outer corners; input itself uses 4px 0 0 4px |
| control | 8px | Login and account utility controls |
| card | 14px | Product and account cards |
| lg | 16px | Rounded secondary panels observed in the page |
| round | 23px | Rounded element observed in the page; not a universal button rule |

The purple hero CTA looks organic because its span::before uses a CSS clip-path shape. Its computed border radius is 0px. The exact measured clip-path is in the button token; a standard pill would be an approximation.

## Components

- Header: white surface with a light-gray utility/segment strip, wordmark and search row, then the main product navigation. Keep the logo separate from navigation text.
- Navigation: INGme 16px, regular 400, 24px line height, dark text and 12px link padding. The active segment has an orange underline in the reference.
- Primary hero CTA: white bold text, purple #7724FF pseudo-element, 19px type, 12px 25px padding and 64px observed height. Preserve the organic silhouette when close visual matching is required.
- Login: transparent surface, #525199 text and 1px outline, 8px corners, 5px 11px padding, 16px bold type and 24px line height.
- Search: white input, INGme 16px, 5px 0 5px 11px padding, rounded left corners and inset gray shadow. Search action occupies the matching right side. This is the only inspected input; validation, focus and disabled states were not measured.
- Cards: white surface, 14px corners and shadow `0 18px 40px rgba(0,0,0,.08), 0 5px 15px rgba(0,0,0,.04)`. Use compact centered illustrations, bold titles and short descriptions.
- Promotional sections: strong orange hero with white type and product imagery, light-lavender account grid, and photography with a pale promo text panel. No separate promo bar was established.
- Editorial and footer: two-column news/service layout followed by a light-gray multi-column footer. Use subdued purple editorial links and small supporting text.

Hover, keyboard focus, disabled controls, loading states and mobile behavior need separate inspection before implementation. Do not assume these default-state measurements define those states.

## Logo usage and rights

The saved [wordmark](../assets/logo.svg) was fetched in-page from [the original header SVG](https://www.ing.pl/_static/img/logo_lsl_new.5800ff4f65b35cf926f5.svg). Preserve proportions and source colors; place it on white as observed. No inverted variant was obtained, and dark-background placement is not verified. The favicon was fetched from [the original icon](https://www.ing.pl/_static/icon/favicon.240313eb651325fefc54.ico).

ING logos, fonts, favicon and page imagery may be protected. Verify usage and redistribution rights before incorporating them in an application or publishing these reference assets. Download availability does not establish permission.

## Visual style summary

The page combines a vivid orange brand anchor with white space and warm dark text. Purple calls to action and pale lavender sections add a playful campaign layer. Large display typography, organic button shapes and rounded illustrated cards make the public banking page approachable. Soft shadows and orderly navigation maintain a clear hierarchy around dense product information.

## Verification and limits

The public page loaded successfully in visible Chrome. The delayed cookie dialog was dismissed and its reject button no longer appeared; the saved screenshot was opened and checked for overlays. All downloaded fonts have plausible nonzero sizes and font file signatures; the SVG and favicon were checked as their actual formats. JSON parsing, local Markdown links and scoped Git checks were completed. The site reported one external Adobe tag load failure (net::ERR_ADDRESS_INVALID); this did not prevent the inspected content or fonts from loading. No login, customer data, live banking flow or application runtime was involved.
