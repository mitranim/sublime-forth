## Overview

Sublime Text syntax definition for Forth. Should be suitable for any Forth which is standard-adjacent. Tested with GForth and VfxForth.

## Installation

### Package Control

1. Get [Package Control](https://packagecontrol.io).
2. Open the command palette: ⇧⌘P or ⇧^P.
3. `Package Control: Install Package`.
4. `Forth`.

### Manual

Clone the repo and symlink it to your Sublime packages directory. Example for MacOS:

```sh
git clone https://github.com/mitranim/sublime-forth.git
cd sublime-forth
ln -sf "$(pwd)" "$HOME/Library/Application Support/Sublime Text/Packages/Forth"
```

To find the packages directory on your system, use Sublime Text menu → Preferences → Browse Packages.

## Build Systems

Doesn't come with a build system, because there are many Forth implementations. Here's how to define one for GForth:

```json
{
  "selector": "source.forth",
  "cmd": ["gforth", "$file", "-e", "bye"],
}
```

## Customization

There are almost as many Forth dialects as there are Forth users. Many do not adhere to any standard. Additionally, even in a "standard" Forth, it's easy to define new parsing words, which may need special syntactic support.

Therefore, you may need to customize this syntax appropriately for your dialect.

```sh
dir="$HOME/Library/Application Support/Sublime Text/Packages/User"
mkdir -p "$dir/Forth"
touch "$dir/Forth/ForthX.sublime-syntax"
```

Open the resulting `.sublime-syntax` file and make it inherit from the "base" syntax:

```yaml
%YAML 1.2
---
version: 2
scope: source.forth
extends: Packages/Forth/Forth.sublime-syntax
file_extensions: [f, fs, ft, fth]

# ... Add your overrides here.
```

You can then override variables, contexts, and so on. You _do not need_ to copy-paste the rest of the syntax; only overrides need to be placed in the new file.

## License

https://unlicense.org
