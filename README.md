# krishagarwal.github.io

Personal academic website, built with [al-folio](https://github.com/alshedivat/al-folio) (Jekyll) and deployed to GitHub Pages by GitHub Actions.

## Editing

| What                                   | Where                                          |
| -------------------------------------- | ---------------------------------------------- |
| Bio, profile photo, homepage sections  | `_pages/about.md`, `assets/img/prof_pic.jpg`   |
| Publications                           | `_bibliography/papers.bib`                     |
| News                                   | `_news/` (one file per item)                   |
| CV                                     | `files/krishagarwal.pdf` (linked from `/cv/`)  |
| Social links                           | `_data/socials.yml`                            |
| Co-author homepage links               | `_data/coauthors.yml`                          |
| Site settings                          | `_config.yml`                                  |

In `papers.bib`, the fields `abbr`, `abstract`, `additional_info`, `annotation`, `arxiv`, `bibtex_show`, `blog`, `code`, `pdf`, `preview`, and `selected` control how an entry is displayed and are stripped from the BibTeX shown by its "Bib" button. Keep each `abstract` on a single line so it is stripped completely. `preview` names a thumbnail in `assets/img/publication_preview/` (4:3 images, 800×600, look most consistent). Mark equal contribution with `*` after an author's name (also stripped from the displayed BibTeX) and add `annotation = {* Equal contribution}`.

## Local preview

Requires Ruby 3.3 and ImageMagick, provided here by the `jekyll` conda environment:

```bash
conda activate jekyll
bundle install
bundle exec jekyll serve -l
```

Then open <http://localhost:4000>.

## Deployment

Pushing to `master` runs `.github/workflows/deploy.yml`, which builds the site and publishes it to the `gh-pages` branch that GitHub Pages serves. Never edit `gh-pages` directly.

## Changes from the al-folio starter

- `_includes/news.liquid` overrides the theme's news list to show dates as month and year. It is acknowledged in `.al-folio-overrides.yml`; after bumping the al-folio gems, run `bundle exec al-folio upgrade overrides audit` to see whether the upstream file changed.
- `_layouts/redirect.html` provides instant redirects for `/cv/` and the old `/projects/...` URLs.
