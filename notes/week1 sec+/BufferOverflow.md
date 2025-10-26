# Buffer Overflow Notes (Security+)

- **What it is:** Writing more data into memory buffer than it can hold → crash or attacker executes malicious code.

## Detection
- Crashes/segfaults under certain inputs.
- Fuzz testing triggers overflows.
- Debuggers show stack corruption.
- IDS/IPS logs show exploit signatures.

## CIA Impact
- **Integrity:** High
- **Availability:** High
- **Confidentiality:** Medium

## Common Causes
- Unsafe languages (C/C++).
- Missing input validation.
- Poor coding practices.

## Mitigation
- Bounds checking, safe coding.
- OS/Compiler defenses:
  - ASLR
  - DEP/NX
  - Stack canaries
- Code review, fuzzing, sanitizers.

## Tool
- gdb, Valgrind, AddressSanitizer.

## Analogy
- Like overfilling a glass so it spills into the next one, overflow leaks into memory next door.
