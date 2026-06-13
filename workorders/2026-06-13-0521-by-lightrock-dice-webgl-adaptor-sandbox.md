# Build DICE WebGL Adaptor Sandbox

## Purpose

Build the first MissionAiry DICE swarm sandbox that makes the DICE adaptor problem visible at simulation scale.

The goal is not to build a polished game, a full drone simulator, or a high-fidelity physics environment. The goal is to create a small but serious WebGL-based simulation substrate where base simulated agents and attached adaptor instances are modeled separately, rendered clearly, and inspected through mission-legible state.

This work should help MissionAiry show the distinction between:

- a base simulated autonomous agent;
- a DICE-style adaptor/control surface attached to that agent;
- peer-to-peer mission/task propagation through adaptors;
- capability/state reporting from agents through adaptors;
- task bidding, task rejection, failure handling, and re-auction;
- role/coherence/trust status visible at the adaptor layer.

The immediate project thesis to preserve is:

```text
DICE governs through local adaptors connected to simulated agents. The adaptor is not merely a vendor API wrapper and not exactly an implanted whole mission brain. It is the simulation-side local control surface through which coordination, capability declaration, role validity, task bidding, and failure recovery can be tested.
```

## Scope

Create a first-pass browser-based WebGL sandbox under a new repo area such as:

```text
webgl_sandbox/
```

or another small, clearly named folder if the current repo structure suggests a better location.

The implementation should include:

1. A runnable browser entry point.

   Create a minimal HTML/JavaScript entry point that can be opened locally or served with a simple static server.

2. A WebGL2 rendering layer.

   Render agents using WebGL2, preferably with instanced rendering or another scalable approach that avoids one DOM element per agent.

   The first target does not need to prove 100,000 agents. It should be structured so the renderer is not the bottleneck for future scaling.

3. A simulation layer separate from rendering.

   Keep simulation state separate from drawing code. The simulation should maintain arrays or structured records for:

   - agents;
   - adaptors;
   - tasks;
   - messages;
   - mission zones;
   - failures or compromised states;
   - metrics.

4. Separate agent and adaptor models.

   A base agent should include fields such as:

   - id;
   - type;
   - position;
   - velocity or movement intent;
   - energy or battery;
   - communication radius;
   - sensing radius or capability;
   - base role;
   - native task state;
   - health/status.

   An attached adaptor should include fields such as:

   - adaptor id;
   - attached agent id;
   - declared role;
   - capability declaration;
   - task bid state;
   - current assigned task;
   - trust/reputation score;
   - role/coherence score;
   - message counts;
   - degraded/failure/isolated state;
   - last rejection reason if it refused a task.

5. A minimal DICE-like mission scenario.

   Include a simple scenario such as:

   ```text
   Observe Sector A, maintain relay coverage, avoid the threat zone, and recover if a scout fails.
   ```

   The scenario should demonstrate:

   - mission broadcast or propagation;
   - adaptors evaluating whether their attached agents can help;
   - agents/adaptors bidding on tasks;
   - task assignment;
   - one simulated failure or compromised node;
   - re-auction or reassignment of the failed task;
   - visible recovery metrics.

6. WebGL visual encoding.

   The display should visually distinguish:

   - base agents;
   - adaptor status ring/halo/glyph;
   - peer-to-peer messages;
   - assigned tasks;
   - mission zones;
   - failed or compromised agents;
   - selected agent/adaptor inspection state.

   It is acceptable for the first version to use simple shapes and text labels. Do not spend time on game art.

7. Basic UI panels.

   Add simple HTML panels outside the WebGL canvas for:

   - mission summary;
   - selected agent state;
   - selected adaptor state;
   - metrics.

   Metrics should include at minimum:

   - number of agents;
   - number of active adaptors;
   - messages exchanged;
   - active tasks;
   - failed agents;
   - isolated/low-trust agents;
   - task reassignments;
   - simple recovery counter or time-to-recover indicator.

8. Documentation.

   Add a short README in the sandbox folder explaining:

   - how to run it;
   - what the demo shows;
   - the agent/adaptor distinction;
   - why this is a MissionAiry/DICE simulation substrate rather than a game;
   - what is intentionally not implemented yet.

## Files/areas likely to change

Likely new files or folders:

- `webgl_sandbox/README.md`
- `webgl_sandbox/index.html`
- `webgl_sandbox/src/main.js`
- `webgl_sandbox/src/sim/agent_state.js`
- `webgl_sandbox/src/sim/adaptor_state.js`
- `webgl_sandbox/src/sim/mission_scenario.js`
- `webgl_sandbox/src/sim/auction_or_bidding.js`
- `webgl_sandbox/src/sim/metrics.js`
- `webgl_sandbox/src/render/gl_context.js`
- `webgl_sandbox/src/render/agent_renderer.js`
- `webgl_sandbox/src/render/link_renderer.js`
- `webgl_sandbox/src/render/zone_renderer.js`
- `webgl_sandbox/src/ui/panels.js`

If the repo already has a better location for browser demos, use that location and explain the decision in the completion note.

Likely existing files to review before editing:

- `README.md`
- `AGENTS.md`
- `TODO.md`
- `docs/architecture_reasoning.md`
- `docs/current_landscape.md`
- `docs/cognitive_map.md`
- `docs/agent-operating-model.md`
- `workorders/README.md`
- `workorders/TEMPLATE.md`
- `schemas/workorder-contract.json`

Existing docs may be updated only if needed to link to the sandbox or preserve discoverability.

## Out of scope

Do not build a full StarCraft clone.

Do not integrate StarCraft II, Battle.net, PySC2, SC2LE, SMAC, HIMA, Unity, Unreal, Isaac Sim, Omniverse, or any external simulation framework in this workorder.

Do not build a high-fidelity drone physics simulator.

Do not build a backend server unless a tiny static-server note is needed for local development.

Do not implement real weapons behavior, targeting logic, or tactical kill-chain features.

Do not add dependencies unless clearly justified. Prefer plain browser JavaScript and WebGL2 for the first pass.

Do not create a giant UI framework app.

Do not flatten MissionAiry into generic swarm-demo language. The demo must preserve the agent/adaptor distinction and mission-legibility purpose.

Do not claim this is a complete DICE TA1/TA2/TA3 implementation. It is an early visual and executable substrate for reasoning about the adaptor problem.

## Constraints

Current repository state beats chat memory. Inspect the current repository before making file or structure decisions.

Follow `AGENTS.md` and the workorder discipline in `workorders/README.md`.

This work is allowed to build UI because the human explicitly requested a WebGL simulation surface for the DICE adaptor issue.

Keep the implementation small enough to review.

Keep simulation and rendering separate.

Keep the agent and adaptor models separate in code.

Use WebGL2 when available. If WebGL2 is unavailable in the browser, fail visibly with a clear message instead of silently falling back to an unrelated implementation.

Make the first demo deterministic or mostly deterministic so behavior can be reviewed and debugged.

Use human-legible naming. Avoid unexplained acronyms in UI labels and README text.

Prefer data structures that could later support many agents and many messages.

Design for future scaling, but do not overbuild a full ECS engine unless the repo already has a clear pattern for that.

The adaptor should be represented as the local control/coordination surface attached to a simulated agent, not as the whole base agent itself.

Capability reporting should be first-class. Each adaptor should expose or mediate basic capability/state fields such as energy, communications radius, sensing capability, role, task fit, rejection reason, trust, and coherence.

The demo should make failures and recovery visible: one agent failure or low-trust/compromised state should trigger reassignment or re-auction.

## Required checks

Run from the repository root when available:

```text
python tools/pmp_check.py --area all
```

Run tests when available:

```text
python -m pytest
```

Also perform a manual browser smoke test of the sandbox:

- open or serve the sandbox;
- verify the WebGL canvas appears;
- verify agents render;
- verify adaptor status is visually distinct from base agent position;
- verify mission/task propagation or assignment occurs;
- verify at least one failure/reassignment behavior occurs;
- verify selected agent/adaptor panels show different state;
- verify metrics update.

If no automated JavaScript test harness exists, do not invent a large one in this workorder. Report the manual smoke test clearly in the completion note.

If checks fail outside the scope of this workorder, report the exact failure and do not hide it.

## Expected result

The repository contains a first-pass WebGL DICE adaptor sandbox that a human can run and inspect.

A reviewer should be able to see:

- multiple simulated agents;
- adaptor overlays or status rings attached to agents;
- peer-to-peer message visualization;
- mission/task zones;
- task bidding or assignment;
- one failure or degraded node;
- visible recovery/reassignment;
- metrics showing messages, tasks, failures, and recovery;
- a selected-agent/adaptor panel that proves agent state and adaptor state are separate.

The sandbox folder contains a README explaining how to run the demo and what it demonstrates.

## Fallback behavior

If WebGL2 setup is blocked by repo structure, browser restrictions, or missing local environment, stop and report the blocker precisely.

If the repo already contains a preferred web/demo location, use that location rather than creating a competing top-level structure, and explain the decision.

If the agent/adaptor distinction becomes ambiguous during implementation, stop and preserve the distinction rather than collapsing them into one object.

If the work grows too large, implement the smallest coherent slice:

- render agents;
- attach adaptor state;
- show one mission;
- show one failure;
- show one reassignment;
- show metrics.

Do not continue expanding into a full game.

If this work reveals a repeated architectural trap, such as confusing a base agent with its adaptor, collapsing DICE into a generic swarm visualization, treating the adaptor as a mere API wrapper, building UI art before executable mission/adaptor state, or letting rendering concerns dominate the simulation model, create or propose a lesson learned.

## Completion note

The executor should report:

```text
changed files
what changed
checks run
checks passed or failed
checks not run and why
manual browser smoke test result
lessons learned created or not needed
open questions
known gaps
exact workorder path
```
