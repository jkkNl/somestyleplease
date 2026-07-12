# some style please!
Super fast and clean [Hugo](https://gohugo.io/) theme based on [nostyleplease](https://github.com/hanwenguo/hugo-theme-nostyleplease). I wanted to keep the minimalist and attractive design, but also add multilingual support and page support. I added more color options.

![Colors](https://github.com/jkkNl/somestyleplease/raw/main/images/colors.webp)

### [Visit theme demo in dark color scheme](https://004822.xyz/demosomestyleplease/).

## Features
* Super fast (**~8 KB of CSS!**)
* Multilingual support
* Many color schemes (light, dark, matrix, bear, together and auto based on system preference)
* Responsive and content first (typography optimized for maximum readability)
* RSS feed (with support for multiple languages)
* MathJax support

## Installation
The easiest way is to clone this repo (or add as a submodule) to `themes/somestyleplease`, then set the theme in your Hugo config (`hugo.toml` / `hugo.yaml` / `config.toml` / `config.yaml`).

**TOML**
```toml
theme = "somestyleplease"
```

**YAML**
```yaml
theme: somestyleplease
```

Pages shipped with the theme as examples use `draft: true` in front matter, so use `--buildDrafts` to render them.

## Usage
Edit your Hugo config file (`hugo.toml` / `hugo.yaml` / `config.toml` / `config.yaml`) to customize title, languages, homepage blocks, date format and appearance.

Theme-specific options are under `params.theme_config`.

**TOML**
```toml
[params.theme_config]
appearance = "auto" # auto | light | dark | matrix | bear | together
date_format = "02.01.2006"
categories = true
tags = true
```

**YAML**
```yaml
params:
  theme_config:
    appearance: auto # auto | light | dark | matrix | bear | together
    date_format: "02.01.2006"
    categories: true
    tags: true
```

Your site config in the Hugo project root overrides theme defaults, so copy the values you want from `themes/somestyleplease/config.toml`.

### Available front matter
You can use standard Hugo front matter plus the theme options below:

| Key | Type | What it does |
| --- | --- | --- |
| `title` | string | Page/post title |
| `date` | date | Publish date |
| `draft` | bool | Keep content as draft |
| `categories` | array | Categories list (used for category pages and homepage blocks by category) |
| `tags` | array | Tags list |
| `toc` | bool | Show table of contents |
| `tocBorder` | bool | Add border around table of contents |
| `mathjax` | bool | Enable MathJax on that page/post |
| `custom_js` | array | Load JS from `assets/js/<name>.js` (use names without `.js`) |
| `weight` | int | Order pages in menus/lists |

Example (TOML front matter):

```toml
+++
title = "My post"
date = 2026-07-09T10:00:00+00:00
draft = false
categories = ["tech"]
tags = ["hugo", "theme"]
toc = true
tocBorder = true
mathjax = false
+++
```

Example (YAML front matter):

```yaml
---
title: "My post"
date: 2026-07-09T10:00:00+00:00
draft: false
categories: ["tech"]
tags: ["hugo", "theme"]
toc: true
tocBorder: true
mathjax: false
---
```

### Multilingual website
This theme supports multilingual sites for homepage, pages, posts, taxonomies and RSS.

1. Configure languages in your Hugo config (`hugo.toml` / `hugo.yaml` / `config.toml` / `config.yaml`):

**TOML**
```toml
defaultContentLanguage = "en"
defaultContentLanguageInSubdir = true

[languages]
  [languages.en]
    languageCode = "en-US"
    languageName = "English"
    weight = 1

  [languages.pl]
    languageCode = "pl-PL"
    languageName = "Polski"
    weight = 2
```

**YAML**
```yaml
defaultContentLanguage: en
defaultContentLanguageInSubdir: true

languages:
  en:
    languageCode: en-US
    languageName: English
    weight: 1
  pl:
    languageCode: pl-PL
    languageName: Polski
    weight: 2
```

2. Create translated content files using language suffixes and the same basename:

- `content/posts/my-post.en.md`
- `content/posts/my-post.pl.md`
- `content/pages/about.en.md`
- `content/pages/about.pl.md`

The basename must match (`my-post` / `about`) so Hugo can link translations together.

3. Add translation strings in your site `i18n/<lang>.yaml` (recommended), for example:

- `homepage.intro`
- `homepage.moreintro`
- `homepage.footer`
- `general.back_home_text`
- `general.categories`
- `general.tags`
- `categories.<category-slug>`

When more than one language is configured, the language switcher and translation links are shown automatically.

> Tip: if you want default language without `/en/` in URLs, set `defaultContentLanguageInSubdir` to `false`.

## Thanks
Some of the code comes from  [hanwenguo/hugo-theme-nostyleplease](https://github.com/hanwenguo/hugo-theme-nostyleplease) and  [wooseopkim/hugo-theme-nostyleplease](https://github.com/wooseopkim/hugo-theme-nostyleplease). Some of the test pages are from [this jekyll theme](https://github.com/huangyz0918/moving). I'm very grateful to everyone who contributed to this template.

## License and contributing
The theme is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT). Bug reports and pull requests are welcome on GitHub.