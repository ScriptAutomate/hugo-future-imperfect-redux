> _**NOTE:** This theme is an extended version of the original Hugo theme, [Hugo Future Imperfect](https://github.com/jpescador/hugo-future-imperfect) by [Julio Pescador](https://jpescador.com). I've noticed that the theme repository hasn't been updated since early **2018** and has >15 PRs, thus why this is here (for my own features, and the extension of the theme by others). This felt like a better idea than merely using layout overrides in my personal website [icanteven.io](https://icanteven.io)_

# Hugo Future Imperfect Redux

Future Imperfect is a responsive theme tailored for blogging. The name is of no
coincidence, because it is a port of [HTML5 UP's theme](http://html5up.net/future-imperfect)
by the same name. In addition to the original features, there are more features
that have been added for you to utilize.

![Hugo Future Imperfect Screenshot](https://raw.githubusercontent.com/jpescador/hugo-future-imperfect/master/images/screenshot.png)

Check out this [site](https://themes.gohugo.io/theme/future-imperfect/) if you are
interested in seeing a live example of Hugo Future Imperfect.

## Table of Contents

<!-- TOC depthFrom:2 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Table of Contents](#table-of-contents)
- [Getting Started](#getting-started)
	- [exampleSite](#examplesite)
	- [config.toml](#configtoml)
	- [Hugo's Built-In Server](#hugos-built-in-server)
    - [Hugo's website SEO](#hugos-website-seo)
- [Shortcodes](#shortcodes)
	- [fancybox](#fancybox)
	- [img-post](#img-post)
	- [img-fit](#img-fit)
	- [url-link](#url-link)
- [New Redux Features](#new-redux-features)
    - [TinyLetter Support](#tinyLetter-support)
    - [Gravatar Support](#gravatar-support)
    - [Upgraded to FontAwesome 5](#upgraded-to-fontawesome-5)
    - [Keybase Social Icon Support](#keybase-social-icon-support)
- [About the Authors](#about-the-authors)
    - [Redux Author](#redux-author)
- [License](#license)

<!-- /TOC -->

## Getting Started

Run the following commands in your Hugo site directory:

```
mkdir themes
cd themes
git clone https://github.com/ScriptAutomate/hugo-future-imperfect-redux.git
```

You will then have access to the theme at _themes/hugo-future-imperfect_ from within
your project folder.

### exampleSite

Within the hugo-future-imperfect folder, there will be a folder in this theme called
_exampleSite_. The structure of the folder will look like this:

```
exampleSite
├── config.toml
├── staticman.yml
├── content
|   ├── about
|   |   └── _index.md
|   ├── blog
|   │   ├── creating-a-new-theme.md
|   │   ├── goisforlovers.md
|   │   ├── hugoisforlovers.md
|   │   └── migrate-from-jekyll.md
|   ├── contact
|   │   └── _index.md
|   └── itemized
|       ├── item1.md
|       ├── item2.md
|       ├── item3.md
|       └── item4.md
├── data
│   └── comments
│       └── .gitkeep
└── static
    ├── css
    │   └── add-on.css
    ├── img
    |   ├── 2014
    |   |   ├── 04
    |   |   |   ├── pic02.jpg
    |   |   |   └── pic03.jpg
    |   |   └── 09
    |   |       └── pic01.jpg
    |   └── main
    |       └── logo.jpg
    └── js
        └── add-on.js
```

Copy _config.toml_ from _exampleSite_ to the root directory of your Hugo site.
If you want static comments hosted by [Staticman](https://staticman.net/), also
copy the _staticman.yml_.

### config.toml

This file is the main sorce of customization within the theme. Each parameter has
a comment included to explain its functionality. Typical usage of _true_ means to
turn a function on, while _false_ means to turn a function off.

This file consists of six main sections. The first section contains the site wide
parameters innate to Hugo. The second section, _[params]_, contains site wide
parameter that are custom to the _hugo-future-imperfect_ theme. The third section,
_[params.staticman]_ controls how staticman comments interact with your repository.
The fourth section, _[params.intro]_ and _[params.postAmount]_, control aspects
of the sidebar. The fifth section, _[[menu.main]]_, sets the navigation menu items.
Lastly, the sixth section, _[social]_, allows you to easily link to, and include,
various social platforms.

### Hugo's Built-In Server

Run the following command to start a local server and to view a live version of
the website:

```
hugo server
```

You will then be able to view your live website at [localhost:1313](http://localhost:1313).

### Hugo's website SEO

This theme support SEO elements for your website.
It was adapted and integrated thanks to the following guide:  
[https://keithpblog.org/post/hugo-website-seo/](https://keithpblog.org/post/hugo-website-seo/)

If you wish to enable SEO on this theme, follow these instructions:
1. To include the following parameters in your _config.toml_
```
# .config.toml
...
enableRobotsTXT = true
canonifyURLs = true
# and if you think your md file names or locations might change:
[permalinks]
    post = "/blog/:title/"
...
```

2. Add your website to Google Search Console:
    - Login to the [Google Search Console](https://www.google.com/webmasters/tools/home)
    - Add your website as property
    - Add the html page as required by google to verify ownership
    - Submit the sitemap (/sitemap.xml) for indexing
    - Wait

3. Add your website to Bing 
    - Login to the [Bing Webmaster Console](https://www.bing.com/toolbox/webmaster/)
    - Add your site, details and verify
    - From the 3 option, we recommend adding the xml file to you website

## Shortcodes
In addition to the native [Hugo shortcodes](https://gohugo.io/extras/shortcodes/),
the theme also includes the following codes that I hope you find useful:
fancybox, img-post, img-fit, and url-link.

### fancybox
[Fancybox](http://fancyapps.com/fancybox/3/) is a jQuery lightbox script for displaying images, videos and more. It is touch
enabled, responsive and fully customizable. The commands are shown below:

**Named**
```
{{< fancybox path="path" file="file" caption="caption" gallery="gallery" >}}
```

**Positional**
```
{{< fancybox "path" "file" "caption" "gallery" >}}
```

Please refer to _layouts/shortcodes/fancybox.html_ for more details on the function.

Credit: [pacollins]

---

### img-post
Add an image which can be aligned center, left, or right. The commands are shown
below:

**Named**
```
{{< img-post path="date" file="filename.jpg" alt="Alt Text" type="left" >}}
```

**Positional**
```
{{< img-post "title" "filename.jpg" "Alt Text" "left" >}}
```

Please refer to _layouts/shortcodes/img-post.html_ for more details on the function.

Credit: [jpescador]

---

### img-fit
Insert multiple images with the ability to create a gallery if needed. The command
is shown below:

**Positional Only**
```
    {{< img-fit
        "4u" "filename1.jpg" "Alt text 1"
        "4u" "filename2.jpg" "Alt text 2"
        "4u$" "filename3.jpg" "Alt text 3"
        "date" >}}
```

Please refer to _layouts/shortcodes/img-fit.html_ for more details on the function.

Credit: [jpescador]

---

### url-link
Create a hyperlink and set a target value for the link. The default value is
`_blank`. The command is shown below:

**Positional Only**
```
{{< url-link "title" "www.link.com" "target">}}
```

Please refer to _layouts/shortcodes/url-link.html_ for more details on the function.

Credit: [jpescador]

## New Redux Features

This **Redux** version of this repository has some new features.

### TinyLetter Support

Adding `tinyletter` to your `config.toml` will embed a [TinyLetter](https://tinyletter.com) subscription box in both the sidebar and navbar.

```toml
# config.toml / .Site.Params.tinyletter
tinyletter = 'https://tinyletter.com/icantevenio'
```

Credit: [scriptautomate]

---

### Gravatar Support

Adding `gravatar` to your `config.toml` will override the `src` profile/image with a [Gravatar](https://www.gravatar.com/) profile image.

```toml
# config.toml / .Site.Params.intro.pic.gravatar
gravatar = 'gravataruser@email.com'
```

Credit: [horgix]

---

### Upgraded to FontAwesome 5

Major sweep in upgrading icon reference from FontAwesome 4 to 5! This took a bit of experimenting, due to some naming convention changes and behavior changes that came along with it.

Credit: [scriptautomate]

---

### Keybase Social Icon Support

Adding `keybase` to your `config.toml` will add a new social icon to your website.

```toml
# config.toml / .Site.Social.keybase
keybase = 'username'
```

Credit: [tygerbytes], with slight modification by [scriptautomate]

---

## About the Authors

Hugo Future Imperfect was ported by [Julio Pescador](https://jpescador.com). Extra
features implemented by the [project contributors](https://github.com/ScriptAutomate/hugo-future-imperfect-redux/graphs/contributors).

Send Julio Pescador a tweet [@julio_pescador](https://twitter.com/julio_pescador),
if you like the theme and are using it for your own personal use.

### Redux Author

Hugo Future Imperfect Redux is an extended, public clone  of Hugo Future Imperfect. It's managed by [Derek Ardolf](https://icanteven.io), who uses Twitter under [@ScriptAutomate](https://twitter.com/scriptautomate). It was initially created as a clone, in order to incorporate new features to be referenced by his personal website (starting with [TinyLetter support](#tinyLetter-support)).

## License

This theme is released under the MIT license. Please read the [license](https://github.com/ScriptAutomate/hugo-future-imperfect-redux/blob/master/LICENSE.md) for more information.

[jpescador]: https://github.com/jpescador
[pacollins]: https://github.com/pacollins
[scriptautomate]: https://github.com/scriptautomate
[horgix]: https://github.com/Horgix
[tygerbytes]: https://github.com/tygerbytes
