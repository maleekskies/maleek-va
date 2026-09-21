# Malik Adesiyan, portfolio site

Personal portfolio for Malik Adesiyan, an Operations & Property
Management Virtual Assistant supporting UK, US and Canada landlords and
Airbnb hosts. Plain HTML, CSS and vanilla JavaScript. No build step, no
framework, no dependencies.

## Pages

| File | Purpose |
|---|---|
| `index.html` | Home page: hero, about, areas of work, tools, a review preview, contact |
| `ops.html` | Operations & Property Management: scope and sample projects |
| `va.html` | Virtual Assistant: scope and sample projects |
| `reviews.html` | Client reviews |
| `404.html` | Not found page |

## Assets

| File | Used on |
|---|---|
| `assets/headshot-01.jpg` | Home page hero, and referenced as the Open Graph share image |
| `assets/fullbody-01.jpg` | Home page about section |
| `assets/exhibit-01.jpeg` | Reviews page, review 1 |

## Adding a review

Reviews are rendered from a JavaScript array near the bottom of
`reviews.html`, inside a `<script>` tag. To add one:

1. Drop the screenshot or image into `assets/`.
2. Add an entry to the `REVIEWS` array with `tag`, `img`, `alt`, `quote`,
   `source`, and `from`.

No other markup needs to change. Text values are HTML-escaped before
rendering, so quotes, apostrophes and ampersands in a review are safe.

## Theme

Light and dark themes are set with CSS custom properties on `:root` and
`html[data-theme="dark"]`. A script in each page:

- checks `localStorage` for a saved choice
- falls back to the visitor's system preference (`prefers-color-scheme`)
- toggles `data-theme="dark"` on `<html>` and saves the choice back to
  `localStorage` when the theme button in the nav is clicked

## Navigation

The nav bar is repeated at the top of every page (no shared header file,
since this project has no templating or build step). Above 760px wide it
shows text links; below that width the links collapse behind a hamburger
button into a dropdown panel.

## Page transitions

A small script on every page fades the page out before following an
internal link, and fades in on load. It skips this for anchor links
(`#section`), `mailto:` links, and external `http` links, which navigate
normally. A `pageshow` listener resets the opacity if the page is
restored from the browser's back/forward cache, so the back button
doesn't land on a blank page.

## SEO and sharing

Each page has its own title, meta description, canonical tag, and Open
Graph / Twitter tags. `sitemap.xml`, `robots.txt`, and `llms.txt` are at
the project root and list only the pages that actually exist.

## Deploying

Static files, no build step. Upload the whole folder to any static host
(Vercel, Netlify, GitHub Pages) keeping the folder structure intact, so
that `assets/` stays alongside the HTML files. The site is
currently deployed at `maleekVA.vercel.app`; that domain is used
in the canonical tags, Open Graph tags, and `sitemap.xml`. If the domain
changes, update it in those files.

## Contact

- Email: maleekskies@gmail.com
