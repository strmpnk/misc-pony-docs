# FulfillIdentity\[A: [Any](builtin-Any) #share\]

An identity function for fulfilling promises.


```pony
class iso FulfillIdentity[A: Any #share]
```

## Constructors

### create

```pony
new iso create()
: FulfillIdentity[A] iso^
```

#### Returns

* [FulfillIdentity](promises-FulfillIdentity)\[A\] iso^

---

## Public Functions

### apply

```pony
fun ref apply(
  value: A)
: A
```
#### Parameters

*   value: A

#### Returns

* A

---

