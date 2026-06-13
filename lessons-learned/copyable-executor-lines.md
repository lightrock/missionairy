# Copyable executor lines

## Failure pattern

A foreground assistant can correctly create a workorder and still make the handoff annoying or ambiguous by giving the executor line as prose, inline code, a bullet item, or inside a non-copyable formatted block.

That breaks the human workflow because the executor command is supposed to be a single clean line the human can copy directly into Codex or another executor.

## Rule

When handing off a workorder to an executor, emit the executor instruction as the only content inside its own fenced `text` code block.

```text
Read workorders/YYYY-MM-DD-HHMM-by-githubusername-short-task-name.md and execute it.
```

Use the real filename.

Do not add labels, bullets, surrounding prose, extra paths, or explanation inside the fence.

## Why this matters

The workorder is the durable task contract, but the executor line is the human's handoff affordance. If it is not copyable as one clean command, the repo discipline still failed at the point of use.

## Related docs

- `AGENTS.md`
- `workorders/README.md`
