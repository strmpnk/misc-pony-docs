# _ProposeWatermark

```pony
primitive val _ProposeWatermark
```

## Constructors

### create

```pony
new val create()
: _ProposeWatermark val^
```

#### Returns

* [_ProposeWatermark](wallaroo-ent-watermarking-_ProposeWatermark) val^

---

## Public Functions

### apply

Determine what we can propose as a new watermark for flushing.

Basic algo is as follows:

  If each route is fully acked; IE every message sent has been acknowledged
  then we can use the highest value as our new watermark. Basically, if
  all work has been done then the last piece of work done is our
  watermark.

  If any route is not fully acked; IE at lease one message that we sent
  downstream hasn't yet been acknowledged then we use the lowest value from
  a not fully acknowledged route as our watermark.

  So...

  Route | Sent | Ack
    A       0     0
    B       2     1
    C       5     5
    D       7     4

  Both B and D have unacknowleged work. The two ack values are 1 and 4.
  From this, we can acknowledge that work up to 1 has been done. We know
  that 2 is outstanding as is 6 and 7.

  Another example:

  Route | Sent | Ack
    A       0     0
    B       3     1
    C       5     5
    D       7     4

  Both B and D have unacknowleged work. The two ack values are 1 and 4.
  From this, we can acknowledge that work up to 1 has been done. We know
  that 3 is outstanding as is 6 and 7. Its unclear, unlike our previous
  example whether 2 has been handled.

  Another example:

  Route | Sent | Ack
    A       0     0
    B       9     1
    C       5     5
    D       7     4

  Both B and D have unacknowleged work. The two ack values are 1 and 4.
  From this, we can acknowledge that work up to 1 has been done as we
  are unable to determine if 2 or 3 have been acknowledged. We know
  that 6,7,8 and 9 definitely haven't because they are above the highest
  acknowledged value.


```pony
fun box apply(
  filter_route: _FilteredOnStep ref,
  routes: Values[_AckedOnRoute ref] ref)
: U64 val
```
#### Parameters

*   filter_route: [_FilteredOnStep](wallaroo-ent-watermarking-_FilteredOnStep) ref
*   routes: [Values](wallaroo-ent-watermarking-Values)\[[_AckedOnRoute](wallaroo-ent-watermarking-_AckedOnRoute) ref\] ref

#### Returns

* [U64](builtin-U64) val

---

### eq

```pony
fun box eq(
  that: _ProposeWatermark val)
: Bool val
```
#### Parameters

*   that: [_ProposeWatermark](wallaroo-ent-watermarking-_ProposeWatermark) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _ProposeWatermark val)
: Bool val
```
#### Parameters

*   that: [_ProposeWatermark](wallaroo-ent-watermarking-_ProposeWatermark) val

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _all_routes_acked

```pony
fun box _all_routes_acked(
  routes: Values[_AckedOnRoute ref] ref)
: Bool val
```
#### Parameters

*   routes: [Values](wallaroo-ent-watermarking-Values)\[[_AckedOnRoute](wallaroo-ent-watermarking-_AckedOnRoute) ref\] ref

#### Returns

* [Bool](builtin-Bool) val

---

