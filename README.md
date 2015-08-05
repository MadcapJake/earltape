Earltape
--------

Run [tape](https://github.com/substack/tape) tests written in [Earl Grey](https://breuleux.github.io/earl-grey/)!

To install: `npm install -g earltape`

The command works exactly the same as the regular `tape` runner, just do `earltape test/*.eg` to run your tests. You can pipe `earltape` into any standard tap reporter as you would expect.

To write your tests, `require('tape')` and use it exactly like you would if you were writing your tests in javascript. You won't get the same API if you require `earltape` as the index file contains macros.

### Macros

Instead of requiring `tape`, you can use the `test` macro:

```earl-grey
require-macro: earltape -> test

test "timing test":
  @plan(2)
  @equal(typeof(Date.now), 'function')
  start = Date.now()

  setTimeout(cb, 100) where cb = ->
    @equal(Date.now() - start, 100)
```


Many thanks to [hflw](https://github.com/hflw) for [Coffeetape](https://github.com/hflw/coffeetape).
