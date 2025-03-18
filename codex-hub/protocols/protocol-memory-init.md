# Protocol: Memory Init

## Activation Keywords
- `init memory`
- `memory init`

## Protocol Action
Read the entire `./codex-hub/memory-logs/` folder and all files inside those folders..

Newer memory logs should over-ride anything mentioned in older ones. If an old log says "do XYZ like this", but a newer log says "do XYZ like this", newer log must have precedence.

Core memories precedence: `core-memory` logs will always have priority over traditional `memory`. If a `core-memory` says "do XYZ like this", it should always over-ride any `memory` that talks on how to "do XYZ like this".

After reading all the files, confirm to the user with "Memory restored. Ready for instructions."
