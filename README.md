# Hugo Bootstrap Theme

This theme is an extreme fast, responsive and feature-rich blog theme for Hugo.

## Table of Contents

- [Features](#features)
- [Palettes](#palettes)
- [Installation](#installation)
- [Configuration](#configuration)
- [Parameters](#parameters)
  - [Global Parameters](global-parameters)
  - [Page Parameters](page-parameters)
- [Comments](#comments)
- [Hooks](#hooks)
- [Custom Assets](#custom-assets).
- [Social Links](#social-links).
- [Various Shortcodes](#shortcodes).
- [Contribute](#contribute)

## Features

- Extreme Fast: [Google PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/?url=https://hbs.razonyang.com/en/)'s score `95-100`.
- Built on top of [Material Design for Bootstrap 5](https://mdbootstrap.com/).
- Responsive.
- [Various Palettes](#palettes).
- [Highly Configurable](#configuration).
- Dark Mode Switcher.
- Multilingual(I18N).
- Search.
- Breadcrumb.
- Archive.
- Lazy Loading Resources, such as `image` and `iframe`.
- Table of Contents.
- [Comments](#comments): supports [Disqus](#disqus) and [Utterances](#utterances).
- [Custom Assets](#custom-assets): custom CSS and JS.
- [Hooks](#hooks): provides ability to add custom code in page, such as `head`, `body`, `sidebar` etc.
- [Social Links](#social-links).
- [Various Shortcodes](#shortcodes).
- [Twitter Cards](https://gohugo.io/templates/internal/#configure-twitter-cards) and [Open Graph](https://gohugo.io/templates/internal/#configure-open-graph).

## Palettes

Available palettes: `blue`, `blue-gray`, `brown`, `cyan`, `gray`, `green`, `indigo`, `orange`, `pink`, `purple`, `red`, `teal`, `yellow`.

![Palettes](https://github.com/razonyang/hugo-theme-bootstrap/blob/master/images/palettes.png)

### Palettes in Dark Mode

![Palettes in Dark Mode](https://github.com/razonyang/hugo-theme-bootstrap/blob/master/images/palettes-dark.png)

## Installation

```shell
$ hugo new site myblog
$ cd myblog
$ git init
$ git submodule add https://github.com/razonyang/hugo-theme-bootstrap themes/hugo-theme-bootstrap
$ cp -a themes/hugo-theme-bootstrap/exampleSite/* .
$ hugo server
```

## Configuration

As the example site shown, the configuration are separated into multiple files, this is much clearer than a single configuration file, especially in a multilingual website.

| Name | Type | Default | Description
|---|:-:|:-:|---
| `title` | String | - | Site title.
| `baseURL` | String | - | Site base URL.
| `copyright` | String | - | Site copyright. The `{year}` placeholder will be replaced with this year.
| `defaultContentLanguage` | String | `en` |
| `defaultContentLanguageInSubdir` | Boolean | `false` |
| `paginate` | Integer | `10` |
| `paginatePath` | String | `page` |
| `enableRobotsTXT` | Boolean | `true` |
| `disqusShortname` | String | - | [Disqus](#disqus) shortname.
| `googleAnalytics` | String | - | Google Analytics.
| `social` | Object | - | A set of [social links](#social-links) that mapping from platform to user identifier.
| `author` | Object | - | Profile information. Available parameters: `name`, `avatar`, `bio`, `company` and `location`.

## Parameters

### Global Parameters

| Name | Type | Default | Description
|---|:-:|:-:|---
| **Page** 
| `mainSections` | Array | `["posts"]` | Main sections
| `titleSeparator` | String | `-` | Title separator
| `comment` | Boolean | `true` | Whether to enable comments
| `utterances` | Object | - | Utterances comments
| `dateFormat` | String | `Jan 2, 2006` | Date format. Checkout the [Hugo Date and Time Templating Reference](https://gohugo.io/functions/format/#hugo-date-and-time-templating-reference) for details.
| `poweredBy` | Boolean | `true` | Whether to show powered by.
| `math` | Boolean | `false` | Whether to enable math globally.
| `logo` | String | `images/logo.webp` | Logo image.
| `brand` | String | - | Brand text.
| `description` | String | - | Site description.
| `palette` | String | - | Default palette.
| `palettes` | Array | **ALL** | Available palettes.
| `featuredPostCount` | Integer | `5` | The number of featured posts shown in sidebar.
| `recentPostCount` | Integer | `5` | The number of recent posts shown in sidebar.
| `relatedPostCount` | Integer | `5` | The number of related posts.
| `categoryCount` | Integer | `10` | The number of categories shown in sidebar.
| `tagCount` | Integer | `10` | The number of tags shown in sidebar.
| `fullWidth` | Boolean | `false` | Full width.
| **Archive**
| `archive` | Object | - | Archive configuration.
| `archive.paginate` | Integer | `100` | Archive pagination.
| `archive.dateFormat` | Integer | `Jan 2` | Archive date format.
| **Search**
| `search` | Object | - | Search configuration.
| `search.resultContentWordCount` | Integer | `240` | The maximum word count of result content for displaying.
| `search.fuse` | Object | - | [Fuse.js options](https://fusejs.io/api/options.html).
| `search.fuse.ignoreLocation` | Boolean | `true` |
| `search.fuse.location` | Integer | - |
| `search.fuse.isCaseSensitive` | Boolean | - |
| `search.fuse.minMatchCharLength` | Integer | - |
| `search.fuse.threshold` | Double | - |
| `search.fuse.distance` | Integer | - |
| `search.fuse.useExtendedSearch` | Boolean | - |
| **Webmaster Site Verification** 
| `siteVerification` | Object | - |
| `siteVerification.google` | String | - | Google Webmaster Tool.
| `siteVerification.bing` | String | - | Bing Webmaster Tool.
| `siteVerification.baidu` | String | - | Baidu Webmaster Tool.
| **Analytics** 
| `analytics` | Object | - | Analytics configuration.
| `analytics.baidu` | String | - | Bing Analytics.
| **Others** 
| `googleAdsense` | String | - | Google Adsense.
| `customCSS` | Array | - | Custom CSS. It is mainly used to import external CSS. See [Custom Assets](#custom-assets).
| `customJS` | Array | - | Custom JS. It is mainly used to import external JS. See [Custom Assets](#custom-assets).
| `utterances` | Object | - | [Utterances](#utterances) configuration.
| `utterances.repo` | String | - | Github repository.
| `utterances.issueTerm` | String | `pathname` | `pathname`, `url`, `title`, `og:title`.
| `utterances.label` | String | - | 
| `utterances.theme` | String | `github-light` | `github-light`, `github-dark`, `preferred-color-scheme`, `github-dark-orange`, `icy-dark`, `dark-blue`, `photon-dark`.

> Except the Google webmaster tool, the other webmaster tools cannot work with `hugo --minify`, because they cannot recognize the minified meta tag.

### Page Parameters

| Name | Type  | Default | Description
|---|:-:|:-:|---
| **Page** 
| `comment` | Boolean | `true` | Whether to enable comments. It won't work if `comment` has been disabled globally.
| `math` | Boolean | `false` | Whether to enable math.

## Comments

### Disqus

```toml
disqusShortname = "yourdiscussshortname"
```

> `disqusShortname` is a site's configuration, **not** a parameter. Place it under the `params` won't work.

Checkout the [Disqus](https://disqus.com/) website for details.

### Utterances

[Utterances](https://utteranc.es/) is a lightweight comments widget built on GitHub issues.

```toml
[utterances]
  repo = "user/repo"
  #issueTerm = "pathname" # pathname, url, title, og:title.
  #label = "comment" # Optional.
  #theme = "github-light" # github-light, github-dark, preferred-color-scheme, github-dark-orange, icy-dark, dark-blue, photon-dark.
```

> Unlike Disqus, Utterances is a parameter. You should put it under the `params`.

## Custom Assets

There are two ways to customize the internal and external assets.

### Internal Assets

This is the best way to customize the theme's CSS and JS. Just create the files `assets/css/custom.css` and `assets/js/custom.js`.
These files will be bundled into one for reducing HTTP requests.

### External Assets

Any external CSS and JS resources can be imported by the parameters `customCSS` and `customJS`.

> Both of `customCSS` and `customJS` can also import the internal assets. Just put the files into the `static` folder.
## Hooks

Hooks are used for adding code on pages.

| Hook | Description |
|---|---|
| `head-end` | Before the `<head>` end |
| `body-end` | Before the `<body>` end |
| `sidebar-begin` | At very top of the sidebar |
| `sidebar-end` | Before the sidebar end |
| `content-begin` | Above of the post content |
| `content-end` | Follow the post content |
| `comments-begin` | Above of the comments |
| `comments-end` | Follow the comments |
| `footer-begin` | At very top of the footer |
| `footer-end` | Before the footer end |

For using a hook, you need to create an HTML file named with the hook name in the directory `layouts/partials/hooks`.

For example:

```shell
$ echo "SIDEBAR BEGIN" > layouts/partials/hooks/sidebar-begin.html
```

## Shortcodes

| Shortcode | Description | Usage
|---|---|---
| `alert` | Alter message | `{{< alert "message" [type] >}}`, `[type]` can be one of `info`, `success`, `warning` and `danger`
| `jsfiddle` | JSFiddle | `{{< jsfiddle "user/id" >}}`
| `codepen` | CodePen | `{{< codepen "id" >}}`
| `jsrun` | JSRUN | `{{< jsrun "id" >}}`
| `bilibili`| Bilibili video player | `{{< bilibili "video ID" >}}`
| `youku`| Youku video player | `{{< youku "video ID" >}}`
| `iqiyi`| iQiyi video player | `{{< iqiyi "vid" "tvid" >}}`
| `tencentvideo`| Tencent video player | `{{< tencentvideo "video ID" >}}`
| `neteasemusic`| Netease music player | `{{< neteasemusic "song ID" >}}`

## Social Links

The `social` is a set of key value pairs of social links that mapping from platform to user identifier.

> 

Enable social links by creating a file `config/_default/social.toml` with the following content:

```toml
email = "user@domain.tld"
github = "githubusername"
# ...
```

| Platform | User Identifier |
|---|---|
| `email` | Email address |
| `facebook` | Facebook username |
| `github` | GitHub username |
| `gitlab` | GitLab username |
| `instagram` | Instagram username |
| `linkedin` | LinkedIn username |
| `quora` | Quora username |
| `stackoverflow` | Stack Overflow user ID |
| `tumblr` | Tumblr username |
| `twitter` | Twitter username |
| `weibo` | Weibo username |
| `zhihu` | Zhihu username |

## Contribute

**Any contributions are welcome.**

- :star: if you are interested in this theme.
- [File an issue](https://github.com/razonyang/hugo-theme-bootstrap/issues/new)
  - Ask questions.
  - Report bugs.
  - Request features.
- Create a PR:
  - Fix issues and bugs.
  - Add new features.
  - Improve documentations.

### Develop

This theme relies on `npm` and `webpack` for development. The source of `js` and `scss` are placed in `src` directory.

**Install dependencies**

```shell
$ npm install
```

**Rebuild assets**

```shell
$ npm run build
```

> `npm run watch` rebuild assets on change.

**Preview**

```shell
$ cd exampleSite
$ hugo server --themesDir=../../
```
