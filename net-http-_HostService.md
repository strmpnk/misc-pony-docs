# _HostService

```pony
class val _HostService is
  Hashable ref,
  Equatable[_HostService val] ref
```

#### Implements

* [Hashable](collections-Hashable) ref
* [Equatable](builtin-Equatable)\[[_HostService](net-http-_HostService) val\] ref

---

## Constructors

### create

```pony
new val create(
  scheme': String val,
  host': String val,
  service': String val)
: _HostService val^
```
#### Parameters

*   scheme': [String](builtin-String) val
*   host': [String](builtin-String) val
*   service': [String](builtin-String) val

#### Returns

* [_HostService](net-http-_HostService) val^

---

## Public fields

* let scheme: [String](builtin-String) val

---

* let host: [String](builtin-String) val

---

* let service: [String](builtin-String) val

---

## Public Functions

### hash

```pony
fun box hash()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### eq

```pony
fun box eq(
  that: _HostService box)
: Bool val
```
#### Parameters

*   that: [_HostService](net-http-_HostService) box

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _HostService val)
: Bool val
```
#### Parameters

*   that: [_HostService](net-http-_HostService) val

#### Returns

* [Bool](builtin-Bool) val

---

