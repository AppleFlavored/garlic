# Garlic Language Runtime
The Garlic Language Runtime (or just Garlic) is a virtual machine for running
platform- and language-agnostic programs in the Garlic bytecode format. Garlic can be
compared to the JVM (primarily for Java) and the CLR (primarily for C#).

## Specification Versions
This document contains the experimental version of the Garlic specification. As such,
the contents of this specification are not final and will change over time.

Snapshots of this document can be found with the format `snapshot-[major].md` where
`[major]` corresponds with a major version of the virtual machine.

## File Format
This section defines the Garlic file format. A Garlic file describes an executable
(or assembly) to be run with the Garlic virtual machine. Internally, Garlic files can
contain type definitions, bytecode, and application resources.

Garlic files do not have a required file format, but `.garlic`, or any variation thereof,
may be used.

Structure definitions use `u8`, `u16`, and `u32` to represent 8-bit, 16-bit, and 32-bit
quantities, respectively. Multi-byte data are always stored in little-endian order.
Strings, indicated by `str`, use the UTF-8 encoding.

A Garlic file consists of a `Assembly` structure:
```
Assembly {
    magic         : u16;
    major_version : u16;
    minor_version : u16;
    segment_count : u16;
    segment_table : Segment[];
}
```

### Segments
\[TODO\]

The `Segment` structure:
```
Segment {
    name_length : u16;
    name        : str;
    data_length : u32;
    data        : u8[];
}