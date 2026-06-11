## Abstract
[abstract.md](docs/abstract.md).

## One pager
[onepager.md](docs/onepager.md).

# MissionAiry

MissionAiry is a common mission operating environment for rapidly integrating, validating, updating, and redeploying emerging AI and autonomy capabilities while keeping mission surfaces human-comprehensible for authorities and operators.

The goal is rapid adaptability without operational confusion. MissionAiry gives authorities and operators a familiar environment for assessing new capabilities, coordinating them with existing systems, and redeploying them as conditions change while preserving mission intent, accountability, and coherence.

The challenge is larger than managing autonomous agents or teaching them to manage themselves. Under rapid AI emergence, the whole mission infrastructure becomes part of the problem: sensors, platforms, communications, data flows, validation, logistics, authorities, safety boundaries, and human decision surfaces. MissionAiry treats these as one living mission system.

The same coordination required for human mission teams is required for heterogeneous autonomous agents. A commander, operator, AI assistant, robotic platform, sensor, semi-independent field asset, and swarm element can all be understood as mission participants with different capabilities, constraints, authorities, and update cycles. MissionAiry supports the command-and-control functions needed across that full spectrum: aligning intent, assigning roles, sharing context, validating action, managing change, and preserving accountability.

MissionAiry adapters are capability adapters, not just API adapters. They expose what an AI or autonomous agent can do, what it is allowed to do, how it communicates, how it is validated, how it updates, and how authorities and operators can understand its role in the mission.

Defensive missions cannot be reduced to missile systems, laser stations, jammers, or fixed counter-drone appliances. As autonomous systems become cheaper, faster, and more numerous, defense itself becomes a drone-on-drone and agent-on-agent coordination problem across land, air, sea, cyber, communications, and critical infrastructure. The challenge is not only to intercept hostile systems, but to coordinate defensive sensors, autonomous patrols, human observers, emergency communications, authorities, and updateable mission rules fast enough to preserve continuity and trust.

As in prior eras of rapid industrial mobilization, the limiting factor is not invention alone. The nation needs disciplined processes for understanding, validating, updating, and fielding new capabilities at operational speed.

## Defensive Posture and the Economics of Autonomy

Defense is the long-term mission under emergence. Offensive autonomy can be episodic, but defensive autonomy must persist: watching, adapting, coordinating, absorbing shocks, restoring function, preserving authority, and maintaining trust while threats, technologies, infrastructure, and human conditions change around it.

Today, much of the attention goes to offensive drones because they are cheap, scalable, and visibly effective. In many cases, the best defense may still be offensive pressure against the enemy’s launch sites, supply chains, operators, and enabling infrastructure.

But offense alone does not level the field. Critical infrastructure still has to be defended. Refineries, ports, pipelines, power systems, communications, logistics hubs, and emergency services cannot simply answer every drone with a missile or every swarm with a fixed defensive appliance. That preserves the attacker’s advantage: cheap systems forcing expensive, brittle, or delayed defensive responses.

MissionAiry treats defense as an adaptive mission posture, not a static shield. The goal is to help authorities and operators coordinate sensors, observers, interceptors, autonomous patrols, emergency communications, evidence, rules of engagement, and updateable mission plans so defense can become cheaper, faster, more distributed, and more resilient.

The strategic problem is deterrence. Nuclear weapons deter nuclear weapons because the cost of use is unmistakably reciprocal. Drones do not yet face an equivalent defensive economy. Until defenders can impose low-cost, reliable, scalable, and accountable drone-on-drone or agent-on-agent defense, autonomous offense will continue to punch above its weight against critical infrastructure.

MissionAiry treats defense as a living mission posture rather than a fixed shield. The purpose is to help authorities and operators continuously integrate new sensors, observers, communications paths, autonomous agents, emergency procedures, evidence flows, and mission updates without losing intent, accountability, escalation control, or public trust.


## Critical Infrastructure and HAM/RACES

MissionAiry also applies to critical infrastructure, emergency communications, and HAM/RACES-style resilience networks. These environments face the same core problem: rapidly changing capabilities, fragile communications, distributed human expertise, local improvisation, and the need to preserve intent, trust, and coordination under stress.

HAM radio and Radio Amateur Civil Emergency Service (RACES) communities are not an afterthought. Amateur radio has repeatedly produced serious technical innovation: amateur-built satellites, global ground-station coordination, packet radio networks, emergency communications practice, and direct radio links with human spaceflight. MissionAiry treats that practical ecosystem as part of the same architecture problem: helping authorities, operators, autonomous systems, and resilient human networks coordinate capabilities when normal infrastructure cannot be assumed.

## Cognitive Map

Why centralized command breaks down when the mission ecosystem itself is rapidly changing.  
See [cognitive_map.md](docs/cognitive_map.md).

## MissionAiry Architecture Reasoning

How MissionAiry preserves awareness, intent, and interoperability across polycentric human and autonomous mission systems.  
See [architecture_reasoning.md](docs/architecture_reasoning.md).

## Current Landscape

Why rapid AI/autonomy industrialization changes the mission problem before the mission even begins.  
See [current_landscape.md](docs/current_landscape.md).

## Continual Process Improvement as Controlled Emergence

MissionAiry treats continual process improvement as controlled emergence. The learning loop starts before the mission, at industrial mobilization, and continues through deployment, operation, assessment, update, and redeployment.

This is where Friction Diction matters. Field pain, vendor quirks, fragile handoffs, operator workarounds, recurring defects, and local exceptions should not remain tribal memory. They should become governed mission memory: captured in human language, structured into reusable friction patterns, tied to evidence and communication flows, converted into adapter requirements or validation checks, and fed back into updated doctrine and redeployed capability.

In that sense, MissionAiry applies Deming-style quality discipline to AI/autonomy mobilization. The goal is not uncontrolled acceleration. The goal is to let the mission system learn quickly without losing authority, evidence, safety, operator trust, or human comprehension.

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
