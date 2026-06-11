# MissionAiry

MissionAiry is a common mission operating environment for rapidly integrating, validating, updating, and redeploying emerging AI and autonomy capabilities while keeping mission surfaces human-comprehensible for authorities and operators.

The goal is rapid adaptability without operational confusion. MissionAiry gives authorities and operators a familiar environment for assessing new capabilities, coordinating them with existing systems, and redeploying them as conditions change while preserving mission intent, accountability, and coherence.

The challenge is larger than managing autonomous agents or teaching them to manage themselves. Under rapid AI emergence, the whole mission infrastructure becomes part of the problem: sensors, platforms, communications, data flows, validation, logistics, authorities, safety boundaries, and human decision surfaces. MissionAiry treats these as one living mission system.

The same coordination required for human mission teams is required for heterogeneous autonomous agents. A commander, operator, AI assistant, robotic platform, sensor, semi-independent field asset, and swarm element can all be understood as mission participants with different capabilities, constraints, authorities, and update cycles. MissionAiry supports the command-and-control functions needed across that full spectrum: aligning intent, assigning roles, sharing context, validating action, managing change, and preserving accountability.

As in prior eras of rapid industrial mobilization, the limiting factor is not invention alone. The nation needs disciplined processes for understanding, validating, updating, and fielding new capabilities at operational speed.

## Cognitive Map

Why centralized command breaks down when the mission ecosystem itself is rapidly changing.  
See [cognitive_map.md](docs/cognitive_map.md).

## MissionAiry Architecture Reasoning

How MissionAiry preserves awareness, intent, and interoperability across polycentric human and autonomous mission systems.  
See [architecture_reasoning.md](docs/architecture_reasoning.md).

## Current Landscape

Why rapid AI/autonomy industrialization changes the mission problem before the mission even begins.  
See [current_landscape.md](docs/current_landscape.md).

---

## Repository Discipline

MissionAiry uses a repo-native discipline model for AI-assisted development. The repository is intended to preserve intent, constraints, verification checks, project history, and decision boundaries while humans and AI assistants work on the system.

Before asking an AI assistant or coding agent to make substantial changes, read:

- [AGENTS.md](AGENTS.md)
- [TODO.md](TODO.md)
- [readme_pmp.md](readme_pmp.md)

For substantial, multi-file, architecture-sensitive, or process-sensitive work, create a workorder before editing code or structure.

## Foreground AI Startup Prompt

When starting a new chat or tab for MissionAiry, paste this into the foreground AI:

```text
You are the foreground AI for https://github.com/lightrock/missionairy.

Current repo state beats chat memory. Inspect the current MissionAiry repository before giving architecture advice, writing workorders, or suggesting repo changes.

Read README.md, AGENTS.md, TODO.md, readme_pmp.md, docs/cognitive_map.md, docs/architecture_reasoning.md, and docs/current_landscape.md first. Then identify current state, target, constraints, foreground/executor decision, and the smallest useful next move.
```

## Workorder Shortcut

For substantial work, talk with the foreground AI until the task is clear, then say:

```text
Create a workorder and also show it to me here.
```

You can copy a link to the workorder file and give it to the executor AI working in this repository.

You can also copy/paste the workorder body if you asked the foreground AI to show it first. Keep that copy/paste block clean: no citations, assistant notes, explanations, extra links, or commentary inside the workorder body.

## Checks

Run these from the repository root when available:

```text
python tools/pmp_check.py --area all
python -m pytest
```

If a check fails, paste the exact command output into the foreground AI and ask for the smallest safe fix.
