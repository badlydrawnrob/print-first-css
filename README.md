# Print First CSS




## Quick intro

> You might ask yourself, "who on earth prints these days?" — I do!
> Quite often actually. As an offline reference to websites, a CV for potential employers; someday, perhaps an eBook.

**This framework is meant for** simple layouts like **PDFs and eBooks**. It can be used for rudimentary websites and blogs, and as a solid typographic base for child themes. It's core purpose is to make reading pleasurable in print-like format.

Only the essentials here, folks:

- No fluff, no grid system
- Basic styling for presentations, ebooks, or pdfs
- Can be used as a base for websites (and custom print styles)
- Preview styles in the [`specimen`](./build/markdown/specimen.html) file.


## Why print first?

Print is often a second citizen these days, but it's useful! You might need to rattle off presentations, write a proposal, [build a CV](https://github.com/badlydrawnrob/print-first-cv), or share ideas quickly. Or, perhaps you're an author publishing an ebook?

Write it down with Markdown, then convert with the app of your choice:

- [Pandoc](https://pandoc.org) if you know what a terminal is,
- [Marked](http://marked2app.com) if you prefer GUIs,
- For websites, you can print or [create a PDF](https://support.apple.com/en-gb/guide/mac-help/mchlp1531/mac) with your browser.


### Print first, screen second

Think about print first; add the finesse for screen-based devices later:

1. `@media all` for **BOTH** screen and print (use often)
2. `@media screen` to **ADD** css for screen only
3. `@media print` to **REMOVE** screen css for print (use sparingly)
4. `@media (orientation: portrait)` (or `landscape`) may come in handy too.

The method isn't suitable for every job, but for printable media, it's much better for a [long blog post](https://wpmudev.com/blog/stop-printing-ugly-wordpress-pages-heres-how-to-fix-it/), or [complex user interfaces](https://www.smashingmagazine.com/2011/11/how-to-set-up-a-print-style-sheet/)!




## Typography

Typography heavily influenced by [Material Design](https://material.io/design/typography/the-type-system.html) — all typography aligns to a [`4dp`](https://stackoverflow.com/a/2025541) grid, with default `--font-size` of `16dp`.

### Some helpers:

1. [A baseline grid](./source/style/modules/mixins/grid-baseline.less) mixin,
2. [Device agnostic `system-ui` fonts](./source/style/modules/variables/typography.less) (for iOS and Android),
3. Some helpful [CSS variables](./source/style/modules/variables/_root.less).

### ⚠️ You may need ...

> Depending on the `font-family` you may need to make some adjustments.

Headings may need `--line-height` and `margin-bottom` changes, or you may have to abandon the `.grid-baseline` depending on the complexity of your design. It's [difficult](#alert-perfect) to achieve pixel perfection with web-based projects!

Online and PDFs aren't quite as easy to stick to a grid as InDesign projects.




## Layout

> <span id="alert-perfect">⚠️</span> **Perfect is the enemy of good** ([Voltaire](https://en.wikipedia.org/wiki/Perfect_is_the_enemy_of_good))
> — try to keep grid-level items divisible by `8` or `4`;

All components and media align to an [`8dp` baseline grid](./source/modules/mixins/grid-baseline.less) (double the [typography](./#typography) baseline).

[Typographic vertical rythmn](http://webtypography.net/2.2.2) and the baseline/grid layouts are notoriously difficult to get right for digital projects, so don't worry about being pixel perfect. Try to keep [`box-model`](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model) children aligned to the baseline grid where possible. For instance, `flexbox` has the option to [`align-items: baseline`](https://css-tricks.com/almanac/properties/a/align-items/) with it's siblings.

**Eyeball it;** does it look right?





## Styleguide

> Just do the enough thing![^1]

1. [Intro to Markdown and writing styleguide](./build/markdown/styleguide.md)
2. [Writing in context](./build/markdown/specimen.md)
3. [A look at base-level components](./build/markdown/partials.md)
4. [Sane stylesheets for css](https://github.com/badlydrawnrob/ecss)






# Installation

1. You have [Node](https://nodejs.org/en/) installed
2. Create your repo and `cd your/folder/`
3. `npm init` 
4. `npm install badlydrawnrob/print-first-css --save-dev`
5. `npm run build`

### Upgrading

Check the release notes first, then:

`npm upgrade`


### Minimally using LESS

> Almost completely pure CSS.
> CSS is NOT a programming language. Don't use it that way!
> One `.grid-baseline()` mixin used only.

The [`less`](http://lesscss.org) files are simply a nice way to split out [different parts](https://en.wikipedia.org/wiki/Separation_of_concerns) of the CSS. I don't advocate using mixins and functions with your CSS. You can compile your CSS like below:

1. Create a [config](./source/style/config.less) file
2. `@import (less) "../../node_modules/print-first-css/build/style/print-first.css";`
3. Change any `:root { --css-variables ... }` you need
4. Create a [main](./source/style/main.less) file
5. Get creative with css!
6. `npm run build`


# License and inspiration

> Print First CSS is licensed under the [MIT Open Source License](./license.md)

There's been a bunch of inspirations over the years, but mostly thanks to [@cbracco](https://github.com/cbracco) (Cardinal CSS) and [Material Design](https://m2.material.io/design/typography/the-type-system.html).



# Further reading

1. [CommonMark](http://commonmark.org/help/)
2. [Mastering markdown](https://guides.github.com/features/mastering-markdown/#examples)
3. [Markdown cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
4. [Pandoc tricks](https://github.com/jgm/pandoc/wiki/Pandoc-Tricks)



[^1]: **Do the enough thing!** Keep `--css-variables` to a minimum, Be [brutal](https://brutalist-web.design/) in your design, "Keep it simple, stupid" and [don't make me think](https://en.wikipedia.org/wiki/Don%27t_Make_Me_Think) — just [do the enough thing](https://fs.blog/jason-fried/)!
