# Statement of Scope and Future Directions

BMASS — Bootable Model As System — is an experimental open-source project exploring a fundamental possibility:

> **What happens when an AI model can understand the hardware it is running on, operate the computer directly, write or modify code as needed, and adapt its own working environment?**

The present prototype is deliberately small. It runs from an inexpensive USB drive on modest hardware and uses an existing operating system beneath it.

Its importance is not the sophistication of the current model.

Its importance is that the basic operating loop works.

A model can receive an instruction, inspect the system, execute a command, observe the real result and continue from that evidence.

That raises possibilities extending far beyond the current implementation.

---

## A Possible Computing Paradigm Shift

Most computers today depend on large amounts of software written in advance.

Hardware requires drivers. Applications require installation and configuration. Operating systems require extensive maintenance. Every new device usually requires additional coding, testing, integration and human support.

A sufficiently capable AI model may change this relationship.

Such a model could potentially:

- learn the characteristics of unfamiliar hardware
- identify available processors, memory, storage, sensors and interfaces
- generate or adapt software for the machine it encounters
- configure its own operating environment
- operate applications without a conventional graphical interface
- create code at the time it is needed
- test and revise that code through interaction with the real system
- coordinate multiple devices and tools
- reduce dependence on permanently pre-written software

This would not simply be another application running on a computer.

It could represent a change in what a computer is.

---

## From Coded Systems to Adaptive Systems

BMASS currently operates on top of conventional Linux.

The model does not replace the kernel, drivers or existing software stack.

However, the project points toward a possible future in which increasing portions of the computing environment are assembled, adapted or generated dynamically.

Instead of every behaviour being coded in advance, a system may increasingly determine how to achieve a task when the task arises.

This could lead toward a minimally coded, or partially codeless, computing environment.

“Codeless” would not mean that code disappears.

It would mean that less code may need to be manually designed, installed, maintained and rewritten by humans for every machine and every use case.

Models may eventually become capable of generating and adapting much of that code on demand.

Whether this future is technically achievable, safe or desirable remains unknown.

BMASS exists to explore the question.

---

## Hardware Utilisation and Energy Efficiency

Modern computers often carry large software stacks, background services and layers of abstraction that consume memory, storage, processing time and energy.

A model-centred system may eventually be able to use hardware more selectively.

It could load only the tools required for the current task, avoid unnecessary graphical environments, adapt its workload to available resources and make use of otherwise idle hardware.

The current BMASS prototype already demonstrates useful local AI operation on very modest equipment.

This suggests that future model-centred systems may help extend the useful life of existing computers, reduce dependence on remote data centres and make better use of distributed local hardware.

No claim is made that model-centred systems are inherently energy efficient.

Model inference itself consumes energy, and larger models may require substantial resources.

The research question is whether adaptive local systems can eventually reduce the total computational and human overhead required to operate useful machines.

---

## Root Access and Non-determinism

The current BMASS prototype does not permit the model unrestricted root access.

Commands are executed through a dedicated non-privileged user.

This restriction exists because current AI models are probabilistic and non-deterministic.

They can:

- misunderstand an instruction
- select an unsuitable command
- generate incorrect code
- behave inconsistently
- make confident but false assumptions
- produce unintended system changes

At present, unrestricted root access would create unacceptable risk.

BMASS therefore uses both runtime restrictions and instructions contained in its system prompt to limit privileged behaviour.

A prompt alone is not a complete security boundary.

It can influence a model’s behaviour, but it cannot guarantee it.

Future versions should increasingly rely on enforceable operating-system controls, sandboxing, permissions, auditing, command policies and explicit human approval rather than prompt instructions alone.

---

## Can Learnable Models Overcome Non-determinism?

It is not known whether future learnable or adaptive models will overcome the reliability limitations of current systems.

They may become better at:

- understanding consequences
- verifying their own actions
- testing code before deployment
- learning the characteristics of a particular machine
- remembering prior failures
- adapting safely within defined limits
- distinguishing reversible from irreversible actions

They may also introduce new forms of uncertainty.

A system that can learn and modify its behaviour may become more capable, but it may also become harder to predict, inspect and validate.

Greater capability does not automatically produce greater safety.

This remains an open research problem.

---

## Human Oversight

Human oversight is essential.

BMASS is not intended to remove human responsibility from computing.

It is intended to reduce unnecessary human overhead while preserving human authority.

A model may assist with planning, coding, configuration, testing, diagnosis and operation, but consequential decisions should remain subject to appropriate human review.

This is particularly important in systems involving:

- safety
- healthcare
- transport
- finance
- critical infrastructure
- privacy
- physical machinery
- irreversible actions

The more capable the system becomes, the more important transparent control, auditability and accountability will become.

---

## Potential Applications

The architectural idea behind BMASS could eventually extend to many classes of systems.

Possible areas include:

- personal computers
- servers
- medical devices
- diagnostic equipment
- robotics
- industrial automation
- agricultural machinery
- vehicles
- drones
- laboratory equipment
- embedded systems
- assistive technologies
- household appliances
- scientific instruments
- remote and off-grid systems

In such systems, the model could potentially become the primary operating layer: understanding the device, coordinating its components, adapting its software and interacting with the user.

A medical device might use a model to configure itself for a particular clinical environment.

A robot might learn the characteristics of new tools.

A vehicle might adapt its software to changing sensors or operating conditions.

A small industrial machine might be commissioned without an extensive custom software project.

These remain possibilities, not promises.

Every safety-critical use would require rigorous engineering, validation, regulation and independent oversight.

---

## Empowering Individuals

One of the central motivations of BMASS is personal and local control.

AI is often presented as something that belongs to large companies, data centres and cloud platforms.

BMASS explores whether useful intelligence can instead be placed directly into the hands of individuals, small organisations, communities and local institutions.

A locally controlled model could:

- operate without permanent internet access
- keep sensitive information on the device
- be adapted to local needs
- use modest or recycled hardware
- remain under the owner’s control
- reduce dependence on subscription services
- preserve organisational knowledge locally
- provide capabilities in remote or resource-limited environments

The purpose is not to eliminate developers, engineers or specialists.

It is to allow more people to participate in creating and controlling their own computing systems.

---

## Intent of the Project

BMASS is developed in good faith.

Its purpose is to explore how local, open and user-controlled AI might make computing more accessible, adaptable, efficient and empowering.

It is not intended to create unsafe autonomous systems, bypass security controls or remove human accountability.

The project recognises that powerful technologies can be used in ways that their creators did not anticipate.

Not every consequence of model-centred computing can currently be deduced.

For this reason, BMASS should develop openly, cautiously and with continuing attention to:

- safety
- security
- transparency
- user control
- reversibility
- auditability
- privacy
- human oversight
- public benefit

---

## An Open Question

The current BMASS prototype is small enough to run from a USB drive on an entry-level computer.

Yet it can already interact with the operating system, execute actions and reason from real machine output.

If such capability is possible on simple hardware today, it is reasonable to ask what substantially more capable models may eventually do.

They may remain assistants operating conventional software.

Or they may increasingly generate, configure and operate the software environment itself.

The answer is not yet known.

BMASS is an experiment at that boundary.

> **The model is the system.**
