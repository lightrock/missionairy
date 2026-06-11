For the public introduction, see the [Doctor Bones GitHub Pages site](https://lightrock.github.io/drbones/).

# MissionAiry

MissionAiry is a common mission operating environment for rapidly understanding, integrating, validating, updating, and redeploying emerging AI and autonomy capabilities while keeping forward mission surfaces human-comprehensible for authorities and operators.

Its purpose is rapid mission adaptability. MissionAiry gives authorities and operators a familiar, mission-sensible environment where new and existing capabilities can be assessed, coordinated, trusted, updated, and redeployed as conditions change, while keeping deployed missions coherent and aligned with commander intent.

This problem is larger than preventing autonomous systems from running amok. In a rapidly emerging AI mission environment, the entire mission infrastructure becomes part of the adaptation challenge: sensors, platforms, communications, data flows, validation methods, logistics, authorities, safety boundaries, update mechanisms, and human decision surfaces. MissionAiry treats these as one living mission system, so new capabilities can be absorbed without losing operational sense, accountability, or coherence.

There are many points along the path to deployment where a mission can fail before an AI agent ever reaches the field. A capability may be promising but poorly understood, integrated but not validated, validated but not authorized, authorized but not explainable, or deployed without a clear way to update it when conditions change. MissionAiry is designed to make those failure points visible and manageable.

Historically, rapid industrial emergence has required more than invention. During World War II, figures such as W. Edwards Deming helped show that national-scale production depended on repeatable processes, quality control, measurement, and feedback loops, not just heroic engineering. MissionAiry applies that lesson to the AI/autonomy era: the nation does not merely need more autonomous tools; it needs a disciplined mission environment for understanding, validating, updating, and redeploying them at operational speed.

This repository is built from the Doctor Bones project template: a lightweight, vendor-independent discipline layer for AI-assisted development. In this project, Doctor Bones provides the repo-native memory, workorder, verification, and boundary structure used to develop MissionAiry without losing intent, constraints, checks, or project history.




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
