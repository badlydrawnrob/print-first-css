# Cardinal Utilities

The `utilities/` directory houses all the helper classes included in Cardinal.

Utilities are typically used for rapid prototyping, or a last resort when needing to apply styles to an element.

# Table of Contents

- [Overview](#overview)
- [Included Utilities](#included-utilities)
  - [Visually Hidden](#visually-hidden)
- [Credits](#credits)

# Included Utilities

## Visually Hidden

[View Demo](http://codepen.io/cbracco/pen/RPaPqa)

Visually Hidden utilities allow you to manipulate the visibility of a given element.

### Usage

```
<!-- Hide only visually, but have it available for screenreaders. -->
<div class="vh">You cannot see me visually, but I am still accessible to screenreaders.</div>
<!-- Hide only visually, but have it available for screenreadersa and also focusable when navigating with the keyboard. -->
<div class="vh focusable">You cannot see me visually, but I am still accessible to screenreaders and also focusable when navigating with the keyboard.</div>
```
