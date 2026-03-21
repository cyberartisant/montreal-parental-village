# Design System Documentation

## 1. Overview & Creative North Star: "The Empathetic Anchor"

This design system is engineered to bridge the gap between high-stakes institutional trust and the warmth required for a community-focused parental support network. Inspired by the authoritative structure of global humanitarian organizations, we are moving away from "template-driven" non-profit layouts toward a **High-End Editorial** experience.

**The Creative North Star: The Empathetic Anchor.**
Our layouts should feel grounded and stable (The Anchor) yet breathable and human (The Empathetic). We achieve this through:
- **Intentional Asymmetry:** Breaking the rigid 12-column grid with overlapping elements and offset typography to create a sense of organic movement.
- **Tonal Depth:** Replacing harsh structural lines with a sophisticated hierarchy of "surfaces" that feel like stacked premium stationery.
- **Urgency through Precision:** Using a high-contrast typography scale where large, bold headlines meet generous whitespace, creating a sense of "quiet urgency."

---

## 2. Color & Surface Architecture

The palette leverages a commanding "Institutional Red" and a "Trust Blue," balanced by a sophisticated range of neutral surfaces.

### The "No-Line" Rule
To maintain a premium, modern aesthetic, **1px solid borders are strictly prohibited** for sectioning or containment. Boundaries must be defined through:
1.  **Background Color Shifts:** Placing a `surface-container-low` section against a `surface` background.
2.  **Tonal Transitions:** Using subtle shifts between container tiers to imply edge and weight.

### Surface Hierarchy & Nesting
Treat the UI as a physical stack of materials. Use the `surface-container` tokens to create "nested" depth:
- **Base Layer:** `surface` (#faf9fb) for the primary background.
- **Secondary Sectioning:** `surface-container-low` (#f4f3f5) for large content blocks.
- **Interactive Cards:** `surface-container-lowest` (#ffffff) to provide a "lifted" feel.
- **High-Impact Insets:** `surface-container-highest` (#e2e2e4) for utility bars or specialized sidebars.

### The "Glass & Gradient" Rule
Standard flat colors can feel "out-of-the-box." To elevate the experience:
- **Signature CTAs:** Apply a linear gradient (Top-Left to Bottom-Right) transitioning from `primary` (#bb001d) to `primary-container` (#e7142a) to add "soul" and dimension to buttons.
- **Floating Navigation:** Use **Glassmorphism** for sticky headers or floating action menus. Use a semi-transparent `surface` color (e.g., 80% opacity) with a `backdrop-blur` of 12px to 20px.

---

## 3. Typography: Authority Meets Accessibility

This system utilizes two high-performance typefaces: **Public Sans** for structure and **Inter** for utility.

- **Display & Headlines (Public Sans):** This face provides an authoritative, "official" tone. Use `display-lg` and `headline-lg` with tight letter-spacing (-0.02em) to create an editorial, high-impact feel for hero sections.
- **Body & Labels (Inter):** Inter is the workhorse of the system. It offers maximum readability for parents who may be viewing the site in stressful, "urgent" situations.
- **The Hierarchy Strategy:** We use extreme scale differences. A `display-lg` headline should often be paired directly with a `body-lg` subhead to create a sophisticated, curated contrast that feels intentional and high-end.

---

## 4. Elevation & Depth: Tonal Layering

Traditional drop shadows often look muddy. We convey hierarchy through **Tonal Layering** and **Ambient Light**.

- **The Layering Principle:** Place a `surface-container-lowest` card on a `surface-container-low` section. The slight color shift creates a natural "lift" that is easier on the eyes than a shadow.
- **Ambient Shadows:** When a floating effect is required (e.g., for a modal or primary action button), use extra-diffused shadows.
    - **Shadow Color:** Use a tinted version of `on-surface` (#1a1c1d) at 4-6% opacity. 
    - **Blur:** Minimum 24px.
- **The "Ghost Border" Fallback:** If a border is required for accessibility (e.g., in high-contrast modes), use the `outline-variant` token at **15% opacity**. Never use a 100% opaque border.

---

## 5. Component Guidelines

### Buttons (The Urgency Drivers)
- **Primary:** `primary` background with the signature gradient. `rounded-md` (0.375rem). Use `label-md` in all caps with +0.05em tracking for an authoritative "Action" feel.
- **Secondary:** `secondary` (#00658f) background. Use for supportive, non-emergency actions (e.g., "Join the Community").
- **Tertiary:** No background. Use `on-surface` text with a `surface-container-high` hover state.

### Cards & Lists (The Editorial Feed)
- **No Dividers:** Prohibit 1px horizontal lines between list items. Use `spacing-6` or `spacing-8` of vertical white space to separate content.
- **Layout:** Cards should use `surface-container-lowest` and a `rounded-lg` (0.5rem) corner. For an editorial look, allow images to "bleed" to the edges of the card or overlap the top edge.

### Inputs & Forms
- **Field Styling:** Instead of outlined boxes, use "Filled" inputs with `surface-container-low`. 
- **Active State:** On focus, transition the background to `surface-container-lowest` and add a 2px bottom-accent using the `primary` token.

### Specialized Component: "The Village Beacon"
A unique floating card component for "Urgent Support." 
- **Style:** Glassmorphic background (80% `primary-container`, 20px blur).
- **Placement:** Bottom-right, offset by `spacing-10`.
- **Purpose:** Immediate access to emergency parental resources.

---

## 6. Do’s and Don’ts

### Do:
- **Use "White Space" as a Tool:** Treat empty space as a structural element, not just a gap. Refer to `spacing-20` and `spacing-24` for hero section padding.
- **Prioritize Tonal Shifts:** Always check if a background color change can solve a layout issue before reaching for a border or shadow.
- **Maintain High Contrast:** Ensure all text on `primary` or `secondary` backgrounds utilizes `on-primary` (#ffffff) or `on-secondary` (#ffffff).

### Don’t:
- **Don’t use "Default" Black:** Never use #000000. Use `on-surface` (#1a1c1d) for text to keep the UI feeling premium and soft.
- **Don’t Over-Round:** Stick to `rounded-md` or `rounded-lg`. Avoid "pill" shapes for buttons unless they are small utility chips, as they can undermine the "authoritative" feel of the non-profit.
- **Don’t Crowd the Content:** If a layout feels cluttered, increase the spacing by two steps on the scale (e.g., move from `spacing-6` to `spacing-10`).