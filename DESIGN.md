# Design System Specification: The Precision Atelier

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Precision Atelier."** 

This system moves beyond the generic "craftsman" aesthetic to embrace a Swiss-inspired, high-end editorial experience. It is designed to feel like a high-performance architectural blueprint: structured, intentional, and impeccably clean. We achieve this by rejecting the standard "boxed-in" UI. Instead, we use **asymmetric layouts**, **extreme white space**, and **tonal layering** to create a sense of digital permanence. 

The goal is to communicate "Swiss quality" not through decoration, but through the perfect alignment of elements and the deliberate weight of typography. Every pixel must feel like it was placed with a master craftsman’s chisel.

---

## 2. Colors: Tonal Sophistication
Our palette is anchored by deep professional slates and a sophisticated metallic secondary. We do not use color to decorate; we use it to direct attention and signify value.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to define sections. Layout boundaries must be defined solely through background color shifts. 
- Use `surface_container_low` (#f3f3f6) against the main `surface` (#f9f9fc) to create structural zones.
- This creates a seamless, "milled" look where components appear to be carved out of a single block rather than pasted on top.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. Use the surface tiers to create depth:
- **Level 0 (Base):** `surface` (#f9f9fc)
- **Level 1 (Sectioning):** `surface_container_low` (#f3f3f6)
- **Level 2 (In-page Components):** `surface_container_highest` (#e2e2e5)
- **Level 3 (Floating/Interactive):** `surface_container_lowest` (#ffffff)

### The "Glass & Gradient" Rule
To elevate the "Modern" requirement, floating elements (like navigation bars or modal overlays) should utilize **Glassmorphism**. Use `surface` with 80% opacity and a `20px` backdrop blur. 
For primary CTAs, do not use flat fills. Apply a subtle linear gradient from `primary` (#0044c9) to `primary_container` (#0059ff) at a 135-degree angle to provide a "soul" and polished finish.

---

## 3. Typography: The Editorial Voice
We utilize **Inter** as our typographic foundation. It is a font of Swiss-style utility and precision.

- **Display Scale:** Use `display-lg` (3.5rem) with a negative letter-spacing of `-0.02em`. This mimics high-end architectural magazines and establishes immediate authority.
- **Headline vs. Body:** Headlines should be set in `on_surface` (#1a1c1e) to provide high-contrast grounding. Body text in `body-lg` (1rem) provides the breathing room necessary for premium readability.
- **The Technical Label:** `label-sm` (0.6875rem) should be used for technical specs, measurements, or metadata. Set these in All Caps with `+0.05em` letter spacing to evoke the feeling of an engraver's mark.

---

## 4. Elevation & Depth: Tonal Layering
In "The Precision Atelier," depth is a function of light and material, not artificial shadows.

### The Layering Principle
Avoid traditional drop shadows for standard cards. Achieve "lift" by placing a `surface_container_lowest` (#ffffff) element on top of a `surface_container_low` (#f3f3f6) background. The subtle shift from off-white to pure white creates a sophisticated, natural elevation.

### Ambient Shadows
When a floating effect is required (e.g., a high-priority modal):
- **Blur:** 40px - 60px.
- **Opacity:** 4% - 8%.
- **Color:** Use a tinted shadow based on `on_surface` (#1a1c1e) rather than pure black to keep the light feeling organic.

### The "Ghost Border" Fallback
If a visual separator is required for accessibility, use the **Ghost Border**: a 1px stroke using `outline_variant` (#c3c5d9) at **15% opacity**. It should be felt, not seen.

---

## 5. Components: Precision Machined
Every component must feel "solid." We utilize the `DEFAULT` roundedness (**0.25rem**) to maintain a sharp, disciplined edge while avoiding the aggressiveness of 90-degree corners.

- **Buttons:** 
    - **Primary:** Gradient fill (`primary` to `primary_container`), `on_primary` text. No border.
    - **Secondary:** `secondary_container` (#fed488) background with `on_secondary_container` (#785a1a) text. This is our "Craftsman Gold" moment.
- **Input Fields:** Use `surface_container_highest` for the field fill. Instead of a full border, use a 2px bottom-stroke of `primary` (#0044c9) only upon focus. This keeps the form feeling "structured" but open.
- **Cards & Lists:** **Strict Rule:** No divider lines. Use `80px` of vertical white space (from our spacing scale) to separate list items, or alternating tonal shifts between `surface` and `surface_container_low`.
- **Chips:** Use `xl` (0.75rem) roundedness for chips to distinguish them as "interactive tokens" against the more rectangular, solid layout of the rest of the system.
- **The "Precision Indicator":** For active states (like a selected tab), use a small, 4px square of `tertiary` (#992900). This "burnt orange/brick" accent acts as a tiny focal point of craftsmanship.

---

## 6. Do's and Don'ts

### Do:
- **Embrace Asymmetry:** Place a `display-md` headline on the left with a massive `120px` gutter before the body text on the right.
- **Use "Data as Art":** Treat numbers and measurements with the `display` scale to highlight the craftsman's precision.
- **Let it Breathe:** If you think there is enough white space, add 20% more.

### Don't:
- **No 1px Lines:** Never use a solid 100% opaque border to separate content.
- **No Pure Blacks:** Always use `on_surface` (#1a1c1e) for text to maintain a "slate/charcoal" professional depth.
- **No "Bubbliness":** Avoid `full` (9999px) roundedness on anything except chips and tags. The system must feel "built," not "inflated."
- **No Generic Grids:** Avoid the 12-column "bootstrap" look. Offset your containers to create a custom, editorial rhythm.