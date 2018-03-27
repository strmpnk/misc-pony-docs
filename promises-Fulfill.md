# Fulfill\[A: [Any](builtin-Any) #share, B: [Any](builtin-Any) #share\]

A function from A to B that is called when a promise is fulfilled.


```pony
interface iso Fulfill[A: Any #share, B: Any #share]
```

## Public Functions

### apply

```pony
fun ref apply(
  value: A)
: B ?
```
#### Parameters

*   value: A

#### Returns

* B ?

---

