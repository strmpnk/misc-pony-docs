# Sig

Define the portable signal numbers. Other signals can be used, but they are
not guaranteed to be portable.


```pony
primitive val Sig
```

## Constructors

### create

```pony
new val create()
: Sig val^
```

#### Returns

* [Sig](signals-Sig) val^

---

## Public Functions

### hup

```pony
fun box hup()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### int

```pony
fun box int()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### quit

```pony
fun box quit()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### ill

```pony
fun box ill()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### trap

```pony
fun box trap()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### abrt

```pony
fun box abrt()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### emt

```pony
fun box emt()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### fpe

```pony
fun box fpe()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### kill

```pony
fun box kill()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### bus

```pony
fun box bus()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### segv

```pony
fun box segv()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### sys

```pony
fun box sys()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### pipe

```pony
fun box pipe()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### alrm

```pony
fun box alrm()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### term

```pony
fun box term()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### urg

```pony
fun box urg()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### stkflt

```pony
fun box stkflt()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### stop

```pony
fun box stop()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### tstp

```pony
fun box tstp()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### cont

```pony
fun box cont()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### chld

```pony
fun box chld()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### ttin

```pony
fun box ttin()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### ttou

```pony
fun box ttou()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### io

```pony
fun box io()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### xcpu

```pony
fun box xcpu()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### xfsz

```pony
fun box xfsz()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### vtalrm

```pony
fun box vtalrm()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### prof

```pony
fun box prof()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### winch

```pony
fun box winch()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### info

```pony
fun box info()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### pwr

```pony
fun box pwr()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### usr1

```pony
fun box usr1()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### usr2

```pony
fun box usr2()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### rt

```pony
fun box rt(
  n: U32 val)
: U32 val ?
```
#### Parameters

*   n: [U32](builtin-U32) val

#### Returns

* [U32](builtin-U32) val ?

---

### eq

```pony
fun box eq(
  that: Sig val)
: Bool val
```
#### Parameters

*   that: [Sig](signals-Sig) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: Sig val)
: Bool val
```
#### Parameters

*   that: [Sig](signals-Sig) val

#### Returns

* [Bool](builtin-Bool) val

---

