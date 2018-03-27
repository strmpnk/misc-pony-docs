# Options package

The Options package provides support for parsing command line arguments.

## Example program
```pony
use "wallaroo_labs/options"

actor Main
  let _env: Env
  // Some values we can set via command line options
  var _a_string: String = "default"
  var _a_number: USize = 0
  var _a_float: Float = F64(0.0)

  new create(env: Env) =>
    _env = env
    try
      arguments()
    end

    _env.out.print("The String is " + _a_string)
    _env.out.print("The Number is " + _a_number.string())
    _env.out.print("The Float is " + _a_float.string())

  fun ref arguments() ? =>
    var options = Options(_env.args)

    options
      .add("string", "t", StringArgument)
      .add("number", "i", I64Argument)
      .add("float", "c", F64Argument)

    for option in options do
      match option
      | ("string", let arg: String) => _a_string = arg
      | ("number", let arg: I64) => _a_number = arg.usize()
      | ("float", let arg: F64) => _a_float = arg
      | let err: ParseError => err.report(_env.out) ; usage() ; error
      end
    end

  fun ref usage() =>
    // this exists inside a doc-string to create the docs you are reading
    // in real code, we would use a single string literal for this but
    // docstrings are themselves string literals and you can't put a
    // string literal in a string literal. That would lead to total
    // protonic reversal. In your own code, use a string literal instead
    // of string concatenation for this.
    _env.out.print(
      "program [OPTIONS]\n" +
      "  --string      N   a string argument. Defaults to 'default'.\n" +
      "  --number      N   a number argument. Defaults to 0.\n" +
      "  --float       N   a floating point argument. Defaults to 0.0.\n"
      )
```


## Public Types

* [primitive StringArgument](wallaroo_labs-options-StringArgument.md)
* [primitive I64Argument](wallaroo_labs-options-I64Argument.md)
* [primitive F64Argument](wallaroo_labs-options-F64Argument.md)
* [primitive Required](wallaroo_labs-options-Required.md)
* [primitive Optional](wallaroo_labs-options-Optional.md)
* [primitive UnrecognisedOption](wallaroo_labs-options-UnrecognisedOption.md)
* [primitive AmbiguousMatch](wallaroo_labs-options-AmbiguousMatch.md)
* [primitive MissingArgument](wallaroo_labs-options-MissingArgument.md)
* [primitive InvalidArgument](wallaroo_labs-options-InvalidArgument.md)
* [type ArgumentType](wallaroo_labs-options-ArgumentType.md)
* [type ErrorReason](wallaroo_labs-options-ErrorReason.md)
* [type ParsedOption](wallaroo_labs-options-ParsedOption.md)
* [interface ParseError](wallaroo_labs-options-ParseError.md)
* [class Options](wallaroo_labs-options-Options.md)


## Private Types

* [class _Option](wallaroo_labs-options-_Option.md)
* [class _ErrorPrinter](wallaroo_labs-options-_ErrorPrinter.md)
