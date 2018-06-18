# Print First CSS



## Quick intro

A simple, print-based starting point for typographic css projects. No fluff, no grid system, [ecss](https://github.com/badlydrawnrob/ecss) and [markdown](http://commonmark.org) compatible.

Only the essentials here, folks.





## Stylus

Uses [Stylus](http://stylus-lang.com) to compile css:

1. **Simple variables**:
    - `modules/variables/*` sets up default variables for typography, color and spacing
    - `modules/mixins/*` sets up a `baseline-grid()`
    - `partials/*` for our component files
2. **Typography**
    - `rem` defaults
    - [Material Design](https://material.io/design/typography/) typographic scale and rythm
3. **[Normalize](https://necolas.github.io/normalize.css/)** as an `npm` dependency
    - See [Current issues](#current-issues)

### Hashes

Uses [hashes](http://stylus-lang.com/docs/hashes.html) for global settings. Most of the `$variables` can (and probably should) be left as-is. It's easier to `@import` the framework and override the HTML. If you prefer, edit or add hashes like so:

- Access values: `$font.family.base`
- Change values: `$font.family.base = 'Arial'`
- Add values: `$color['theme'] = {primary: 'blue', secondary: 'yellow'}`
    + You may need to escape `\` or use `unquote()` for some values
- [Source order matters](https://github.com/stylus/stylus/issues/2136), so I set some sensible `$default-` values to make them easier to override.
    + Override the hashes, **not** the `$default-`s!

### Typography

All typography aligns to a Material Design `4sp/px` grid. Each of the headings have their own line-height. To achieve a perfect alignment to our base `24sp/px` line-height, you'll need to change the `margin-bottom` on headings, as well as any other elements you might like to align.

> Arial is default. Other fonts may require fine-tuning to properly fit the baseline-grid

- Default `font-size` is `16sp/px` — it's easier to calculate!
    - See `modules/variables/defaults.styl` for other font size combos
- Use `baseline-grid()` and `$spacing.x` to align your components
    - ⚠ Sets the container to `position: relative` so be aware of unintended consequences!
- Default `$spacing.base` is `1.5rem` (same as line-height `1.5`)
    - There are aliases setup, i.e `$spacing.whole` to make things easier





## Installation

Install with (npm)[https://www.npmjs.com/]:

```git
npm install badlydrawnrob/cardinal-stylus --save
```

### Using Cardinal stylus

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






## Styleguide
It's best to stick to the following conventions:



### ECSS

Ben Frain's [ECSS](https://github.com/badlydrawnrob/ecss) naming conventions. All components are self-contained, grouped with their `html`/`js`/`...` files.


### CSS declaration order

Use [css declaration order](http://codeguide.co/#css-declaration-order) by @mdo — `mixins()` come first.

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
  font: normal 13px "Helvetica Neue", sans-serif
  line-height: 1.5
  color: $color.bbbb
  text-align: center

  // Visual
  background-color: $color.llll
  border: 1px solid $color.ll
  border-radius: $border.radius

  // Misc
  opacity: 1
```






## Credits

Heavily leans on the original [Cardinal CSS](http://cardinalcss.com/) framework, but has departed enough from it's original ethos to "rebrand" for my own purposes.





## ⚠ Current Issues

- Normalize doesn't compile properly because of the `.` in the `npm` folder name. Added to `/partials` for now.
  - Pull in via `npm` and overwrite `/partials/_normalize.styl`
- Careful with Hashes, they fail silently if they've been used but not declared.
  - `$this.hash.isnt.setup` but is referenced, with no errors given
