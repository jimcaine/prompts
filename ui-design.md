## Design System Prompt
**Aesthetic Direction:** *Dark Luxury Utilitarian* — the interface should feel like a Bloomberg terminal crossed with a high-end editorial publication. Authoritative, data-dense, and precise without ever feeling clinical or cold.

---
### Color Palette
Use a near-black background (around `#0d0f14`) as the base, with layered dark surface tones (`#141720`, `#1c2030`) to create depth hierarchy. The primary accent is a **warm antique gold** (`#c8a96e`) — used sparingly for labels, CTAs, and decorative dividers. A secondary **seafoam/teal** accent (`#6ec8a9`) is reserved for positive states and success indicators. Danger/negative states use a muted brick red (`#e07070`). Body text is an off-white (`#e8e6e0`) — never pure white. Muted text is a cool slate (`#7a7f94`). All colors should be declared as CSS custom properties for full consistency.

---
### Typography
Pair two fonts only:
- **Display / Headings:** *DM Serif Display* — use regular and italic weights. Headlines should feel editorial and refined. Italic variant used for emphasis within headlines (e.g., a key phrase in a two-line heading).
- **Body / UI / Data:** *DM Mono* — monospace, used for everything else: labels, inputs, data values, table cells, buttons. This creates a deliberate "instrument panel" feel for data-heavy interfaces.

Never use sans-serif system fonts (no Inter, Roboto, Arial). The monospace-for-UI choice is intentional and non-negotiable — it gives the interface its character.

---
### Layout & Spacing
- Primary layout: a two-column asymmetric grid — narrower input/control panel on the left (~380px fixed), wider output/results area on the right (flexible).
- Panels use flat rectangular containers with a `1px` border in the dark border color — no rounded corners, no box shadows, no cards with elevation.
- Generous internal padding (`24px`) within panels. Tight but consistent spacing between fields (`18px`).
- Section dividers are a labeled rule: small all-caps text in the gold accent, followed by a horizontal line that fills remaining width.

---
### Form Controls & Inputs
- All inputs and selects: dark background, `1px` border, monospace font, no rounded corners. Border changes to gold accent on focus — the only interactive color feedback needed.
- Number inputs: suppress browser spinners entirely.
- Buttons: full-width, solid gold background, near-black text, all-caps monospace label with wide letter-spacing. No border-radius. Hover state is a simple opacity reduction.

---
### Data Display Components
Three component types for output:
1. **Verdict Banner** — a wide panel with a colored left border (4px) indicating status: teal for positive, red for negative, gold for neutral. Contains a small eyebrow label, a large serif headline verdict, and right-aligned supporting detail text. Background tint matches the status color at very low opacity.
2. **Metric Cards** — a grid of small rectangular cards (3-column). Each card has: a 9px all-caps muted label, a large serif number value (colored positive/negative when applicable), and a small muted subtitle. No icons.
3. **Data Table** — full-width, borderless except for horizontal row dividers. Header row uses a slightly lighter surface color with all-caps muted column labels. Row hover applies a subtle surface highlight. Numeric cells right-aligned. Positive/negative delta columns colored accordingly.

---
### Charts
Use Chart.js or equivalent. Style to match the dark theme: transparent background, grid lines in the dark surface color, axis tick labels in the muted slate color and monospace font. Two line series — one gold, one teal — with very subtle fill opacity beneath each line. Tooltip styled as a dark panel with border.

---
### Texture & Atmosphere
Apply a subtle film grain overlay across the entire page using an SVG noise filter at very low opacity (`~3%`). This is a `position: fixed` element, pointer-events none, z-index above everything. It gives the interface a tactile, printed quality that differentiates it from flat digital UIs.

---
### Disclaimer / Warning Blocks
Left-bordered block (`3px` gold or amber), slightly warm dark background (not matching the main surface). Small monospace text in a muted amber tone. Used for legal/contextual warnings — visually distinct but not alarming.

---
### Tone Summary
The overall feel should be: **a private terminal for serious people**. No gradients, no illustrations, no playful micro-animations. Precision over decoration. Every pixel either carries information or creates intentional breathing room. If a designer were to describe it in one sentence: *"What if The Economist built a data tool."*
