# Osama — Portfolio

## Before you publish

1. **Add your photo**
   Put your picture at `images/me.jpg` (already referenced in `index.html`).
   Also save a copy as `images/me.png` — it's used for social-media preview cards (Open Graph / Twitter).

2. **Add your work screenshots**
   Drop real images into `images/work/` using these exact filenames (or update the `src` in `index.html` if you rename them):
   - `educamp.jpg` — screenshot of the EduCamp site
   - `instagram-ad-1.jpg`, `instagram-ad-2.jpg` — your Instagram ad designs
   - `thumbnail-1.jpg`, `thumbnail-2.jpg` — your YouTube thumbnails

   Until you add these, each card shows a clean icon placeholder automatically — nothing looks broken.

3. **Set your real contact email**
   In `index.html`, replace `your-email@example.com` in the "Say hello" button with your real address.

4. **Update the domain if needed**
   If you're not publishing at `https://osmyt.github.io/`, update the URL in:
   - `index.html` (canonical link, Open Graph/Twitter tags, JSON-LD)
   - `sitemap.xml`
   - `robots.txt`

## Getting indexed by Google (Search Console)

1. Go to [Google Search Console](https://search.google.com/search-console) and add your site as a property.
2. Verify ownership — you already have a verification meta tag in `index.html` (`google-site-verification`), so if this is the same Search Console account as before, it should verify instantly. If you created a new property, replace that tag with the new code Google gives you.
3. Once verified, submit `sitemap.xml` under **Sitemaps** in the left menu.
4. Use **URL Inspection** on your homepage and click **Request Indexing**.

## Arabic language

There's a language switch button in the header (العربية / English). Clicking it:
- Swaps all text to Arabic
- Switches the page to right-to-left (`dir="rtl"`) and flips the hero layout to match
- Switches fonts to Cairo (an Arabic-friendly font) while in Arabic mode
- Updates the page `<title>` and meta description
- Remembers the visitor's choice for their next visit (via `localStorage`)

To edit the Arabic text, open `script.js` and look for the `translations.ar` object near the top — every string on the page has a matching English/Arabic pair there.

**Note on SEO:** this is a client-side toggle on one URL, not two separate pages, so Google will generally index the English version (the default) rather than the Arabic text. If ranking in Arabic search results matters to you, the stronger long-term setup is a separate `/ar/` page with its own URL and `hreflang` tags — happy to help set that up if you want it.

## What's already handled for SEO

- Unique `<title>` and `<meta description>`
- Open Graph + Twitter Card tags for link previews
- `rel="canonical"` link
- JSON-LD structured data (`Person` + `WebSite`)
- Semantic HTML (`header`, `nav`, `main`, `section`, `figure/figcaption`, one `<h1>` per page, logical heading order)
- Descriptive `alt` text on every image
- `robots.txt` + `sitemap.xml`
- Fast load: no heavy frameworks, fonts/icons loaded from CDN with `preconnect`

## Structure

```
index.html
style.css
script.js
robots.txt
sitemap.xml
images/
  icon.svg
  me.jpg        (add this)
  work/         (add screenshots here)
```
