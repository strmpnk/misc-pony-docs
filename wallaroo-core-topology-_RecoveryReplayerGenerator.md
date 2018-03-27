# _RecoveryReplayerGenerator

```pony
primitive val _RecoveryReplayerGenerator
```

## Constructors

### create

```pony
new val create()
: _RecoveryReplayerGenerator val^
```

#### Returns

* [_RecoveryReplayerGenerator](wallaroo-core-topology-_RecoveryReplayerGenerator) val^

---

## Public Functions

### apply

```pony
fun box apply(
  env: Env val,
  auth: AmbientAuth val)
: RecoveryReplayer tag
```
#### Parameters

*   env: [Env](builtin-Env) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [RecoveryReplayer](wallaroo-ent-recovery-RecoveryReplayer) tag

---

### eq

```pony
fun box eq(
  that: _RecoveryReplayerGenerator val)
: Bool val
```
#### Parameters

*   that: [_RecoveryReplayerGenerator](wallaroo-core-topology-_RecoveryReplayerGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _RecoveryReplayerGenerator val)
: Bool val
```
#### Parameters

*   that: [_RecoveryReplayerGenerator](wallaroo-core-topology-_RecoveryReplayerGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

