# JsonObject

```pony
class ref JsonObject
```

## Constructors

### create

Create a map with space for prealloc elements without triggering a
resize. Defaults to 6.


```pony
new iso create(
  prealloc: USize val = seq)
: JsonObject iso^
```
#### Parameters

*   prealloc: [USize](builtin-USize) val = seq

#### Returns

* [JsonObject](json-JsonObject) iso^

---

### from_map

Create a Json object from a map.


```pony
new ref from_map(
  data': HashMap[String val, (F64 val | I64 val | Bool val | None val | String val | JsonArray ref | JsonObject ref), HashEq[String val] val] ref)
: JsonObject ref^
```
#### Parameters

*   data': [HashMap](collections-HashMap)\[[String](builtin-String) val, ([F64](builtin-F64) val | [I64](builtin-I64) val | [Bool](builtin-Bool) val | [None](builtin-None) val | [String](builtin-String) val | [JsonArray](json-JsonArray) ref | [JsonObject](json-JsonObject) ref), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref

#### Returns

* [JsonObject](json-JsonObject) ref^

---

## Public fields

* var data: [HashMap](collections-HashMap)\[[String](builtin-String) val, ([F64](builtin-F64) val | [I64](builtin-I64) val | [Bool](builtin-Bool) val | [None](builtin-None) val | [String](builtin-String) val | [JsonArray](json-JsonArray) ref | [JsonObject](json-JsonObject) ref), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref

---

## Public Functions

### string

Generate string representation of this object.


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

## Private Functions

### _show

Append the string representation of this object to the provided String.


```pony
fun box _show(
  buf': String iso,
  indent: String val = seq,
  level: USize val,
  pretty: Bool val)
: String iso^
```
#### Parameters

*   buf': [String](builtin-String) iso
*   indent: [String](builtin-String) val = seq
*   level: [USize](builtin-USize) val
*   pretty: [Bool](builtin-Bool) val

#### Returns

* [String](builtin-String) iso^

---

