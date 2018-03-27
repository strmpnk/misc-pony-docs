# RejectAlways\[A: [Any](builtin-Any) #share\]

A reject that always raises an error.


```pony
class iso RejectAlways[A: Any #share]
```

## Constructors

### create

```pony
new iso create()
: RejectAlways[A] iso^
```

#### Returns

* [RejectAlways](promises-RejectAlways)\[A\] iso^

---

## Public Functions

### apply

```pony
fun ref apply()
: A ?
```

#### Returns

* A ?

---

