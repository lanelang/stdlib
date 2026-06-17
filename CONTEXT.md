# Lane Standard Library

The standard library repository owns Lane source that is loaded as the default
prelude and later ordinary library code.

## Language

**Prelude**:
The initial Lane environment containing primitive operation wrappers and
contextual offers required by ordinary programs.
_Avoid_: compiler builtin table, source import system

**Standard Intrinsic Use**:
A standard-library call to a Lane intrinsic defined by the language and
implemented by the compiler/runtime boundary.
_Avoid_: host plugin API, arbitrary native call

**Contextual Operation Value**:
A prelude value such as `Add[Int]` offered for contextual resolution.
_Avoid_: trait instance, open binding

## Relationships

- `stdlib` is written in Lane source and checked by `lanec`.
- The language and intrinsic contract is specified by `spec`.
- The `lane` tool locates and loads this repository's prelude for single-file
  runs and checks.
