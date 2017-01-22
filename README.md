# Cardinal Stylus

## Quick intro

A slimmed down version of the [Cardinal](http://cardinalcss.com/) framework, which also imports [Jeet](http://jeet.gs/), removes most utility classes, all mixins, most components, following [ECSS principles](https://benfrain.com/my-fourth-book-enduring-css/).

Only the essentials here, folks.

## Stylus

Theres a few changes out of necessity, such as:

1. `_underscore` filenames for [globbing](http://stylus-lang.com/docs/import.html#file-globbing) hierarchy
2.  Reordering and renaming of some variables, making them easier to find
    - `base/variables/grid.styl` holds globals, margins and padding
    - `base/variables/colors.styl` holds, you guessed it, colors.
    - `base/variables/typography.styl` ... well, you get the idea.
3. `rem` is the default, no `px` fallback.
4. Barebones components and utilities
5. [Jeet](http://jeet.gs/) for grids.
6. Everything else as-is

### Hashes

We're using [hashes](http://stylus-lang.com/docs/hashes.html) for global settings:

- Access values: `$font.family.serif`
- Change values: `$font.family.serif = 'Arial'`
- You may need to escape `\` or use `unquote()` for some values
- With hashes, [source order matters](https://github.com/stylus/stylus/issues/2136), so we set some sensible `$default-` values to make them easier to override.
  - Override the hashes, **not** the `$default-`s!


## Instructions

1. Create a `main.styl` file
2. `@import `./base/_variables/*`
3. After these are imported, you can reset the variables
  - Mirror the `_variables` folder with any `$hash` overrides you like
  - [`@import` order matters](https://github.com/stylus/stylus/issues/2136)
  - Add any new hashes you might need, `$color[primary] = #92C96E`
4. `@import` the remaining files, as in `cardinal.styl`
5. Integrate your project files


## Issues

- Careful with Hashes, they fail silently if they've been used but not declared.
  - `$line.height.ratio` was used but not set up, no errors were given
