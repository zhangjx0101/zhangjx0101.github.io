# Zhang Jiaxing's Personal Academic Website

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-deployed-blue?logo=github)](https://zhangjx.com)
[![Quarto](https://img.shields.io/badge/Built%20with-Quarto-blue?logo=quarto)](https://quarto.org/)

Bilingual (English / Chinese) academic personal website built with [Quarto](https://quarto.org/), deployed on GitHub Pages.

**Live site: [zhangjx.com](https://zhangjx.com)**

## Features

- Bilingual support (English / 中文) with runtime language switching
- Research listing with status badges, abstracts, and category filtering
- Custom SCSS theme based on Bootstrap 5 (Cosmo)
- Responsive design for desktop and mobile
- Blog with code highlighting and category support

## Tech Stack

| Component | Technology |
|-----------|-----------|
| Static site generator | [Quarto](https://quarto.org/) |
| Styling | SCSS (Bootstrap 5) |
| Templates | EJS (Quarto listing templates) |
| Fonts | LXGW WenKai, Noto Serif SC, Commissioner, Fraunces |
| Deployment | GitHub Pages (`gh-pages` branch) |
| CDN | Cloudflare (free plan) |
| Domain | Custom domain via CNAME |

## Project Structure

```
.
├── _quarto.yml                 # Global configuration
├── _variables.yml              # Site-wide variables
├── index.qmd                   # English homepage
├── about/index.qmd             # About page (with banner)
├── research/index.qmd          # Research listing
│   ├── trade-policy/
│   ├── housing-consumption/
│   ├── digital-finance/
│   └── education-mobility/
├── blog/index.qmd              # Blog listing
├── software/index.qmd          # Software page
├── talks/index.qmd             # Talks page
├── teaching/index.qmd          # Teaching page
├── zh/                         # Chinese mirror pages
│   ├── index.qmd
│   ├── about/index.qmd
│   ├── research/index.qmd
│   ├── blog/index.qmd
│   ├── software/index.qmd
│   ├── talks/index.qmd
│   └── teaching/index.qmd
├── static/
│   ├── html/
│   │   ├── custom.scss         # Custom theme
│   │   ├── lang-switch.html    # Language switcher script
│   │   ├── list-research.ejs   # English research template
│   │   └── list-research-zh.ejs # Chinese research template
│   └── img/                    # Images
└── _extensions/                # Quarto extensions
```

## Documentation

For detailed guides, see the [Wiki](https://github.com/zhangjx0101/zhangjx0101.github.io/wiki):

- [Installation Troubleshooting](https://github.com/zhangjx0101/zhangjx0101.github.io/wiki/installation-troubleshooting)
- [Windows Claude Code Troubleshooting](https://github.com/zhangjx0101/zhangjx0101.github.io/wiki/windows-claude-code-troubleshooting)
- [macOS Usage Guide](https://github.com/zhangjx0101/zhangjx0101.github.io/wiki/daily-usage-guide)
- [Windows Setup & Usage Guide](https://github.com/zhangjx0101/zhangjx0101.github.io/wiki/windows-setup-guide)
- [Deployment & Custom Domain](https://github.com/zhangjx0101/zhangjx0101.github.io/wiki/deployment-guide)
- [Cloudflare CDN Configuration](https://github.com/zhangjx0101/zhangjx0101.github.io/wiki/cloudflare-cdn-guide)
- [Build Notes & Lessons Learned](https://github.com/zhangjx0101/zhangjx0101.github.io/wiki/quarto-website-build-notes)

## Local Development

### Prerequisites

- [Quarto](https://quarto.org/docs/get-started/) (>= 1.4)

### Preview

```bash
quarto preview
```

### Build

```bash
quarto render
```

### Deploy

```bash
quarto publish gh-pages
```

## License

Content: All rights reserved.

Website template and code: MIT License.
