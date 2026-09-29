# oisifgames.com

Static site for Oisif Games: landing page, support, privacy policy, terms of use.

Plain HTML and one stylesheet. No build step, no framework, no third-party
resources — every asset is served from this origin.

```
index.html          landing
support/            support page (App Store "Support URL")
privacy/            privacy policy (App Store "Privacy Policy URL")
terms/              terms of use
assets/style.css    the only stylesheet
404.html            not-found page
```

## Adding app-ads.txt

Ad networks require an `app-ads.txt` at the domain declared as the developer
website in the store listing. Generate the exact lines from the LevelPlay and
Unity dashboards and commit them as `app-ads.txt` at the repository root.

Do not publish a placeholder or comment-only file: crawlers read it as "no seller
is authorised" and ad demand drops.
