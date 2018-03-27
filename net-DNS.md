# DNS

Helper functions for resolving DNS queries.


```pony
primitive val DNS
```

## Constructors

### create

```pony
new val create()
: DNS val^
```

#### Returns

* [DNS](net-DNS) val^

---

## Public Functions

### apply

Gets all IPv4 and IPv6 addresses for a host and service.


```pony
fun box apply(
  auth: (AmbientAuth val | NetAuth val | DNSAuth val),
  host: String val,
  service: String val)
: Array[NetAddress val] iso^
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [DNSAuth](net-DNSAuth) val)
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val

#### Returns

* [Array](builtin-Array)\[[NetAddress](net-NetAddress) val\] iso^

---

### ip4

Gets all IPv4 addresses for a host and service.


```pony
fun box ip4(
  auth: (AmbientAuth val | NetAuth val | DNSAuth val),
  host: String val,
  service: String val)
: Array[NetAddress val] iso^
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [DNSAuth](net-DNSAuth) val)
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val

#### Returns

* [Array](builtin-Array)\[[NetAddress](net-NetAddress) val\] iso^

---

### ip6

Gets all IPv6 addresses for a host and service.


```pony
fun box ip6(
  auth: (AmbientAuth val | NetAuth val | DNSAuth val),
  host: String val,
  service: String val)
: Array[NetAddress val] iso^
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [DNSAuth](net-DNSAuth) val)
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val

#### Returns

* [Array](builtin-Array)\[[NetAddress](net-NetAddress) val\] iso^

---

### broadcast_ip4

Link-local IP4 broadcast address.


```pony
fun box broadcast_ip4(
  auth: (AmbientAuth val | NetAuth val | DNSAuth val),
  service: String val)
: Array[NetAddress val] iso^
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [DNSAuth](net-DNSAuth) val)
*   service: [String](builtin-String) val

#### Returns

* [Array](builtin-Array)\[[NetAddress](net-NetAddress) val\] iso^

---

### broadcast_ip6

Link-local IP6 broadcast address.


```pony
fun box broadcast_ip6(
  auth: (AmbientAuth val | NetAuth val | DNSAuth val),
  service: String val)
: Array[NetAddress val] iso^
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [DNSAuth](net-DNSAuth) val)
*   service: [String](builtin-String) val

#### Returns

* [Array](builtin-Array)\[[NetAddress](net-NetAddress) val\] iso^

---

### is_ip4

Returns true if the host is a literal IPv4 address.


```pony
fun box is_ip4(
  host: String val)
: Bool val
```
#### Parameters

*   host: [String](builtin-String) val

#### Returns

* [Bool](builtin-Bool) val

---

### is_ip6

Returns true if the host is a literal IPv6 address.


```pony
fun box is_ip6(
  host: String val)
: Bool val
```
#### Parameters

*   host: [String](builtin-String) val

#### Returns

* [Bool](builtin-Bool) val

---

### eq

```pony
fun box eq(
  that: DNS val)
: Bool val
```
#### Parameters

*   that: [DNS](net-DNS) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: DNS val)
: Bool val
```
#### Parameters

*   that: [DNS](net-DNS) val

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _resolve

Turns an addrinfo pointer into an array of addresses.


```pony
fun box _resolve(
  auth: (AmbientAuth val | NetAuth val | DNSAuth val),
  family: U32 val,
  host: String val,
  service: String val)
: Array[NetAddress val] iso^
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [DNSAuth](net-DNSAuth) val)
*   family: [U32](builtin-U32) val
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val

#### Returns

* [Array](builtin-Array)\[[NetAddress](net-NetAddress) val\] iso^

---

