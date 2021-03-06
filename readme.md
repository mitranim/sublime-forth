## Overview

Sublime Text syntax definition for Forth. Tested with GForth.

Supports the general principles of the syntax, comments, declarations. Tries to avoid unnecessary built-ins, which may vary between environments. Probably very incomplete.

## Installation

### Package Control

1. Get [Package Control](https://packagecontrol.io).
2. Open the command palette: ⇪⌘P or ⇪^P.
3. `Package Control: Install Package`.
4. `Forth`.

### Manual

Clone the repo and symlink it to your Sublime packages directory. Example for MacOS:

```sh
git clone https://github.com/mitranim/sublime-forth.git
cd sublime-forth
ln -sf "$(pwd)" "$HOME/Library/Application Support/Sublime Text 3/Packages/Forth"
```

To find the packages directory on your system, use Sublime Text menu → Preferences → Browse Packages.

## Build Systems

Doesn't come with a build system, because there are many Forth implementations. Here's how to define one for GForth:

```json
{
  "cmd": ["gforth", "$file", "-e", "bye"],
  "selector": "source.forth",
}
```

## License

https://unlicense.org

## Misc

I'm receptive to suggestions. If this package _almost_ satisfies you but needs changes, open an issue or chat me up. Contacts: https://mitranim.com/#contacts
