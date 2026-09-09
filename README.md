# Framework Studio

Marketing and portfolio site for **Framework Studio**, a web design practice building sites for small businesses, nonprofits and creatives.

Live: <https://tahvia127.github.io/framework-studio/>

## What's here

A single-page static site. No build step, no dependencies, no framework.

```
index.html              The whole site: hero, work, services, process, pricing, FAQ, contact
assets/css/styles.css   Design system and layout
assets/img/             Screenshots of live client sites (WebP)
```

## Running it

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## Editing the things that change most

| What | Where |
|---|---|
| Prices | The `.tiers` block in `index.html`, and the `.addons` table below it |
| Availability banner | The `.tagline` paragraph at the top of the hero |
| Work samples | The four `<article class="proj">` blocks in `#work` |
| FAQ | The `<details>` elements in `#faq` |

### Refreshing a work screenshot

```bash
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" \
  --headless=new --window-size=1440,1000 \
  --screenshot=shot.png --virtual-time-budget=12000 "https://example.com/"
cwebp -q 82 -resize 1200 0 shot.png -o assets/img/example.webp && rm shot.png
```

## Design notes

- **Type:** DM Serif Display for headings, Space Mono for body and labels, both from Google Fonts.
- **Color:** cream `#F7F0E4`, ink `#2A1C16`, brick red `#B4322A`. Every text pairing clears WCAG AA (lowest is 4.71:1).
- **Motifs:** parenthetical section labels, a red scrolling marquee, asterisk accents, hard-bordered cards that cast a solid red shadow on hover.
- **Accessibility:** skip link, visible focus rings, semantic landmarks, and full `prefers-reduced-motion` support.
- **Images** are WebP, capped at 1200px wide, lazy-loaded below the fold.
