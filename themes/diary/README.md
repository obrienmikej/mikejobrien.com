# hugo-theme-diary
![](https://img.shields.io/badge/license-MIT-blue.svg)

[Live Demo](https://amazingrise.net/hugo-theme-diary/)

Original Author: [SumiMakito](https://github.com/SumiMakito)

隻言片語・於此匯聚

Moments piled up.
---

A Hugo theme ported from [SumiMakito/hexo-theme-Journal](https://github.com/SumiMakito/hexo-theme-Journal/).

Hereinafter referred to the original version made by SumiMakito as `the ori`.

The porting is basically finished.

[And more functions are on the way.](https://github.com/AmazingRise/hugo-theme-diary/projects/3).

## Screenshots

[Live Demo here!](https://amazingrise.net/hugo-theme-diary/)

![](https://raw.githubusercontent.com/AmazingRise/hugo-theme-diary/master/images/screenshot.png)

Site Main Page

![](https://raw.githubusercontent.com/AmazingRise/hugo-theme-diary/master/images/essay.png)

An essay with picture.

![](https://raw.githubusercontent.com/AmazingRise/hugo-theme-diary/master/images/m_main.png)

Mobile Main Page

## Features

Features in the ori.:

- Simple and easy to customize
- Concentrated on reading <del>and writing (find a Markdown editor then)</del> experience
- Mobile-friendly & widescreen-friendly
- Flexible commenting control

Features in this ported version:

- Add support for gitalk.
- Tag & category page appending more easily.
- Customizable color scheme. (Some bug in original version, fixed.)
- Firefox-friendly. (CSS issue in original version, fixed.)
- `featured_image` url bug is fixed.

## Quick Start

If your website is using Git as version control, please do as follows:

1. Fetch the theme dir.

From the root of your Hugo site, open the terminal and execute:
```bash
git submodule add https://github.com/AmazingRise/hugo-theme-diary.git themes/diary
```
2. Update git repository.

Then update the git repository from the root of your site:
```bash
git submodule update --remote --merge
```

3. Run example site.

From the root of themes/diary/exampleSite:
```bash
hugo server --themesDir ../..
```
## Using & Customize

As for other details, please visit [the project wiki](https://github.com/amazingrise/hugo-theme-diary/wiki) for details.

[Change color scheme](https://github.com/AmazingRise/hugo-theme-diary/wiki/Customization#change-color-scheme)

[Add or disable comment area](https://github.com/AmazingRise/hugo-theme-diary/wiki/Customization#add-comment-area)

[Add Google Analytics](https://github.com/AmazingRise/hugo-theme-diary/wiki/Customization#add-google-analytics)

[About sidebar and taxonomies](https://github.com/AmazingRise/hugo-theme-diary/wiki/Tag-&-Category-Index-or-Taxonomies)

### Example config

Here is an example config. (The same as `/exampleSite/config.toml`)
```
baseURL = "http://example.org/"
languageCode = "en-us"
title = "A Hugo Site"
copyright = "This is a customized copyright."

theme = "diary"
# googleAnalytics = "UA-123-45"

[params]
subtitle = "Themed by Diary."
enableGitalk = true

[params.gitalk]
owner = "user"
repo = "repo name"
client_id = "your client id"
client_secret = "your client secret"

[taxonomies]
tag = "tags"
category = "categories"
```

## Comparison

For details about the difference lies in the new version, please click [here.](https://github.com/AmazingRise/hugo-theme-diary/wiki/Comparison)