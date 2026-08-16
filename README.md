# zixu.wang

Source of my personal website, [www.zixu.wang](https://www.zixu.wang).

Built with [Jekyll](https://jekyllrb.com/) and the [al-folio](https://github.com/alshedivat/al-folio) theme (MIT), deployed to GitHub Pages by the `deploy.yml` workflow.

## Editing

| What                 | Where                                   |
| -------------------- | --------------------------------------- |
| Bio, photo caption   | `_pages/about.md`                       |
| Publications         | `_bibliography/papers.bib`              |
| News items           | `_news/*.md`                            |
| Links (email, etc.)  | `_data/socials.yml`                     |
| Site settings        | `_config.yml`                           |
| Accent colours       | `_sass/_variables.scss` (two hex values) |
| Photo                | `assets/img/prof_pic.jpg`               |

## Local preview

```bash
export PATH="/usr/local/opt/ruby/bin:$PATH"   # Homebrew Ruby (system Ruby is too old)
export LANG=en_US.UTF-8 LC_ALL=en_US.UTF-8     # bibtex parsing needs UTF-8
bundle install                                 # first time only
bundle exec jekyll serve                       # http://127.0.0.1:4000/
```

Requires ImageMagick (`brew install imagemagick`) for responsive image generation.
