For the public introduction, see the [Doctor Bones GitHub Pages site](https://lightrock.github.io/drbones/).

# MissionAiry

MissionAiry is a common mission operating environment for rapidly integrating, validating, updating, and redeploying emerging AI and autonomy capabilities while keeping mission surfaces human-comprehensible for authorities and operators.

The goal is rapid adaptability without operational confusion. MissionAiry gives authorities and operators a familiar environment for assessing new capabilities, coordinating them with existing systems, and redeploying them as conditions change while preserving mission intent, accountability, and coherence.

The challenge is larger than managing autonomous agents or teaching them to manage themselves. Under rapid AI emergence, the whole mission infrastructure becomes part of the problem: sensors, platforms, communications, data flows, validation, logistics, authorities, safety boundaries, and human decision surfaces. MissionAiry treats these as one living mission system.

The same coordination required for human mission teams is required for heterogeneous autonomous agents. A commander, operator, AI assistant, robotic platform, sensor, semi-independent field asset, and swarm element can all be understood as mission participants with different capabilities, constraints, authorities, and update cycles. MissionAiry supports the command-and-control functions needed across that full spectrum: aligning intent, assigning roles, sharing context, validating action, managing change, and preserving accountability.

As in prior eras of rapid industrial mobilization, the limiting factor is not invention alone. The nation needs disciplined processes for understanding, validating, updating, and fielding new capabilities at operational speed.

# Cognitive Map

Think of the book or movie Ender's Game. One commander in a centralized environment, supported by a team of geniuses, guides an offensive against a rapidly adapting enemy.

Think of the history of war, there is a hierarchical structure of military command.

## This is not right in the modern world

Ender Wiggin was a single point of failure. Hierarchical command structure is for humans because not everyone can be taught to be a soldier and a general.

The modern landscape is different. AI Systems "have an app for that".  "Today I am a commander, or a relay, or a package delivery vehicle."  "Later today I gave myself my own battlefield promotion, and in order to achieve my mission I need at least four participants with the following capabilities..."

This kind of resilience under expected heavy attrition is new.  The commander is now a fractal expression spread throughout the operational AI ecosystem. "I am the one who has discovered the best odds of success with the highest confidence%, 'You three! Follow me now...'"  Or, better said "This is the new local or global mission plan with the best chance of success, broadcast it to all nodes." 

To a degree this collapses many functions at once, command and control, intelligence and analysis, and critical mission updates on the fly. A learning and adapting hive mind would have beaten the pants off of Ender Wiggin, but his enemy was also hierarchical in structure.

Imagine an operational set of AI's engaged in performance of a mission and along comes a "new guy". The new guy is aware that the other guys will not know the meaning of his new capabilities, he may or may not have to tell them "Trust me, put me here, and I will improve your chances".  Old systems will not always be able to understand the capabilities of the new guy who suddenly appeared into the collective, he has to be assertive (if the others even need to know); at least he knows his own fit. 



# MissionAiry Architecture Reasoning

There are two main issues, Awareness and Intent. Everything else is either evolving at a pace that seems impossible to predict, or else already easily classifiable into known subsystems.

The environment is pervasively Polycentric and Federated, starting all the way back at the industrial mobilization before there are even Missions to perform.

Planning and Control surfaces have to somehow aim for stability as new capabilities arrive, a human cannot be expected to be re-learning whole new systems every week.

Training for humans should be enabled to be rapid, and easily digested; intutive.

Classical scaling of missions must be preserved. Food supply, logistics, medevac... various functions can have extremely local command and control issues, and to be efficient they may have control surfaces optimized for their types of missions.  Think, dozens and not hundreds or thousands of nodes. Whatever the more strategic surfaces are the interoperability is to be preserved. Again, Awareness, Intent, Polycentric, Federated...

There are existing good high level abstractions like "Polycentric Federated Evidence Mesh" preserving rules of evidence, scoring, and confidence%. Such things as this can be rapidly instantiated in a variety of forms by modern AI assisted software development practices. This adds the idea of "Polymorphic" to "Polycentric Federated..."  PFEM is already proven in the commercial and opensource landscape as an analysis tool for Agents and Agent Ecosystems simply because the formal rules of evidence and boundaries enforce cognition and awareness of deficiencies in existing code bases. In a half hour, a PFEM analysis of another project can produce easily three pages of bug fixes and architectrual deficiencies that need to be addressed in other sytsems in a form that is usable by a coding agent to go fix them all within another few hours.

The same thing as PFEM inverts to "Polycentric Federated Command Mesh" with the same principles applied to command and control and "hive mind" or resilient swarm-like systems.



# Existing Landscape

See [current_landscape.md](docs/current_landscape.md).






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
