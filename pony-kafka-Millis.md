# Millis

```pony
primitive val Millis
```

## Constructors

### create

```pony
new val create()
: Millis val^
```

#### Returns

* [Millis](pony-kafka-Millis) val^

---

## Public Functions

### from_wall_clock

```pony
fun box from_wall_clock(
  wall: (I64 val , I64 val))
: U64 val
```
#### Parameters

*   wall: ([I64](builtin-I64) val , [I64](builtin-I64) val)

#### Returns

* [U64](builtin-U64) val

---

### eq

```pony
fun box eq(
  that: Millis val)
: Bool val
```
#### Parameters

*   that: [Millis](pony-kafka-Millis) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: Millis val)
: Bool val
```
#### Parameters

*   that: [Millis](pony-kafka-Millis) val

#### Returns

* [Bool](builtin-Bool) val

---

