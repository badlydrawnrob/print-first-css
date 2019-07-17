# Print First CSS




## Quick intro

A simple starting point for typographic css projects. Only the essentials here, folks:

- No fluff, no grid system
- Great for presentations, ebooks, or pdfs


### Why print first?

Print is often a second citizen these days, but it's useful! You might need to rattle off presentations or share ideas quickly. Or an author publishing an ebook.

Write it down with Markdown, then convert with the app of your choice:

- [Pandoc](https://pandoc.org) if you know what a terminal is,
- [Marked](http://marked2app.com)) if you like an app to do the work,
- Print with Safari, Chrome or Firefox


#### Print first, screen second

Think about print first; add the finesse for screen-based devices later:

- `@media all` for **BOTH** screen and print
- `@media screen` to **ADD** css for screen only
- `@media print` to **REMOVE** css (only when necessary)

It's not suitable for every job, but for printable media, it's much [better than this](https://flyingdogcreative.com/why-your-web-pages-print-badly-and-how-to-fix-them/)!




## Typography

Typography heavily influenced by [Material Design](https://material.io/design/typography/the-type-system.html) — all typography aligns to a Material Design `4dp/px` grid. [Vertical rhythm](http://webtypography.net/2.2.2) is notoriously difficult to get right, so I wouldn't worry too much.

Some helpers:

1. [A baseline grid](./source/style/modules/mixins/grid-baseline.less)
2. [Default iOS and Android fonts](./source/style/modules/variables/typography.less)
3. [CSS variables](./source/style/modules/variables/_root.less)
4. Headings have their own `--line-height` depending on font
5. Default `--font-size` is `16dp/px`




## Layout

> All components and media should be divisible by `8` or `4`;

All components and media align to the `8dp/px` [baseline grid](./source/modules/mixins/grid-baseline.less) (that's double [typography](./#typography) baseline). Don't worry about [being pixel perfect](http://webtypography.net/2.2.2) — it's notoriously difficult to get right.




## Installation

1. You have [Node](https://nodejs.org/en/) installed
2. Create your repo and `cd your/folder/`
3. `npm init` 
4. `npm install badlydrawnrob/print-first-css --save-dev`
5. `npm run build`

### Upgrading

Check the release notes first, then:

`npm ugrade`




## Less

Print First is 99% standard CSS. I've added [`.less`](http://lesscss.org) files into the mix to make things easier on the eye. Creating your CSS is simple as:

1. Create a [config](./source/style/config.less) file
2. `@import (less) "../../node_modules/print-first-css/build/style/print-first.css";`
3. Change any `:root { --css-variables ... }` you need
4. Create a [main](./source/style/main.less) file
5. Get creative with css!
6. `npm run build`




----




## Styleguide

1. [Intro to Markdown and writing styleguide](./build/markdown/styleguide.md)
2. [Writing in context](./build/markdown/speciman.md)
3. [A look at the components](./build/markdown/partials.md)
4. [Sane stylesheets for css](https://github.com/badlydrawnrob/ecss)




----


## Further reading

1. [CommonMark](http://commonmark.org/help/)
2. [Mastering markdown](https://guides.github.com/features/mastering-markdown/#examples)
3. [Markdown cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
4. [Pandoc tricks](https://github.com/jgm/pandoc/wiki/Pandoc-Tricks)
