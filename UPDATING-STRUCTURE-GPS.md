Simplifying the folder structure
--------------------------------

> Remember, CSS sucks and you want to do it as little as possible.
> Keep things simple, no more complex than an e-reader UI.
> `variables/`, `base/` or `vars/`, `html/` (or `partials/`?)
> This is a "no fluff" print-first system ... we only need a simple `specimen` file.
> `ds/` (design-system), `.gl-`obal and `#page` is out of scope!


## Folders

- **We definitely need a `variables/` folder**
- I don't think `modules` is the right name
    - In programming, they're basically files with functions
    - I NEVER use functions in css anymore.
- `partials/` is the right idea, but don't think it needs to be called this
    - `global/` or `base/`? I don't like them either.
- **GPS folders** for `.gl-` files
- `page/` for `#page` and `#section`
    - Does it live with it's page template?

Could be `variables/`, `raw/` (or `html/`), `globals/`, and `page/` or `pages/`



## Files

- `main.less` and `config.less` are quite handy.
    - Do I just need one master file for both of these?
- perhaps have a `user-config.less` file?
    - Or get them to copy it and add to `.gitignore`?
- `_root.less` is twice, so perhaps we condense this file
    - Include the variables AND the base styles?


## Questions

1. Can I get rid of normalise now? A different one?
2. Make some rules about what styles live in a [specimen](https://typespecimens.xyz/) (raw html)
3. Make some rules about _slightly_ different `.gl-` elements
4. Look over the GPS doc and make some basic rules.
5. There's a lot of nuance, so it'll likely take a while
