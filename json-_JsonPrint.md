# _JsonPrint

```pony
primitive val _JsonPrint
```

## Constructors

### create

```pony
new val create()
: _JsonPrint val^
```

#### Returns

* [_JsonPrint](json-_JsonPrint) val^

---

## Public Functions

### eq

```pony
fun box eq(
  that: _JsonPrint val)
: Bool val
```
#### Parameters

*   that: [_JsonPrint](json-_JsonPrint) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _JsonPrint val)
: Bool val
```
#### Parameters

*   that: [_JsonPrint](json-_JsonPrint) val

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _indent

Add indentation to the buf to the appropriate indent_level


```pony
fun box _indent(
  buf: String iso,
  indent: String val,
  level': USize val)
: String iso^
```
#### Parameters

*   buf: [String](builtin-String) iso
*   indent: [String](builtin-String) val
*   level': [USize](builtin-USize) val

#### Returns

* [String](builtin-String) iso^

---

### _string

Generate string representation of the given data.


```pony
fun box _string(
  d: (F64 val | I64 val | Bool val | 
    None val | String val | JsonArray box | 
    JsonObject box),
  buf': String iso,
  indent: String val,
  level: USize val,
  pretty: Bool val)
: String iso^
```
#### Parameters

*   d: ([F64](builtin-F64) val | [I64](builtin-I64) val | [Bool](builtin-Bool) val | 
    [None](builtin-None) val | [String](builtin-String) val | [JsonArray](json-JsonArray) box | 
    [JsonObject](json-JsonObject) box)
*   buf': [String](builtin-String) iso
*   indent: [String](builtin-String) val
*   level: [USize](builtin-USize) val
*   pretty: [Bool](builtin-Bool) val

#### Returns

* [String](builtin-String) iso^

---

### _escaped_string

Generate a version of the given string with escapes for all non-printable
and non-ASCII characters.


```pony
fun box _escaped_string(
  buf: String iso,
  s: String val)
: String iso^
```
#### Parameters

*   buf: [String](builtin-String) iso
*   s: [String](builtin-String) val

#### Returns

* [String](builtin-String) iso^

---

