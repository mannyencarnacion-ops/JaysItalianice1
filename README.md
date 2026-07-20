# Jay's Italian Ice — static site

Static, hand-coded copy of jaysitalianice1.com, migrated **off Shopify** onto
**Cloudflare Pages** (ShopMora standard static stack). One-page brochure site —
no ecommerce. Catering runs through Instagram DM (no form backend).

## Structure
```
index.html            One-page site (hero, flavors, sizes, about+van, find, events, catering, footer)
styles.css            Theme CSS (dark-navy glass look — carried verbatim from the Shopify theme)
site.js               Reveal/parallax/smooth-scroll (GSAP + Lenis; degrades gracefully if libs fail)
404.html              Branded not-found page
assets/
  jays-logo.png       Mascot logo (optimized 588KB -> 96KB, no visible change)
  jays-van.jpg        Sprinter van photo
  og-image.jpg        Social share image (1200x628)
  favicon.png         64x64
  apple-touch-icon.png
_redirects            301s for old Shopify system paths -> home
_headers              Security headers + caching (no immutable on un-hashed assets)
robots.txt            Allow all + sitemap
sitemap.xml           Single URL
```

## Deploy
Cloudflare Pages, Framework preset **None**, no build command, output dir **/** (root).
Auto-deploys on push to `main`. Custom domains: `jaysitalianice1.com` + `www`.

## Notes
- External libs (GSAP 3.12.5, ScrollTrigger, Lenis 1.0.42) load from jsdelivr, same as
  the original theme. If they fail to load, `site.js` reveals all content (no blank page).
- Contact is links-only: tel `+1-877-926-7423`, mailto `jaysitalianice1@gmail.com`,
  Instagram DM `https://ig.me/m/jaysitalianice1`. No server-side form.
- SEO carried: title, meta description, canonical, OG/Twitter, `IceCreamShop` +
  `Event` JSON-LD. Google Search Console verification TXT stays on the domain at cutover.

Migrated 2026-07-19 by ShopMora.
