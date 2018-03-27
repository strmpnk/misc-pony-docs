# JsonArray

```pony
class ref JsonArray
```

## Constructors

### create

Create an array with zero elements, but space for len elements.


```pony
new iso create(
  len: USize val = seq)
: JsonArray iso^
```
#### Parameters

*   len: [USize](builtin-USize) val = seq

#### Returns

* [JsonArray](json-JsonArray) iso^

---

### from_array

Create a Json array from an actual array.


```pony
new ref from_array(
  data': Array[(F64 val | I64 val | Bool val | None val | String val | JsonArray ref | JsonObject ref)] ref)
: JsonArray ref^
```
#### Parameters

*   data': [Array](builtin-Array)\[([F64](builtin-F64) val | [I64](builtin-I64) val | [Bool](builtin-Bool) val | [None](builtin-None) val | [String](builtin-String) val | [JsonArray](json-JsonArray) ref | [JsonObject](json-JsonObject) ref)\] ref

#### Returns

* [JsonArray](json-JsonArray) ref^

---

## Public fields

* var data: [Array](builtin-Array)\[([F64](builtin-F64) val | [I64](builtin-I64) val | [Bool](builtin-Bool) val | [None](builtin-None) val | [String](builtin-String) val | [JsonArray](json-JsonArray) ref | [JsonObject](json-JsonObject) ref)\] ref

---

## Public Functions

### string

Generate string representation of this array.


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

Append the string representation of this array to the provided String.


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

