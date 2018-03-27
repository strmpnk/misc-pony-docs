# Serialise package

This package provides support for serialising and deserialising arbitrary data
structures.

The API is designed to require capability tokens, as otherwise serialising
would leak the bit patterns of all private information in a type (since the
resulting Array[U8] could be examined.

Deserialisation is fundamentally unsafe currently: there isn't yet a
verification pass to check that the resulting object graph maintains a
well-formed heap or that individual objects maintain any expected local
invariants. However, if only "trusted" data (i.e. data produced by Pony
serialisation from the same binary) is deserialised, it will always maintain a
well-formed heap and all object invariants.

Note that serialised data is not usable between different Pony binaries,
possibly including recompilation of the same code. This is due to the use of
type identifiers rather than a heavy-weight self-describing serialisation
schema. This also means it isn't safe to deserialise something serialised by
the same program compiled for a different platform.

The Serialise.signature method is provided for the purposes of comparing
communicating Pony binaries to determine if they are the same. Confirming this
before deserialising data can help mitigate the risk of accidental serialisation
across different Pony binaries, but does not on its own address the security
issues of accepting data from untrusted sources.


## Public Types

* [primitive Serialise](serialise-Serialise.md)
* [primitive SerialiseAuth](serialise-SerialiseAuth.md)
* [primitive DeserialiseAuth](serialise-DeserialiseAuth.md)
* [primitive OutputSerialisedAuth](serialise-OutputSerialisedAuth.md)
* [primitive InputSerialisedAuth](serialise-InputSerialisedAuth.md)
* [class Serialised](serialise-Serialised.md)


## Private Types

* [class _MachineWords](serialise-_MachineWords.md)
* [class _StructWords](serialise-_StructWords.md)
* [class _Simple](serialise-_Simple.md)
* [actor _EmptyActor](serialise-_EmptyActor.md)
* [class _HasActor](serialise-_HasActor.md)
* [class _BoxedWord](serialise-_BoxedWord.md)
