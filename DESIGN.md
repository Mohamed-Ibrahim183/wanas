# Design System Strategy: Nocturnal Vibrancy

## 1. Overview & Creative North Star: "The Electric Salon"
This design system is built to move beyond the static "dark mode" template. The Creative North Star is **"The Electric Salon"**—a digital space that feels like a high-end, late-night gathering. It combines the deep, soulful intimacy of velvet-textured purples with the high-energy "spark" of bioluminescent teals.

To achieve a "signature" look, we reject the rigid, boxed-in layouts of standard SaaS products. Instead, we utilize **intentional asymmetry**, **overlapping glass layers**, and **extreme typographic contrast**. We don't just display content; we curate it within a fluid, celebratory environment that prioritizes human connection over grid-based perfection.

---

## 2. Color & Atmospheric Depth
Our palette is not just a set of hex codes; it is a hierarchy of light. We treat the UI as a physical space where light emits from the center and fades into the shadows.

### The "No-Line" Rule
**Borders are strictly prohibited for sectioning.** To separate content, you must use "Tonal Carving." Transition between `surface-container-low` and `surface-container-high` to define edges. High-end design is felt through value shifts, not seen through lines.

### Surface Hierarchy & Nesting
Depth is achieved by "stacking" the surface tiers:
*   **Base Layer:** `background` (#160037).
*   **The "Stage":** Use `surface-container` for the primary content area.
*   **The "Spotlight":** Use `surface-bright` for active or featured sections.
*   **The "Recess":** Use `surface-container-lowest` (#000000) for persistent navigation or utility bars to create a grounded sense of "floor."

### The "Glass & Gradient" Rule
To capture the "Celebratory" vibe, floating elements (Modals, FABs, Popovers) should use **Glassmorphism**:
*   **Fill:** `surface_variant` at 60% opacity.
*   **Effect:** 20px to 40px Background Blur.
*   **Signature Texture:** Main CTAs should not be flat. Apply a subtle linear gradient from `primary` (#6cf0f0) to `primary_container` (#22bbbb) at a 135° angle to give the action "weight" and a metallic, premium sheen.

---

## 3. Typography: Editorial Rhythm
We use **Be Vietnam Pro** not as a utility font, but as a brand voice. The system relies on "Dramatic Scaling"—using very large display type alongside tightly tracked labels to create an editorial, magazine-like feel.

*   **Display (lg/md):** Reserved for "Hero Moments." Use `display-lg` with -2% letter spacing to create a bold, authoritative presence in the `on_background` color.
*   **Headlines:** Used to introduce new chapters of the community experience. These should always be high contrast against the background.
*   **Body (md/lg):** Optimized for readability with a generous 1.6x line-height. Never use pure white; use `on_surface_variant` (#bc9af8) for body text to reduce eye strain and maintain the "Nocturnal" atmosphere.
*   **Labels:** Use `label-md` in all-caps with +5% letter spacing for category tags or metadata, adding a touch of sophisticated "Metadata Chic."

---

## 4. Elevation & Depth: Tonal Layering
Traditional shadows look "muddy" on deep purple backgrounds. We use **Ambient Glows** instead.

*   **The Layering Principle:** Place `surface-container-lowest` cards on a `surface-container-low` section. The "darker-on-lighter" approach creates a sense of "carved out" space rather than "pasted on" boxes.
*   **Ambient Shadows:** For floating components, use a shadow with a 40px blur, 0px offset, and 8% opacity. The color should be `#000000` mixed with 10% `primary` to ensure the shadow feels like a natural occlusion of the ambient purple light.
*   **The "Ghost Border" Fallback:** If a boundary is required for accessibility, use the `outline_variant` token (#56358c) at **15% opacity**. It should be a whisper of an edge, not a shout.

---

## 5. Components

### Buttons: The "Energy" Elements
*   **Primary:** Full round (`9999px`). Gradient fill from `primary` to `primary_container`. Text color: `on_primary` (#005858).
*   **Secondary:** No fill. A "Ghost Border" of `primary` at 40% opacity. This makes the button feel like it’s vibrating with light.
*   **Tertiary/Text:** Purely typographic, using `primary_dim` to indicate interactivity without visual clutter.

### Cards & Lists: The "No-Divider" Mandate
*   **Cards:** Use `surface-container-high`. Rounding must be `xl` (3rem) for a friendly, community-focused embrace. 
*   **Dividers:** **Forbidden.** Use a 32px vertical gap (`Spacing-32`) or a subtle shift to `surface-container-low` to separate list items.
*   **Chips:** Use `secondary_container` for the background and `on_secondary_container` for the text. Rounding: `full`.

### Input Fields: The "Luminous" State
*   **Default:** `surface-container-highest` background, no border.
*   **Focused:** Use a 1px `tertiary` (#47fbbe) "Ghost Border" and a subtle outer glow (4px blur) of the same color. The cursor should always be the `primary` color.

### Signature Component: The "Community Pulse"
*   A custom component for this system: A floating, glassmorphic bar that sits at the bottom of the screen using `surface_container_highest` at 70% opacity with a heavy blur. It houses "Vibe" reactions or quick-join buttons, feeling integrated into the "Electric Salon" atmosphere.

---

## 6. Do's and Don'ts

### Do:
*   **Do** embrace negative space. If you think there's enough room between elements, double it.
*   **Do** use `tertiary` (#47fbbe) for "success" or "positive community" moments—it’s more vibrant than a standard green.
*   **Do** overlap elements. Let a card "peak" over a header boundary to create a sense of three-dimensional space.

### Don't:
*   **Don't** use `#000000` for backgrounds unless it's the `surface-container-lowest` utility layer. Pure black kills the "purple glow" of the system.
*   **Don't** use sharp corners. Everything must be `full` or `xl` roundness to maintain the "Celebratory" and approachable brand personality.
*   **Don't** use high-contrast white text for long-form body copy. It is too jarring. Stick to the `on_surface_variant` violet-grey.