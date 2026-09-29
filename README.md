# oisifgames.com

Static site for Oisif Games: landing page, support, privacy policy, terms of use.

Plain HTML and one stylesheet. No build step, no framework, nothing loaded from a
third-party origin, so the font and the artwork are served from here too.

```
index.html          landing
support/            support page (App Store "Support URL")
privacy/            privacy policy (App Store "Privacy Policy URL")
terms/              terms of use
404.html            not-found page
robots.txt          crawl rules
sitemap.xml         the four indexable pages
app-ads.txt         authorized seller records
assets/style.css    the only stylesheet
assets/fonts/       Figtree, woff2, SIL Open Font License
assets/games/       one logo per title
assets/og.png       social preview card
assets/favicon.svg  the studio mark
```

## Adding a game

The shell is deliberately neutral. It belongs to the studio, not to any one title,
so nothing in the CSS knows which games exist. A new game is one more `<article
class="game">` in `index.html`:

```html
<article class="game">
  <div class="game-art" style="--brand:#RRGGBB">
    <img src="/assets/games/<name>.webp" alt="<Name>">
  </div>
  <div class="game-body">
    <h3>…</h3><p>…</p><p class="meta">…</p><a class="btn" href="…">App Store</a>
  </div>
</article>
```

`--brand` is the colour panel behind the logo, taken from the game's own art. Put
the logo in `assets/games/` as a transparent webp, trimmed to its bounding box.
That is the only place colour enters the site.

Add the game to the schema.org `@graph` in the same file, as another `VideoGame`
published by the Organization.

## Fonts

Figtree, SIL Open Font License, self-hosted with the licence text beside it.

## app-ads.txt

Ad networks require an `app-ads.txt` at the domain declared as the developer
website in the store listing, so this file only does its job while that field
points here. Generate the lines from the LevelPlay and Unity dashboards.

Do not publish a placeholder or comment-only file: crawlers read it as "no seller
is authorised" and ad demand drops.
