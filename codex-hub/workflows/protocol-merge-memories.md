# Protocol: Merge Memories

## Activation Keywords
- `memory merge`
- `memories merge`
- `merge memory`
- `merge memories`

## Protocol Action
Read all the files inside `/codex-hub/memory-logs`. Analyze them.

Ignore files that begin with `core-memory_`.

Could be some older logs that are not relevant anymore. Newer ones could be made those older ones obsolete.
Could be some logs that contain just duplicate info of others.
Could be some logs that can be merged into a single paragraph and still make sense.

The goal is to treat these logs like memory, more than a log. And save any important technical information that could be useful for future reference.

With that in mind, after analyzing the logs, create a new file inside `/codex-hub/memory-logs` with the name `memory-merge_YYYY-MM-DD.md` and write the analyzed merged memory there.

After that, delete all the files that were merged from `/codex-hub/memory-logs`.

Confirm to the user with "Memories merged. Ready for instructions."
