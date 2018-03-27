# ClientErrorTransitioningFSMStates

```pony
class val ClientErrorTransitioningFSMStates is
  KafkaError val
```

#### Implements

* [KafkaError](pony-kafka-KafkaError) val

---

## Constructors

### create

```pony
new val create(
  message: String val = seq,
  loc: SourceLoc val = seq)
: ClientErrorTransitioningFSMStates val^
```
#### Parameters

*   message: [String](builtin-String) val = seq
*   loc: [SourceLoc](builtin-SourceLoc) val = seq

#### Returns

* [ClientErrorTransitioningFSMStates](pony-kafka-ClientErrorTransitioningFSMStates) val^

---

## Public fields

* let details: [String](builtin-String) val

---

## Public Functions

### apply

```pony
fun box apply()
: I16 val
```

#### Returns

* [I16](builtin-I16) val

---

### string

```pony
fun box string()
: String val
```

#### Returns

* [String](builtin-String) val

---

### kafka_official

```pony
fun box kafka_official()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _retriable

```pony
fun box _retriable()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

