# Cardinal Stylus

## Quick intro

A slimmed down version of the [Cardinal](http://cardinalcss.com/) framework, which also imports [Jeet](http://jeet.gs/), removes most utility classes, all mixins, most components, following [ECSS principles](https://benfrain.com/my-fourth-book-enduring-css/).

Only the essentials here, folks.



## Stylus

Theres a few changes out of necessity, such as:

1. Reordering and renaming of some variables, making them easier to find, `@imports` using [globbing](http://stylus-lang.com/docs/import.html#file-globbing)
    - `modules/variables/*` sets up default variables and hashes,
    - `modules/mixins/*` holds components mixins,
    - `partials/*` for our default framework files,
    - `vendor/*` for 3rd party utilities, like [normalize.css](https://necolas.github.io/normalize.css/)
2. `rem` is the default, no `px` fallback.
3. Barebones components and utilities
4. [Jeet](http://jeet.gs/) for grids.
5. Everything else as-is

### Hashes

We're using [hashes](http://stylus-lang.com/docs/hashes.html) for global settings:

- Access values: `$font.family.serif`
- Change values: `$font.family.serif = 'Arial'`
- You may need to escape `\` or use `unquote()` for some values
- With hashes, [source order matters](https://github.com/stylus/stylus/issues/2136), so we set some sensible `$default-` values to make them easier to override.
  - Override the hashes, **not** the `$default-`s!



## Installation

Install with (npm)[https://www.npmjs.com/] using the `#master` branch.

```git
npm install git+https://github.com/badlydrawnrob/cardinal-stylus.git#master --save
```

### Using Cardinal stylus

1. Create a `main.styl` file
2. `@import modules/variables/*`
3. After these are imported, you can reset the variables:
  - Mirror the `variables` folder with any `$hash` overrides you like
  - [`@import` order matters](https://github.com/stylus/stylus/issues/2136)
  - Add any new hashes you might need, `$color.primary = #92C96E`
4. `@import` the remaining files, as in `cardinal.styl`
5. Integrate your project files

### Updating

```git
npm update
```



## Styleguide
Use the following conventions:

### [ECSS]()
> != Under construction!

Ben Frain's [ECSS](http://ecss.io/chapter5.html) naming conventions. All components are self-contained, grouped with their `html`/`js`/`...` files.

> Be pragmatic, use as much as is appropriate

#### Example

```text
shopping-cart-template/
- shopping-cart.html
- shopping-cart.css
- shopping-cart.js
```

```stylus
// .[namespace][-ModuleOrComponent][_ChildNode][-variant]
.namespace-ModuleOrComponent_ChildNode-variant {}

// A standalone component
.sc-Title {}
.sc-RemoveBtn {}

// A component with multiple views
.mc-ShoppingCart_Title {}
.mc-ShoppingCart_RemoveBtn {}
```

### CSS declaration order
> != Under construction!

Use [css declaration order](http://codeguide.co/#css-declaration-order) by @mdo

1. Positioning
2. Box model
3. Typographic
4. Visual

```css
.declaration-order {
  /* Positioning */
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 100;

  /* Box-model */
  display: block;
  float: right;
  width: 100px;
  height: 100px;

  /* Typography */
  font: normal 13px "Helvetica Neue", sans-serif;
  line-height: 1.5;
  color: #333;
  text-align: center;

  /* Visual */
  background-color: #f5f5f5;
  border: 1px solid #e5e5e5;
  border-radius: 3px;

  /* Misc */
  opacity: 1;
}
```



## Issues

- Careful with Hashes, they fail silently if they've been used but not declared.
  - `$line.height.ratio` was used but not set up, no errors were given
