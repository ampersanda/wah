# wah

[![CircleCI](https://circleci.com/gh/ampersanda/wah/tree/master.svg?style=svg)](https://circleci.com/gh/ampersanda/wah/tree/master) [![Clojars Project](https://img.shields.io/clojars/v/wah.svg)](https://clojars.org/wah)

Shortcuts for wasm

| wah       | wasm                                      |
|---------------|-------------------------------------------|
| `(0 = 1)`     | `(set_local 0 (i32.const 1))`             |
| `(%$a + %$b)` | `(f64.add (get_local $a) (get_local $b))` |
| `(0 + 1)` | `(i32.add (i32.const 0) (i32.const 1))` |
| `(0.0 + 1.0)` | `(f64.add (f64.const 0) (f64.const 1))` |

* Adds infix operators: `*, +, -, /, ==, >, <, >=, <=`
* Supports (0 = 1) shortcut for `set_local`
* Supports bare numbers that become f64.const if they have a decimal point, and
  i32.const if they don't.
* Supports type inference by walking up the tree, paying attention to param
  and local types.

## [Introduction](doc/intro.md)

## [Flow](doc/flow.txt)

## [Rationale](doc/rationale.md)

## [Planning](doc/planning.md)

## Contributing & open source

This is a PR-only repository: there's no issue tracker.

* To report a bug, open a PR with a failing testcase
* To propose a feature, open a PR with a failing testcase or an initial implementation

I'll be overjoyed to review & merge PRs!

## Make executable file

1. Install Clojure CLI (https://clojure.org/guides/getting_started)
2. Install GraalVM (https://www.graalvm.org/downloads/)
3. Set `$GRAALVM_HOME` environment variables pointed to graalvm folder (not graalvm `bin` folder) or `export GRAALVM_HOME=path_to_graalvm_folder`
4. Install `native-image` using `gu` or `$GRAALVM_HOME/bin/gu native-image`
5. Generate executable by executing `clj -A:native-image`

## License

Copyright © 2017 Tom MacWright

Distributed under the Eclipse Public License either version 1.0 or (at
your option) any later version.
