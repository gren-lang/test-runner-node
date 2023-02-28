# test-runner-node

This package allows you to execute tests and output the results to the terminal.

To define the actual tests, you'll need to use the [gren-lang/test](https://github.com/gren-lang/test) package.

## Quick start

A minimal test program will have the following in a Main.gren file:

```gren
module Main exposing (main)

import Test exposing (describe, test)
import Test.Runner.Node exposing (Program, run)

main : Program
main =
    run <|
        describe "All tests"
            [ test "Failing test" <| \_ ->
                Expect.equal True False
            ]
```
