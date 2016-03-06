# Cardinal CSS: Stylus

## Quick intro

This is a slimmed down version of the [Cardinal](http://cardinalcss.com/) framework,
 which also imports [Jeet](http://jeet.gs/). I've also removed many of the utility
 classes and components, as I'm a recent convert to [ECSS principles](https://benfrain.com/my-fourth-book-enduring-css/).

Only the essentials here, folks.

## Stylus

Theres a few changes out of necessity, such as:

1. `_underscore` filenames for [globbing](http://stylus-lang.com/docs/import.html#file-globbing) hierarchy
2.  Reordering and renaming of some variables, making them easier to find
    - `_base.styl` holds globals, margins and padding
    - `_colors.styl` holds, you guessed it, colors.
    - `_typography.styl` well, you get the idea.
3. `rem` is the default, no `px` fallback.
4. [Jeet](http://jeet.gs/) for grids.
5. Everything else as-is, minus a few components/utilities
