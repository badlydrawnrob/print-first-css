# Print First CSS

- A bare-bones print layout with custom font
- ePub, PDF, and typographic layouts
- Handy for CVs, technical docs, and writing.
- Great for editing notes by hand.
- Not a framework (but can be extended for tiny apps)[^1]


## Quick intro

> Does anyone print anymore? I do!

Solid typography, stacked elements, and pleasurable reading (on low-fi and high-def screens).

Only the essentials here, folks:

- Basic styling for reading
- No grid system, no fluff, no nonsense
- Extend for colourful eBooks (like Libra)
- [Specimen](./build/markdown/specimen.html) files included (preview styles)


## Why print first?

> Everything is motion these days, but lets go back to our roots!

Print is often a second citizen these days, but it's useful! You might need to rattle off presentations, write a proposal, [build a CV](https://github.com/badlydrawnrob/print-first-cv), or share ideas quickly. Perhaps you're a budding author publishing an ebook!

Write it with Markdown, convert with the app of your choice:

- [Pandoc](https://pandoc.org) if you know what a terminal is,
- [Marked](http://marked2app.com) if you prefer GUIs,
- Save as a PDF with your browser (using `print-first-css`) with `file -> print`.


### Print first, screen second

Think about print first; add the finesse for screen-based devices later:

1. `@media all` for **BOTH** screen and print (use often)
2. `@media screen` to **ADD** css for screen only
3. `@media print` to **REMOVE** screen css for print (use sparingly)
4. `@media (orientation: portrait)` (or `landscape`) may come in handy too.

The method isn't suitable for every job, but for printable media, it's much better for a [long blog post](https://wpmudev.com/blog/stop-printing-ugly-wordpress-pages-heres-how-to-fix-it/), or [complex user interfaces](https://www.smashingmagazine.com/2011/11/how-to-set-up-a-print-style-sheet/)!


## Typography

> Nice default font with [fallback `system-ui`](./source/style/modules/variables/typography.less) (Android and iOS)

All typography aligns to a [`4dp`](https://stackoverflow.com/a/2025541) grid, with default `--font-size` of `16dp` (... change?)

### The `x-height` problem

Inline `code` and `pre` blocks use `font-size: inherit`. It seems most devices have the `monospace` font with a larger `x-height` than the regular font. It's best if you find a monospace font that's similar in height to your default, but here's a [small fix](https://tinyurl.com/2p9xpevw) for if it isn't.


## Layout

> - `.gl-BaselineGrid` class for vertical rythmn.
> - Aim to keep grid-level items divisible by `8` or `4`
> - You may need to adjust your font's `--line-height` and `margin-bottom`

Everything aligns to an [`8dp` baseline grid](./source/modules/mixins/grid-baseline.less) (double the [typography](./#typography) baseline). A [vertical rythmn](http://webtypography.net/2.2.2) is nice in theory, difficult in practice for web-based styles. Try to keep the [`box-model`](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model) aligned and consider [`align-items: baseline`](https://css-tricks.com/almanac/properties/a/align-items/) if using `flexbox`.

Remember, "Perfect is the enemy of good" ([Voltaire](https://en.wikipedia.org/wiki/Perfect_is_the_enemy_of_good)) so sometimes it's best to just **eyeball it;** does it feel right?



## Styleguide

> Just do the enough thing![^1]

1. [Intro to Markdown and writing styleguide](./build/markdown/styleguide.md)
2. [Writing in context](./build/markdown/specimen.md)
3. [A look at base-level components](./build/markdown/partials.md)
<!--4. [Sane stylesheets for css](https://github.com/badlydrawnrob/ecss)-->



# Installation

1. You'll have [Node](https://nodejs.org/en/) installed
2. Create your repo and `cd ./project`
3. `npm init`
4. `npm install badlydrawnrob/print-first-css --save-dev`
5. `npm run build`

To upgrade, check the release notes first, then `npm upgrade`.



# License and inspiration

> Print First CSS is licensed under the [MIT Open Source License](./license.md)

There's been a bunch of inspirations over the years, but mostly thanks to [@cbracco](https://github.com/cbracco) (Cardinal CSS) and [Material Design](https://m2.material.io/design/typography/the-type-system.html).



# Further reading

1. [CommonMark](http://commonmark.org/help/)
2. [Mastering markdown](https://guides.github.com/features/mastering-markdown/#examples)
3. [Markdown cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
4. [Pandoc tricks](https://github.com/jgm/pandoc/wiki/Pandoc-Tricks)



[^1]: You can `@import (less)` files into your own project and override the `--css-variables` in `:root`. Recompile with NPM (`npm run build`) and you're ready to [do the enough thing](https://fs.blog/knowledge-project-podcast/jason-fried/). Follow the [don't make me think](https://en.wikipedia.org/wiki/Don%27t_Make_Me_Think) principles for styles and UI and try to be [consistent](https://google.github.io/styleguide/htmlcssguide.html) with your code.
