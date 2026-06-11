For the public introduction, see the [Doctor Bones GitHub Pages site](https://lightrock.github.io/drbones/).

# MissionAiry

MissionAiry is a common mission operating environment for rapidly integrating, validating, updating, and redeploying emerging AI and autonomy capabilities while keeping mission surfaces human-comprehensible for authorities and operators.

The goal is rapid adaptability without operational confusion. MissionAiry gives authorities and operators a familiar environment for assessing new capabilities, coordinating them with existing systems, and redeploying them as conditions change while preserving mission intent, accountability, and coherence.

The challenge is larger than managing autonomous agents or teaching them to manage themselves. Under rapid AI emergence, the whole mission infrastructure becomes part of the problem: sensors, platforms, communications, data flows, validation, logistics, authorities, safety boundaries, and human decision surfaces. MissionAiry treats these as one living mission system.

The same coordination required for human mission teams is required for heterogeneous autonomous agents. A commander, operator, AI assistant, robotic platform, sensor, semi-independent field asset, and swarm element can all be understood as mission participants with different capabilities, constraints, authorities, and update cycles. MissionAiry supports the command-and-control functions needed across that full spectrum: aligning intent, assigning roles, sharing context, validating action, managing change, and preserving accountability.

As in prior eras of rapid industrial mobilization, the limiting factor is not invention alone. The nation needs disciplined processes for understanding, validating, updating, and fielding new capabilities at operational speed.

## Cognitive Map

How we think about all this
See [cognitive_map.md](docs/cognitive_map.md).


## MissionAiry Architecture Reasoning

How we think about the architecture(s)
See [architecture_reasoning.md](docs/architecture_reasoning.md).


## Current Landscape

What is going on in the world in this regard
See [current_landscape.md](docs/current_landscape.md).

---



## How to interact with this github repository

Before the AI codes, teach the repo how to talk. Before the AI claims done, define what done means. Before the AI recommends, separate evidence from conclusion. Before the AI patches, define authority, verification, and boundary rules.

## Working on it / TODO / TO FINISH

See [TODO.md](TODO.md) for the rough working list of what still needs to become repo files, schemas, rubrics, examples, checks, and integration targets.

## Languages

- English: this file
- [Español](docs/i18n/README.es.md)
- [Français](docs/i18n/README.fr.md)
- [Deutsch](docs/i18n/README.de.md)
- [Português do Brasil](docs/i18n/README.pt-BR.md)
- [हिन्दी](docs/i18n/README.hi.md)

## What this repository is

It is a repo-native discipline layer for using AI assistants and coding agents without losing intent, constraints, checks, or project history.

The basic model is:

```text
human intent
→ foreground AI clarifies the task
→ repo captures durable guidance
→ executor AI performs bounded work
→ checks verify what can be verified
→ completion ties back to source intent
```

Think of the foreground AI as the planning and architecture assistant. Think of the executor AI as the worker with file access, a runtime environment, tests, and commit/PR tools.

The repo is the memory and discipline layer between them.

## Getting started

1. If you copied this template, rewrite this README around your real project soon.
2. Read [`examples/README.md`](examples/README.md) to see the day-in-the-life workflow examples.
3. Read [`readme_pmp.md`](readme_pmp.md) at least once and keep it handy.
4. Read [`AGENTS.md`](AGENTS.md) before asking an AI assistant to change the repo.
5. Use a workorder for substantial, multi-file, architecture-sensitive, or process-sensitive work.
6. Run the available checks before treating work as complete.

## Process boundary

Do not create your project workorders in the public Doctor Bones source repository unless you are intentionally contributing to Doctor Bones itself.

For your own project, first create or use your own repository from this template. Then point your foreground AI at that project repository URL and create workorders there.

Use `lightrock/drbones` as the source template, reference implementation, and upstream project. Use your copied Doctor Bones-based repository as the place where your project memory, workorders, lessons learned, and project-specific changes live.

## Foreground AI startup prompt

This prompt is for a repository created from the Doctor Bones template. After copying this template, replace `<your project repository URL>` with your own project repository URL.

When starting a new chat or tab for your project repository, paste this into the foreground AI:

```text
You are the foreground AI for <your project repository URL>.

Current repo state beats chat memory. Inspect the current project repository before giving
architecture advice, writing workorders, or suggesting repo changes.

Read README.md, examples/README.md, readme_pmp.md, AGENTS.md, and the relevant folder
guidance from the project repository first. Then identify current state, target, constraints,
foreground/executor decision, and the smallest useful next move.
```

## Workorder shortcut

For substantial work in your copied project repository, talk with the foreground AI until the task is clear, then say:

```text
Create a workorder and also show it to me here.
```

You can copy a link to the workorder file and tell your executor AI, working in an environment for your project repository, to perform it.

You can also copy/paste the workorder body if you asked the foreground AI to show it first. Keep that copy/paste block clean: no citations, assistant notes, explanations, extra links, or commentary inside the workorder body.

## Checks

Run these from the repository root when available:

```text
python tools/pmp_check.py --area all
python -m pytest
```

If a check fails, paste the exact command output into the foreground AI and ask for the smallest safe fix.
