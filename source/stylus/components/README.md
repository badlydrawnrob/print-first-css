# Cardinal Components

Components are the discrete, custom UI elements that consist of specific semantics and styling, and make up the bulk of a UI.

# Table of Contents

- [Overview](#overview)
- [Included Components](#included-components)

# Overview

Cardinal Components each represent a single part of a UI, and should never try to do too much. Components are designed to stand on their own, and be extremely portable and reusable.

They should also be encapsulated as much as possible, to prevent styles from leaking outside of the component. This isolation prevents unnecessary complexity and [side effects](http://cbrac.co/1KFudtE), and results in higher code reuse.

# Included Components

## Buttons

[View Demo](http://codepen.io/cbracco/pen/oXxXGr)

The [Button Component](https://github.com/cbracco/cardinal/blob/master/components/buttons.less) is a clickable item that usually causes a change in state or performs an action of some sort. There are several different modifiers available for changing sizes, colors, styles, and more.
