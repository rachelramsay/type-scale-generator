# TypeNerd

A responsive type scale generator — modular ratios stepped down for tablet and mobile.

TypeNerd is a single self-contained HTML file. Open `index.html` in a browser and you have the whole tool; there is no build step and no dependencies (Google Fonts are loaded for previews, but everything else works offline).

## What it does

- **Modular scales from musical-interval ratios** (Minor Second 1.067 through Golden Ratio 1.618, or custom): every step is `base × ratio^n`, after the approach popularized by [precise-type.com](https://precise-type.com/) and Tim Brown's modular scale work.
- **Three breakpoint scales** — large, medium, and small, each with an editable preview viewport. Medium and small can auto-derive from the large scale (ratio damped to 75% / 55% of the interval; base never below 16px) or be set independently. Headings step down on small screens while body text stays put.
- **4px / 8px grid tuning** — every line-height snaps to the grid, sizes round to whole pixels, and a baseline-grid overlay lets you see the vertical rhythm. The grid ships in the exports as `--baseline-grid`.
- **Line-height and tracking curves** — leading tightens and letter-spacing goes negative as sizes grow, anchored at the base size, using an exponential tracking curve.
- **Google Fonts picker** — searches an embedded index of the ~1,770 library families that target Latin scripts (script-specific faces such as `Noto Sans JP` are filtered out), loading each family's real weights on demand. An optional second family sets body text while the first sets headings.
- **Steps and Page views** — inspect the raw scale, or preview it on an example article (headings, lead, body in a 66ch measure, blockquote, list, captions, a UI card) with hover labels showing each block's token.
- **Craft checks** — a live audit of the current breakpoint against published guidance: body size, line spacing, measure (with real canvas text measurement), vertical rhythm, letterspacing, relative units, WCAG 1.4.12 text-spacing tolerance, glyph legibility, block spacing, and font-loading restraint.
- **Exports** — stepped CSS custom properties with media queries, fluid `clamp()` CSS interpolating small → large viewports, and JSON tokens.

## Sources

The craft checks cite, and the defaults conform to:

- [Butterick's Practical Typography](https://practicaltypography.com/summary-of-key-rules.html) — body 15–25px, line spacing 120–145%, measure 45–90 characters, +5–12% tracking for caps
- [The Elements of Typographic Style Applied to the Web](https://webtypography.net/toc) — measure (§2.1.2), vertical rhythm in measured intervals (§2.2.2), letterspacing (§2.1.6–2.1.8)
- [Google Fonts Knowledge: The foundations of web typography](https://fonts.google.com/knowledge/using_type/the_foundations_of_web_typography)
- [U.S. Web Design System: Typography](https://designsystem.digital.gov/components/typography/) — ≥16px effective body size, line-height tokens, 66-character measure target, block spacing
- [WebAIM: Fonts](https://webaim.org/techniques/fonts/) — relative units (WCAG 1.4.4), text-spacing overrides (WCAG 1.4.12), glyph disambiguation

## Use

```
open index.html
```

Pick a base size and ratio, tune the rhythm, flip between breakpoints and the Steps/Page views, then Export.
