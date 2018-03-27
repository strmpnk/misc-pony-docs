# Startup

```pony
actor tag Startup
```

## Constructors

### create

```pony
new tag create(
  env: Env val,
  application: Application val,
  app_name: (String val | None val))
: Startup tag^
```
#### Parameters

*   env: [Env](builtin-Env) val
*   application: [Application](wallaroo-Application) val
*   app_name: ([String](builtin-String) val | [None](builtin-None) val)

#### Returns

* [Startup](wallaroo-Startup) tag^

---

## Public Behaviours

### initialize

```pony
be initialize()
```

---

### complete_join

```pony
be complete_join(
  info_sending_host: String val,
  m: InformJoiningWorkerMsg val)
```
#### Parameters

*   info_sending_host: [String](builtin-String) val
*   m: [InformJoiningWorkerMsg](wallaroo-core-messages-InformJoiningWorkerMsg) val

---

### recover_not_join

Called when the cluster informs us we should be recovering instead of
joining (i.e. we've already joined, so we must be coming back up).


```pony
be recover_not_join()
```

---

### clean_recovery_files

```pony
be clean_recovery_files()
```

---

### dispose

```pony
be dispose()
```

---

## Private Functions

### _set_recovery_file_names

```pony
fun ref _set_recovery_file_names(
  auth: AmbientAuth val)
: None val
```
#### Parameters

*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [None](builtin-None) val

---

### _remove_file

```pony
fun ref _remove_file(
  filename: String val)
: None val
```
#### Parameters

*   filename: [String](builtin-String) val

#### Returns

* [None](builtin-None) val

---

### _recover_worker_names

Read in a list of the names of all workers after recovery.


```pony
fun ref _recover_worker_names(
  worker_names_filepath: FilePath val)
: Array[String val] val
```
#### Parameters

*   worker_names_filepath: [FilePath](files-FilePath) val

#### Returns

* [Array](builtin-Array)\[[String](builtin-String) val\] val

---

### _print_link_to_community_license

```pony
fun ref _print_link_to_community_license()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _setup_shutdown_handler

```pony
fun ref _setup_shutdown_handler(
  c: Connections tag,
  r: RecoveryFileCleaner tag,
  a: AmbientAuth val)
: None val
```
#### Parameters

*   c: [Connections](wallaroo-ent-network-Connections) tag
*   r: [RecoveryFileCleaner](wallaroo-core-common-RecoveryFileCleaner) tag
*   a: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [None](builtin-None) val

---

