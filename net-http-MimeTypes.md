# MimeTypes

Provide mapping from file names to MIME types.
TODO load from /etc/mime.types


```pony
primitive val MimeTypes
```

## Constructors

### create

```pony
new val create()
: MimeTypes val^
```

#### Returns

* [MimeTypes](net-http-MimeTypes) val^

---

## Public Functions

### apply

Mapping is based on the file type, following the last period in the name.


```pony
fun box apply(
  name: String val)
: String val^
```
#### Parameters

*   name: [String](builtin-String) val

#### Returns

* [String](builtin-String) val^

---

### eq

```pony
fun box eq(
  that: MimeTypes val)
: Bool val
```
#### Parameters

*   that: [MimeTypes](net-http-MimeTypes) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: MimeTypes val)
: Bool val
```
#### Parameters

*   that: [MimeTypes](net-http-MimeTypes) val

#### Returns

* [Bool](builtin-Bool) val

---

