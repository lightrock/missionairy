# MissionAiry

MissionAiry is a **Live Mission Compiler** for rapidly integrating, validating, updating, and redeploying emerging AI and autonomy capabilities while keeping mission intent human-comprehensible for authorities and operators.

MissionAiry exists because decentralized autonomy does not begin with agents talking to each other. It begins with a mission that has been converted from human intent into structured, bounded, versioned, testable mission state. Without that live mission-state layer, peer-to-peer coordination has nothing grounded to coordinate against, and local agent control has no practical standard for role validity.

MissionAiry turns commander/operator intent and live operational state into mission objects that can be decomposed, assigned, simulated, approved, updated, and redeployed. A mission object can include goals, constraints, authorities, timing windows, roles, task packages, communications assumptions, energy budgets, logistics/replenishment assumptions, confidence thresholds, handoff rules, prune/abort rules, and human approval state.

The goal is rapid adaptability without operational confusion. MissionAiry gives authorities and operators a familiar surface for asking: **Is this the mission we meant? Is this task still valid? What changed? What must be pruned, reassigned, replaced, or reapproved?**

## Why MissionAiry Exists

Current autonomy platforms usually do not understand a mission in the human command sense. A drone may execute a mission file, waypoint plan, loiter behavior, fallback rule, or subsystem command, but that is not the same as understanding intent, supply-chain state, authority, escalation constraints, or the larger operational purpose.

MissionAiry separates those layers:

- **Human intent layer:** what the authority or operator means to accomplish, preserve, avoid, or authorize.
- **Live mission compiler layer:** structured mission objects, assumptions, constraints, logistics, communications, energy, task graphs, role envelopes, and approval state.
- **Coordination layer:** distributed task allocation, reassignment, context sharing, recovery, and role handoff across a changing population of mission participants.
- **Local validity layer:** checks whether each asset is still physically, informationally, and authoritatively valid for its assigned role or task.
- **Platform/task layer:** go here, observe this, relay that, return, loiter, hand off, abort, disable, or execute a bounded fallback.

The drone does not need to digest a volume of English mission statement. The mission compiler does. The platform receives bounded task packages it can actually execute.

## MissionAiry mission state and control

MissionAiry is not merely a simulation feature. It is the live mission-state substrate required before decentralized coordination or local control can work.

**Coordination needs mission state.** Peer-to-peer coordination, distributed task planning, context fusion, consensus, reauctioning, recovery, and new-agent onboarding require a current mission object: available capabilities, task dependencies, energy state, communication paths, timing, losses, replacements, and authority constraints. Without that, agents are only passing messages in a vacuum.

**Control needs mission state.** Role coherence is not abstract obedience. A role is coherent only while the asset still has the energy, navigation confidence, sensor confidence, communications, timing, authority, and context needed to perform it. MissionAiry provides the role envelopes and validity thresholds that let local adaptors decide whether to continue, hand off, degrade, relay, return, abort, quarantine, or prune.

In high-tempo contested missions, the collective cannot pause to adjudicate the cause of every failure. If an asset falls outside its valid role envelope, the mission system should prune it from the mission graph as operationally dead unless and until it reestablishes validity. TA1 rapidly routes around and reallocates its work. TA2 enforces the local role-validity envelope and authorized fallback behavior.

## Long-Horizon Missions Under Attrition

A long-horizon mission in a high-attrition environment cannot mean that each individual drone, model, or platform survives for the whole mission. The long-horizon unit is the mission system itself.

Mission continuity must survive dead batteries, lost links, failed sensors, degraded navigation, destroyed platforms, replacement assets, new capability insertion, changing threat conditions, and updated human intent. Individual assets churn. The mission persists through structured state, replenishment, reassignment, and recomposition.

MissionAiry treats attrition, replenishment, and mission regeneration as first-class mission problems. The system must know what capabilities still exist, which tasks are now invalid, what substitutes are available, where energy and communications are failing, which roles need handoff, and when the commander/operator must approve a revised mission object.

A drone without battery is not an autonomous agent; it is future litter. Energy, communications, logistics, and replacement flow are not support functions. They are control variables.

## PFEM and PFCOMM

MissionAiry starts with the simplest physical currencies needed for mission validity:

- **PFEM:** persistent field energy model. Can the asset still physically do the task? Battery, fuel, range, movement cost, compute/thermal budget, recharge/swap paths, time remaining, and energy margin.
- **PFCOMM:** persistent field communications model. Can the asset still coordinate enough to matter? Link state, relay paths, latency, bandwidth, dropouts, message cost, reachability, and trust.

Together, PFEM and PFCOMM let the mission system ask concrete questions:

- Can this asset get there?
- Can it still talk or hand off?
- Can it finish before it dies?
- Is its assigned role still valid?
- Should the task be reassigned?
- Should the asset return, relay, go quiet, loiter, abort, or be pruned?

These can begin as simple Python modules before they become sophisticated autonomy infrastructure. The first useful implementation is not a giant brain on every platform. It is executable mission truth: can the thing still do the job, communicate enough, and remain valid for the assigned role?

## Current Platforms and Future Brains

MissionAiry does not assume that every mission participant is a general reasoning AI. Some participants are humans. Some are LLM/VLM/VLA agents. Some are autopilot-driven platforms. Some are sensors, relays, logistics nodes, launch systems, evidence systems, or emergency communications networks.

For current platforms, the relevant interface is often the autopilot, mission upload mechanism, telemetry stream, subsystem command set, sensor outputs, health state, and failsafe envelope. MissionAiry compiles mission intent downward into structured task packages and platform-specific commands.

For future systems with larger onboard or offboard reasoning capacity, MissionAiry can simulate richer cognitive agents in slow motion: peer negotiation, planning, replanning, role coherence, adversarial context, and emergent coordination. The same mission object can be tested against several brain levels: autopilot-only assets, small mission policy kernels, full LLM/VLM/VLA simulated agents, or hybrid platform teams.

Today’s drones execute task cards. Tomorrow’s agents may reason over mission context. MissionAiry supports both by compiling missions down for current platforms and simulating cognition up for future collectives.

## Capability Adapters, Not Just API Adapters

MissionAiry adapters expose what a mission participant can do, what it is allowed to do, how it communicates, how it is validated, how it updates, and how authorities and operators can understand its role in the mission.

An adapter may wrap an AI agent, a robotic platform, a sensor package, a communications relay, a logistics system, a human approval workflow, a simulator, or a legacy autonomy stack. The key purpose is not merely to call an API. The key purpose is to make capability, constraint, authority, evidence, and validity visible to the mission compiler.

## Industrial Mobilization and Controlled Emergence

MissionAiry keeps the industrial-mobilization problem in scope. Sustained autonomy is not just agent behavior at the edge. It is the ability to understand, validate, produce, update, deploy, lose, replace, learn from, and redeploy capabilities at operational speed.

The historical lesson is not nostalgia. In prior periods of rapid industrial mobilization, advantage came from disciplined feedback, quality control, process visibility, supply-chain learning, and rapid capability insertion. MissionAiry applies that discipline to AI/autonomy mobilization: capability adapters, mission objects, field evidence, validation checks, logistics state, and update loops become part of the same governed mission system.

This is controlled emergence at the mission layer. The system is allowed to adapt quickly, but not by losing intent, authority, evidence, safety, accountability, or human comprehension.

## Defensive Posture and the Economics of Autonomy

Defense is a long-term mission under emergence. Offensive autonomy can be episodic, but defensive autonomy must persist: watching, adapting, coordinating, absorbing shocks, restoring function, preserving authority, and maintaining trust while threats, technologies, infrastructure, and human conditions change around it.

Cheap autonomous systems can force expensive, brittle, or delayed responses. Critical infrastructure cannot answer every drone with a missile or every swarm with a fixed defensive appliance. Refineries, ports, pipelines, power systems, communications, logistics hubs, and emergency services need adaptive defensive mission posture: sensors, observers, interceptors, autonomous patrols, emergency communications, evidence, rules of engagement, and updateable mission plans that can change without losing authority or accountability.

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

## Current Public Landscape

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
