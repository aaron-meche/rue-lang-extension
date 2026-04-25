# Rue Language for VS Code

Syntax highlighting for `.rue` files.

Rue is a small stylesheet language for writing CSS with nested selectors, shared variables, inline nested styles, and JavaScript-powered helper functions.

## Features

- Syntax highlighting for `.rue` files
- Highlights nested selector blocks
- Highlights `def` and `_name_` variable declarations
- Highlights Rue variable calls like `_accent_`
- Highlights JavaScript helper functions inside Rue files
- Highlights CSS properties, values, comments, and selectors

## Rue Example

```rue
_accent-hue_: 175

func getAccent(sat, light) {
    return "hsl(" + _accent-hue_ + ", " + sat + "%, " + light + "%)"
}

def accent: getAccent(75, 50)
_surface_: getAccent(10, 12)

.card{
    background: _surface_
    color: white
    border: 1px solid _accent_

    .title{
        color: _accent_
        font-weight: 800
    }
}

.actions { display: flex; gap: .75rem; a { color: _accent_; } }
```

## About Rue Variables

Rue treats these two declarations as equivalent:

```rue
def accent: royalblue
_accent_: royalblue
```

Both create a Rue variable that can be referenced with `_accent_`, and both emit a CSS custom property in the compiled output.

## File Extension

Use the `.rue` extension:

```text
styles.rue
```

## Recommended Usage

Install this extension alongside the Rue npm package:

```bash
npm install rue-lang
```

Then compile Rue files with your app, build tool, or the included Rue compiler.

## Links

- npm: `rue-lang`
- Repository: `https://github.com/aaron-meche/rue-lang-compiler`

## Author

Created by Aaron Meche.