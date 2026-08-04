# paritas - coming-soon page

Single static page. No framework, no build step. `index.html` (all CSS inline) plus `assets/`.

**The name is always lowercase: `paritas`.** Never capitalised, anywhere - wordmark, `<title>`,
meta, email, alt text, comments. It is written lowercase in the HTML source and never
`text-transform`ed, so it stays lowercase even if CSS fails to load.

This repo is **completely separate** from the platform repo (`spot-mvp`) and from the earlier
`theta-website` folder. It shares no code with either.

## Preview locally

```bash
python3 -m http.server 4173
# then open http://localhost:4173
```

## Assets

Copied from the brand `branding assets/` set:

- `assets/paritas-icon.svg` - square navy icon (greige bars). SVG favicon.
- `assets/apple-touch-icon.png` - 180x180, resized from the 1000px master via `sips`.
- `assets/paritas-icon-1000.png` - og:image, and the resize source.

The page logo is the **transparent** mark inlined as SVG (`fill="currentColor"`, coloured navy),
not an `<img>` - so it inherits colour and animates. Geometry matches `paritas-icon-transparent.svg`.

## Built to the brief

- Colours: navy `#1C3049` on greige `#E7E4DC`, warm ink `#4A4A44` for "Coming soon" and the email.
- Type: Inter 400 + 600 (Google Fonts, `display=swap`, preconnect + preload). Verified Inter
  actually loads, not a fallback.
- Wordmark Inter 600, `-0.025em`, 64px desktop / 40px mobile. Mark width = 1.2x wordmark (77 / 48px).
- Slash eyebrow `/ working capital`, navy at 55% opacity.
- Motion: staggered fade-up on load (600ms, `cubic-bezier(.16,1,.3,1)`, 80ms apart in DOM order),
  the two bars fading 100ms apart (lower second). Respects `prefers-reduced-motion`. Under 1s total.
- No gradients, shadows, rounded cards, emoji, countdown, or form. Nothing beyond "Coming soon".

## Before going public

- `og:image` is a relative path. Once the domain is live, make it an **absolute URL**
  (`https://paritas.finance/assets/paritas-icon-1000.png`) or link previews will not render.
- Static host: Vercel / Netlify / GitHub Pages, repo root, no build command.
- The `mailto:` link is plain, as specified. No backend, no tracking.
