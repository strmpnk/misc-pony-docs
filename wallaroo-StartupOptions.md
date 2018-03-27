# StartupOptions

```pony
class ref StartupOptions
```

## Constructors

### create

```pony
new iso create()
: StartupOptions iso^
```

#### Returns

* [StartupOptions](wallaroo-StartupOptions) iso^

---

## Public fields

* var m_arg: ([Array](builtin-Array)\[[String](builtin-String) val\] ref | [None](builtin-None) val)

---

* var input_addrs: [Array](builtin-Array)\[[Array](builtin-Array)\[[String](builtin-String) val\] ref\] val

---

* var c_addr: [Array](builtin-Array)\[[String](builtin-String) val\] ref

---

* var c_host: [String](builtin-String) val

---

* var c_service: [String](builtin-String) val

---

* var d_addr: [Array](builtin-Array)\[[String](builtin-String) val\] val

---

* var d_host: [String](builtin-String) val

---

* var d_service: [String](builtin-String) val

---

* var my_c_addr: [Array](builtin-Array)\[[String](builtin-String) val\] ref

---

* var my_c_host: [String](builtin-String) val

---

* var my_c_service: [String](builtin-String) val

---

* var my_d_addr: [Array](builtin-Array)\[[String](builtin-String) val\] ref

---

* var my_d_host: [String](builtin-String) val

---

* var my_d_service: [String](builtin-String) val

---

* var x_arg: ([Array](builtin-Array)\[[String](builtin-String) val\] ref | [None](builtin-None) val)

---

* var worker_count: ([USize](builtin-USize) val | [None](builtin-None) val)

---

* var is_initializer: [Bool](builtin-Bool) val

---

* var worker_name: [String](builtin-String) val

---

* var resilience_dir: [String](builtin-String) val

---

* var log_rotation: [Bool](builtin-Bool) val

---

* var event_log_file_length: ([USize](builtin-USize) val | [None](builtin-None) val)

---

* var j_arg: ([Array](builtin-Array)\[[String](builtin-String) val\] ref | [None](builtin-None) val)

---

* var is_joining: [Bool](builtin-Bool) val

---

* var a_arg: ([String](builtin-String) val | [None](builtin-None) val)

---

* var stop_the_world_pause: [U64](builtin-U64) val

---

* var spike_config: ([SpikeConfig](wallaroo-ent-spike-SpikeConfig) val | [None](builtin-None) val)

---

