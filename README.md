# some style please!

A minimalist, fast, and responsive [Hugo](https://gohugo.io/) theme based on [nostyleplease](https://github.com/hanwenguo/hugo-theme-nostyleplease). It preserves the original’s simple, text-focused character while adding multilingual support, pages, taxonomies, image captions, galleries, and lightweight shortcodes.

### [Theme demo](https://004822.xyz)

![Color schemes](https://github.com/jkkNl/somestyleplease/raw/main/images/colors.webp)

## Features

- minimalist and responsive interface;
- color schemes: `auto`, `light`, `dark`, `matrix`, `bear`, and `together`;
- multilingual support for pages, posts, taxonomies, and RSS;
- language switcher showing only available translations;
- categories and tags;
- language-specific RSS feeds;
- configurable favicon;
- optional bordered table of contents;
- MathJax support;
- image and video captions with Markdown link support;
- responsive image galleries without JavaScript;
- highlighted content without additional global CSS;
- native Goldmark footnotes in page content;
- Hugo Pipes and CSS fingerprinting;
- no required Node.js dependencies.

## Installation

Clone the repository or add it as a submodule under `themes/somestyleplease`, then set the theme in your Hugo configuration.

**TOML**

~~~toml
theme = "somestyleplease"
~~~

**YAML**

~~~yaml
theme: somestyleplease
~~~

Example content shipped with the theme uses `draft = true`. To render it locally, run:

~~~bash
hugo server --buildDrafts
~~~

The repository also includes a `gallery-demo` post showing galleries, captions, links in captions, and highlighted content.

## Configuration

Theme settings are configured under `params.theme_config`.

**TOML**

~~~toml
[params.theme_config]
appearance = "auto" # auto | light | dark | matrix | bear | together
date_format = "02.01.2006"
categories = true
tags = true
post_limit = 100
show_more_url = "posts"
favicon = "favicon.ico"
~~~

**YAML**

~~~yaml
params:
  theme_config:
    appearance: auto
    date_format: "02.01.2006"
    categories: true
    tags: true
    post_limit: 100
    show_more_url: posts
    favicon: favicon.ico
~~~

Your project configuration takes precedence over the theme defaults.

### Favicon

Place the file in the site’s `static` directory:

~~~text
static/favicon.ico
~~~

Then configure its filename:

~~~toml
[params.theme_config]
favicon = "favicon.ico"
~~~

## Creating content

### Front matter

The theme uses standard Hugo front matter. The main supported fields are:

| Field | Type | Purpose |
| --- | --- | --- |
| `title` | string | Page or post title |
| `date` | date | Publication date |
| `draft` | bool | Hide content from regular builds |
| `categories` | array | Post categories |
| `tags` | array | Post tags |
| `toc` | bool | Enable the table of contents |
| `tocBorder` | bool | Add a border to the table of contents |
| `mathjax` | bool | Enable MathJax on the page |
| `custom_js` | array | Load JS files from `assets/js/` |
| `weight` | int | Page and menu ordering |

Example:

~~~toml
+++
title = "My post"
date = 2025-07-19T12:00:00+02:00
draft = false
categories = ["technology"]
tags = ["hugo", "markdown"]
toc = true
tocBorder = true
mathjax = false
+++
~~~

### Footnotes

Add footnotes to regular Markdown content using Goldmark’s native syntax:

~~~markdown
This is text with a footnote[^1].

[^1]: Footnote content.
~~~

Footnotes are not intercepted inside image captions. This keeps Hugo’s native and predictable footnote handling intact.

## Images and video

### Image captions

Use the optional image title to display a centered caption:

~~~markdown
![Alternative text](image.jpg "Visible caption")
~~~

Captions can contain basic Markdown, including links:

~~~markdown
![Watch](watch.webp "Photo from [Reddit](https://www.reddit.com/)")
~~~

Images without a title are rendered without a caption. Alternative text remains separate from the caption and is used for accessibility.

### Video with Markdown

Embed video using the same syntax as an image:

~~~markdown
![video](/attachment/example/video.webm)
~~~

The theme also detects the `webm`, `mp4`, `m4v`, `ogv`, `ogg`, and `mov` extensions, so the alternative text can describe the recording:

~~~markdown
![Hand comparison](/attachment/example/video.webm "Video caption")
~~~

Videos include controls, `preload="metadata"`, and responsive sizing.

## Shortcodes

### Image galleries

The `gallery` shortcode creates a responsive CSS Grid gallery without JavaScript:

~~~markdown
{{< gallery label="Watch gallery" >}}

![Casio](casio.webp "Casio")
![Tissot](tissot.webp "Tissot")
![Tudor](tudor.webp "Tudor")

{{< /gallery >}}
~~~

Captions and links in captions work the same way as they do for individual images. The gallery automatically adapts the number of columns to the available width.

### Highlighted content

The `highlight` shortcode surrounds an important fragment with a minimalist border similar to the table of contents:

~~~markdown
{{< highlight >}}

This is an important note with **bold text** and a [link](https://gohugo.io/).

{{< /highlight >}}
~~~

The highlight CSS is included directly in the shortcode, so it does not increase the global stylesheet when the feature is not used.

### Details

The `details` shortcode creates a collapsible HTML element:

~~~markdown
{{< details summary="Show more" open="false" >}}

Hidden content with **Markdown**.

{{< /details >}}
~~~

### Video shortcode

A video shortcode is also available for compatibility:

~~~markdown
{{< video src="/attachment/example/video.webm" >}}
~~~

For new content, the Markdown syntax above is recommended because it is shorter and uses the same image render hook.

### Mathematics

On a page with `mathjax = true`, you can use the `texi` and `texd` shortcodes:

~~~markdown
{{< texi "x^2 + y^2 = z^2" >}}
~~~

## Taxonomies

When `categories = true` or `tags = true`, the theme generates category and tag pages. Term names are displayed in lowercase, and the homepage link has the same top spacing as it does in articles.

A post can have multiple categories and tags:

~~~toml
categories = ["watches", "technology"]
tags = ["hugo", "markdown"]
~~~

## Multilingual websites

The theme supports multiple languages for pages, posts, taxonomies, and RSS.

### Language configuration

**TOML**

~~~toml
defaultContentLanguage = "en"
defaultContentLanguageInSubdir = true

[languages]
  [languages.en]
    locale = "en-US"
    label = "English"
    weight = 1

  [languages.pl]
    locale = "pl-PL"
    label = "Polski"
    weight = 2
~~~

**YAML**

~~~yaml
defaultContentLanguage: en
defaultContentLanguageInSubdir: true

languages:
  en:
    locale: en-US
    label: English
    weight: 1
  pl:
    locale: pl-PL
    label: Polski
    weight: 2
~~~

### Translation files

Use the same basename with a language code suffix:

~~~text
content/posts/my-post.en.md
content/posts/my-post.pl.md
content/pages/about.en.md
content/pages/about.pl.md
~~~

The language switcher shows only other available translations of the same resource. If no translation exists, no empty or unnecessary link is displayed.

### Interface translations

Add `i18n/<language>.yaml` files, for example:

~~~text
i18n/en.yaml
i18n/pl.yaml
~~~

The theme uses keys such as:

- `homepage.intro`;
- `homepage.moreintro`;
- `homepage.footer`;
- `general.back_home_text`;
- `general.categories`;
- `general.tags`;
- `categories.<category-slug>`.

To avoid the `/en/` prefix for the default language, set:

~~~toml
defaultContentLanguageInSubdir = false
~~~

## Customizing the theme

Hugo allows you to override theme files in the project directory. For example, a custom footer can be placed at:

~~~text
layouts/partials/footer.html
~~~

Custom CSS and JavaScript files can be added under:

~~~text
assets/css/
assets/js/
~~~

The theme uses Hugo Pipes, minification, and CSS fingerprinting. Node.js and npm are not required.

## License and acknowledgements

This theme is available under the [MIT License](https://opensource.org/licenses/MIT). Bug reports and pull requests are welcome.

Some code comes from [hanwenguo/hugo-theme-nostyleplease](https://github.com/hanwenguo/hugo-theme-nostyleplease) and [wooseopkim/hugo-theme-nostyleplease](https://github.com/wooseopkim/hugo-theme-nostyleplease). Some example content comes from [this Jekyll theme](https://github.com/huangyz0918/moving).
