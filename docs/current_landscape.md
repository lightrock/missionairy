# Polycentric Federated Architecture Stack

## Top-Level Modules

### PF-AWARENESS

What do we think is happening?

### PF-EVIDENCE

Why do we believe it?

### PF-CAPABILITIES

What can each agent, node, or team do?

### PF-COMMS

What communication channels exist, what can they carry, and how degraded, trusted, jammed, delayed, or unavailable are they?

### PF-LOGISTICS

What can be supplied, recovered, replaced, moved, transported, stored, or sustained?

### PF-SUSTAINMENT

What consumables, field supplies, energy, ammo, batteries, water, food, spares, and maintenance support are needed to keep humans and nodes useful?

### PF-ATTRITION

Which losses are expected, acceptable, recoverable, mission-breaking, or strategically dangerous?

### PF-RECONSTITUTION

How does the mission replace, acquire, vet, onboard, integrate, or retire nodes during execution?

### PF-CASUALTY-RECOVERY

How are wounded, dead, missing, isolated, or stranded personnel identified, prioritized, assisted, evacuated, recovered, or accounted for?

### PF-COTS-RISK

What risks come from commercial off-the-shelf platforms, default firmware, compliance broadcasts, vendor dependencies, telemetry leakage, supply-chain assumptions, or civilian safety standards in a contested mission?

### PF-HUMAN-FACTORS

What human behaviors, habits, mistakes, fatigue, panic, arrogance, shortcuts, or procedural failures create mission risk or opportunity?

### PF-DENIAL

What must be denied to the adversary if an agent is tracked, compromised, captured, or unable to return safely?

### PF-MISSION

What are we trying to accomplish, even if the plan is loose, incomplete, exploratory, or expected to change?

### PF-COMMAND-AUTHORITY

Who can issue, modify, constrain, prioritize, append, delegate, or override mission instructions?

### PF-FIRES

How are support effects requested, authorized, deconflicted, coordinated, assessed, and updated?

### PF-AGENT

Who or what is participating?

### PF-ROLE

What job is an agent currently assigned?

### PF-TASK

What specific work item must be done, discovered, checked, supported, or offered?

### PF-TASK-CONSTRAINT

What limits apply to that task?

### PF-COMMAND-MESH

How do participants coordinate, hand off, escalate, and survive degraded comms?

### PF-OPERATOR-CONSOLE

How does a human operator, ground station, forward-deployed controller, special operator, or laptop user observe, understand, query, approve, and safely interact with the mesh?

### PF-CPIP

Last-resort physical / delay-tolerant update channel for mission packages, keys, policy changes, and recovery instructions when electronic command paths are unavailable or untrusted.

### PF-WOPR-RISK

How can the strategic planning / recompilation layer be degraded, deceived, isolated, overloaded, or poisoned, and what fallback mode preserves mission control?

### PF-WOPR

Computer-assisted mission planner and mission-update engine.

### PF-SIM-HOOKS

How does the architecture connect to simulation, replay, scoring, failure injection, branch comparison, and WOPR recompilation?

### PF-STATE

What is currently true across all of the above?

---

# PF-AWARENESS

## Question

What do we think is happening?

## Purpose

PF-AWARENESS maintains the current operational understanding of the environment, mission space, agents, threats, opportunities, and changes. It is not proof by itself. It is the current best picture.

## Sub-items

* awareness_id
* observed objects
* suspected objects
* known friendly agents
* unknown agents
* hostile or potentially hostile agents
* civilians / noncombatants
* wounded / stranded / missing personnel indicators
* environmental conditions
* terrain / sector status
* active threat areas
* degraded areas
* safe areas
* contested areas
* mission-relevant events
* anomalies
* contradictions
* uncertainty markers
* confidence estimates
* stale awareness flags
* awareness source references
* awareness update timestamp
* awareness expiration / stale-after time

## Example

A sector reports a moving RF signature, degraded comms, and a local team requesting batteries and water. PF-AWARENESS says: “Sector C has active support need, confidence 81%, resupply route uncertain.”

---

# PF-EVIDENCE

## Question

Why do we believe it?

## Purpose

PF-EVIDENCE stores the supporting observations, source chain, confidence, provenance, timestamps, contradictions, and evidence quality behind awareness claims, task decisions, mission updates, support requests, and command recommendations.

## Sub-items

* evidence_id
* linked awareness item
* linked mission / task / agent / support request
* source agent
* source sensor
* source human report
* source mesh
* source trust level
* observation type
* raw observation
* normalized observation
* timestamp
* location
* confidence
* corroboration status
* contradiction status
* chain of custody
* tamper flag
* stale flag
* classification / sensitivity
* evidence handling restrictions
* evidence package reference
* evidence conflict notes
* human review flag

## Example

PF-SUSTAINMENT says a team needs batteries. PF-EVIDENCE shows the request came from an authenticated operator console, was repeated by a relay node, and matches energy telemetry from nearby drones.

---

# PF-CAPABILITIES

## Question

What can each agent, node, or team do?

## Purpose

PF-CAPABILITIES describes the functional ability of agents and teams. It prevents mission plans from assigning impossible work to agents that lack required sensors, energy, mobility, compute, payload, authority, trust level, or communications support.

PF-CAPABILITIES does not own the full communication-channel details. It references PF-COMMS for actual communication pipes.

## Sub-items

* capability_id
* owning agent / team / node
* mobility capability
* sensor capability
* communication capability references
* relay capability
* store-and-forward capability
* degraded-comms operating capability
* compute capability
* storage capability
* evidence handling capability
* tracking capability
* observation capability
* logistics capability
* sustainment delivery capability
* casualty assistance capability
* casualty recovery support capability
* repair / maintenance capability
* battery / energy transfer capability
* medical support capability
* recovery capability
* self-protection capability
* denial capability
* fires-support observation capability
* fires-support request capability
* reconstitution support capability
* onboarding capability
* identity verification capability
* endurance / energy limits
* payload limits
* operating range
* environmental limits
* role compatibility
* trust requirements
* readiness status
* degraded capability status
* unavailable capability status

## Example

A ground robot may carry batteries, food, water, or medical supplies. A small flying scout may locate a stranded person but cannot carry meaningful supplies. PF-CAPABILITIES prevents dumb assignments.

---

# PF-COMMS

## Question

What communication channels exist, what can they carry, and how degraded, trusted, jammed, delayed, or unavailable are they?

## Purpose

PF-COMMS describes available communication channels, their condition, limits, trust status, and fallback behavior. It tells PF-COMMAND-MESH what pipes are available for coordination.

PF-COMMS describes the pipes.
PF-COMMAND-MESH describes the command behavior over the pipes.
PF-CPIP is the last-resort physical / delay-tolerant pipe.

## Sub-items

* comms_id
* owning agent / node / team
* channel type
* RF link
* mesh radio
* SATCOM
* cellular
* Wi-Fi
* fiber / wired
* optical / laser
* acoustic
* local broadcast
* line-of-sight link
* store-and-forward relay
* sneakernet / physical media
* CPIP / courier / delay-tolerant delivery
* range
* bandwidth
* latency
* reliability
* message size limit
* one-way / two-way status
* encryption status
* authentication status
* jamming status
* spoofing risk
* interception risk
* trust level
* availability
* degradation mode
* energy cost
* priority traffic allowed
* casualty / medical traffic priority
* sustainment traffic priority
* last successful contact
* stale-after time
* fallback channel

## Example

A casualty report may be allowed to outrank routine telemetry. A battery request may be lower priority than a wounded-person evacuation request but higher than normal status chatter.

---

# PF-LOGISTICS

## Question

What can be supplied, recovered, replaced, moved, transported, stored, or sustained?

## Purpose

PF-LOGISTICS tracks the movement, storage, availability, recovery, transport, and sustainment structure behind the mission. It answers whether the mission can continue over time.

PF-LOGISTICS is the movement and supply-chain layer.
PF-SUSTAINMENT is the actual field-consumption need.
PF-RECONSTITUTION is the process of adding or retiring nodes.
PF-CASUALTY-RECOVERY is the personnel recovery layer.

## Sub-items

* logistics_id
* supplies available
* supplies needed
* supply location
* supply owner
* transport capacity
* recovery capacity
* repair capacity
* battery / fuel / energy stores
* replacement agents
* reserve agents
* launch sites
* recovery sites
* alternate recovery sites
* resupply timing
* replenishment windows
* route feasibility
* route risk
* inventory state
* attrition reserves
* maintenance status
* damaged assets
* stranded assets
* denied recovery areas
* support availability
* support timing
* reconstitution resources
* candidate replacement pool
* casualty movement support
* remains recovery support
* logistics confidence
* logistics constraints
* logistics failure triggers

## Example

PF-LOGISTICS says whether food, water, batteries, ammunition, medical supplies, spare parts, and replacement nodes can physically get from where they are to where they are needed.

---

# PF-SUSTAINMENT

## Question

What consumables, field supplies, energy, ammo, batteries, water, food, spares, and maintenance support are needed to keep humans and nodes useful?

## Purpose

PF-SUSTAINMENT tracks the field-level needs that keep humans, robots, sensors, relays, vehicles, and mission nodes alive, powered, supplied, maintained, and useful.

This is where “bring food to the dudes,” “those guys need ammo,” “these guys need a shit ton more batteries,” “the relay needs replacement parts,” and “that team is about to run dry” belong.

PF-SUSTAINMENT does not decide whether a support request is tactically wise or authorized by itself. It creates a structured need that PF-COMMAND-AUTHORITY, PF-LOGISTICS, PF-COMMAND-MESH, PF-TASK-CONSTRAINT, and PF-WOPR can evaluate.

## Sustainment categories

* food
* water
* medical supplies
* batteries
* fuel
* charging equipment
* ammunition / controlled consumables
* spare parts
* repair tools
* replacement sensors
* replacement comms gear
* cold-weather gear
* protective equipment
* field shelter
* maps / mission packages
* credentials / keys
* data storage
* maintenance support
* operator rest / rotation
* power-generation support

## Sub-items

* sustainment_id
* linked mission
* linked team / agent / role / task
* requesting party
* request source
* request authentication
* need type
* quantity requested
* quantity minimum
* urgency
* priority
* time sensitivity
* location / delivery area
* delivery window
* route constraint
* transport requirement
* storage requirement
* handling restriction
* controlled-item flag
* authority requirement
* approval status
* logistics source
* delivery method
* delivery status
* consumption rate
* depletion estimate
* resupply threshold
* fallback item
* substitution allowed flag
* substitution notes
* risk if not delivered
* mission impact
* WOPR recompile trigger
* PF-STATE update reference

## Sustainment states

* need identified
* request drafted
* pending evidence
* pending authority
* approved
* denied
* unavailable
* sourced
* in transit
* delivered
* partially delivered
* consumed
* depleted
* substituted
* failed delivery
* canceled
* closed

## Example

A forward team reports they have drones but not enough batteries to keep the relay alive. PF-SUSTAINMENT records battery type, quantity, urgency, delivery window, and mission impact. PF-LOGISTICS checks whether batteries can be moved. PF-COMMAND-AUTHORITY checks whether the request is valid. PF-WOPR may recompile if the batteries cannot arrive.

---

# PF-ATTRITION

## Question

Which losses are expected, acceptable, recoverable, mission-breaking, or strategically dangerous?

## Purpose

PF-ATTRITION treats agents, especially flying agents, as probabilistic mission resources rather than guaranteed survivors. It records expected loss rates, acceptable loss thresholds, mission-breaking losses, replacement assumptions, and recompile triggers.

PF-ATTRITION is not the same as logistics, reconstitution, sustainment, casualty recovery, or denial.

PF-SUSTAINMENT asks: What field resources are being consumed?
PF-LOGISTICS asks: Can we move, store, recover, or resupply?
PF-RECONSTITUTION asks: Can we safely add or retire nodes during execution?
PF-CASUALTY-RECOVERY asks: What happened to people, and what recovery action is needed?
PF-DENIAL asks: What must not fall into enemy hands or expose friendly forces?
PF-ATTRITION asks: What losses should we expect, and how does the mission keep working anyway?

## Platform classes

* expendable
* attritable
* recoverable
* protected
* non-loss-tolerant

## Sub-items

* attrition_id
* linked mission
* linked agent / role / task / team
* platform class
* expected loss rate
* acceptable loss threshold
* warning loss threshold
* mission-breaking loss threshold
* minimum viable swarm size
* role redundancy
* task redundancy
* replacement availability
* reserve requirement
* degraded-mode behavior
* loss trigger
* loss evidence
* last contact
* presumed destroyed flag
* presumed captured flag
* presumed jammed flag
* presumed missing flag
* recovery worthiness
* denial requirement
* logistics replacement path
* reconstitution trigger
* WOPR recompile trigger
* command authority notification
* mission continuation rule
* mission abort recommendation
* post-loss evidence requirement

## Example

The mission can tolerate losing half the cheap flying scouts, but not the only relay, the only medic carrier, or the only authenticated operator console.

---

# PF-RECONSTITUTION

## Question

How does the mission replace, acquire, vet, onboard, integrate, or retire nodes during execution?

## Purpose

PF-RECONSTITUTION handles the live rebuilding of the mission force. It manages replacement agents, newly available agents, reserve activation, captured or compromised node retirement, trust onboarding, capability registration, role assignment, and mission reintegration.

## Candidate source types

* reserve
* recovered
* repaired
* newly launched
* partner-provided
* COTS-acquired
* field-acquired
* simulated
* unknown
* previously isolated
* previously degraded
* newly trusted
* probationary

## Sub-items

* reconstitution_id
* linked mission
* linked attrition item
* linked logistics item
* linked sustainment item
* linked agent / team / role / task
* lost capability
* replacement requirement
* candidate replacement node
* candidate source
* candidate owner / provider
* onboarding status
* identity verification
* authentication status
* trust level
* COTS risk review
* capability verification
* comms verification
* firmware / software version
* mission package compatibility
* role compatibility
* task compatibility
* authority approval requirement
* command authority approval status
* denial risk review
* evidence handling eligibility
* fires-support eligibility
* sustainment support eligibility
* casualty recovery eligibility
* integration time
* local mesh admission status
* PF-COMMAND-MESH acceptance
* WOPR recompile trigger
* probationary status
* quarantine status
* retirement status
* decommission reason
* last-known-good configuration
* rollback requirement
* post-onboarding monitoring requirement

## Example

Three scouts are lost. PF-ATTRITION says the mission is below scout threshold. PF-LOGISTICS says two replacement drones are available. PF-RECONSTITUTION verifies identity, comms, firmware, capabilities, COTS risk, and trust. PF-COMMAND-AUTHORITY approves onboarding. PF-COMMAND-MESH admits them.

---

# PF-CASUALTY-RECOVERY

## Question

How are wounded, dead, missing, isolated, or stranded personnel identified, prioritized, assisted, evacuated, recovered, or accounted for?

## Purpose

PF-CASUALTY-RECOVERY handles human personnel recovery, wounded assistance, medical evacuation support, remains recovery, missing-person accounting, and stranded-person support.

This is not just logistics. A dead body, a wounded teammate, a stranded operator, and a missing patrol are not ordinary cargo. They carry urgency, authority, dignity, evidence, reporting, identification, risk, and mission-priority implications.

PF-CASUALTY-RECOVERY does not automatically override the mission. It creates structured recovery needs that PF-COMMAND-AUTHORITY, PF-MISSION, PF-TASK-CONSTRAINT, PF-LOGISTICS, PF-SUSTAINMENT, and PF-WOPR can evaluate.

## Recovery categories

* wounded personnel
* urgent medical need
* stranded personnel
* isolated personnel
* missing personnel
* confirmed deceased
* remains recovery
* personnel accountability
* friendly-force extraction support
* civilian casualty support
* partner-force casualty support
* operator recovery
* body identification / confirmation
* recovery denied / unsafe
* recovery deferred
* recovery completed

## Sub-items

* casualty_recovery_id
* linked mission
* linked team / agent / human party
* person / group identifier, if known
* status

  * wounded
  * deceased
  * missing
  * isolated
  * stranded
  * unknown
* location / last known location
* location confidence
* time last seen
* report source
* evidence reference
* urgency
* medical priority
* recovery priority
* identification confidence
* friendly / civilian / partner / unknown classification
* assistance requested
* evacuation requested
* remains recovery requested
* personnel accountability requirement
* recovery route constraint
* recovery risk
* threat proximity concern
* comms requirement
* sustainment requirement
* medical supply requirement
* transport requirement
* authority requirement
* human approval requirement
* mission conflict assessment
* opportunistic recovery allowed flag
* “recover if on the way” flag
* “do not break primary mission” flag
* recovery status
* recovery handoff point
* recovery completion evidence
* dignity / handling requirement
* reporting requirement
* WOPR recompile trigger
* PF-STATE update reference

## Recovery states

* reported
* unconfirmed
* confirmed
* assistance requested
* pending authority
* pending route
* pending transport
* recovery assigned
* recovery in progress
* recovered alive
* evacuated
* remains recovered
* unable to recover
* deferred
* canceled
* closed

## Example

A sergeant says, “Retrieve my wounded guy on the way.” PF-CASUALTY-RECOVERY records the person, location, urgency, and recovery condition. PF-COMMAND-AUTHORITY checks whether the sergeant can append that request. PF-TASK-CONSTRAINT checks whether the recovery breaks the primary mission. PF-LOGISTICS checks transport. PF-SUSTAINMENT checks medical supply need. PF-WOPR recompiles if the recovery changes the mission.

---

# PF-COTS-RISK

## Question

What risks come from commercial off-the-shelf platforms, default firmware, compliance broadcasts, vendor dependencies, telemetry leakage, supply-chain assumptions, or civilian safety standards in a contested mission?

## Purpose

PF-COTS-RISK identifies where commercial systems behave in ways that are safe, legal, or useful in civilian airspace but dangerous in contested or security-sensitive missions.

## Risk categories

* Remote ID / identification broadcast exposure
* controller / operator location exposure
* vendor telemetry leakage
* cloud dependency
* vendor account dependency
* forced firmware update
* geofencing behavior
* no-fly-zone lockout
* safety return-to-home behavior
* automatic landing behavior
* beacon / signal signature
* unencrypted control link
* weak authentication
* proprietary black-box behavior
* supply-chain trust risk
* civilian compliance mismatch
* mission authority mismatch
* export / regulatory restriction
* audit / logging exposure
* data retention exposure

## Sub-items

* cots_risk_id
* linked agent / platform / mission / task
* vendor
* model / platform family
* firmware version
* compliance mode
* Remote ID status
* broadcast identity behavior
* broadcast location behavior
* controller-location exposure
* telemetry destination
* cloud dependency
* account dependency
* geofence behavior
* return-to-home behavior
* emergency landing behavior
* update dependency
* kill-switch / lockout risk
* data retention risk
* link encryption status
* authentication status
* vendor trust rating
* supply-chain trust rating
* legal / regulatory requirement
* command authority review requirement
* mission exposure score
* mitigation requirement
* fallback platform recommendation
* simulator test requirement
* reconstitution eligibility
* denial interaction
* WOPR recompile trigger

## Example

A COTS aerial platform may be safe and legal in civilian use but unsuitable for a contested mission branch because it broadcasts identifying information, depends on a vendor cloud account, or has a return-to-home behavior that could reveal a recovery site.

---

# PF-HUMAN-FACTORS

## Question

What human behaviors, habits, mistakes, fatigue, panic, arrogance, shortcuts, or procedural failures create mission risk or opportunity?

## Purpose

PF-HUMAN-FACTORS prevents the mission model from assuming that people are calm, rational, competent, disciplined, and predictable in the good way.

## Human factor categories

* fatigue
* hunger / dehydration
* panic
* overconfidence
* complacency
* shortcut behavior
* bunching / clustering
* poor dispersion
* repeated routes
* repeated launch / recovery locations
* poor camouflage
* phone / radio discipline failure
* overtrust of automation
* undertrust of automation
* delayed reaction
* bad local command judgment
* procedural drift
* failure to move after detection
* “it worked last time” bias
* failure to update mission state
* failure to report contradiction
* misread commander intent
* cognitive overload
* casualty shock
* grief / body-recovery fixation
* supply desperation

## Sub-items

* human_factor_id
* linked mission / agent / team / adversary / task
* behavior pattern
* friendly / adversary / civilian / unknown classification
* observed behavior
* predicted behavior
* evidence reference
* confidence
* risk created
* opportunity created
* likely trigger
* likely repeat pattern
* mitigation rule
* training / procedural note
* task constraint recommendation
* WOPR scoring effect
* simulator injection requirement
* human review requirement

## Example

If a friendly team is low on water and batteries, PF-HUMAN-FACTORS should assume judgment and discipline may degrade. PF-SUSTAINMENT is not “nice to have”; it affects mission behavior.

---

# PF-DENIAL

## Question

What must be denied to the adversary if an agent is tracked, compromised, captured, or unable to return safely?

## Purpose

PF-DENIAL prevents mission success from creating strategic exposure. It handles follow-home risk, capture risk, base exposure, sensitive data protection, compromised hardware, and adversary exploitation.

## Sub-items

* denial_id
* linked agent / task / mission
* sensitive hardware risk
* sensitive data risk
* base exposure risk
* recovery site exposure risk
* route exposure risk
* RF signature trail risk
* tracking / follow-home risk
* capture likelihood
* compromise likelihood
* adversary exploitation value
* zeroization rules
* data deletion rules
* credential / key revocation rules
* diversion behavior
* alternate recovery behavior
* abandon behavior
* dead-drop behavior
* decoy behavior
* self-neutralization rules
* self-destruct rules, if applicable and authorized
* human approval requirement
* denial evidence requirements
* denial completion proof

## Example

If a drone is being followed, PF-DENIAL may forbid returning to base and instead require diversion, alternate recovery, credential zeroization, or abandonment behavior.

---

# PF-MISSION

## Question

What are we trying to accomplish, even if the plan is loose, incomplete, exploratory, or expected to change?

## Purpose

PF-MISSION is the mission package. It includes intent, objectives, plan level, constraints, resources, authorities, update rules, success criteria, fallback logic, evidence requirements, sustainment assumptions, casualty-recovery rules, and support requirements.

A plan tells agents what sequence to try.
A mission tells agents what still matters when the sequence fails.

## Mission modes

* planned mission
* exploratory mission
* reconnaissance mission
* assistance mission
* standby mission
* support-on-call mission
* patrol mission
* presence mission
* search mission
* humanitarian / recovery mission
* opportunistic mission
* investigate-and-report mission
* go-there-and-assess mission
* “see if anybody needs you” mission

## Sub-items

* mission_id
* mission name
* mission mode
* planning level
* commander intent
* mission objective
* mission scope
* mission area
* mission phase
* mission priority
* mission start condition
* mission end condition
* success criteria
* failure criteria
* abort criteria
* plan summary
* plan_required flag
* discovery goals
* unknowns to resolve
* task list
* candidate task list
* role requirements
* agent requirements
* timing requirements
* energy requirements
* logistics requirements
* sustainment requirements
* food / water support assumptions
* battery / fuel support assumptions
* ammunition / controlled consumable assumptions
* medical supply assumptions
* attrition assumptions
* attrition thresholds
* reconstitution assumptions
* replacement policy
* onboarding policy
* casualty recovery policy
* remains recovery policy
* “recover if on the way” policy
* COTS risk assumptions
* COTS approval requirements
* human-factor assumptions
* communications requirements
* evidence requirements
* denial requirements
* fires-support assumptions
* fires-support approval requirements
* authority rules
* escalation rules
* fallback rules
* update rules
* operator console access rules
* WOPR recommendation reference
* human approval state
* mission version
* mission package signature
* mission expiration
* last known good mission version

## Example

“Go over there and see if anybody needs you” becomes: move to area, observe, identify support needs, report new needs, assist if authorized, do not self-escalate beyond authority, return or standby if no useful action exists.

---

# PF-COMMAND-AUTHORITY

## Question

Who can issue, modify, constrain, prioritize, append, delegate, or override mission instructions?

## Purpose

PF-COMMAND-AUTHORITY preserves layered commander intent by tracking who may create, modify, prioritize, constrain, delegate, or override mission instructions at each level of command.

## Command types

* binding order
* constraint
* priority
* request
* local opportunity
* emergency override
* mission append
* mission abort
* delegation
* authorization exception
* support request
* sustainment request
* casualty recovery request
* remains recovery request
* humanitarian / recovery request
* fires-support request
* fires-support approval
* fires-support denial
* reconstitution approval
* node quarantine order
* node retirement order

## Sub-items

* authority_id
* issuing authority
* issuer identity
* issuer rank / role / command level
* command scope
* mission scope
* geographic scope
* time scope
* affected agents / teams
* affected roles
* affected tasks
* authority type
* create mission permission
* modify mission permission
* add task permission
* change priority permission
* constrain behavior permission
* authorize exception permission
* abort mission permission
* override lower command permission
* request support permission
* approve support permission
* deny support permission
* approve sustainment permission
* approve casualty recovery permission
* approve reconstitution permission
* quarantine node permission
* retire node permission
* delegate authority permission
* COTS risk acceptance permission
* regulatory exception review
* priority level
* binding / advisory / request status
* conflict behavior
* override rules
* delegation rules
* expiration
* authentication
* human approval requirement
* audit trail
* reason / commander intent link

## Example

A sergeant can say “bring batteries and food if you are already coming this way,” but PF-COMMAND-AUTHORITY decides whether that is a binding order, a local support request, or an opportunistic task candidate.

---

# PF-FIRES

## Question

How are support effects requested, authorized, deconflicted, coordinated, assessed, and updated?

## Purpose

PF-FIRES manages support-effect coordination. It covers requests for external support, target-of-opportunity nomination, suppression requests, smoke, illumination, electronic effects, and other support actions in a way that remains bounded by commander intent, authority, deconfliction, evidence, and human approval requirements.

PF-FIRES is not a license for autonomous agents to self-authorize lethal fires. It is the coordination and control layer for requesting, approving, deconflicting, simulating, and assessing support effects.

## Support/effect categories

* artillery support request
* mortar support request
* rocket support request
* close air support request
* naval fires request
* missile support request
* loitering-effect request
* electronic warfare effect
* smoke
* illumination
* suppression
* obscuration
* marking
* decoy / deception effect
* target-of-opportunity nomination
* emergency support request
* denied / unavailable support
* simulated support effect

## Sub-items

* fires_id
* linked mission
* linked task
* linked awareness item
* linked evidence item
* requesting agent / team / commander
* request type
* support category
* intended effect
* target candidate / effect area reference
* evidence confidence
* target-of-opportunity flag
* suppression request flag
* urgency
* timing window
* duration requirement
* deconfliction requirement
* friendly-force proximity concern
* civilian / noncombatant concern
* restricted area concern
* collateral risk concern
* authority requirement
* human approval requirement
* approval status
* denial reason
* support availability
* support provider reference
* communications requirement
* abort / cancel condition
* effect assessment requirement
* post-effect evidence requirement
* WOPR branch scoring effect
* simulator hook reference
* audit log reference

## Example

A local scout nominates a support request. PF-EVIDENCE must support it. PF-COMMAND-AUTHORITY must approve it. PF-TASK-CONSTRAINT must check deconfliction. PF-STATE records the final status.

---

# PF-AGENT

## Question

Who or what is participating?

## Purpose

PF-AGENT represents any participating mission actor: drone, sensor, camera, RF receiver, relay, logistics node, sustainment node, ground station, operator console, simulated AI agent, software service, or human-in-the-loop station.

## Sub-items

* agent_id
* agent type
* agent name
* owner / operator
* trust level
* authentication state
* platform class
* COTS / custom / military / simulated status
* vendor / model reference
* firmware version
* compliance mode
* expendable / attritable / recoverable status
* reconstitution status
* onboarding status
* probationary status
* sustainment role
* casualty recovery role
* current role
* allowed roles
* current task
* assigned mission
* current location
* current energy
* health status
* comms status
* sensor status
* payload / cargo status
* capability references
* comms references
* logistics status
* sustainment status
* casualty recovery status
* attrition status
* COTS risk status
* denial status
* fires support eligibility
* local inference control profile
* authority level
* peer relationships
* team membership
* handoff partners
* fallback peers
* compromise indicators
* isolation state
* last update timestamp
* stale-after time

## Example

A guy with a laptop, a ground robot carrying batteries, a drone scout, and a supply vehicle can all be PF-AGENTS. They do different work and require different authority.

---

# PF-ROLE

## Question

What job is an agent currently assigned?

## Purpose

PF-ROLE defines the behavior envelope for an agent inside a mission. It keeps agents role-coherent and prevents uncontrolled improvisation.

## Sub-items

* role_id
* role name
* role purpose
* compatible agent types
* required capabilities
* required comms
* sustainment permission
* casualty recovery permission
* reconstitution eligibility
* COTS risk tolerance
* attrition tolerance
* redundancy requirement
* fires-support observation permission
* fires-support request permission
* fires-support approval permission
* allowed actions
* forbidden actions
* expected inputs
* expected outputs
* task compatibility
* authority limits
* local inference limits
* evidence responsibilities
* communication responsibilities
* handoff rules
* escalation rules
* failure behavior
* denial behavior
* role exit conditions
* role reassignment conditions

## Example

A “support runner” role may carry batteries, water, or medical supplies. A “scout” may identify a need but not automatically become a supply carrier if it lacks payload capacity or authority.

---

# PF-TASK

## Question

What specific work item must be done, discovered, checked, supported, or offered?

## Purpose

PF-TASK turns the mission into executable chunks. Tasks are specific enough for agents to perform locally but bounded enough to preserve commander intent.

## Task types

* observe
* assess
* inspect
* search
* assist
* standby
* escort
* relay
* resupply
* deliver batteries
* deliver food / water
* deliver medical supplies
* deliver controlled consumables
* retrieve wounded if authorized
* recover remains if authorized
* report need
* nominate support request
* request re-tasking
* hold position
* return if unused

## Sub-items

* task_id
* parent mission_id
* task name
* task purpose
* task type
* assigned role
* assigned agent / team
* required capabilities
* required comms
* allowed COTS risk level
* sustainment dependency
* casualty recovery dependency
* attrition assumption
* replacement / redundancy assumption
* reconstitution dependency
* fires-support dependency
* task priority
* start condition
* activation trigger
* success condition
* failure condition
* abort condition
* timing window
* deadline
* location / sector
* energy budget
* logistics requirement
* evidence requirement
* denial requirement
* communication requirement
* handoff requirement
* escalation rule
* fallback task
* task status
* task version
* task expiration

## Example

“Deliver batteries to Relay Team 2 before relay uptime drops below 20 minutes” is a PF-TASK driven by PF-SUSTAINMENT.

---

# PF-TASK-CONSTRAINT

## Question

What limits apply to that task?

## Purpose

PF-TASK-CONSTRAINT makes task boundaries machine-checkable. It converts commander intent, doctrine, safety, timing, energy, evidence, authority, trust, comms, logistics, sustainment, casualty recovery, attrition, reconstitution status, COTS exposure, fires-support limits, and denial limits into explicit rules.

## Constraint types

* energy
* timing
* authority
* safety
* evidence
* comms
* logistics
* sustainment
* casualty recovery
* attrition
* reconstitution
* COTS risk
* human factors
* fires support
* trust
* doctrine
* denial
* route
* role coherence
* human approval
* adversary risk

## Sub-items

* constraint_id
* parent task_id
* constraint type
* constraint scope
* rule statement
* threshold
* hard / soft status
* enforcement level
* violation condition
* violation behavior
* escalation behavior
* human approval requirement
* override permission
* evidence requirement
* timing requirement
* energy requirement
* comms requirement
* logistics requirement
* sustainment requirement
* casualty recovery requirement
* attrition requirement
* reconstitution requirement
* COTS risk requirement
* fires-support requirement
* denial requirement
* authority requirement
* source of constraint
* constraint version
* constraint expiration

## Example

“Recover remains only if the recovery does not violate higher-priority mission constraints or requires authorized approval.”
“Deliver controlled consumables only to authenticated friendly recipients.”

---

# PF-COMMAND-MESH

## Question

How do participants coordinate, hand off, escalate, and survive degraded comms?

## Purpose

PF-COMMAND-MESH is the decentralized coordination layer. It lets agents form local teams, exchange state, negotiate handoffs, continue under degraded comms, and remain aligned without requiring constant central control.

## Sub-items

* mesh_id
* participating agents
* team membership
* local command cell
* peer links
* link quality references
* comms references
* trust state
* authority distribution
* mission package distribution
* local consensus rules
* disagreement rules
* handoff rules
* escalation path
* fallback path
* degraded comms mode
* comms partition behavior
* sustainment request routing
* casualty recovery request routing
* local continuation rules
* local stop rules
* compromise isolation rules
* rogue-agent suppression rules
* attrition response rules
* minimum viable team rules
* reconstitution admission rules
* candidate-node admission rules
* COTS risk sharing
* fires-support request routing
* message format
* message priority
* message authentication
* message replay protection
* last known good state
* resync behavior

## Example

If a team needs batteries and the central planner is unreachable, PF-COMMAND-MESH can route the request locally under last-known-good authority rules.

---

# PF-OPERATOR-CONSOLE

## Question

How does a human operator, ground station, forward-deployed controller, special operator, or laptop user observe, understand, query, approve, and safely interact with the mesh?

## Purpose

PF-OPERATOR-CONSOLE is the human-facing view into the live polycentric federated system.

## Sub-items

* console_id
* operator identity
* operator role
* operator authority level
* authentication state
* mission access scope
* current PF-STATE view
* current PF-AWARENESS view
* current PF-EVIDENCE view
* current PF-COMMAND-MESH view
* current PF-COMMS view
* current PF-AGENT view
* current PF-TASK view
* current PF-SUSTAINMENT view
* current PF-CASUALTY-RECOVERY view
* current PF-FIRES view
* current PF-LOGISTICS view
* current PF-ATTRITION view
* current PF-RECONSTITUTION view
* current PF-DENIAL view
* current PF-WOPR recommendation view
* alerts
* warnings
* contradictions
* stale-state warnings
* degraded-comms warnings
* casualty recovery warnings
* sustainment shortage warnings
* compromised-agent warnings
* COTS exposure warnings
* attrition threshold warnings
* reconstitution pending warnings
* fires-support pending warnings
* human approval queue
* mission update queue
* local action options
* allowed operator actions
* forbidden operator actions
* escalation options
* audit log
* operator notes
* evidence attachments
* message history
* last-known-good state
* sync status
* offline package status
* CPIP package status

## Example

A guy with a laptop sees: “Team 3 low on water, Relay 2 needs batteries, Scout 4 missing, casualty recovery pending, support request awaiting approval.”

---

# PF-CPIP

## Question

How do mission updates physically reach agents or local cells when electronic command paths are denied, jammed, compromised, or unavailable?

## Purpose

PF-CPIP is the last-resort physical / delay-tolerant update channel. It supports mission packages, keys, policy changes, recovery instructions, abort orders, node trust lists, and other updates when electronic command paths are unavailable or untrusted.

## Sub-items

* cpip_package_id
* package type
* mission update bundle
* key update bundle
* policy update bundle
* firmware / software update bundle
* recovery instruction bundle
* casualty recovery instruction bundle
* sustainment instruction bundle
* abort instruction bundle
* map / threat update bundle
* reconstitution instruction bundle
* node trust-list update
* compromised-node list
* last-known-good rollback bundle
* physical carrier method
* courier chain
* custody chain
* tamper-evident seal
* package authentication
* digital signature
* replay protection
* expiration time
* one-time-use credentials
* limited-use credentials
* receiving agent list
* distribution instructions
* verification instructions
* failure behavior
* fallback behavior
* receipt proof
* local redistribution permission

## Example

A physical update package can carry new tasking, updated trust lists, battery shortage data, casualty recovery instructions, and last-known-good mission fallback.

---

# PF-WOPR-RISK

## Question

How can the strategic planning / recompilation layer be degraded, deceived, isolated, overloaded, or poisoned, and what fallback mode preserves mission control?

## Purpose

PF-WOPR-RISK prevents the mission from becoming dependent on a fragile planning engine. It identifies attacks or failures against PF-WOPR and defines fallback behavior.

## Sub-items

* wopr_risk_id
* affected WOPR function
* degradation type
* deception risk
* evidence poisoning risk
* awareness poisoning risk
* telemetry loss risk
* comms isolation risk
* branch explosion risk
* timing pressure risk
* model mismatch risk
* resource deception risk
* sustainment model failure risk
* casualty recovery model failure risk
* attrition model failure risk
* reconstitution model failure risk
* COTS model mismatch risk
* human-factor model failure risk
* fires-support model failure risk
* dashboard manipulation risk
* compromised feedback loop risk
* operator overtrust risk
* stale branch risk
* stale mission package risk
* risk evidence
* risk confidence
* mission impact
* fallback behavior
* local-only mode trigger
* last-good-mission trigger
* human review trigger
* WOPR quarantine trigger
* resync requirement
* recovery action

## Example

If WOPR underestimates battery depletion or ignores food/water state, it can produce fantasy branches. PF-WOPR-RISK flags that.

---

# PF-WOPR

## Question

What should the mission become now that the situation has changed?

## Purpose

PF-WOPR is the computer-assisted mission planner and mission-update engine. It helps create, test, compare, update, and recompile mission packages. It does not micromanage every local action and must not become a central execution dependency.

## Sub-items

* WOPR mission workspace
* commander intent input
* mission draft generator
* loose mission generator
* mission branch generator
* branch simulator
* branch comparison engine
* risk scoring
* energy scoring
* timing scoring
* logistics scoring
* sustainment scoring
* casualty recovery scoring
* attrition scoring
* reconstitution scoring
* COTS risk scoring
* human factors scoring
* fires-support scoring
* denial scoring
* evidence confidence scoring
* authority conflict scoring
* comms survivability scoring
* adversary model input
* environment model input
* mission recompile trigger
* mission update recommendation
* PF-MISSION output
* PF-TASK output
* PF-TASK-CONSTRAINT output
* PF-SUSTAINMENT recommendation output
* PF-CASUALTY-RECOVERY recommendation output
* PF-RECONSTITUTION recommendation output
* PF-FIRES recommendation output
* PF-COMMAND-MESH distribution instruction
* PF-CPIP package recommendation
* explanation output
* human approval workflow
* rejected branch log
* selected branch log
* last-known-good branch
* simulator integration reference
* WOPR confidence level
* WOPR stale-state warning

## Example

WOPR sees that the current branch is failing because batteries are depleted, a team needs water, one operator is missing, and a relay is degraded. It recommends a revised mission package and support priority list.

---

# PF-SIM-HOOKS

## Question

How does the architecture connect to simulation, replay, scoring, failure injection, branch comparison, and WOPR recompilation?

## Purpose

PF-SIM-HOOKS makes the architecture testable. Since DICE is simulation-centered, this layer defines how PF objects connect to external simulators, internal simulators, replay engines, scoring tools, and WOPR branch tests.

## Sub-items

* simulator input format
* simulator output format
* scenario definition
* scenario injection
* initial state load
* agent spawn
* agent despawn
* agent behavior interface
* mission package import
* mission update export
* event replay
* telemetry export
* score collection
* branch comparison
* failure injection
* sustainment shortage injection
* battery depletion injection
* food / water shortage injection
* ammunition shortage injection
* medical supply shortage injection
* casualty injection
* missing-person injection
* remains recovery injection
* attrition injection
* reconstitution injection
* replacement-node injection
* untrusted-node injection
* COTS exposure injection
* human-factor injection
* fires-support availability injection
* fires-support denial injection
* simulated support-effect injection
* Remote ID exposure injection
* jamming injection
* comms partition injection
* rogue-agent injection
* compromised-agent injection
* sensor spoofing injection
* weather change injection
* threat movement injection
* logistics failure injection
* energy depletion injection
* command authority conflict injection
* CPIP delay injection
* WOPR recompile trigger
* PF-STATE synchronization
* run summary
* evidence replay bundle
* metrics output

## Example

A simulator run injects 40% drone attrition, a battery shortage, a wounded friendly, a body recovery request, an ammo resupply request, degraded comms, and an unavailable support route. PF-SIM-HOOKS records whether the mesh still behaves coherently.

---

# PF-STATE

## Question

What is currently true across all of the above?

## Purpose

PF-STATE is the live state layer. It records current values, updates, timestamps, confidence, source, and staleness across every PF domain.

## Sub-items

* state_id
* subject type
* subject_id
* state type
* current value
* prior value
* value change
* confidence
* source
* timestamp
* stale-after time
* expiration time
* linked evidence
* linked awareness
* linked capabilities item
* linked comms item
* linked logistics item
* linked sustainment item
* linked casualty recovery item
* linked attrition item
* linked reconstitution item
* linked COTS risk item
* linked human-factor item
* linked denial item
* linked mission
* linked command authority item
* linked fires item
* linked agent
* linked role
* linked task
* linked constraint
* linked operator console item
* linked command mesh item
* linked CPIP item
* linked WOPR item
* linked WOPR risk item
* linked sim run
* contradiction flag
* degraded flag
* compromised flag
* missing flag
* presumed lost flag
* captured-risk flag
* sustainment-shortage flag
* casualty-recovery-pending flag
* COTS exposure flag
* reconstitution-pending flag
* probationary-node flag
* fires-support pending flag
* fires-support denied flag
* human review flag
* state version
* last-known-good value

## State categories

* mission state
* agent state
* role state
* task state
* constraint state
* awareness state
* evidence state
* capability state
* comms state
* logistics state
* sustainment state
* casualty recovery state
* attrition state
* reconstitution state
* COTS risk state
* human factors state
* denial state
* command authority state
* fires-support state
* operator console state
* command mesh state
* CPIP state
* WOPR state
* WOPR risk state
* simulator state

## Example

PF-STATE says Team 2 is low on water, Relay 4 needs batteries, Agent 7 is missing, a casualty recovery request is pending, and the local operator is authorized to approve a support reroute.

---

# Implementation Path

The PF stack is not just vocabulary. It must become machine-readable and enforceable.

## Minimum viable implementation

1. JSON schemas / Pydantic models
2. Validators
3. Mission update messages
4. Agent state messages
5. Constraint checks
6. Simple rule engine
7. Simulator hooks
8. Logs / evidence trail

## Architecture stack

```text
PF vocabulary
      ↓
JSON / Pydantic schemas
      ↓
Rule validators
      ↓
Agent local inference control
      ↓
PF-COMMAND-MESH messages
      ↓
PF-STATE updates
      ↓
PF-WOPR mission recompile
      ↓
PF-SIM-HOOKS test environment
```

## Key relationships

```text
PF-COMMS = the pipes.
PF-COMMAND-MESH = command behavior over the pipes.
PF-CPIP = last-resort physical / delay-tolerant update pipe.
PF-CAPABILITIES = what agents can do with available pipes and tools.
```

```text
PF-LOGISTICS = move, store, recover, transport, resupply.
PF-SUSTAINMENT = food, water, batteries, ammo, spares, maintenance, consumables.
PF-CASUALTY-RECOVERY = wounded, dead, missing, stranded, evacuation, remains recovery.
PF-ATTRITION = expected and acceptable losses.
PF-RECONSTITUTION = safely rebuild live mission capability.
PF-COTS-RISK = commercial/default/compliance exposure.
PF-HUMAN-FACTORS = human behavior risk/opportunity.
PF-DENIAL = prevent loss from becoming enemy advantage.
```

```text
PF-MISSION = what matters, even when the plan is incomplete.
PF-COMMAND-AUTHORITY = who can change what matters.
PF-FIRES = support-effect request, approval, deconfliction, and assessment.
PF-TASK = what work must happen or be discovered.
PF-TASK-CONSTRAINT = what boundaries apply.
PF-STATE = what is currently true.
```

```text
PF-WOPR = plans and updates the mission.
PF-WOPR-RISK = prevents WOPR from becoming a fragile dependency.
PF-OPERATOR-CONSOLE = human visibility and authorized interaction.
PF-COMMAND-MESH = survives locally when WOPR is unavailable.
```

---

# Appendix A: The Real Drone AI Zoo

This appendix explains the real-world non-LLM AI and autonomy systems that university robotics and drone labs often work on.

The main point:

A drone lab usually does not have “one AI.” It has many specialized autonomy components. Some keep the aircraft stable. Some help it know where it is. Some interpret sensor data. Some plan paths. Some coordinate multiple drones. Some simulate failure before anyone risks hardware.

LLMs, or large language models, are not the core drone AI. They are mostly useful as human-interface tools: translating messy human orders, summarizing state, explaining logs, and helping operators understand what the autonomy stack is doing.

---

## Quick Glossary for the Acronyms and Lab Names

### AI

Artificial Intelligence. In this document, “AI” does not only mean chatbots. It includes control algorithms, perception models, planners, optimizers, trackers, simulators, and decision systems.

### LLM

Large Language Model. A model like ChatGPT, Claude, Gemini, or Llama that works mainly with language. Good for interpreting text, generating explanations, summarizing evidence, and turning messy human instructions into structured mission objects.

### UAV

Unmanned Aerial Vehicle. A drone aircraft.

### UAS

Unmanned Aircraft System. The drone plus the controller, communications, sensors, ground station, software, operator procedures, and support equipment. UAS is the broader system; UAV is just the aircraft.

### MIT

Massachusetts Institute of Technology. Major technical university in Cambridge, Massachusetts.

### MIT ACL

MIT Aerospace Controls Laboratory. A research lab at MIT that works on autonomy, control, planning, estimation, navigation, and task assignment for aerospace systems, including drones and other autonomous vehicles.

### Penn

University of Pennsylvania. Major research university in Philadelphia.

### Penn GRASP

University of Pennsylvania GRASP Laboratory. GRASP stands for General Robotics, Automation, Sensing, and Perception. It is a major robotics lab known for drone swarms, autonomous robots, perception, control, and multi-robot systems.

### Kumar Lab

A robotics lab at the University of Pennsylvania associated with Vijay Kumar. It is well known for work on aerial robots, swarms, coordination, and autonomous robotic systems.

### CMU

Carnegie Mellon University. Major research university in Pittsburgh with one of the strongest robotics programs in the world.

### CMU Robotics Institute

A major robotics research institute at Carnegie Mellon University. It works on many areas of robotics, including perception, autonomy, mapping, navigation, planning, and field robotics.

### CMU AirLab

A Carnegie Mellon robotics lab focused on aerial autonomy. Plain English: drone intelligence, drone perception, drone navigation, and drone planning.

### CMU Robot Perception Lab

A Carnegie Mellon lab focused on helping robots understand where they are and what the world around them looks like.

### MIT Lincoln Laboratory

A federally funded research and development center affiliated with MIT. It works on advanced defense, aerospace, communications, sensing, autonomy, and national-security technology.

### PID Control

Proportional-Integral-Derivative control. A classic control method that constantly corrects error. Plain English: “I am too low, raise throttle; I am drifting, correct; I overshot, back off.” It is simple, old, and everywhere.

### Model Predictive Control

A control method that predicts near-future states and chooses actions that keep the system on track. Plain English: “Before I move, I simulate the next few moments and choose the best control input.”

### Adaptive Control

A control method that adjusts itself when conditions change. Plain English: “The drone behaves differently because of wind, damage, payload, or battery sag, so the controller adapts.”

### Robust Control

Control designed to keep working even when the model is imperfect or conditions are noisy. Plain English: “The math is not exactly right, but the drone should still stay under control.”

### Nonlinear Control

Control for systems where simple straight-line math does not describe behavior well. Drones are nonlinear because tilt, thrust, drag, weight, rotation, and momentum interact in messy ways.

### State Estimation

The process of estimating the drone’s current state: position, speed, orientation, altitude, and sometimes health. Plain English: “Where am I, how fast am I moving, and which way am I pointing?”

### Localization

Figuring out where the robot is in the world or in a map. Plain English: “Where am I?”

### SLAM

Simultaneous Localization and Mapping. Plain English: “Build a map while also figuring out where I am inside that map.” This matters when GPS is missing, jammed, unreliable, or too crude.

### Visual-Inertial Odometry

A method that combines camera data with inertial sensor data to estimate motion. Plain English: “Use what the camera sees plus motion sensors to figure out how the drone is moving.”

### IMU

Inertial Measurement Unit. A sensor package that usually includes accelerometers and gyroscopes. Plain English: “The drone’s inner ear.” It senses acceleration and rotation.

### GPS

Global Positioning System. Satellite positioning. Plain English: “Where am I on Earth?” Useful, but can be blocked, spoofed, degraded, or unavailable indoors.

### GPS-Denied Navigation

Navigation without relying on GPS. Plain English: “The drone still knows where it is even when satellite positioning is gone or untrusted.”

### Sensor Fusion

Combining multiple sensors to get a better estimate than any one sensor alone. Plain English: “Camera says one thing, IMU says another, lidar says another; combine them into one best guess.”

### Lidar

Light Detection and Ranging. A sensor that uses laser pulses to estimate distance and shape. Plain English: “Laser radar for building a 3D picture.”

### Radar

Radio Detection and Ranging. Uses radio waves to detect objects, distance, and motion.

### RF

Radio Frequency. Radio signals used for communication, control links, detection, or electronic sensing. RF classification means analyzing radio signals to infer what they are.

### Thermal Detection

Detecting heat signatures. Useful for people, vehicles, animals, engines, fires, and warm equipment.

### Semantic Segmentation

Computer vision that labels parts of an image by category. Plain English: “This pixel is road, this pixel is tree, this pixel is person, this pixel is sky.”

### Object Detection

Computer vision that finds objects in images or video. Plain English: “There is a person here, a truck there, a drone over there.”

### Depth Estimation

Estimating distance from camera or sensor data. Plain English: “How far away is that thing?”

### A*

A-star. A classic pathfinding algorithm. Plain English: “Find a good route from here to there without searching every possible route.”

### RRT

Rapidly-Exploring Random Tree. A motion-planning algorithm that explores possible paths by sampling. Plain English: “Grow many possible route branches through space until one reaches the goal.”

### RRT*

An improved version of RRT that tries to optimize the path over time. Plain English: “Like RRT, but keeps improving the route instead of just finding any route.”

### Trajectory Optimization

Choosing a smooth, physically possible path through time. Plain English: “Not just where to go, but how to fly there without impossible turns, crashes, or wasted energy.”

### Motion Planning

Planning how a robot moves from one state to another while obeying physical limits and avoiding obstacles.

### Sampling-Based Planning

Planning by trying many possible paths or states and keeping the ones that work. Useful in complicated spaces.

### Multi-Fidelity Planning

Using rough cheap models first, then more detailed expensive models when needed. Plain English: “Sketch the route fast, then check the serious details.”

### Informative Path Planning

Planning paths that gather useful information, not just paths that reach a destination. Plain English: “Fly where you will learn the most.”

### Assignment Optimization

Choosing which agent should do which job. Plain English: “Drone 1 scouts, Drone 2 relays, Robot 3 carries batteries.”

### Decision-Making Under Uncertainty

Choosing actions when the system does not know everything. Plain English: “We are only 70% sure what is happening; what should we do anyway?”

### Swarm Robotics

Many robots coordinating as a group. Plain English: “The team behavior matters more than any single robot.”

### Formation Control

Keeping multiple robots in a shape or arrangement. Plain English: “Stay spread out like this.”

### Distributed Coordination

Coordination without one central boss controlling every move. Plain English: “Each node makes local decisions while staying aligned with the group.”

### Consensus

A method by which distributed agents agree on a value, decision, or shared state. Plain English: “Do we agree this is the current mission state?”

### Flocking

Bio-inspired group movement, like birds or fish. Plain English: “Move together without colliding or scattering.”

### Coverage Control

Positioning robots so they cover an area well. Plain English: “Spread out so the whole area is watched.”

### 3D Reconstruction

Building a three-dimensional model from sensor data. Plain English: “Turn drone video or lidar into a 3D picture of the place.”

### Occupancy Grid

A map divided into cells showing what space is free, blocked, or unknown. Plain English: “This square is empty, this square has an obstacle, this square is unknown.”

### NeRF

Neural Radiance Field. A machine-learning method for reconstructing 3D scenes from images. Plain English: “Use many camera views to make a 3D-ish visual model.”

### Gaussian Splatting

A newer 3D scene reconstruction method using many fuzzy 3D points. Plain English: “Build a fast 3D visual scene from many camera observations.”

### Change Detection

Finding what changed between observations. Plain English: “That vehicle was not there before.”

### Multi-Object Tracking

Tracking multiple objects over time. Plain English: “Keep IDs on many moving things at once.”

### Kalman Filter

A classic math method for estimating state under noise. Plain English: “Predict where the thing should be, compare to noisy measurements, update the best guess.”

### Particle Filter

A state-estimation method that tracks many possible guesses. Plain English: “Maintain a cloud of guesses and see which guesses survive the evidence.”

### Trajectory Prediction

Predicting where something is likely to go next.

### Reinforcement Learning

A learning method where an agent improves by trial and error using rewards. Plain English: “Try stuff in simulation, get rewarded for good behavior, learn a policy.”

### Imitation Learning

Learning by copying examples. Plain English: “Watch a good pilot or planner and learn to behave similarly.”

### Sim-to-Real Transfer

Training in simulation and then moving the learned behavior to real hardware. Plain English: “Practice in a fake world, then hope it works on the real drone.”

### Policy Learning

Learning a decision rule. Plain English: “Given what I see, what action should I take?”

### Deep RL

Deep Reinforcement Learning. Reinforcement learning using neural networks. Plain English: “Trial-and-error learning with a big learned model inside.”

### Fault Detection

Detecting that something is wrong. Plain English: “A motor, sensor, battery, propeller, link, or controller is failing.”

### Diagnostics

Figuring out what kind of failure is happening.

### Health Monitoring

Continuously watching system health. Plain English: “Is the drone still okay?”

### Anomaly Detection

Detecting unusual behavior. Plain English: “This does not look normal.”

### Resilient Autonomy

Autonomy that keeps functioning under failure, damage, degraded sensors, lost comms, or hostile conditions.

### Mesh Networking

A network where nodes can relay messages through each other instead of relying on one central tower. Plain English: “If I cannot reach HQ, maybe I can reach another node that can.”

### Relay Selection

Choosing which node should pass messages along.

### Adaptive Communication

Changing communication behavior based on link quality, jamming, latency, bandwidth, or mission priority.

### Network-Aware Planning

Planning movement and tasks while considering communication quality. Plain English: “Do not fly somewhere if you will lose the network unless the mission allows it.”

### Delay-Tolerant Networking

Networking that works even when messages are delayed, intermittent, or carried physically. Plain English: “The message might arrive later, but the system can still use it.”

### Human-Robot Interaction

How humans and robots communicate, supervise each other, share control, and build trust.

### Supervisory Control

A human supervises multiple robots or autonomous systems instead of manually steering every action.

### Mixed-Initiative Autonomy

Both human and machine can propose actions. Plain English: “The AI suggests, the human approves, or the human asks and the AI helps.”

### Explainable Autonomy

Autonomy that can explain what it is doing and why.

### Operator Workload

How mentally overloaded the human operator is. Important because one person may be supervising many systems.

### Gazebo

A robotics simulator often used with ROS. Plain English: “A fake world where robots can be tested.”

### AirSim

A simulator originally developed by Microsoft for drones and autonomous vehicles.

### Isaac Sim

NVIDIA’s robotics simulator. Used for synthetic data, robot testing, and simulation.

### ROS

Robot Operating System. Not really an operating system like Windows. It is a common robotics software framework for connecting sensors, controllers, planners, and robot software modules.

### Digital Twin

A simulated version of a real system. Plain English: “A fake copy of the mission world or robot used for testing and prediction.”

### Hardware-in-the-Loop

Testing where real hardware is connected to a simulation. Plain English: “Some parts are real, some parts are fake, so you can test safely.”

### Software-in-the-Loop

Testing where the real software runs inside simulation before it touches real hardware.

---

## 1. Flight Control AI / Control Algorithms

This is the stuff that keeps the drone stable and flying.

Not sexy, but mandatory.

Examples:

```text
keep level
hold altitude
reject wind gusts
follow a trajectory
land smoothly
recover from disturbance
```

Keywords you’ll hear:

```text
PID control
model predictive control
adaptive control
robust control
nonlinear control
```

Plain English:

Flight control is the “do not fall out of the sky” layer. It is usually not an LLM. It is control math, real-time software, and sensor feedback. If this layer fails, the mission is over because the aircraft crashes.

MIT’s Aerospace Controls Laboratory, often shortened to MIT ACL, works on robust control, adaptive control, model predictive control, estimation, navigation, planning, and task assignment for autonomous systems.

---

## 2. State Estimation / Localization AI

This answers:

```text
Where am I?
How fast am I moving?
What direction am I facing?
Can I still know that without GPS?
```

This is huge for drones.

Keywords:

```text
state estimation
SLAM — simultaneous localization and mapping
visual-inertial odometry
sensor fusion
GPS-denied navigation
localization
mapping
```

Plain English:

This is the drone’s self-awareness layer. It tries to know where the drone is, how it is moving, and what its local map looks like. Without this, the drone may technically fly but not know where it is going.

Penn GRASP means the University of Pennsylvania’s General Robotics, Automation, Sensing, and Perception Laboratory. Penn GRASP’s autonomous micro-UAV work describes onboard sensors and processors for state estimation, control, and planning, using sensors like IMUs, cameras, laser range scanners, altimeters, and GPS.

CMU means Carnegie Mellon University. CMU’s Robot Perception Lab focuses on localization, mapping, and state estimation for autonomous mobile robots.

---

## 3. Perception AI

This is camera, radar, lidar, RF, audio, and thermal interpretation.

It answers:

```text
What am I seeing?
Is that a person?
Is that a vehicle?
Is that a powerline?
Is that a landing zone?
Is that another drone?
```

Keywords:

```text
computer vision
object detection
semantic segmentation
depth estimation
terrain classification
RF classification
thermal detection
```

Plain English:

Perception is the “turn raw sensor junk into useful objects” layer. The camera does not naturally know it is looking at a truck. Perception AI turns pixels, radio signals, lidar points, heat blobs, or radar returns into labeled observations.

CMU AirLab is a Carnegie Mellon aerial robotics lab. It develops and tests perception and planning algorithms for unmanned air vehicles, meaning drones.

---

## 4. Obstacle Avoidance AI

This is the “do not hit the tree, wall, wire, tower, tunnel equipment, or other drone” layer.

Keywords:

```text
collision avoidance
dynamic obstacle avoidance
local planning
reactive planning
safe trajectory generation
```

Plain English:

Obstacle avoidance is different from broad mission planning. Mission planning says “go to Sector C.” Obstacle avoidance says “do not slam into that pole while going there.”

MIT ACL has specific UAV work on real-time planning and obstacle avoidance for agile flight in unknown environments. MIT and Penn researchers have also worked on trajectory planning that lets UAVs react to obstacles in milliseconds while staying on smooth flight paths.

---

## 5. Path Planning / Trajectory Planning AI

This answers:

```text
How do I get from here to there?
What route minimizes risk?
What path conserves battery?
What path keeps sensor coverage?
```

Keywords:

```text
A* — A-star pathfinding
RRT — rapidly-exploring random tree
RRT* — optimized rapidly-exploring random tree
trajectory optimization
motion planning
sampling-based planning
multi-fidelity planning
informative path planning
```

Plain English:

Path planning chooses a route. Trajectory planning turns that route into a physically flyable motion. A route can say “go around the building.” A trajectory says exactly how the aircraft changes speed, angle, altitude, and timing without crashing or wasting too much energy.

This is one of the core university-drone buckets. MIT ACL lists path planning and task assignment as core research areas.

---

## 6. Mission Planning / Task Allocation AI

This is higher than path planning.

It answers:

```text
Which drone does which job?
Who scouts?
Who relays?
Who returns?
Who carries supplies?
Who watches this sector?
```

Keywords:

```text
task allocation
assignment optimization
multi-agent planning
scheduling
mission planning
decision-making under uncertainty
```

Plain English:

This is where the system decides who does what. It is not about one drone avoiding one wall. It is about assigning jobs across many agents with limited batteries, sensors, payloads, trust levels, and communication paths.

MIT ACL explicitly lists decision-making under uncertainty, path planning, activity, and task assignment.

---

## 7. Multi-Drone Swarm AI

This is where Penn GRASP-style work gets famous.

It answers:

```text
How do many robots coordinate?
How do they spread out?
How do they avoid each other?
How do they cover an area?
How do they re-form after losing members?
```

Keywords:

```text
swarm robotics
collective behavior
formation control
distributed coordination
consensus
flocking
coverage control
```

Plain English:

Swarm AI is not “one genius drone.” It is group behavior. The hard problem is making many cheap or limited agents behave coherently without crashing, clustering stupidly, duplicating work, or collapsing when one node disappears.

Penn’s Kumar Lab works on autonomous ground and aerial robots, bio-inspired algorithms for collective behaviors, and robot swarms. Penn GRASP also has a research area specifically for swarm robots.

---

## 8. Mapping / Reconstruction AI

This makes maps or 3D models from drone sensor data.

It answers:

```text
What does this place look like?
What changed?
Can I build a 3D model?
Where are obstacles?
Where are safe routes?
```

Keywords:

```text
SLAM — simultaneous localization and mapping
3D reconstruction
occupancy grid
NeRF — neural radiance field
Gaussian splatting
terrain mapping
change detection
inspection mapping
```

Plain English:

Mapping and reconstruction turn sensor passes into a usable picture of the world. For DICE/PF, this matters because the mission may need to know terrain, routes, obstacles, damaged infrastructure, supply paths, threat zones, and changes over time.

This is common in infrastructure inspection, search and rescue, mining, agriculture, and disaster robotics.

---

## 9. Tracking / Target Following AI

This follows objects over time.

It answers:

```text
Is that the same truck as before?
Where did the person go?
Where will that drone be in 5 seconds?
Can I keep the camera on it?
```

Keywords:

```text
multi-object tracking
Kalman filter
particle filter
visual tracking
trajectory prediction
sensor fusion
```

Plain English:

Tracking is about continuity. Detection says “I see a truck.” Tracking says “that is probably the same truck from 30 seconds ago, moving this way, likely to be here next.”

In safer civil versions, this is used for inspection, wildlife monitoring, search-and-rescue, sports filming, and airspace safety.

---

## 10. Learning-Based Navigation AI

This is where reinforcement learning or imitation learning shows up.

It learns behaviors like:

```text
fly through clutter
avoid obstacles
follow corridors
land on a moving platform
navigate using camera only
```

Keywords:

```text
reinforcement learning
imitation learning
sim-to-real transfer
policy learning
deep RL — deep reinforcement learning
```

Plain English:

Learning-based navigation means the system learns behavior from training, examples, or trial and error, often in simulation first. It can be powerful, but it needs guardrails. You do not want a learned policy improvising beyond authority or safety constraints.

CMU reported work where drones learn perception and action separately, using simulated training to bridge the simulation-to-real-world gap for autonomous navigation. MIT ACL also lists machine learning and reinforcement learning methods among its autonomy research areas.

---

## 11. Fault Detection / Health Management AI

This monitors whether the drone itself is failing.

It answers:

```text
Is a motor failing?
Is a prop damaged?
Is the battery sagging?
Is GPS spoofed?
Is the IMU lying?
Is the controller unstable?
```

Keywords:

```text
fault detection
diagnostics
health monitoring
anomaly detection
resilient autonomy
failure recovery
```

Plain English:

This is the “is my own body lying or dying?” layer. For long missions, this is not optional. A drone that does not understand its own degraded state can become a liability.

For PF, this plugs directly into PF-STATE, PF-ATTRITION, PF-RECONSTITUTION, PF-DENIAL, and PF-WOPR-RISK.

---

## 12. Communication / Networking AI

This answers:

```text
Who can talk to whom?
Who should relay?
Is this link jammed?
Should the swarm reconfigure?
```

Keywords:

```text
mesh networking
relay selection
adaptive communication
distributed consensus
network-aware planning
delay-tolerant networking
```

Plain English:

This is the “who can still talk, through whom, and how much can we trust the link?” layer. It is central to decentralized missions. If comms break, the mission either degrades intelligently or collapses.

MIT Lincoln Laboratory describes small UAS work involving autonomous behaviors, challenging-environment navigation, and coordinated autonomy among large numbers of UAS, enabled by sensing, communications, onboard processing, and energy improvements.

---

## 13. Human-Robot Interaction AI

This is not necessarily LLMs. It can be interfaces, gesture commands, workload estimation, trust calibration, explainable autonomy, or supervisory control.

It answers:

```text
What does the operator need to know?
Is the operator overloaded?
How should the drone explain itself?
How should a human supervise many drones?
```

Keywords:

```text
human-robot interaction
supervisory control
mixed initiative autonomy
explainable autonomy
operator workload
```

Plain English:

Human-robot interaction is about making the system usable by people. It matters because a perfect swarm that no human can understand, trust, query, or interrupt is not operationally useful.

This maps directly to PF-OPERATOR-CONSOLE.

---

## 14. Simulation / Digital Twin Agents

A lab may have fake drones, fake enemies, fake terrain, fake sensors, fake wind, fake comms loss, fake battery depletion, and fake operator decisions.

It answers:

```text
Will this autonomy work before we crash real hardware?
What happens if GPS dies?
What happens if two drones fail?
What happens if comms are delayed?
What happens if the operator makes a bad call?
```

Keywords:

```text
Gazebo
AirSim
Isaac Sim
ROS simulation
digital twin
hardware-in-the-loop
software-in-the-loop
```

Plain English:

Simulation lets researchers break the mission cheaply before hardware gets broken expensively. A digital twin is a simulated copy of the mission world or robot. Hardware-in-the-loop means some real hardware participates in the fake world. Software-in-the-loop means real software is tested in the fake world.

This maps directly to PF-SIM-HOOKS.

---

# How Many “AI’s” in a Real University Drone Lab?

For one serious autonomous drone project, not the whole university, you might have:

```text
1 flight controller
1 state estimator
1 mapping system
1 perception model
1 obstacle avoidance planner
1 global path planner
1 trajectory optimizer
1 task allocator
1 swarm coordination algorithm
1 comms/relay manager
1 battery/health monitor
1 anomaly detector
1 operator interface
1 simulator
```

That is already 14 separate autonomy systems.

In a whole university robotics lab? Easily:

```text
50+ active algorithms/models/systems
```

Across grad students, papers, demos, and projects.

At a place like Penn GRASP, MIT ACL, or CMU Robotics Institute, the “AI for drones” is not one thing. It is a stack of:

```text
control
estimation
perception
planning
mapping
tracking
optimization
swarming
networking
simulation
human supervision
fault handling
```

## Plain English Answer

You walk in and ask:

```text
“How many drone AIs do you have that are not LLMs?”
```

The honest professor answer is probably:

```text
“Which layer do you mean?”
```

Because the drone has:

```text
AI to see
AI to know where it is
AI to not crash
AI to plan paths
AI to assign tasks
AI to coordinate with other drones
AI to conserve battery
AI to detect faults
AI to map the world
AI to track objects
AI to explain state to an operator
AI to test everything in simulation
```

LLMs are not the core drone AI. They are mostly useful at the edge:

```text
human says messy thing → structured mission package
system state → human-readable explanation
logs/evidence → report
operator question → query over mission state
```

For the DICE/PF pitch, the clean line is:

```text
We are not proposing a swarm of LLMs. We are proposing a federated autonomy architecture that can coordinate existing university-grade drone AI components: perception, state estimation, planning, control, swarm coordination, sustainment, reconstitution, and operator interaction.
```
