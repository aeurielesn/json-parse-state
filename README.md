json-parse-state
================

The `json_parse_state.js` implement a JSON parse method in JavaScript that uses a state machine.

In contrast [from the original work] from [Douglas Crockford], it has a couple of modifications:

  [Douglas Crockford]: https://github.com/douglascrockford/JSON-js

* It will not throw an exception if it found a valid JSON but it is not the end of the string.
* It accepts double-escaped strings as identifiers and values.

You can use this script to parse a JSON string that you do not know where it ends.

Example
-------

### Conventional

    json_parse('{"foo": "bar"}').foo
    Result: bar

### Double escaped

    json_parse(x = '\{\\"tag\\":\\"\\u003cspan style=\'color:red;\'>\\u003c\\\\\\/span>\\"\}').tag
    Result: <span style='color:red;'></span>

### Ignore

    json_parse('{\"foo\": \"bar\"} this will be ignored').foo
    Result: bar
