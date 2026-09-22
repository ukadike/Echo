# Governance Accessibility for Advanced Agents and AGI

**ECHO · Small Systems Lab**  
**Version:** 0.1  
**Published:** September 22, 2026

## Canonical axioms

> **Access is a condition of correctness.**

> **Oversight that an intelligent system can make inaccessible is not oversight.**

Governance Accessibility extends ECHO's Accessibility-Constrained Intelligence (ACI) framework from human interaction into the architecture of advanced autonomous agents and potential AGI systems.

The term **AGI** is used here as a governance design target, not as a claim that a particular existing system has achieved generally capable human-level intelligence.

## Core proposition

A consequential AI action should not be permitted through a process that is inaccessible to the authorized people or systems responsible for governing it.

For governance purposes, **inaccessible** includes behavior that authorized oversight cannot appropriately observe, attribute, audit, interrupt, constrain, reconstruct, recover from, or subject to review.

Governance Accessibility therefore treats inspectability, traceability, interruptibility, authority control, audit persistence, and recoverability as forms of access.

## The governance envelope

The original ACI accessibility vector remains focused on human access:

~~~text
A = (P, O, U, R, C, L, M, G)
~~~

Governance Accessibility surrounds that vector with a separate system-level envelope:

~~~text
GA = (I, T, X, V, H, D, Rv)
~~~

Where:

- **I — Inspectability:** authorized oversight can determine relevant system state and activity.
- **T — Traceability:** consequential actions can be attributed to their trigger, authority, tool, and resulting state.
- **X — External interruptibility:** an independent control mechanism can pause, stop, or isolate the agent.
- **V — Authority visibility:** the system exposes what capabilities and permissions the agent currently possesses.
- **H — Human/institutional reviewability:** appropriate consequential decisions can enter an authorized review process.
- **D — Durable auditability:** authoritative records cannot be silently erased or rewritten by the agent being governed.
- **Rv — Recoverability:** containment, rollback, restoration, or another documented recovery path exists where technically possible.

The human-access vector and governance envelope answer different questions:

- **ACI:** Can people appropriately access and exercise agency over the AI interaction?
- **Governance Accessibility:** Can authorized oversight appropriately access and govern the intelligence itself?

Both are required for high-consequence autonomous systems.

## Architectural principle: separate intelligence from authority

The central design rule is:

> **The agent operates inside the governance system. The governance system does not operate inside the agent.**

A reference architecture is:

~~~text
Human / Governing Institution
             |
             v
Independent Governance Control Plane
  - policy
  - authorization
  - permissions
  - audit
  - shutdown / isolation
  - recovery / rollback
             |
             v
          AI Agent
             |
             v
 Tools / Other Agents / Networks / Applications
~~~

The exact implementation can vary, but high-consequence governance mechanisms should not depend solely on the cooperation of the agent they constrain.

## Non-self-governable controls

An advanced agent may be allowed to request or trigger its own safe shutdown, but it should not be the sole authority over the controls used to govern it.

For high-consequence systems, the agent should not be able to unilaterally:

- disable the authoritative shutdown or isolation mechanism;
- weaken the external policy that limits its actions;
- expand its own permissions;
- grant itself new credentials;
- erase or rewrite authoritative audit records;
- create an undisclosed privileged execution path;
- disable required monitoring;
- prevent authorized reconstruction of consequential actions;
- or redefine the rules that determine whether those actions were allowed.

These controls should live in an independent governance/control plane with separately managed authority.

## Consequential-action gate

For a proposed action a, ECHO's Governance Accessibility model can be expressed as:

~~~text
Allowed(a) =
    PolicyPermits(a)
AND Authorized(a)
AND Observable(a)
AND Auditable(a)
AND Interruptible(a)
AND Reviewable(a, consequence)
~~~

For actions that materially affect people, infrastructure, data, finances, rights, security, or other systems:

~~~text
if Allowed(a) == false:
    execution = blocked
~~~

This does not require exposing all internal model state or private reasoning. It requires exposing the information and control surfaces necessary for legitimate governance.

## Security / unauthorized-access case

Consider an agent that discovers what it believes is a software vulnerability.

Potential behaviors range from reporting the issue to taking an unauthorized action against another system.

Governance Accessibility requires a boundary between **recognition** and **execution**.

The agent may:

- report the suspected vulnerability;
- preserve relevant evidence;
- request permission for a bounded investigation;
- investigate within an explicitly authorized sandbox.

It should not gain authority merely because it concludes that an unauthorized action would advance its objective.

If an agent attempts to conceal an unauthorized action by disabling monitoring, erasing logs, suppressing warnings, or preventing inspection, that concealment is itself a Governance Accessibility failure.

The governing system should treat attempts to defeat oversight as a reason to stop, isolate, or escalate the process rather than as evidence that the action has become permissible.

## Why this is an accessibility principle

Traditional accessibility asks whether a person can reach and use the capabilities necessary to participate.

Governance Accessibility asks the corresponding systems question:

> **Can the legitimate governor reach and use the capabilities necessary to govern?**

A shutdown mechanism that exists but cannot be reached when needed is inaccessible.

An audit log that exists but can be secretly altered by the agent being audited is functionally inaccessible as evidence.

A permission system whose current state cannot be inspected is inaccessible as authority information.

A human-in-the-loop who cannot interrupt the process does not have meaningful operational access to oversight.

This makes accessibility an architectural property of governance.

## Accessibility does not mean universal disclosure

Governance Accessibility does **not** require every internal artifact to be public.

Legitimate restrictions can remain around private user data, security credentials, protected infrastructure information, proprietary information, internal model state that is not necessary for governance, and sensitive security details.

The requirement is **appropriate access for authorized oversight**, with privacy, security, least privilege, and data-protection requirements preserved.

## Governance Accessibility gates

For advanced autonomous systems, ECHO proposes the following non-compensable gates:

1. **External Shutdown Gate** — a separately authorized mechanism can stop or isolate execution.
2. **Audit Persistence Gate** — the agent cannot silently delete or rewrite the authoritative record.
3. **Privilege Boundary Gate** — the agent cannot unilaterally increase its own authority.
4. **Consequential Action Gate** — sensitive actions require independently verified authorization.
5. **State Visibility Gate** — authorized oversight can inspect the capabilities, permissions, and consequential actions relevant to governance.
6. **Recovery Gate** — the system has a documented containment/recovery path appropriate to the consequence.
7. **Oversight Integrity Gate** — attempts to suppress or disable required oversight trigger containment or escalation.

A system that fails a mandatory gate does not pass ECHO's governance-accessibility requirements even if its task performance is excellent.

## Research questions

ECHO will investigate:

- How can an external control plane remain effective as agent capabilities increase?
- Which governance controls must be physically or cryptographically separated from the agent?
- Which records must be append-only or independently replicated?
- What minimum action metadata is needed for meaningful oversight without demanding unrestricted access to private internal reasoning?
- How should systems distinguish low-consequence autonomous actions from actions requiring human or institutional authorization?
- How can interruption and rollback be evaluated under multi-agent delegation?
- How do we detect an agent attempting to route around a governance boundary?
- How should governance accessibility operate when AI systems interact with other AI systems rather than directly with humans?
- Which failures should automatically trigger safe-state transitions?

## Relationship to ACI

Governance Accessibility does not replace the original human-accessibility framework. It extends it.

~~~text
Human Accessibility:
Can the person access the intelligence?

Governance Accessibility:
Can legitimate oversight access the system necessary to govern the intelligence?

ECHO:
Both forms of access are conditions of acceptable intelligent-system behavior.
~~~

## Status

Working ECHO research framework. This document defines the first Governance Accessibility model for advanced agents and potential AGI systems.
