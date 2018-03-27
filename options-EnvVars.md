# EnvVars

```pony
primitive val EnvVars
```

## Constructors

### create

```pony
new val create()
: EnvVars val^
```

#### Returns

* [EnvVars](options-EnvVars) val^

---

## Public Functions

### apply

Turns an array of strings that look like environment variables, ie
key=value, into a map from string to string.


```pony
fun box apply(
  from: Array[String val] val)
: HashMap[String val, String val, HashEq[String val] val] val
```
#### Parameters

*   from: [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [HashMap](collections-HashMap)\[[String](builtin-String) val, [String](builtin-String) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### eq

```pony
fun box eq(
  that: EnvVars val)
: Bool val
```
#### Parameters

*   that: [EnvVars](options-EnvVars) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: EnvVars val)
: Bool val
```
#### Parameters

*   that: [EnvVars](options-EnvVars) val

#### Returns

* [Bool](builtin-Bool) val

---

