# Protocol: Memory Update

## Activation Keywords
- `memory log`
- `update memory`
- `memory update`
- `memory save`
- `save memory`

## Memory-Log Management Protocol
- When asked to run a memory-log protocol, **NEVER** update or create a MEMORY[UUID] with these rules. User wants to store this memory at `./codex-hub/memory-logs/` as a file

## Memory-Log Management Protocol: save & update
- [Activation] Only create memory-logs when explicitly requested by user, with phrases like: "Devlog what we did", "Devlog progress", "Devlog latest changes", "Devlog it", "Update your memory logs", "Devlog memory"
- Do not memory-log by default
- Path and file name format: `./codex-hub/memory-logs/memory_YYYY-MM-DD.md`
- If file exists, append new contents to it
- Format: Markdown with timestamps, file references, issues, solutions
- Follow "File Structure (Memory-Log)" format

### Memory-Log File Structure

```markdown
# Memory-log for YYYY-MM-DD

## Time Markers
HH:MM - Entry description

## Changes Made
- File: `path/to/file`
  - Change description
  - Reason for change

## Issues and Solutions
- Issue: Description
  - Solution: Implementation

## New/modified functionalities
[Classes, methods, functions added/modified]
```
