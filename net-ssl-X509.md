# X509

```pony
primitive val X509
```

## Constructors

### create

```pony
new val create()
: X509 val^
```

#### Returns

* [X509](net-ssl-X509) val^

---

## Public Functions

### valid_for_host

Checks if an OpenSSL X509 certificate is valid for a given host.


```pony
fun box valid_for_host(
  cert: Pointer[X509 val] ref,
  host: String val)
: Bool val
```
#### Parameters

*   cert: [Pointer](builtin-Pointer)\[[X509](net-ssl-X509) val\] ref
*   host: [String](builtin-String) val

#### Returns

* [Bool](builtin-Bool) val

---

### common_name

Get the common name for the certificate. Raises an error if the common name
contains any NULL bytes.


```pony
fun box common_name(
  cert: Pointer[X509 val] ref)
: String val ?
```
#### Parameters

*   cert: [Pointer](builtin-Pointer)\[[X509](net-ssl-X509) val\] ref

#### Returns

* [String](builtin-String) val ?

---

### all_names

Returns an array of all names for the certificate. Any names containing
NULL bytes are not included. This includes the common name and all subject
alternate names.


```pony
fun box all_names(
  cert: Pointer[X509 val] ref)
: Array[String val] val
```
#### Parameters

*   cert: [Pointer](builtin-Pointer)\[[X509](net-ssl-X509) val\] ref

#### Returns

* [Array](builtin-Array)\[[String](builtin-String) val\] val

---

### eq

```pony
fun box eq(
  that: X509 val)
: Bool val
```
#### Parameters

*   that: [X509](net-ssl-X509) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: X509 val)
: Bool val
```
#### Parameters

*   that: [X509](net-ssl-X509) val

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _match_name

Returns true if the name extracted from the certificate is valid for the
given host.


```pony
fun box _match_name(
  host: String val,
  name: String val)
: Bool val
```
#### Parameters

*   host: [String](builtin-String) val
*   name: [String](builtin-String) val

#### Returns

* [Bool](builtin-Bool) val

---

