# Cardinal partials

Here you'll find the base partials that make Cardinal work. They've been adapted from the original version.


## Overview

Cardinal Base provides a solid foundation for the framework, including things like:

- [normalize.css](https://necolas.github.io/normalize.css/)
- a thin reset layer `reset.styl` on top of normalization
- Sensible default styles for common HTML elements


## normalize.css

Cardinal includes the 3rd-party library [normalize.css](https://github.com/necolas/normalize.css), which makes browsers render all elements more consistently and in line with modern web standards.

It's included as a dependency, so you'll have to `@import` it in your project.


## Reset

On top of [normalize.css](https://github.com/necolas/normalize.css), Cardinal includes a light reset layer to add even more consistency to the framework.

- All elements inherit `box-sizing: border-box;` property from the `<html>` element ([more info](http://cbrac.co/RQrDL5)).
- Remove margins, paddings, and borders from HTML elements ([more info](http://cbrac.co/1Ev9etR)).
- Remove default border for `<iframe>` elements ([more info](http://cbrac.co/1CVyNTj)).
- Remove `:focus` outline on links that cannoy be accessed via keyboard ([more info](http://cbrac.co/1Evazku)).


## Default Styles

After [normalize.css](https://github.com/necolas/normalize.css) and a light reset, Cardinal sets some more default styles for common HTML elements.


### Root

Root defines core styles for the `<html>` element, such as default font family, font size, line height, background and text colors, forcing vertical scrollbars in IE, and more.

It also ensures the `<body>` element is at least the viewport height, sets a consistent margin for common elements to maintain a vertical rhythm, adds word-wrapping and basic hyphenation to common elements, and sets default `:focus` styles for the framework.


### Anchors

[View Demo](http://codepen.io/cbracco/pen/BNKNBo)

Default anchor link styles for this framework reside here.


### Text Elements

[View Demo](http://codepen.io/cbracco/pen/jPqPqm)

This file adds some opinionated default styles for inline text elements, such as adding the appropriate `cursor` styles to `<abbr>` elements, and adding `text-decoration: line-through` styles to `<del>` elements.


### Headings

[View Demo](http://codepen.io/cbracco/pen/PqNqzP)

Headings help break up blocks of text and visual content into consumable chunks, and Cardinal includes some default headings styles to facilitate better readability from the get-go.


### Lists

[View Demo](http://codepen.io/cbracco/pen/vOGOXB)

List elements like `<dl>`, `<ul>`, and `<ol>` also get their own default styles to provide a more consistent experience across browsers.


### Horizontal Rules

[View Demo](http://codepen.io/cbracco/pen/yNONaP)

`<hr>` elements also help break up text and visual content into consumable chunks, and Cardinal normalizes the styling of this element so it displays consistently across browsers.

```
hr {
  display: block;
  padding: 0;
  border: 0;
  .to-rem(border-top, @hr-border-width, @hr-border-style @hr-border-color);
}
```


### Embedded Content

[View Demo](http://codepen.io/cbracco/pen/pJyJNW)

Cardinal also includes some basic fixes and styles for embedded content (e.g. images, HTML5 audio & video, iframe, canvas, and SVG).

Embedded content elements are responsive out-of-the-box, by simply declaring `width: 100%` on these elements. Images and several other elements can resize automatically, and images will maintain their aspect ratio by way the following:

```
embed,
img,
object,
video {
  max-width: 100%;
  height: auto;
}

embed,
object {
  height: 100%;
}
```

Some basic styles are also given to `<figure>` and `<figcaption>` elements, just in case you need it.


### Form Elements

[View Demo](http://codepen.io/cbracco/pen/xGVGqm)

Forms are notoriously finicky, so this base file aims to remove and normalize the form experience before any major aesthetic design decisions are made.


### Tables

[View Demo](http://codepen.io/cbracco/pen/QbNbvg)

Similarly to forms, tables can be difficult to style correctly. This file corrects some table oddities to make the basic table element behave more consistently across browsers.


### Print

A default `@print` stylesheet is also included in Cardinal, which is an almost-exact copy of the [HTML5 Boilerplate print styles](http://cbrac.co/1PgyYR2).

These styles are inlined to avoid an extra HTTP request.


## Optional extras

If you want to include webfonts, use Google fonts or [`@font-face` code](https://css-tricks.com/snippets/css/using-font-face/):

```stylus
@font-face
  font-family: 'metallophile'
  font-style: normal
  font-weight: 700
  src:  url('./fonts/metallophilesp8-medium-webfont.woff2') format('woff2'),
        url('./fonts/metallophilesp8-medium-webfont.woff') format('woff')
```
