# StepSeqIdGenerator

Generate a new sequence id based on what has happened so far in the step.

**`new_incoming_message` must be called at the start of handling each
incoming message**

`new_id` always generates the next id in the sequence.

`latest_for_run` will generate a new id if we haven't yet generated one when
handling the current message (as denoted by calling `new_incoming_message`).
If we have already generated a message, then `latest_for_run` will return the
most recently generated sequence id.


```pony
class ref StepSeqIdGenerator
```

## Constructors

### create

```pony
new ref create(
  initial_seq_id: U64 val = seq)
: StepSeqIdGenerator ref^
```
#### Parameters

*   initial_seq_id: [U64](builtin-U64) val = seq

#### Returns

* [StepSeqIdGenerator](wallaroo-core-topology-StepSeqIdGenerator) ref^

---

## Public Functions

### latest_for_run

Gets the most recent id for a given step run.

If no id, has been generated yet, then we want to generate a
new one, otherwise, use the most recent for this run.


```pony
fun ref latest_for_run()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### new_id

Generate a new id


```pony
fun ref new_id()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### new_incoming_message

Needs to be called at the beginning of a run on a step to set up correct
`latest_for_run` usage.


```pony
fun ref new_incoming_message()
: None val
```

#### Returns

* [None](builtin-None) val

---

### last_id

```pony
fun box last_id()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

