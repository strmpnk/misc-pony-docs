# NetAddress

Represents an IPv4 or IPv6 address. The family field indicates the address
type. The addr field is either the IPv4 address or the IPv6 flow info. The
addr1-4 fields are the IPv6 address, or invalid for an IPv4 address. The
scope field is the IPv6 scope, or invalid for an IPv4 address.

This class is modelled after the C data structure for holding socket
addresses for both IPv4 and IPv6 `sockaddr_storage`.

The public fields of this class model exactly the fields of `sockaddr_in`
and are in network byte order. Use the `name` method
to obtain address/hostname and port/service as Strings.


```pony
class val NetAddress is
  Equatable[NetAddress val] ref
```

#### Implements

* [Equatable](builtin-Equatable)\[[NetAddress](net-NetAddress) val\] ref

---

## Constructors

### create

```pony
new iso create()
: NetAddress iso^
```

#### Returns

* [NetAddress](net-NetAddress) iso^

---

## Public fields

* let length: [U8](builtin-U8) val

---

* let family: [U8](builtin-U8) val

---

* let port: [U16](builtin-U16) val

---

* let addr: [U32](builtin-U32) val

---

* let addr1: [U32](builtin-U32) val

---

* let addr2: [U32](builtin-U32) val

---

* let addr3: [U32](builtin-U32) val

---

* let addr4: [U32](builtin-U32) val

---

* let scope: [U32](builtin-U32) val

---

## Public Functions

### ip4

Returns true for an IPv4 address.


```pony
fun box ip4()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### ip6

Returns true for an IPv6 address.


```pony
fun box ip6()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### name

Returns the host and service name.

If `reversedns` is an instance of `DNSLookupAuth`
a DNS lookup will be executed and the hostname
for this address is returned as first element of the result tuple.
If no hostname could be found, an error is raised.
If `reversedns` is `None` the plain IP address is given
and no DNS lookup is executed.

If `servicename` is `false` the numeric port is returned
as second element of the result tuple.
If it is `true` the port is translated into its
corresponding servicename (e.g. port 80 is returned as `"http"`).

Internally this method uses the POSIX C function `getnameinfo`.


```pony
fun box name(
  reversedns: (AmbientAuth val | NetAuth val | DNSAuth val | 
    None val) = seq,
  servicename: Bool val = seq)
: (String val , String val) ?
```
#### Parameters

*   reversedns: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [DNSAuth](net-DNSAuth) val | 
    [None](builtin-None) val) = seq
*   servicename: [Bool](builtin-Bool) val = seq

#### Returns

* ([String](builtin-String) val , [String](builtin-String) val) ?

---

### eq

```pony
fun box eq(
  that: NetAddress box)
: Bool val
```
#### Parameters

*   that: [NetAddress](net-NetAddress) box

#### Returns

* [Bool](builtin-Bool) val

---

### host_eq

```pony
fun box host_eq(
  that: NetAddress box)
: Bool val
```
#### Parameters

*   that: [NetAddress](net-NetAddress) box

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: NetAddress val)
: Bool val
```
#### Parameters

*   that: [NetAddress](net-NetAddress) val

#### Returns

* [Bool](builtin-Bool) val

---

