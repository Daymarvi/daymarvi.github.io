# daymarvi.github.io

Source of my personal blog, published at <https://daymarvi.github.io>.

Topics: server administration, system engineering, automation and home networking.

## Writing a post

Add a Markdown file to `_posts/` named `YYYY-MM-DD-title.md`:

```markdown
---
title: My post
date: 2022-02-08 12:00:00
categories: [General]
tags: [example]
---

Content…
```

The file name (without the date) becomes the URL: `/posts/title/`, so it must be unique.

## Running locally

Requires Ruby (version in `.ruby-version`) and Bundler.

```console
$ bundle install
$ bash tools/run.sh
```

The site is then served at <http://127.0.0.1:4000>.

## Deployment

`master` is protected: changes go through a pull request, and the `build` check
(Jekyll build + html-proofer) must pass before merging.

On merge, the workflow in `.github/workflows/pages-deploy.yml` builds the site
and deploys it with GitHub Pages (source: GitHub Actions).
Dependabot opens monthly PRs to keep gems and actions up to date.

## Configuration

- Site settings: `_config.yml`
- Contact links in the sidebar: `_data/contact.yml`
- Custom styles: `assets/css/style.scss`; SASS variable overrides: `_sass/variables-hook.scss`

## License

MIT, see [LICENSE](LICENSE).
