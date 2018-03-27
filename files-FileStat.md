# FileStat

```pony
primitive val FileStat
```

## Constructors

### create

```pony
new val create()
: FileStat val^
```

#### Returns

* [FileStat](files-FileStat) val^

---

## Public Functions

### value

```pony
fun box value()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### eq

```pony
fun box eq(
  that: FileStat val)
: Bool val
```
#### Parameters

*   that: [FileStat](files-FileStat) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: FileStat val)
: Bool val
```
#### Parameters

*   that: [FileStat](files-FileStat) val

#### Returns

* [Bool](builtin-Bool) val

---

