---
title:  "Code 39"
---

# {{ page.title }}

Available font variants:

  * **Tight Code 39** is without text below.
  * **Libre Barcode 39 Text** has text below.
  * **Tight Code 39 Extended** supports additional characters, and is without text below.
  * **Libre Barcode 39 Extended Text** supports additional characters, and has text below.

To use these wrap the text to encode into `*` asterisks, enter `*HELLO WORLD*`:

Result:

<span class="code39Text">\*HELLO WORLD\*</span>

## Tight Code 39 fonts

The bars fill the font's em vertically. Each barcode starts at the left edge
and ends at the last bar when OpenType contextual alternates (`calt`) are
enabled. Use one asterisk-delimited barcode per text run with zero letter
spacing. Preserve spaces in the encoded text.

```css
@font-face {
    font-family: "Tight Code 39";
    src: url("/fonts/TightCode39-Regular.woff2") format("woff2");
}

.barcode {
    display: inline-block;
    font: 64px/1 "Tight Code 39";
    font-feature-settings: "calt" 1;
    letter-spacing: 0;
    white-space: pre;
}
```

For scanning, leave a blank quiet zone of at least ten narrow modules
(`0.3em` at the default module width) on each side in the surrounding layout.

## Plain Variants:

Supports the input characters: "$ / + % 0–9 A–Z - ."  and " "(space)

## Extended Variants:

Supports full ASCII as input characters.

From [Full ASCII Code 39](https://en.wikipedia.org/wiki/Code_39):

> Code 39 is restricted to 43 characters. In Full ASCII Code 39 Symbols
0-9, A-Z, ".", "-" and space are the same as their representations in
Code 39. Lower case letters, additional punctuation characters and control
characters are represented by sequences of two characters of Code 39.

This means, internally in the font e.g. an "a" is encoded as "+A" or
an "@" as "%V". There's a table in the linked Wikipedia article.

Thus, **be aware**, some scanners will interpret "extended Code 39" as
just plain Code 39 and decode e.g. "Hello" as "H+E+L+L+O".

See the [Wikipedia Code 39 page](https://en.wikipedia.org/wiki/Code_39) for more info.

