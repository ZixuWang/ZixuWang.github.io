# CLAUDE.md

Personal website of Zixu Wang — an al-folio v1 Jekyll starter, deployed to GitHub Pages at
https://www.zixu.wang. This is a **user site built from the template**, not the upstream
al-folio repo. Upstream's docs live in `docs/`; where they talk about the upstream repo
(baseurl `/al-folio`, style-contract lint, PR workflow) they do NOT apply here.

## Facts that differ from upstream docs

- `baseurl` is intentionally **blank** and `url` is `https://www.zixu.wang`. Do not "fix" it to `/al-folio`.
- `_sass/_variables.scss` and `_sass/_themes.scss` are deliberate local overrides of the
  `al_folio_core` gem (allowed for user sites). `_themes.scss` is a verbatim copy that exists only
  so its `@use "variables"` resolves to the local file. All colour changes go in `_variables.scss`.
- Only `.github/workflows/deploy.yml` is kept. It builds with Ruby 3.3.5 + `Gemfile.lock` and pushes
  `_site/` to the `gh-pages` branch. **Do not modify `Gemfile.lock` casually** — CI uses it verbatim.
- `_data/socials.yml`: every key must have a value; a bare `key:` crashes jekyll-socials
  (`no implicit conversion of nil into String`). Comment unused keys out.
- `CNAME` (content `www.zixu.wang`) belongs in the repo root **only after** the DNS CNAME record
  exists at DNSPod; adding it earlier makes zixuwang.github.io redirect to a dead domain.
- Cloudflare Web Analytics beacon token is in `_config.yml` → `analytics.cloudflare` (public, not secret).

## Local dev

```bash
export PATH="/usr/local/opt/ruby/bin:$PATH"; export LANG=en_US.UTF-8 LC_ALL=en_US.UTF-8
bundle exec jekyll serve          # http://127.0.0.1:4000/
bundle exec jekyll build          # → _site/
```

## Before publishing anything

Content is public. Nothing Infineon-internal (unpublished numbers, internal project names,
non-public data details) goes on the site. Publications: only what is on arXiv / Google Scholar
(user: JT_D5sUAAAAJ). Photo in `assets/img/prof_pic.jpg` is EXIF-stripped; keep it that way.
