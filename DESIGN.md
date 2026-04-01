# Design System Strategy: Atmospheric Precision

## 1. Overview & Creative North Star
This design system is built upon the "Atmospheric Precision" North Star. For a Brazilian AI and automation powerhouse, the UI must transcend the "SaaS template" look. We are not just building software; we are crafting a digital atmosphere where complex intelligence feels weightless and intuitive.

The system breaks away from traditional grid-bound layouts by using **intentional asymmetry** and **high-contrast typographic scales**. By utilizing the "Humbleteam" editorial influence, we treat the screen as a canvas where empty space is a deliberate design choice, not a void. We replace rigid structural lines with tonal depth and glassmorphism, creating a signature aesthetic that feels premium, cinematic, and profoundly modern.

---

## 2. Colors & Surface Logic
The palette is rooted in a deep, nocturnal base (`surface: #131313`) punctuated by the high-energy vibrancy of Electric Blue (`primary: #b9c3ff` / `#4F6EF7`).

*   **The "No-Line" Rule:** To maintain an ultra-premium feel, designers are strictly prohibited from using 1px solid borders to section off content. Boundaries must be defined through background shifts. For instance, a section utilizing `surface_container_low` should sit directly against a `surface` background. The transition of tone is the divider.
*   **Surface Hierarchy & Nesting:** Treat the UI as a series of physical layers. Use the `surface_container` tiers to create "nested" depth. 
    *   *Level 0:* `surface_container_lowest` (Background)
    *   *Level 1:* `surface_container` (Major sections)
    *   *Level 2:* `surface_container_high` (Interactive cards or floating elements)
*   **The "Glass & Gradient" Rule:** Floating elements (like Navbars or Modals) must utilize Glassmorphism. Apply `surface` colors at 60% opacity with a `backdrop-filter: blur(24px)`. 
*   **Signature Textures:** For primary CTAs and hero highlights, move beyond flat colors. Use a subtle linear gradient transitioning from `primary` (#b9c3ff) to `primary_container` (#6e88ff) at a 135-degree angle to add "soul" and dimension.

---

## 3. Typography: The Editorial Voice
We utilize a dual-font strategy to balance technical precision with sophisticated branding.

*   **Display & Headlines (Plus Jakarta Sans):** These are the "Hero" elements. Use `display-lg` (3.5rem) and `headline-lg` (2rem) with bold weights and tight letter-spacing (-0.02em). This conveys the authoritative, "Big AI" presence.
*   **Body & Labels (Inter):** For utility and readability. Inter provides a neutral, high-legibility contrast to the expressive headlines. 
*   **Editorial Contrast:** To achieve a high-end look, pair a massive `display-lg` headline with a small, uppercase `label-md` (0.75rem) sub-header. This extreme scale variance is the hallmark of premium digital experiences.

---

## 4. Elevation & Depth
Depth is achieved through **Tonal Layering** rather than traditional structural shadows.

*   **The Layering Principle:** Stack `surface-container` tiers to create natural lift. Place a `surface_container_highest` card on a `surface_container_low` section to create a soft, organic hierarchy.
*   **Ambient Shadows:** If a floating effect is required (e.g., a modal), use an "Ambient Shadow." Shadows must be extra-diffused: `blur: 40px`, `y-offset: 20px`, and `opacity: 8%`. The shadow color should be a tinted version of `surface_container_lowest`, never pure black.
*   **The "Ghost Border" Fallback:** If a container requires definition against a similar background, use a "Ghost Border." Apply the `outline_variant` token at **15% opacity**. 100% opaque borders are strictly forbidden.
*   **Interaction Depth:** Upon hover, elements should not just change color; they should "lift" by shifting from `surface_container_low` to `surface_container_high`, creating a tactile sense of responsiveness.

---

## 5. Components

### Navigation & Command
*   **Floating Navbar:** A translucent bar using `surface` at 50% opacity with `backdrop-filter: blur(20px)`. No border. Use `spacing-6` (2rem) for horizontal padding.
*   **Buttons:**
    *   *Primary:* Gradient fill (`primary` to `primary_container`), `rounded-full`, and `spacing-5` horizontal padding.
    *   *Secondary:* Glass background with a `Ghost Border`.
    *   *Tertiary:* Pure text using `primary` color with a subtle underline on hover.

### Data & Content
*   **Cards:** Use `surface_container_low` with `rounded-xl`. Forbid divider lines within cards. Separate headers from body text using `spacing-4` (1.4rem).
*   **Chips:** Minimalist pills using `surface_container_highest`. Text should be `label-md` in `on_surface_variant`. 
*   **Lists:** Forbid divider lines. Use `spacing-3` of vertical white space between items. Highlight selected items by shifting their background to `surface_container_high`.

### Inputs & Interaction
*   **Input Fields:** `surface_container_lowest` background. No border in default state. On focus, apply a `Ghost Border` using the `primary` color and a subtle outer glow (4px blur).
*   **Checkboxes/Radios:** Use `primary` for the selected state. The "unselected" state should be a subtle `outline_variant` ring with no fill.

---

## 6. Do’s and Don’ts

### Do
*   **Do** embrace generous whitespace. If in doubt, add more padding.
*   **Do** use `Roboto Mono` (from the brand profile) for technical data points or AI-generated strings to emphasize the "automation" aspect.
*   **Do** use smooth fade-in animations (duration: 400ms, easing: cubic-bezier(0.4, 0, 0.2, 1)) for all page transitions.

### Don’t
*   **Don’t** use 1px solid borders for layout containers.
*   **Don’t** use pure `#000000` for backgrounds; stick to the nuanced `surface` tokens to maintain depth.
*   **Don’t** crowd the interface. This system thrives on a "Less, but better" philosophy.
*   **Don’t** use standard "drop shadows" with high opacity. They break the glassmorphic illusion.