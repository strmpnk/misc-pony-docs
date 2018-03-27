# JsonDoc

Top level JSON type containing an entire document.
A JSON document consists of exactly 1 value.


```pony
class ref JsonDoc
```

## Constructors

### create

```pony
new iso create()
: JsonDoc iso^
```

#### Returns

* [JsonDoc](json-JsonDoc) iso^

---

## Public fields

* var data: ([F64](builtin-F64) val | [I64](builtin-I64) val | [Bool](builtin-Bool) val | 
    [None](builtin-None) val | [String](builtin-String) val | [JsonArray](json-JsonArray) ref | 
    [JsonObject](json-JsonObject) ref)

---

## Public Functions

### string

Generate string representation of this document.


```pony
fun box string(
  indent: String val = seq,
  pretty_print: Bool val = seq)
: String val
```
#### Parameters

*   indent: [String](builtin-String) val = seq
*   pretty_print: [Bool](builtin-Bool) val = seq

#### Returns

* [String](builtin-String) val

---

### parse

Parse the given string as a JSON file, building a document.
Raise error on invalid JSON in given source.


```pony
fun ref parse(
  source: String val)
: None val ?
```
#### Parameters

*   source: [String](builtin-String) val

#### Returns

* [None](builtin-None) val ?

---

### parse_report

Give details of the error that occurred last time we attempted to parse.
If parse was successful returns (0, "").


```pony
fun box parse_report()
: (USize val , String val)
```

#### Returns

* ([USize](builtin-USize) val , [String](builtin-String) val)

---

## Private Functions

### _parse_value

Parse a single JSON value of any type, which MUST be present.
Raise error on invalid or missing value.


```pony
fun ref _parse_value(
  context: String val)
: (F64 val | I64 val | Bool val | 
    None val | String val | JsonArray ref | 
    JsonObject ref) ?
```
#### Parameters

*   context: [String](builtin-String) val

#### Returns

* ([F64](builtin-F64) val | [I64](builtin-I64) val | [Bool](builtin-Bool) val | 
    [None](builtin-None) val | [String](builtin-String) val | [JsonArray](json-JsonArray) ref | 
    [JsonObject](json-JsonObject) ref) ?

---

### _parse_keyword

Parse a keyword, the first letter of which has already been peeked.


```pony
fun ref _parse_keyword()
: (Bool val | None val) ?
```

#### Returns

* ([Bool](builtin-Bool) val | [None](builtin-None) val) ?

---

### _parse_number

Parse a number, the leading character of which has already been peeked.


```pony
fun ref _parse_number()
: (F64 val | I64 val) ?
```

#### Returns

* ([F64](builtin-F64) val | [I64](builtin-I64) val) ?

---

### _parse_decimal

Parse a decimal integer which must appear immediately in the source.


```pony
fun ref _parse_decimal()
: (I64 val , U8 val) ?
```

#### Returns

* ([I64](builtin-I64) val , [U8](builtin-U8) val) ?

---

### _parse_object

Parse a JSON object, the leading { of which has already been peeked.


```pony
fun ref _parse_object()
: JsonObject ref ?
```

#### Returns

* [JsonObject](json-JsonObject) ref ?

---

### _parse_array

Parse an array, the leading [ of which has already been peeked.


```pony
fun ref _parse_array()
: JsonArray ref ?
```

#### Returns

* [JsonArray](json-JsonArray) ref ?

---

### _parse_string

Parse a string, which must be the next thing found, other than whitesapce.


```pony
fun ref _parse_string(
  context: String val)
: String val ?
```
#### Parameters

*   context: [String](builtin-String) val

#### Returns

* [String](builtin-String) val ?

---

### _parse_escape

Process a string escape sequence, the leading \ of which has already been
consumed.


```pony
fun ref _parse_escape()
: String val ?
```

#### Returns

* [String](builtin-String) val ?

---

### _parse_unicode_escape

Process a Unicode escape sequence, the leading \u of which has already been
consumed.


```pony
fun ref _parse_unicode_escape()
: String val ?
```

#### Returns

* [String](builtin-String) val ?

---

### _parse_unicode_digits

Parse the hex digits of a Unicode escape sequence, the leading \u of which
has already been consumed, and return the encoded character value.


```pony
fun ref _parse_unicode_digits()
: U32 val ?
```

#### Returns

* [U32](builtin-U32) val ?

---

### _dump_whitespace

Dump all whitespace at the current read location in source, if any.


```pony
fun ref _dump_whitespace()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _peek_char

Peek the next char in the source, without consuming it.
If an eof_context is given then an error is thrown on eof, setting a
suitable message.
If eof_context is None then 0 is returned on EOF. It up to the caller to
handle this appropriately.


```pony
fun ref _peek_char(
  eof_context: (String val | None val) = seq)
: U8 val ?
```
#### Parameters

*   eof_context: ([String](builtin-String) val | [None](builtin-None) val) = seq

#### Returns

* [U8](builtin-U8) val ?

---

### _get_char

Get and consume the next char in the source.
If an eof_context is given then an error is thrown on eof, setting a
suitable message.
If eof_context is None then 0 is returned on EOF. It up to the caller to
handle this appropriately.


```pony
fun ref _get_char(
  eof_context: (String val | None val) = seq)
: U8 val ?
```
#### Parameters

*   eof_context: ([String](builtin-String) val | [None](builtin-None) val) = seq

#### Returns

* [U8](builtin-U8) val ?

---

### _last_char

Get the last character peeked or got from the source as a String.
For use generating error messages.


```pony
fun ref _last_char()
: String val
```

#### Returns

* [String](builtin-String) val

---

### _error

Record an error with the given message.


```pony
fun ref _error(
  msg: String val)
: None val
```
#### Parameters

*   msg: [String](builtin-String) val

#### Returns

* [None](builtin-None) val

---

