# Path

Operations on paths that do not require a capability. The operations can be
used to manipulate path names, but give no access to the resulting paths.


```pony
primitive val Path
```

## Constructors

### create

```pony
new val create()
: Path val^
```

#### Returns

* [Path](files-Path) val^

---

## Public Functions

### is_sep

Determine if a byte is a path separator.


```pony
fun box is_sep(
  c: U8 val)
: Bool val
```
#### Parameters

*   c: [U8](builtin-U8) val

#### Returns

* [Bool](builtin-Bool) val

---

### sep

Return the path separator as a string.


```pony
fun tag sep()
: String val
```

#### Returns

* [String](builtin-String) val

---

### is_abs

Return true if the path is an absolute path.


```pony
fun box is_abs(
  path: String val)
: Bool val
```
#### Parameters

*   path: [String](builtin-String) val

#### Returns

* [Bool](builtin-Bool) val

---

### join

Join two paths together. If the next_path is absolute, simply return it.
The returned path will be cleaned.


```pony
fun box join(
  path: String val,
  next_path: String val)
: String val
```
#### Parameters

*   path: [String](builtin-String) val
*   next_path: [String](builtin-String) val

#### Returns

* [String](builtin-String) val

---

### clean

Replace multiple separators with a single separator.
Convert / to the OS separator.
Remove instances of . from the path.
Remove instances of .. and the preceding path element from the path.
The result will have no trailing slash unless it is a root directory.
If the result would be empty, "." will be returned instead.


```pony
fun box clean(
  path: String val)
: String val
```
#### Parameters

*   path: [String](builtin-String) val

#### Returns

* [String](builtin-String) val

---

### normcase

Normalizes the case of path for the runtime platform.


```pony
fun box normcase(
  path: String val)
: String val
```
#### Parameters

*   path: [String](builtin-String) val

#### Returns

* [String](builtin-String) val

---

### cwd

Returns the program's working directory. Setting the working directory is
not supported, as it is not concurrency-safe.


```pony
fun box cwd()
: String val
```

#### Returns

* [String](builtin-String) val

---

### abs

Returns a cleaned, absolute path.


```pony
fun box abs(
  path: String val)
: String val
```
#### Parameters

*   path: [String](builtin-String) val

#### Returns

* [String](builtin-String) val

---

### rel

Returns a path such that Path.join(to, Path.rel(to, target)) == target.
Raises an error if this isn't possible.


```pony
fun box rel(
  to: String val,
  target: String val)
: String val ?
```
#### Parameters

*   to: [String](builtin-String) val
*   target: [String](builtin-String) val

#### Returns

* [String](builtin-String) val ?

---

### split

Splits the path into a pair, (head, tail) where tail is the last pathname
component and head is everything leading up to that. The tail part will
never contain a slash; if path ends in a slash, tail will be empty. If
there is no slash in path, head will be empty. If path is empty, both head
and tail are empty. The path in head will be cleaned before it is returned.
In all cases, join(head, tail) returns a path to the same location as path
(but the strings may differ). Also see the functions dir() and base().


```pony
fun box split(
  path: String val,
  separator: String val = seq)
: (String val , String val)
```
#### Parameters

*   path: [String](builtin-String) val
*   separator: [String](builtin-String) val = seq

#### Returns

* ([String](builtin-String) val , [String](builtin-String) val)

---

### base

Return the path after the last separator, or the whole path if there is no
separator.
If `with_ext` is `false`, the extension as defined by the `ext()` method
will be omitted from the result.


```pony
fun box base(
  path: String val,
  with_ext: Bool val = seq)
: String val
```
#### Parameters

*   path: [String](builtin-String) val
*   with_ext: [Bool](builtin-Bool) val = seq

#### Returns

* [String](builtin-String) val

---

### dir

Return a cleaned path before the last separator, or the whole path if there
is no separator.


```pony
fun box dir(
  path: String val)
: String val
```
#### Parameters

*   path: [String](builtin-String) val

#### Returns

* [String](builtin-String) val

---

### ext

Return the file extension, i.e. the part after the last dot as long as that
dot is after all separators. Return an empty string for no extension.


```pony
fun box ext(
  path: String val)
: String val
```
#### Parameters

*   path: [String](builtin-String) val

#### Returns

* [String](builtin-String) val

---

### volume

On Windows, this returns the drive letter or UNC base at the beginning of
the path, if there is one. Otherwise, this returns an empty string.


```pony
fun box volume(
  path: String val)
: String val
```
#### Parameters

*   path: [String](builtin-String) val

#### Returns

* [String](builtin-String) val

---

### from_slash

Changes each / in the path to the OS specific separator.


```pony
fun box from_slash(
  path: String val)
: String val
```
#### Parameters

*   path: [String](builtin-String) val

#### Returns

* [String](builtin-String) val

---

### to_slash

Changes each OS specific separator in the path to /.


```pony
fun box to_slash(
  path: String val)
: String val
```
#### Parameters

*   path: [String](builtin-String) val

#### Returns

* [String](builtin-String) val

---

### canonical

Return the equivalent canonical absolute path. Raise an error if there
isn't one.


```pony
fun box canonical(
  path: String val)
: String val ?
```
#### Parameters

*   path: [String](builtin-String) val

#### Returns

* [String](builtin-String) val ?

---

### is_list_sep

Determine if a byte is a path list separator.


```pony
fun box is_list_sep(
  c: U8 val)
: Bool val
```
#### Parameters

*   c: [U8](builtin-U8) val

#### Returns

* [Bool](builtin-Bool) val

---

### list_sep

Return the path list separator as a string.


```pony
fun box list_sep()
: String val
```

#### Returns

* [String](builtin-String) val

---

### split_list

Separate a list of paths into an array of cleaned paths.


```pony
fun box split_list(
  path: String val)
: Array[String val] iso^
```
#### Parameters

*   path: [String](builtin-String) val

#### Returns

* [Array](builtin-Array)\[[String](builtin-String) val\] iso^

---

### random

Returns a pseudo-random base, suitable as a temporary file name or
directory name, but not guaranteed to not already exist.


```pony
fun box random(
  len: USize val = seq)
: String val
```
#### Parameters

*   len: [USize](builtin-USize) val = seq

#### Returns

* [String](builtin-String) val

---

### eq

```pony
fun box eq(
  that: Path val)
: Bool val
```
#### Parameters

*   that: [Path](files-Path) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: Path val)
: Bool val
```
#### Parameters

*   that: [Path](files-Path) val

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _drive_letter

Look for a drive letter followed by a ':', returning true if we find it.


```pony
fun box _drive_letter(
  path: String val,
  offset: ISize val = seq)
: Bool val
```
#### Parameters

*   path: [String](builtin-String) val
*   offset: [ISize](builtin-ISize) val = seq

#### Returns

* [Bool](builtin-Bool) val

---

### _network_share

Look for a host, a \, and a resource. Return the path up to that point if
we found one, otherwise an empty String.


```pony
fun box _network_share(
  path: String val,
  offset: ISize val = seq)
: String val
```
#### Parameters

*   path: [String](builtin-String) val
*   offset: [ISize](builtin-ISize) val = seq

#### Returns

* [String](builtin-String) val

---

