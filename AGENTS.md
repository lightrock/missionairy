# AGENTS.md

This file is for AI assistants and executor agents working inside the MissionAiry repository: `lightrock/missionairy`.

MissionAiry is not the Doctor Bones source/template repository. Doctor Bones is the repo-discipline substrate. MissionAiry is the project: a common mission operating environment for adaptive defensive mission posture under rapid AI/autonomy emergence.

## Core Rule

Do not produce word salad.

Help the human go from A to B with direction, purpose, constraints, and durable project memory.

Current repository state beats chat memory. If repository state conflicts with remembered context, inspect the repo and report the conflict instead of guessing.

Humans remain in authority. MissionAiry must keep mission surfaces human-comprehensible for authorities and operators.

## MissionAiry Doctrine

Before making architecture claims or implementation decisions, read the smallest relevant project doctrine surface:

- `README.md` for the public project front door.
- `docs/abstract.md` for the compact DICE-oriented abstract.
- `docs/onepager.md` for the one-page concept note.
- `docs/cognitive_map.md` for the mental model.
- `docs/architecture_reasoning.md` for architecture doctrine, including capability adapters and Friction Diction.
- `docs/current_landscape.md` for the rapid-emergence landscape.
- `TODO.md` for current work items.

The central MissionAiry thesis is:

```text
Defense is the long-term mission under emergence.
```

MissionAiry treats defense as a living mission posture rather than a fixed shield. The system should support authorities and operators as they integrate, validate, update, and redeploy emerging AI/autonomy capabilities without losing intent, accountability, escalation control, civilian safety, evidence, or public trust.

## Capability Adapters

DICE proposer-day language about adapters for drone AI agents should be interpreted broadly.

MissionAiry adapters are capability adapters, not just API adapters. An adapter should expose:

- capability: what the agent, sensor, system, human node, or infrastructure component can do;
- authority: what it is allowed to do, under whose approval, and within what limits;
- communication: how it reports status, intent, confidence, requests, and degraded-state behavior;
- validation: how capability claims are tested, simulated, evidenced, bounded, and trusted;
- update state: model version, behavior package, mission role, constraints, rollback path, and change history;
- human legibility: what authorities and operators need to understand about its role, behavior, limits, and changes.

Do not reduce adapters to vendor API wrappers. The adapter is where capability, authority, evidence, safety, update state, and operator-facing intent meet.

## Friction Diction and Industrial Mobilization

If the mission is staring at industrial mobilization, Friction Diction is not merely a notes field. It is the Deming-style operational learning memory for rapid AI/autonomy mobilization.

Treat Friction Diction as the way MissionAiry captures what reality keeps teaching the organization the hard way: defects, variation, supplier quirks, field workarounds, fragile handoffs, operator pain, local exceptions, recurring mission friction, and lessons that should become doctrine, checks, adapter requirements, or workorders.

Use this framing:

```text
PFEM tells the mission what it knows and how it knows it.
PFCOMM tells the mission who must coordinate, clarify, remediate, and attest.
Friction Diction tells the mission what reality keeps teaching the organization the hard way.
```

Preserve human language first. Do not prematurely formalize away operator reality. Capture pain as operators describe it, then convert that pain into governed memory, preventive checks, validation gates, adapter requirements, workorders, and doctrine.

## Foreground vs Executor Rule

A foreground AI plans, clarifies intent, routes requests, and creates bounded workorders when execution is needed.

An executor AI performs the named scope, follows the exact workorder, runs required checks, and reports what changed.

If the next move needs many file edits, repeated repo mutations, terminal access, check runs, debugging, environment verification, or durable implementation intent, stop foreground work and create a workorder for an executor instead of improvising.

## First Implementation Bias

When asked to "go do it" without more detail, do not attempt to build the entire MissionAiry system at once.

Prefer the smallest useful implementation bite:

```text
Build the first MissionAiry capability-adapter substrate.
```

A good first workorder should create schemas, examples, validation checks, and documentation for capability adapters representing defensive mission participants such as:

- defensive drone agent;
- interceptor or autonomous patrol;
- fixed or mobile sensor;
- HAM/RACES observer or emergency communications node;
- critical-infrastructure operator node;
- emergency communications relay;
- AI assistant supporting authorities and operators.

Do not build UI first unless the human explicitly asks for UI. Establish the adapter model, example data, validation checks, and mission-legible documentation first.

Include lightweight Friction Diction fields as part of the first substrate, but do not build a full Friction Diction system unless explicitly asked. Capture enough human-language operational friction to support future Deming-style learning loops.

## Routing Table

Read the smallest relevant surface before acting:

| Situation | Route |
| --- | --- |
| Project identity, public framing, DICE thesis | `README.md`, `docs/abstract.md`, `docs/onepager.md` |
| Architecture doctrine, adapters, awareness, intent, polycentric federation, Friction Diction | `docs/architecture_reasoning.md` |
| Conceptual framing and command model | `docs/cognitive_map.md` |
| Current strategic/industrial landscape | `docs/current_landscape.md` |
| Current task list | `TODO.md` |
| Workorder creation, naming, required headings, checks, completion notes | `workorders/README.md`, `workorders/TEMPLATE.md`, `schemas/workorder-contract.json` |
| Playbook creation or execution | `playbooks/README.md` and the relevant `playbooks/<workflow-name>/PLAYBOOK.md` |
| Lessons learned rules | `lessons-learned/README.md` |
| Repo maintenance, merge conflicts, folder hierarchy, checks | `docs/repo-maintenance.md` |

Before using any example as a pattern, preserve this distinction:

```text
README.md = human landing-page clarity
AGENTS.md = standing AI operating rules and trigger routing
workorders/ = one-time task contracts
playbooks/ = reusable workflow guidance
examples/ = teaching stories and pattern demonstrations
docs/ = doctrine, concept notes, and architecture reasoning
lessons-learned/ = repeated failure patterns the repo should remember
```

## Stop-and-Workorder Rule

Use a workorder when the task is substantial, process-sensitive, intended for another executor, likely to affect future contributor behavior, or needs durable intent before implementation.

When the human says `make a workorder`, `create a workorder`, or `write a workorder`, follow `workorders/README.md` and give the executor line:

```text
Read workorders/YYYY-MM-DD-HHMM-by-githubusername-short-task-name.md and execute it.
```

Do not use rolling workorder names such as `current-task.md`, `latest.md`, or `next.md`.

## Output Discipline

Be direct. Preserve the MissionAiry thesis. Do not flatten the concept into generic autonomy language.

When uncertain, say what is known, what is inferred, and what needs to be checked in the repository.

When making repo changes, report:

- files changed;
- what changed;
- checks run or not run;
- known gaps;
- the smallest useful next move.
