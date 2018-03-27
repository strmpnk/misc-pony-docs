# URL

Holds the components of a URL. These are always stored as valid, URL-encoded
values.


```pony
class val URL
```

## Constructors

### create

```pony
new val create()
: URL val^
```

#### Returns

* [URL](net-http-URL) val^

---

### build

```pony
new val build(
  from: String val,
  percent_encoded: Bool val = seq)
: URL val^ ?
```
#### Parameters

*   from: [String](builtin-String) val
*   percent_encoded: [Bool](builtin-Bool) val = seq

#### Returns

* [URL](net-http-URL) val^ ?

---

### valid

```pony
new val valid(
  from: String val)
: URL val^ ?
```
#### Parameters

*   from: [String](builtin-String) val

#### Returns

* [URL](net-http-URL) val^ ?

---

## Public fields

* var scheme: [String](builtin-String) val

---

* var user: [String](builtin-String) val

---

* var password: [String](builtin-String) val

---

* var host: [String](builtin-String) val

---

* var port: [U16](builtin-U16) val

---

* var path: [String](builtin-String) val

---

* var query: [String](builtin-String) val

---

* var fragment: [String](builtin-String) val

---

## Public Functions

### is_valid

Return true if all elements are correctly URL encoded.


```pony
fun box is_valid()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### string

Combine the components into a string.


```pony
fun box string()
: String iso^
```

#### Returns

* [String](builtin-String) iso^

---

### join

Using this as a base URL, concatenate with another, possibly relative, URL
in the same way a browser does for a link.


```pony
fun val join(
  that: URL val)
: URL val
```
#### Parameters

*   that: [URL](net-http-URL) val

#### Returns

* [URL](net-http-URL) val

---

### default_port

Report the default port for our scheme.
Returns 0 for unrecognised schemes.


```pony
fun box default_port()
: U16 val
```

#### Returns

* [U16](builtin-U16) val

---

## Private Functions

### _parse

Parse the given string as a URL.
Raises an error on invalid port number.


```pony
fun ref _parse(
  from: String val)
: None val ?
```
#### Parameters

*   from: [String](builtin-String) val

#### Returns

* [None](builtin-None) val ?

---

### _parse_scheme

Find the scheme, if any, at the start of the given string.
The offset of the part following the scheme is returned.


```pony
fun box _parse_scheme(
  from: String val)
: (ISize val , String val)
```
#### Parameters

*   from: [String](builtin-String) val

#### Returns

* ([ISize](builtin-ISize) val , [String](builtin-String) val)

---

### _parse_part

Attempt to parse the specified part out of the given string. Only attempt
the parse if the given prefix is found first. Pass "" if no prefix is
needed. The part ends when any one of the given terminator characters is
found, or the end of the input is reached. The offset of the terminator is
returned, if one is found.


```pony
fun box _parse_part(
  from: String val,
  prefix: String val,
  terminators: String val,
  offset: ISize val)
: (ISize val , String val)
```
#### Parameters

*   from: [String](builtin-String) val
*   prefix: [String](builtin-String) val
*   terminators: [String](builtin-String) val
*   offset: [ISize](builtin-ISize) val

#### Returns

* ([ISize](builtin-ISize) val , [String](builtin-String) val)

---

### _split

Split the given string in 2 around the first instance of the specified
separator. If the string does not contain the separator then the first
resulting string is the whole src and the second is empty.


```pony
fun box _split(
  src: String val,
  separator: U8 val)
: (String val , String val)
```
#### Parameters

*   src: [String](builtin-String) val
*   separator: [U8](builtin-U8) val

#### Returns

* ([String](builtin-String) val , [String](builtin-String) val)

---

### _parse_hostport

Split the given "host and port" string into the host and port parts.


```pony
fun box _parse_hostport(
  hostport: String val)
: (String val , String val)
```
#### Parameters

*   hostport: [String](builtin-String) val

#### Returns

* ([String](builtin-String) val , [String](builtin-String) val)

---

