# Design System: Precision Editorial

## 1. Overview & Creative North Star

### Creative North Star: "The Architectural Ledger"
The design system is built upon the concept of the "Architectural Ledger." Surveying is a profession of extreme precision, where data meets the earth. Our visual language must reflect this by moving away from generic app templates and toward a high-end editorial experience. 

We break the "standard mobile" look by utilizing **intentional asymmetry**, **oversized typography scales**, and **layered depth**. Instead of traditional boxes, we treat the UI as a series of sophisticated, overlapping planes. This system prioritizes breathing room (whitespace) as a functional tool to reduce cognitive load while maintaining a professional, authoritative tone.

---

## 2. Colors

This system utilizes a high-contrast palette rooted in professional greens and deep charcoals, optimized for clarity and premium feel.

### The "No-Line" Rule
**Explicit Instruction:** Use of 1px solid borders for sectioning or card definition is strictly prohibited. Structure must be defined through background color shifts or surface elevation tiers.
*   **Surface Separation:** A `surface-container-low` section sitting on a `surface` background provides all the definition needed.

### Surface Hierarchy & Nesting
Treat the interface as physical layers of fine paper. 
*   **Background:** `surface` (#f9f9f9)
*   **Lower Tier:** `surface-container-low` (#f3f3f4) for secondary content areas.
*   **Highest Tier:** `surface-container-highest` (#e2e2e2) for active elements.
*   **Nesting:** Place a `surface-container-lowest` (#ffffff) card inside a `surface-container-low` (#f3f3f4) section to create a soft, natural lift.

### The Glass & Gradient Rule
*   **Glassmorphism:** For the Bottom Tab Bar and high-level overlays, use `surface` at 80% opacity with a `backdrop-blur` of 20px. This ensures the UI feels integrated and modern.
*   **Signature Textures:** Main Action Buttons and Hero Cards should use a subtle linear gradient from `primary` (#3b6a00) to `primary-container` (#74b72c) at a 135-degree angle. This adds "visual soul" and depth that flat hex codes cannot achieve.

---

## 3. Typography

The typography strategy pairs the technical precision of **Inter** with the editorial authority of **Plus Jakarta Sans**.

*   **Display & Headlines (Plus Jakarta Sans):** Used for impactful "Editorial" moments. These should be set with tight letter spacing (-0.02em) to feel custom and premium.
*   **Titles & Body (Inter):** Used for data-heavy surveying reports and descriptions. Inter provides the "Trustworthy" legibility required for technical details.
*   **Labels (Work Sans):** Used for micro-copy and tags. The slightly wider stance of Work Sans ensures readability at tiny scales (11px-12px).

**Hierarchy as Identity:**
By using `display-lg` (3.5rem) for key landing stats and `body-sm` for legal details, we create a high-contrast "Big & Small" dynamic that feels like a luxury architectural magazine rather than a basic utility app.

---

## 4. Elevation & Depth

### Tonal Layering
Depth is achieved through the Spacing Scale and color, not lines.
*   **Layering Principle:** Stack `surface-container-lowest` on `surface-container-low`. The 1% difference in luminosity is enough for the human eye to perceive hierarchy without visual clutter.

### Ambient Shadows
When a "Floating Action Button" (FAB) or Inquiry Card requires a shadow:
*   **Softness:** Use a blur radius of at least 24px.
*   **Opacity:** 4% to 8% max.
*   **Tinting:** Never use pure black (`#000000`) for shadows. Use a tinted version of `on-surface` (#1a1c1c) to mimic natural light hitting a physical surface.

### The "Ghost Border" Fallback
If a boundary is required for accessibility (e.g., input fields), use the `outline-variant` (#c1cab3) at **15% opacity**. This creates a "whisper" of a line that guides the eye without breaking the "No-Line" Rule.

---

## 5. Components

### Cards & Lists
*   **Style:** `surface-container-lowest` with `roundedness-lg` (1rem).
*   **Requirement:** Forbid divider lines. Separate list items using `spacing-4` (1rem) of vertical white space or a subtle background toggle between `surface` and `surface-container-low`.

### Buttons (The "Precision" Set)
*   **Primary:** Gradient (`primary` to `primary-container`), white text, `roundedness-md`.
*   **Secondary:** `surface-container-high` background with `primary` text. No border.
*   **Floating Action Button (Inquiries):** An oversized `primary` circle or extended pill. It must utilize the **Glassmorphism** principle if it overlaps content.

### Inputs (Field Survey Style)
*   **Default:** `surface-container-low` background, no border, `roundedness-sm`.
*   **Active:** A 2px bottom-only stroke using `primary`. This references the "baseline" of a surveyor's level.

### Navigation: The Glass Bottom Bar
*   **Pattern:** A floating tab bar, inset from the screen edges by `spacing-4`. 
*   **Effect:** `backdrop-blur` with 80% opacity `surface`. This allows the map or content to peak through, maintaining a sense of scale.

---

## 6. Do's and Don'ts

### Do:
*   **Do** use asymmetrical margins. A wider left margin for headlines creates an editorial "indented" look.
*   **Do** use `primary-fixed-dim` (#94da4c) for subtle highlights in technical data tables.
*   **Do** prioritize vertical rhythm. Use the `spacing-8` (2rem) and `spacing-12` (3rem) tokens to let the layout breathe.

### Don't:
*   **Don't** use 100% opaque black text. Always use `on-surface` (#1a1c1c) for better visual comfort.
*   **Don't** use standard "Drop Shadows." If it looks like a default Photoshop style, it is too heavy.
*   **Don't** use dividers. If two pieces of content feel too close, increase the spacing token rather than adding a line.