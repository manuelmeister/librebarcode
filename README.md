# Libre Barcode Font Project

Fonts to write barcodes.

[Manual Pages](https://graphicore.github.io/librebarcode/)

## Code 39

* Tight Code 39 ([TTF](fonts/TightCode39-Regular.ttf), [WOFF2](fonts/TightCode39-Regular.woff2))
* Libre Barcode 39 Text
* Tight Code 39 Extended ([TTF](fonts/TightCode39Extended-Regular.ttf), [WOFF2](fonts/TightCode39Extended-Regular.woff2))
* Libre Barcode 39 Extended Text

[Code 39 manual](documentation/code39.md)

## Code 128

* Libre Barcode 128
* Libre Barcode 128 Text

[Code 128 manual](https://graphicore.github.io/librebarcode/documentation/code128)

## EAN 13 (EAN 8, UPC-A, UPC-E, 2- and 5-digit Add-Ons)

* Libre Barcode EAN13 Text

[EAN 13 manual](https://graphicore.github.io/librebarcode/documentation/ean13)

## How to install and build

You'll need these installed and configured first:

* `git`
* `bash` (or compatible shell, like `zsh`)
* [`node`](https://nodejs.org/) – [`fnm`](https://github.com/Schniz/fnm/) or
  [`vp env`](https://viteplus.dev/guide/env) is recommended for Node.js
  version management; `nvm` won't respect the pinned Node.js version.
* [`uv`](https://docs.astral.sh/uv/)

```shell
# fetch the sources
path/to $ git clone https://github.com/manuelmeister/librebarcode.git
path/to $ cd librebarcode

# install and switch to the pinned Node.js version if necessary, e.g.
path/to/librebarcode $ n use
# ℹ️ fnm or vp env will do this for you

# install JavaScript dependencies
path/to/librebarcode $ npm install
path/to/librebarcode $ npx bower install

# install the pinned Python version and Python dependencies
path/to/librebarcode $ uv sync

# now build (uv run ensures the Python venv is on PATH)
path/to/librebarcode $ uv run ./app/bin/buildAll

# the fonts should be in the fonts/ directory
# the UFO sources should be in the sources/ directory
```

To produce the webfonts from the built TrueType files, run `woff2_compress`
from the [WOFF2 tools](https://github.com/google/woff2) on each `fonts/TightCode*-Regular.ttf` file.

## Licensing

The fonts are licensed under the [SIL Open Font License 1.1](OFL.txt).
Tight Code 39 and Tight Code 39 Extended are derived from the corresponding
Libre Barcode fonts by the [Libre Barcode Project Authors](AUTHORS.txt).

The barcode font generators and encoders are GPL3+.
