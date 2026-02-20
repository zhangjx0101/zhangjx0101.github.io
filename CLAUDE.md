# Project: zhangjx0101.github.io

Bilingual (EN/ZH) academic personal website for Zhang Jiaxing, built with Quarto.

## Tech Stack

- **Framework**: Quarto 1.8.27 (static site generator)
- **Styling**: SCSS (Bootstrap 5 Cosmo theme override) at `static/html/custom.scss`
- **Templates**: EJS for listing pages (research, blog, etc.)
- **i18n**: JavaScript runtime translation in `static/html/lang-switch.html`
- **Fonts**: LXGW WenKai (CN body), Noto Serif SC (CN headings), Commissioner (EN body), Fraunces (EN headings)
- **Deployment**: GitHub Pages via `gh-pages` branch, auto-deployed by GitHub Actions

## Project Structure

- `_quarto.yml` — Global config (navbar, footer, theme, font links)
- `_variables.yml` — Site-wide variables (URLs, email)
- `index.qmd` / `zh/index.qmd` — EN/ZH homepages (trestles template)
- `about/` / `zh/about/` — About pages (banner image, title-block-style: none)
- `research/` — Research papers (shared data, EN/ZH use different EJS templates)
- `blog/` / `zh/blog/` — Blog (posts in `blog/2026/*/index.qmd`)
- `software/`, `talks/`, `teaching/` — Other pages with zh/ mirrors
- `static/html/custom.scss` — All style customization (colors, fonts, layouts)
- `static/html/lang-switch.html` — JS for navbar translation, footer translation, category sidebar translation, language dropdown
- `static/html/list-research.ejs` / `list-research-zh.ejs` — Research listing templates

## Key Patterns

- **Bilingual**: EN pages at root, ZH mirrors at `zh/`. Only `zh/` pages have `lang: zh-Hans` in frontmatter. Chinese navbar/footer text is translated at runtime by `lang-switch.html`.
- **Research categories**: Translations must be updated in 3 places: `list-research-zh.ejs` (catMap), `lang-switch.html` (catTextMap), and the EJS statusLabel map.
- **SCSS caching**: After modifying `.scss` or `.ejs`, must clear `_site/`, `.quarto/`, `_freeze/` for changes to take effect.
- **Font loading**: LXGW WenKai via jsDelivr CDN `<link>` tags in `_quarto.yml` include-in-header (not CSS @import). Noto Serif SC also via `<link>` with preconnect.
- **$font-family-base** (not $font-family-sans-serif) controls `--bs-body-font-family` in Bootstrap.
- **$primary: $color-main (#516db0)** — overrides Cosmo theme's default pink.

## Common Tasks

- **Preview**: `rm -rf _site .quarto _freeze && quarto preview`
- **Deploy**: Just `git push origin main` — GitHub Actions auto-deploys
- **Add research paper**: Create `research/<name>/index.qmd` with status field (published/working-papers/work-in-progress)
- **Add blog post**: Create `blog/2026/<name>/index.qmd`

## Important Notes

- Do NOT use CSS `@import` for web fonts in SCSS — use HTML `<link>` tags via `include-in-header`
- Quarto `title-block-banner` with image path generates invalid CSS — use markdown image + `.about-banner` CSS class instead
- `title: ""` causes Quarto to skip generating title block — use `title-block-style: none` + `pagetitle` instead
- `project.resources: - static/img/**` is required for images to be copied to `_site/`
