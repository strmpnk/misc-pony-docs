# _IThen\[A: [Any](builtin-Any) #share\]

An interface representing an abstract Then. This allows for any Then that
accepts an input of type A, regardless of the output type.


```pony
interface ref _IThen[A: Any #share]
```

## Public Functions

### apply

```pony
fun ref apply(
  value: A)
: None val
```
#### Parameters

*   value: A

#### Returns

* [None](builtin-None) val

---

### reject

```pony
fun ref reject()
: None val
```

#### Returns

* [None](builtin-None) val

---

