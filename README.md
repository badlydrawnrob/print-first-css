# Cardinal Stylus



## Quick intro

A slimmed down version of the [Cardinal](http://cardinalcss.com/) framework, to create a solid starting point for your projects (rather than a framework). Sets up some basics for my [Material Design](https://github.com/badlydrawnrob/cardinal-material) framework, uses [Jeet](http://jeet.gs/) as a grid system, and [ECSS](https://github.com/badlydrawnrob/ecss) as a css styleguide.

Only the essentials here, folks.



## Stylus

The following changes have been made:

1. **Simplified variables** (opinionated), `@import`ed with [globbing](http://stylus-lang.com/docs/import.html#file-globbing):
  - `modules/variables/*` sets up default variables and hashes,
  - `modules/mixins/*` holds `baseline-grid()` mixin,
  - `partials/*` for our default framework files,
  - `vendor/*` for 3rd party utilities
2. **`rem` is the default**
  - no `px` fallback.
3. **Simplified components**:
  - Removes utilities, but adds variables
5. **Typography defaults** from [Material Design](https://material.io/guidelines/style/typography.html):
  - One global `$font.family.base` only (with a `$mono` font for code)
6. **Mixins** (_Only one!_):
  - A `baseline-grid()` mixin for our vertical rhythm (based on MD)
7. **Use [Jeet](http://jeet.gs/) for grids**, or roll your own:
  - We're using custom `$spacing.x` variables for margins/padding.
8. **[Normalize](https://necolas.github.io/normalize.css/)** as an `npm` dependency
    - See [Current issues](#current-issues)
9. **Everything else as-is**

### Hashes

We're using [hashes](http://stylus-lang.com/docs/hashes.html) for global settings:

- Access values: `$font.family.base`
- Change values: `$font.family.base = 'Arial'`
- Add values: `$color['theme'] = {primary: 'blue', secondary: 'yellow'}`
- You may need to escape `\` or use `unquote()` for some values
- With hashes, [source order matters](https://github.com/stylus/stylus/issues/2136), so we set some sensible `$default-` values to make them easier to override.
  - Override the hashes, **not** the `$default-`s!

### Typography

All typography aligns to a Material Design `4sp/px` grid. Each of the headings have their own line-height. To achieve a perfect alignment to our base `24sp/px` line-height, you'll need to change the `margin-bottom` on headings, as well as any other elements you might like to align.

> Arial is default. Other fonts may require fine-tuning to properly fit the baseline-grid

- Use `baseline-grid()` and `$spacing.x` to align your components
  - ⚠ Sets the container to `position: relative` so be aware of unintended consequences!
- Default `$spacing.base` is `1.5rem` (same as line-height `1.5`)
  - There are aliases setup, i.e `$spacing.whole` to make things easier






# Installation

Install with (npm)[https://www.npmjs.com/] using the `#master` branch.

```git
npm install git+https://github.com/badlydrawnrob/cardinal-stylus.git#master --save
```



## Using Cardinal stylus

1. Create a `main.styl` file
2. `@import modules/variables/*`
3. You can now reset the variables:
  - Mirror the `variables/*` folder with any `$hash` overrides you like
  - [`@import` order matters](https://github.com/stylus/stylus/issues/2136)
  - Add any new hashes you might need
4. `@import` the remaining files, as in `cardinal.styl`
5. Integrate your project files



## Updating

```git
npm update
```






# Styleguide
Use the following conventions:



## ECSS

Ben Frain's [ECSS](https://github.com/badlydrawnrob/ecss) naming conventions. All components are self-contained, grouped with their `html`/`js`/`...` files.


## CSS declaration order
> != Under construction!

Use [css declaration order](http://codeguide.co/#css-declaration-order) by @mdo,
but mixins come first.

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
  width: 100px
  height: 100px

  // Typography
  font: normal 13px "Helvetica Neue", sans-serif
  line-height: 1.5
  color: #333
  text-align: center

  // Visual
  background-color: #f5f5f5
  border: 1px solid #e5e5e5
  border-radius: 3px

  // Misc
  opacity: 1
```






# ⚠ Current Issues

- Normalize doesn't compile properly because of the `.` in the `npm` folder name. Added to `/partials` for now
- Careful with Hashes, they fail silently if they've been used but not declared.
  - `$this.hash.isnt.setup` but is referenced, with no errors given
