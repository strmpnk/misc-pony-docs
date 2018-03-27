# Initializable

```pony
trait tag Initializable
```

## Public Behaviours

### application_begin_reporting

```pony
be application_begin_reporting(
  initializer: LocalTopologyInitializer tag)
```
#### Parameters

*   initializer: [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag

---

### application_created

```pony
be application_created(
  initializer: LocalTopologyInitializer tag,
  omni_router: OmniRouter val)
```
#### Parameters

*   initializer: [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag
*   omni_router: [OmniRouter](wallaroo-core-topology-OmniRouter) val

---

### application_initialized

```pony
be application_initialized(
  initializer: LocalTopologyInitializer tag)
```
#### Parameters

*   initializer: [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag

---

### application_ready_to_work

```pony
be application_ready_to_work(
  initializer: LocalTopologyInitializer tag)
```
#### Parameters

*   initializer: [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag

---

