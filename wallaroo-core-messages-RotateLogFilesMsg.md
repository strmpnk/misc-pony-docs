# RotateLogFilesMsg

This message is sent to a worker instructing it to rotate its log files.


```pony
primitive val RotateLogFilesMsg is
  ChannelMsg val
```

#### Implements

* [ChannelMsg](wallaroo-core-messages-ChannelMsg) val

---

## Constructors

### create

```pony
new val create()
: RotateLogFilesMsg val^
```

#### Returns

* [RotateLogFilesMsg](wallaroo-core-messages-RotateLogFilesMsg) val^

---

## Public Functions

### eq

```pony
fun box eq(
  that: RotateLogFilesMsg val)
: Bool val
```
#### Parameters

*   that: [RotateLogFilesMsg](wallaroo-core-messages-RotateLogFilesMsg) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: RotateLogFilesMsg val)
: Bool val
```
#### Parameters

*   that: [RotateLogFilesMsg](wallaroo-core-messages-RotateLogFilesMsg) val

#### Returns

* [Bool](builtin-Bool) val

---

