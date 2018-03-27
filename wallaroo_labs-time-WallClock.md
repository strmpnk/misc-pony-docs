# WallClock

```pony
primitive val WallClock
```

## Constructors

### create

```pony
new val create()
: WallClock val^
```

#### Returns

* [WallClock](wallaroo_labs-time-WallClock) val^

---

## Public Functions

### nanoseconds

```pony
fun box nanoseconds()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### microseconds

```pony
fun box microseconds()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### milliseconds

```pony
fun box milliseconds()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### seconds

```pony
fun box seconds()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### eq

```pony
fun box eq(
  that: WallClock val)
: Bool val
```
#### Parameters

*   that: [WallClock](wallaroo_labs-time-WallClock) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: WallClock val)
: Bool val
```
#### Parameters

*   that: [WallClock](wallaroo_labs-time-WallClock) val

#### Returns

* [Bool](builtin-Bool) val

---

