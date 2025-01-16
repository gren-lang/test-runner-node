# Gren Node Test Runner

This package allows you to execute tests and output the results to the terminal.

See [`gren-lang/test-runner-browser`](https://packages.gren-lang.org/package/gren-lang/test-runner-browser/version/latest/overview) if you want to run your tests in the browser.

To define the actual tests, you'll need to use the [gren-lang/test](https://github.com/gren-lang/test) package.

## Quick start

Initialize a gren program targeting node:

```sh
mkdir tests
cd tests
gren init --platform=node
```

Install the necessary packages:

```sh
gren package install gren-lang/test
gren package install gren-lang/test-runner-node
```

Create a `src/Main.gren` with your tests:

```elm
module Main exposing (main)

import Expect
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

Compile and run:

```
gren make src/Main.gren
node app
```

If you have any questions, please [reach out](https://gren-lang.org/community)!
