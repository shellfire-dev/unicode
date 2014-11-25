# `unicode`: functions module for [shellfire]

This module provides a simple framework for encoding `unicode` with a [shellfire] application. An example user is the [jsonreader] module, which uses it to convert unicode code points to UTF-8 strings.

## Overview

To encode the ellipsis … code point as UTF-8 (0xE280A6), use the following code:-

```bash
# U+2026
unicode_utf8_encodeCodePoint 8230
# Or, if using hexadecimal
unicode_utf8_encodeCodePoint 0x2026
```

## Importing

To import this module, add a git submodule to your repository. From the root of your git repository in the terminal, type:-
```bash
mkdir -p lib/shellfire
cd lib/shellfire
git submodule add "https://github.com/shellfire-dev/unicode.git"
cd -
git submodule init --update
```

You may need to change the url `https://github.com/shellfire-dev/unicode.git` above if using a fork.

You will also need to add paths - include the module [paths.d].

## Namespace `unicode`

This currently exposes no functions.


## Namespace `unicode_utf8`

This namespace exposes functions to convert a code point to a UTF-8 sequence.

### To use in code

If calling from another [shellfire] module, add to your shell code the line
```bash
core_usesIn unicode utf8
```
in the global scope (ie outside of any functions). A good convention is to put it above any function that depends on functions in this module. If using it directly in a program, put this line _inside_ the `_program()` function:-

```bash
_program()
{
	core_usesIn unicode utf8
	…
}
```

### Functions

***
#### `unicode_utf8_encodeCodePoint`

|Parameter|Value|Optional|
|---------|-----|--------|
|`codePoint`|A decimal, octal (preceeded by `0`) or hexadecimal value (preceeded by `0x`).|_No_|

Writes the UTF-8 sequence of bytes for the code point to standard out. Exits with an error for an incorrect value.

***
## Namespace `unicode_utf16`

This namespace exposes functions to convert a code point to a UTF-8 sequence.

### To use in code

If calling from another [shellfire] module, add to your shell code the line
```bash
core_usesIn unicode utf8
```
in the global scope (ie outside of any functions). A good convention is to put it above any function that depends on functions in this module. If using it directly in a program, put this line _inside_ the `_program()` function:-

```bash
_program()
{
	core_usesIn unicode utf8
	…
}
```

### Functions

***
#### `unicode_utf16_encodeCodePoint`

|Parameter|Value|Optional|
|---------|-----|--------|
|`codePoint`|A decimal, octal (preceeded by `0`) or hexadecimal value (preceeded by `0x`).|_No_|

Writes the UTF-16 sequence of bytes for the code point to standard out. Exits with an error for an incorrect value. Writes correct surrogate pairs.


[swaddle]: https://github.com/raphaelcohn/swaddle "Swaddle homepage"
[shellfire]: https://github.com/shellfire-dev "shellfire homepage"
[core]: https://github.com/shellfire-dev/core "shellfire core module homepage"
[paths.d]: https://github.com/shellfire-dev/paths.d "paths.d shellfire module homepage"
[github api]: https://github.com/shellfire-dev/github "github shellfire module homepage"
[jsonwriter]: https://github.com/shellfire-dev/jsonwriter "jsonwriter shellfire module homepage"
[jsonreader]: https://github.com/shellfire-dev/jsonreader "jsonreader shellfire module homepage"
[urlencode]: https://github.com/shellfire-dev/urlencode "urlencode shellfire module homepage"
[unicode]: https://github.com/shellfire-dev/unicode "unicode shellfire module homepage"
[version]: https://github.com/shellfire-dev/version "version shellfire module homepage"
