# Signal Gradient Tools

On-brand gradient generators for the **Signal Design System** (Intelligence Node). Every tool is a single, self-contained HTML file — no build step, no dependencies. Open any of them directly in a browser.

All output is constrained to the Signal system: the legal **extended gradient hues** (which are legal *only* inside gradients), the palette base tones, and the mandatory `feTurbulence` grain at `soft-light`.

## 🔗 Live link

**▶ Open the studio: https://gkahadane123.github.io/signal-gredient/**

Post that link anywhere — it opens the gradient studio in the browser, no install needed. *(Served via GitHub Pages from the `main` branch.)*

Instant CDN mirror (works even before Pages finishes building):
`https://raw.githack.com/gkahadane123/signal-gredient/main/index.html`

## Tools

| File | Live | What it is |
| --- | --- | --- |
| [`index.html`](index.html) | [open](https://gkahadane123.github.io/signal-gredient/) | **Main studio.** Static design-system gradient in a full-bleed UI — view switcher (Full bleed / Cards / Website / Mobile / Product), Edit drawer with a per-bloom layer editor, and a *Get the code* modal that exports the exact `sig-grad-*` CSS or rasterizes a PNG (up to 4K) via SVG. |
| [`minimal.html`](minimal.html) | [open](https://gkahadane123.github.io/signal-gredient/minimal.html) | Minimal static generator — a side-by-side layout for quickly composing blooms and copying the exact system CSS. |
| [`animated.html`](animated.html) | [open](https://gkahadane123.github.io/signal-gredient/animated.html) | Animated WebGL variant (Neat-style live gradient). Kept for reference. |

## Gradient model

Each gradient is a base color plus layered radial "blooms":

```css
.sig-grad-custom{
  background-color:#E8443C;
  background-image:
    var(--grain),
    radial-gradient(95% 85% at 72% 18%,rgb(247 235 70/.85) 0%,rgb(247 235 70/.3) 45%,rgb(247 235 70/0) 78%),
    /* …more blooms… */;
  background-blend-mode:soft-light,normal,normal,normal,normal;
  background-size:160px 160px,auto,auto,auto,auto;
}
```

The six coded presets (Ember, Depth, Current, Bloom, Glow, Night) reproduce the design system's gradients exactly.

## Usage

1. Open the [live link](https://gkahadane123.github.io/signal-gredient/) (or any file in a browser).
2. Pick a preset, tune the blooms.
3. **Get the code** → copy the CSS (drop the class on any full-width section) or export a PNG for slides / section backgrounds.

---

Internal use · Intelligence Node
