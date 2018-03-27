# FileMode

This stores a UNIX-style mode broken out into a Bool for each bit. For other
operating systems, the mapping will be approximate. For example, on Windows,
if the file is readable all the read Bools will be set, and if the file is
writeable, all the write Bools will be set.

The default mode is read/write for the owner, read-only for everyone else.


```pony
class ref FileMode
```

## Constructors

### create

```pony
new iso create()
: FileMode iso^
```

#### Returns

* [FileMode](files-FileMode) iso^

---

## Public fields

* var setuid: [Bool](builtin-Bool) val

---

* var setgid: [Bool](builtin-Bool) val

---

* var sticky: [Bool](builtin-Bool) val

---

* var owner_read: [Bool](builtin-Bool) val

---

* var owner_write: [Bool](builtin-Bool) val

---

* var owner_exec: [Bool](builtin-Bool) val

---

* var group_read: [Bool](builtin-Bool) val

---

* var group_write: [Bool](builtin-Bool) val

---

* var group_exec: [Bool](builtin-Bool) val

---

* var any_read: [Bool](builtin-Bool) val

---

* var any_write: [Bool](builtin-Bool) val

---

* var any_exec: [Bool](builtin-Bool) val

---

## Public Functions

### exec

Set the executable flag for everyone.


```pony
fun ref exec()
: None val
```

#### Returns

* [None](builtin-None) val

---

### shared

Set the write flag for everyone to the same as owner_write.


```pony
fun ref shared()
: None val
```

#### Returns

* [None](builtin-None) val

---

### group

Clear all of the any-user flags.


```pony
fun ref group()
: None val
```

#### Returns

* [None](builtin-None) val

---

### private

Clear all of the group and any-user flags.


```pony
fun ref private()
: None val
```

#### Returns

* [None](builtin-None) val

---

## Private Functions

### _os

Get the OS specific integer for a file mode. On Windows, if any read flag
is set, the path is made readable, and if any write flag is set, the path
is made writeable.


```pony
fun box _os()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

