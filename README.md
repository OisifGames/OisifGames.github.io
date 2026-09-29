# oisifgames.com

Static site for Oisif Games: landing page, support, privacy policy, terms of use.

Plain HTML and one stylesheet. No build step, no framework, nothing loaded from a
third-party origin, so the fonts and the artwork are served from here too.

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
assets/fonts/       Fraunces and Figtree, woff2, SIL Open Font License
assets/img/         props from Hole City
assets/og.png       social preview card
assets/favicon.svg  the hole mark
```

## The artwork

The props are renders of Hole City's own meshes. They ship with the game's
backdrop baked in as an opaque `#EEF7FB`, and the cut-outs here were made by
keying that colour out to alpha with a soft ramp, then cropping to the bounding
box.

`--sky` in the stylesheet is that same `#EEF7FB`, which is why a prop dropped on
the page has no visible edge. Change one and you change the other.

The street in the hero is a flex row whose heights are percentages of the row's
own aspect ratio, so a new prop needs a height that keeps the row under 100% at
every breakpoint.

## Fonts

Fraunces for display, Figtree for text, both under the SIL Open Font License and
self-hosted with the licence text beside them. The font Hole City uses in game is
a commercial licence that covers the app rather than a website, so it is not here.

## app-ads.txt

Ad networks require an `app-ads.txt` at the domain declared as the developer
website in the store listing, so this file only does its job while that field
points here. Generate the lines from the LevelPlay and Unity dashboards.

Do not publish a placeholder or comment-only file: crawlers read it as "no seller
is authorised" and ad demand drops.
