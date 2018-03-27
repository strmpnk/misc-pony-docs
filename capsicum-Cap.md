# Cap

The Capsicum rights.


```pony
primitive val Cap
```

## Constructors

### create

```pony
new val create()
: Cap val^
```

#### Returns

* [Cap](capsicum-Cap) val^

---

## Public Functions

### enter

This places the current process into capability mode, a mode of execution
in which processes may only issue system calls operating on file
descriptors or reading limited global system state. Access to global name
spaces, such as file system or IPC name spaces, is prevented.


```pony
fun box enter()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### read

```pony
fun box read()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### write

```pony
fun box write()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### seek_tell

```pony
fun box seek_tell()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### seek

```pony
fun box seek()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### pread

```pony
fun box pread()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### pwrite

```pony
fun box pwrite()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### mmap

```pony
fun box mmap()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### mmap_r

```pony
fun box mmap_r()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### mmap_w

```pony
fun box mmap_w()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### mmap_x

```pony
fun box mmap_x()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### mmap_rw

```pony
fun box mmap_rw()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### mmap_rx

```pony
fun box mmap_rx()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### mmap_wx

```pony
fun box mmap_wx()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### mmap_rwx

```pony
fun box mmap_rwx()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### creat

```pony
fun box creat()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### fexecve

```pony
fun box fexecve()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### fsync

```pony
fun box fsync()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### ftruncate

```pony
fun box ftruncate()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### lookup

```pony
fun box lookup()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### fchdir

```pony
fun box fchdir()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### fchflags

```pony
fun box fchflags()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### chflagsat

```pony
fun box chflagsat()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### fchmod

```pony
fun box fchmod()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### fchmodat

```pony
fun box fchmodat()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### fchown

```pony
fun box fchown()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### fchownat

```pony
fun box fchownat()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### fcntl

```pony
fun box fcntl()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### flock

```pony
fun box flock()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### fpathconf

```pony
fun box fpathconf()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### fsck

```pony
fun box fsck()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### fstat

```pony
fun box fstat()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### fstatat

```pony
fun box fstatat()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### fstatfs

```pony
fun box fstatfs()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### futimes

```pony
fun box futimes()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### futimesat

```pony
fun box futimesat()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### linkat

```pony
fun box linkat()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### mkdirat

```pony
fun box mkdirat()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### mkfifoat

```pony
fun box mkfifoat()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### mknodat

```pony
fun box mknodat()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### renameat

```pony
fun box renameat()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### symlinkat

```pony
fun box symlinkat()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### unlinkat

```pony
fun box unlinkat()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### accept

```pony
fun box accept()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### bind

```pony
fun box bind()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### connect

```pony
fun box connect()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### getpeername

```pony
fun box getpeername()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### getsockname

```pony
fun box getsockname()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### getsockopt

```pony
fun box getsockopt()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### listen

```pony
fun box listen()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### peeloff

```pony
fun box peeloff()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### recv

```pony
fun box recv()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### send

```pony
fun box send()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### setsockopt

```pony
fun box setsockopt()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### shutdown

```pony
fun box shutdown()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### bindat

```pony
fun box bindat()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### connectat

```pony
fun box connectat()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### sock_client

```pony
fun box sock_client()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### sock_server

```pony
fun box sock_server()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### mac_get

```pony
fun box mac_get()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### mac_set

```pony
fun box mac_set()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### sem_getvalue

```pony
fun box sem_getvalue()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### sem_post

```pony
fun box sem_post()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### sem_wait

```pony
fun box sem_wait()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### event

```pony
fun box event()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### kqueue_event

```pony
fun box kqueue_event()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### ioctl

```pony
fun box ioctl()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### ttyhook

```pony
fun box ttyhook()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### pdgetpid

```pony
fun box pdgetpid()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### pdwait

```pony
fun box pdwait()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### pdkill

```pony
fun box pdkill()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### exattr_delete

```pony
fun box exattr_delete()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### exattr_get

```pony
fun box exattr_get()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### exattr_list

```pony
fun box exattr_list()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### exattr_set

```pony
fun box exattr_set()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### acl_check

```pony
fun box acl_check()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### acl_delete

```pony
fun box acl_delete()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### acl_get

```pony
fun box acl_get()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### acl_set

```pony
fun box acl_set()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### kqueue_change

```pony
fun box kqueue_change()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### kqueue

```pony
fun box kqueue()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### eq

```pony
fun box eq(
  that: Cap val)
: Bool val
```
#### Parameters

*   that: [Cap](capsicum-Cap) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: Cap val)
: Bool val
```
#### Parameters

*   that: [Cap](capsicum-Cap) val

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _id

Build a Capsicum ID from an index and a bit position.


```pony
fun box _id(
  idx: U64 val,
  bit: U64 val)
: U64 val
```
#### Parameters

*   idx: [U64](builtin-U64) val
*   bit: [U64](builtin-U64) val

#### Returns

* [U64](builtin-U64) val

---

