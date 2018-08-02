# Print First CSS



## Quick intro

A simple, print-based starting point for typographic css projects. No fluff, no grid system, [ecss](https://github.com/badlydrawnrob/ecss) and [markdown](http://commonmark.org) compatible.

Only the essentials here, folks.


### Why print first?

If you're like me, you often need to rattle off print or PDF presentations. Just write your musings with Markdown, use an app like [Marked](http://marked2app.com) and export away. You can also convert into HTML (or write vanilla HTML) and let print in Safari, Chrome or Firefox.

It could also be useful for authors, if writing ebooks is your thing.


### Typography

All typography aligns to a Material Design `4sp/px` grid. [Vertical rhythm](http://webtypography.net/2.2.2) is notoriously difficult to get right, so I wouldn't worry too much.

1. **Headings** have their own `$line.height.x`
    + You'll may need to adjust the `margin-bottom` with a new `font-family`
    + [Cap height](https://bit.ly/2tseu0u) may also be an issue
2. **Components** simply make sure the total `height`, `margin`, and `padding` align to the `4sp/px` grid for any given component.
3. **Default** `font-size` is `16sp/px`
    + It's easier to calculate
    + See `modules/variables/defaults.styl` for all `font-size` and `line-height` variations
4. **Baseline** the `baseline-grid()` and `$spacing` variables can be used to get the right vertical rhythm
    + **Total height / 4** combined height of a component or text elements (including `height` + `margin` + `padding` etc) should be divisible by 4
5. **Image sizes** should stick to the `4sp/px` grid wherever possible


## Roll your own theme

### Print first, `@media` second

I use [ecss](#ecss) to create my CSS/HTML components, thinking _mobile-first_ and _print-first-css_ ... it's simple:

1. **Add** styles for devices with `@media screen`
2. **Remove** sections you don't need printed with `@media print` and `display: none`.

### Stylus

Uses [Stylus](http://stylus-lang.com) to compile css:

1. **[Normalize](https://necolas.github.io/normalize.css/)** as an `npm` dependency
    - See [Current issues](https://github.com/badlydrawnrob/print-first-css/issues/5)
2. **Simple variables**:
    - `source/stylus/modules/variables/*` sets up default variables for typography and spacing
    - `source/stylus/modules/mixins/*` sets up a `baseline-grid()`
    - `source/stylus/partials/*` for our component files
3. **Typography**
    - `rem` defaults
    - [Material Design](https://material.io/design/typography/) typographic scale and rythm
4. **Lightweight `@media print` resets**
    - Vendor defaults for _anchors_
    - `source/stylus/partials/print.styl`
4. **No fancy stuff**
    - Plain text only!
    - Minimal background colours (_black prints faster!_)
    - Roll your own buttons, color themes and components :)
    - Use [`@media` queries](https://caniuse.com/#feat=css-mediaqueries) for screen-specific styles
        - See [Current issues](#current-issues)

### Hashes

Uses [hashes](http://stylus-lang.com/docs/hashes.html) for global settings. Most of the `$variables` can (and probably should) be left as-is. It's easier to `@import` the framework and override the HTML. If you prefer, edit or add hashes like so:

- Access values: `$font.family.base`
- Change values: `$font.family.base = 'Arial'`
- Add values: `$color['primary'] = #6200EE`
    + Some values may require `\escaping` or `unquote()`
- [Source order matters](https://github.com/stylus/stylus/issues/2136), so I set some sensible `$default-` values to make them easier to override.
    + Override the hashes, **not** the `$default-`s!


----


## Installation

Install with (npm)[https://www.npmjs.com/]:

```git
npm install badlydrawnrob/print-first-css --save
```

### Compiling Stylus

Compile with [Codekit](https://codekitapp.com), or choose your own.

1. Create a `source/stylus/config.styl` file
    + `@import` the `print-first.styl` file from the npm folder
2. Mirror the `modules/..` folder layout
    + `@import 'modules/variables/*'`
    + `@import 'partials/*'`
3. Reset any variables if required
    + See [hashes](#hashes)
4. Create an `ecss/components/..` folder for your component files
5. Create a `source/stylus/main.styl` file
    + `@import` your `source/stylus/config.styl` file
    + `@import` your `ecss/component/*` stylus files
6. Compile your css in your `build` folder

### Updating

```git
npm update
```


----


## Styleguide

I try to follow these conventions, I'd advise you to do the same:


### ECSS

Ben Frain's [ECSS](https://github.com/badlydrawnrob/ecss) naming conventions. All components are self-contained, grouped with their `html`/`js`/`...` files.


### CSS declaration order

Based on @mdo [css declaration order](http://codeguide.co/#css-declaration-order) styleguide.

1. Mixins
2. Positioning
3. Box model
4. Typographic
5. Visual

```stylus
.declaration-order
  // Mixins
  baseline-grid()

  // Positioning
  position: absolute
  top: 0
  right: 0
  bottom: 0
  left: 0
  z-index: 100

  // Box-model
  display: block
  float: right
  width: $spacing.base
  height: $spacing.base

  // Typography
  color: #000
  font: normal 13px "Helvetica Neue", sans-serif
  line-height: 1.5
  text-align: center

  // Visual
  border: 1px solid #f1f1f1
  border-radius: $border.radius

  // Misc
  opacity: 1
```


----


## Credits

1. **[Cardinal CSS](http://cardinalcss.com/):** Heavily leans on the original Cardinal framework, but has departed enough from it's original ethos to "rebrand" for my own purposes.
2. **Markdown:** Notes on `.md` collated from:
    - [CommonMark](http://commonmark.org/help/)
    - [Github](https://guides.github.com/features/mastering-markdown/#examples)
    - [Adam Pritchard](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
