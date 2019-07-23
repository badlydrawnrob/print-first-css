# Print First CSS




## Quick intro

A simple starting point for typographic css projects. Only the essentials here, folks:

- No fluff, no grid system
- Great for presentations, ebooks, or pdfs


### Why print first?

Print is often a second citizen these days, but it's useful! You might need to rattle off presentations or share ideas quickly, or perhaps you're an author publishing an ebook.

Write it down with Markdown, then convert with the app of your choice:

- [Pandoc](https://pandoc.org) if you know what a terminal is,
- [Marked](http://marked2app.com) if you like an app to do the work,
- Print with Safari, Chrome or Firefox


#### Print first, screen second

Think about print first; add the finesse for screen-based devices later:

1. `@media all` for **BOTH** screen and print (use often)
2. `@media screen` to **ADD** css for screen only
3. `@media print` to **REMOVE** screen css for print (use sparingly)

The method isn't suitable for every job, but for printable media, it's much [better than this](https://flyingdogcreative.com/why-your-web-pages-print-badly-and-how-to-fix-them/)!




## Typography

Typography heavily influenced by [Material Design](https://material.io/design/typography/the-type-system.html) — all typography aligns to a [`4dp`](https://stackoverflow.com/a/2025541) grid, with default `--font-size` of `16dp`.

**Some helpers:**

1. [A baseline grid](./source/style/modules/mixins/grid-baseline.less)
2. [Default iOS and Android fonts](./source/style/modules/variables/typography.less)
3. [CSS variables](./source/style/modules/variables/_root.less)

**<span id="alert-headings">⚠️</span> Watch out for ...**

- Headings may need `--line-height` and `margin-bottom` adjusting [depending on font](https://graphicdesign.stackexchange.com/q/4035)
- Don't worry too much about [pixel perfection](#alert-perfect)




## Layout

> Everything should be divisible by `8` or `4`;

All components and media align to a [`8dp` baseline grid](./source/modules/mixins/grid-baseline.less) (double the [typography](./#typography) baseline).

> <span id="alert-perfect">⚠️</span> **Perfect is the enemy of good** ([Voltaire](https://en.wikipedia.org/wiki/Perfect_is_the_enemy_of_good))
> [Typographic vertical rythmn](http://webtypography.net/2.2.2) and the layout baseline is notoriously difficult to get right, so don't worry about being pixel perfect. Try to keep each ["chunk" of content](https://internetingishard.com/html-and-css/css-box-model/) consistent, [aligned to the baseline](https://css-tricks.com/almanac/properties/a/align-items/) — eyeball it; does it work?





## Styleguide

1. [Intro to Markdown and writing styleguide](./build/markdown/styleguide.md)
2. [Writing in context](./build/markdown/speciman.md)
3. [A look at the components](./build/markdown/partials.md)
4. [Sane stylesheets for css](https://github.com/badlydrawnrob/ecss)




----




## Installation

1. You have [Node](https://nodejs.org/en/) installed
2. Create your repo and `cd your/folder/`
3. `npm init` 
4. `npm install badlydrawnrob/print-first-css --save-dev`
5. `npm run build`

### Upgrading

Check the release notes first, then:

`npm upgrade`




## Less

> 99% standard CSS with a hint of less

I've added [`.less`](http://lesscss.org) files into the mix to make things [easier on the eye](https://en.wikipedia.org/wiki/Separation_of_concerns). Creating your CSS is simple as:

1. Create a [config](./source/style/config.less) file
2. `@import (less) "../../node_modules/print-first-css/build/style/print-first.css";`
3. Change any `:root { --css-variables ... }` you need
4. Create a [main](./source/style/main.less) file
5. Get creative with css!
6. `npm run build`




----




## Further reading

1. [CommonMark](http://commonmark.org/help/)
2. [Mastering markdown](https://guides.github.com/features/mastering-markdown/#examples)
3. [Markdown cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
4. [Pandoc tricks](https://github.com/jgm/pandoc/wiki/Pandoc-Tricks)
