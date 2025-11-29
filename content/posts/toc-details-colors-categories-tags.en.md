+++
title = 'Table of contents, details, color schemes, categories and tags (This post has a really long title!)'
date = 2025-11-20T13:34:54+02:00
draft = true
toc = true
tocBorder = true
categories = ["sample posts", "second category"]
tags = ["can be", "various tags too"]
+++

## Table of Contents
### What is it?
The Table of Contents (TOC) is what you see at the very top of this post. The TOC can be bordered or unbordered. Clicking an item in the TOC takes the user to the appropriate section of the page, and the header is highlighted.

### How do I enable TOC?

When creating a new post, at the very top, where the post title and date are, you need to put:
```toml
toc = true
tocBorder = true
```
You can, of course, open this post `../themes/somestyleplease/content/posts/test-toc-and-details.pl.md` and open it in a text editor to see how it works.

## Details
### What is this?
An HTML standard, unfortunately, not supported by markdown. But this template supports it anyway, so if you sometimes want to hide something, use it.
{{< details summary="Click me" >}}
There may be a lot of text here.
{{< /details >}}
### How do I use "Details"?
Well, you'll have to check for yourself. Open `../themes/somestyleplease/content/posts/test-toc-and-details.pl.md` in a text editor and everything will become clear.

## Color Schemes
If you want to change the template's colors, edit the config.toml file and find the line:
```toml
appearance = "auto"
```
You can change it to several predefined styles (`light`, `dark`, `matrix`, `bear`, `together`). If you leave it on `auto`, the color scheme will match your operating system's colors (between `light` and `dark`). You can easily add your own color schemes, just edit the CSS. It's simple, and if you're comfortable with Hugo, editing CSS shouldn't be too difficult either. ;-)
