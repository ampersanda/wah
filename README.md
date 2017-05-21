# wah

[![CircleCI](https://circleci.com/gh/tmcw/wah.svg?style=shield)](https://circleci.com/gh/tmcw/wah)

Shortcuts for wasm

| wah       | wasm                                      |
|---------------|-------------------------------------------|
| `(0 = 1)`     | `(set_local 0 (f64.const 0))`             |
| `(%$a + %$b)` | `(f64.add (get_local $a) (get_local $b))` |
| `(0 + 1)` | `(i32.add (i32.const 0) (i32.const 1))` |
| `(0.0 + 1.0)` | `(f64.add (f64.const 0) (f64.const 1))` |

* Adds infix operators: `*, +, -, /, ==, >, <, >=, <=`
* Supports (0 = 1) shortcut for `set_local`
* Supports bare numbers that become f64.const if they have a decimal point, and
  i32.const if they don't.
* Supports type inference by walking up the tree, paying attention to param
  and local types.

## Installation


## Usage

FIXME: explanation

    $ java -jar wah-0.1.0-standalone.jar [args]

## Options

## Examples

...

## Open Questions

* The next big step is _arrays_ and dealing with data. Will we want to introduce
  new syntax sugar for that too?
* Right now it only supports floats, indicated by a decimal point, and ints,
  indicated by not. How could we make it simple to use all number types, so both
  f64 and f32?
* Since source and output is 1:1, can / should we support compilation from
  WAST to WAH too?

## License

Copyright © 2017 Tom MacWright

Distributed under the Eclipse Public License either version 1.0 or (at
your option) any later version.
