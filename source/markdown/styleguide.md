---
title: Print First CSS: Styleguide
subtitle: A brief intro to Markdown and how to write
author: @badlydrawnrob 
Marked Style: print-first-markdown
---


# [%title]
[%subtitle] • [%author]

<!--TOC-->




## CommonMark


### Headers

```text
# H1
## H2
### H3
#### H4
##### H5
###### H6

Alternatively, for H1 and H2, an underline-ish style:

Alt-H1
======

Alt-H2
------
```


### Emphasis

```text
Emphasis, aka italics, with *asterisks* or _underscores_.

Strong emphasis, aka bold, with **asterisks** or __underscores__.

Combined emphasis with **asterisks and _underscores_**.
```


### Lists

```text
1. One
2. Two
3. Three

- Lists
- Lists
- Lists
    + Can also use
    * These characters
```


### Links

```text
[Link](http://a.com)
```


### Images

```text
![Image](http://url/a.png)
```


### Blockquotes

```text
> I don't think that you have any insight whatsoever into your <mark>capacity for good</mark> ... [My notes on the original quote or 'sic' spelling mistake] until you have some well-developed <i>insight into your capacity</i> for evil. <cite>(Jordan Peterson, pg.148, my italics)</cite>
```


### Code

```text
`Inline code` with backticks
```

`Inline code` with backticks

Blocks of code are surrounded by lines of 3 backticks:

````text
```python
# code block
print('3 backticks or')
print('indent 4 spaces')
```
````


### Tables

You can optionally add pipes `|` either side of table

```text
size | material     | color
---- | ------------ | ------------
9    | leather      | brown
10   | hemp canvas  | natural
11   | glass        | transparent
```


### Horizontal rules

Use sparingly

```text
---
***
```




## HTML elements supported

It can be a little confusing when to use each specific tag, so as a rough guide:

### Highlighting importance

- `strong`: [Strong importance, seriousness or urgency](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/strong)
    - Does not change the meaning of the sentence
- `em`: Stressed, emphasis on a word or sentence
    - Changes the meaning of the sentence (Cats _are_ cute)
    - A _comparison_ can also be called _compare_
- `q`: Inline quotations ([some examples](https://academiccoachingandwriting.org/academic-writing/resources/citations))
- `blockquote`: Long-form quotations (some examples [here](https://academiccoachingandwriting.org/academic-writing/resources/citations) and [here](https://library.leeds.ac.uk/info/1402/referencing/50/leeds_harvard_style/4))
    - Should probably be [_limited_ to lines of text `> 3`](https://writingcommons.org/format/apa/675-block-quotations-apa) — and <i>do they have to be indented</i>?
    - `blockquote` > `mark`:
      - Highlight interesting parts of original text
    - `blockquote` > `i`:
        - Character thoughts, replaced/inserted text
- `cite`: [A book, research paper, essay or reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/cite)
    - To reference the source material
    - Can be used within a paragraph or a `blockquote`

### Highlighting presentation

1. `b`: [Bring attention to](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/b)
    - Presentational: indicate keywords or highlighted passages
    - <i>Don't use when: indicating stressed importance within a sentence. Use `strong` instead</i>
2. `i`: [Offset from normal text](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/i)
    - Technical details, foreign language phrases, a characters thoughts, names [possibly], places [possibly]
    - <i>Don't use when: indication stress that changes the tone of the sentence. Use `em` instead</i>
3. `mark`: [Highlighted for reference or notation](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/mark)
    - A `q` or `blockquote` to comment or reference a passage
    - In context app use (i.e. search term)
4. `s`, `del`, `ins`: [Changes in relevance, or an edited passage](http://html5doctor.com/ins-del-s/)
5. `span`: Visually change for decoration purposes with css


### Highlighting technical elements

1. `abbr`: [Abbreviation or acronym](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/abbr)
2. `kbd`: [ Denotes textual user input from a keyboard](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/kbd)
3. **Potentially useful:**
    - `samp`: [Output from computer program](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/samp)
        - Can be used with `kbd` to denote instructions
    - `details`: [Expanding item blocks](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details)
