# Accessibility-Constrained Intelligence (ACI)

**ECHO · Small Systems Lab**  
**Version:** 0.2  
**Published:** September 22, 2026

## Core doctrine

> **Access is a condition of correctness.**

Accessibility-Constrained Intelligence (ACI) is ECHO's working research framework for treating accessibility as a governing requirement of artificial intelligence rather than a downstream interface accommodation.

The framework begins from the premise that human ability is variable and contextual. An AI system therefore cannot be evaluated only against an imagined default user.

## Problem

AI quality is commonly evaluated through combinations of task performance, benchmark scores, preference judgments, factuality, safety tests, latency, cost, and other measures.

These can still permit a system to score highly while an affected person cannot:

- perceive its output;
- understand its reasoning or uncertainty;
- operate its controls;
- use an alternate modality;
- interrupt an agent;
- correct an error;
- refuse an action;
- appeal a consequential result.

ACI treats those failures as defects in system quality and governance.

## Constraint model

A simplified system objective is:

```text
maximize    Q(x)
subject to  A(x) >= τ
```

`Q(x)` is the quality objective appropriate to the application. `A(x)` is a multidimensional accessibility evaluation. `τ` is the minimum threshold required for deployment or task success.

The constraint matters. A weighted average can allow a severe accessibility failure to be hidden by strong scores elsewhere. A gate does not.

For a safety-critical or rights-affecting use, ECHO may define multiple non-compensable gates:

```text
P >= τp
O >= τo
U >= τu
G >= τg
...
```

A failure on a required gate fails the evaluated interaction even if aggregate quality remains high.

## Accessibility vector

```text
A = (P, O, U, R, C, L, M, G)
```

### P — Perceivable
Information, state, warning, uncertainty, controls, and outcomes must be perceivable by the affected person through appropriate forms.

### O — Operable
Interaction must not depend unnecessarily on a single motor, sensory, timing, or input capability.

### U — Understandable
The system must be capable of communicating at an appropriate level of complexity, structure, pacing, and terminology while preserving essential meaning.

### R — Robust
AI outputs and controls should remain interpretable through assistive technologies, structured representations, alternate clients, and evolving interfaces.

### C — Cognitive access
The system should account for variation in attention, memory, executive function, processing speed, reading load, and information density.

### L — Linguistic access
The system should support meaningful participation across language, dialect, register, and literacy differences without treating dominant linguistic forms as synonymous with competence.

### M — Modal equivalence
Where a task permits it, essential meaning should be transformable across modalities: text, speech, image description, structured data, captions, transcripts, tactile representations, or other appropriate forms.

### G — Agency
A person should be able to understand what the AI is doing, inspect important uncertainty, correct it, interrupt it, override it, refuse it, and seek review where consequences matter.

## AI lifecycle insertion points

ACI is a systems framework, not a claim that accessibility should be directly encoded as a scalar on every predicted token.

Accessibility requirements can enter at:

### 1. Data
- representation across disability and access contexts;
- multilingual and multimodal data;
- accessible metadata;
- provenance;
- documentation of missing populations and modalities.

### 2. Training objectives
- loss terms or auxiliary objectives for specific measurable behaviors;
- contrastive examples of accessible versus inaccessible responses;
- preservation of semantic content across transformed modalities.

### 3. Preference and reward systems
- human or model evaluation rubrics that explicitly reward accessible behavior;
- penalties for inaccessible or agency-reducing behavior;
- raters with diverse access needs.

### 4. Evaluation / TEVV
- benchmarks that include access contexts;
- assistive-technology testing;
- cognitive-load testing;
- language and dialect testing;
- agent interruption and override testing;
- modal-equivalence testing.

### 5. System and agent architecture
- accessible tool outputs;
- state visibility;
- confirmation before consequential actions;
- interruption and rollback;
- explanations proportional to consequence;
- accessible recovery from error.

### 6. Product interface
- semantic structure;
- keyboard access;
- screen-reader support;
- captions and transcripts;
- high contrast;
- zoom and reflow;
- low-bandwidth paths;
- reduced-motion options where relevant.

### 7. Deployment
- accessibility acceptance criteria;
- documented exceptions;
- public limitations;
- monitoring by affected communities;
- rollback when access gates fail.

### 8. Redress
- understandable notices;
- correction mechanisms;
- human review;
- appeal;
- traceable decision records.

## Governance Accessibility: advanced agents and potential AGI

ACI also extends beyond the accessibility of human interaction. For advanced autonomous agents and potential AGI systems, ECHO defines a second systems requirement:

> **Oversight that an intelligent system can make inaccessible is not oversight.**

This is called **Governance Accessibility**.

The original accessibility vector remains focused on whether affected people can access and exercise agency over AI interaction. Governance Accessibility is a separate system-level envelope asking whether authorized oversight can inspect, trace, interrupt, constrain, review, and recover the intelligence itself.

For high-consequence autonomy, ECHO proposes that authoritative policy, permission, audit, shutdown/isolation, and recovery mechanisms sit in an **independent governance control plane** that the governed agent cannot unilaterally disable, rewrite, or expand.

See [Governance Accessibility for Advanced Agents and AGI](GOVERNANCE_ACCESSIBILITY.md).

## Governance implications

### Explainability becomes relational
An explanation is not simply present or absent. It must be intelligible to the person who needs it.

### Oversight requires access
A theoretical human-in-the-loop is insufficient when the human cannot perceive system state or operate intervention controls.

### Transparency requires usability
Disclosure that cannot be found, perceived, or understood does not provide functional transparency.

### Consent requires communicative access
Meaningful permission depends on the ability to understand choices and consequences.

### Fairness includes capability distribution
AI can distribute capability unevenly by working well for dominant languages, interaction patterns, cognitive styles, sensory modes, or physical abilities while failing others.

### Safety controls must themselves be accessible
Warnings, uncertainty indicators, emergency stops, override mechanisms, and escalation paths are part of safety architecture.

## Research hypotheses

ECHO will test, rather than assume, the following:

1. Accessibility gates reveal important failures that aggregate quality scores conceal.
2. Training and preference data that include diverse access contexts can improve general system robustness.
3. Modal-equivalence evaluation can detect semantic loss that conventional multimodal benchmarks miss.
4. Accessible explanations can improve error detection and human oversight beyond disability-specific contexts.
5. Agent interruption and override should be evaluated as both safety and accessibility properties.
6. Accessibility failures can serve as early indicators of broader governance failures.
7. An autonomous system whose oversight mechanisms can be made inaccessible by the governed agent has a structural governance failure.
8. Separating agent intelligence from policy, authorization, authoritative audit, and external interruption can make consequential autonomy more governable.

## Relationship to standards

ACI draws inspiration from WCAG 2.2's perceivable, operable, understandable, and robust principles, but it is not a WCAG replacement or an assertion that WCAG currently governs model internals.

It also aligns with the lifecycle orientation of the NIST AI Risk Management Framework. NIST's AI RMF organizes work around Govern, Map, Measure, and Manage and identifies multiple characteristics of trustworthy AI. ECHO proposes accessibility as a cross-cutting quality constraint that can be operationalized through those lifecycle functions.

References:

- W3C, Web Content Accessibility Guidelines (WCAG) 2.2: https://www.w3.org/TR/WCAG22/
- NIST, AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- NIST, TEVV-Athlon Framework for Evaluating AI Systems, initial public draft announced August 7, 2026: https://www.nist.gov/artificial-intelligence/ai-research/tevv-athlon-framework-evaluating-ai-systems

## Research output

ACI is the core theoretical framework of ECHO. The companion [AI Accessibility Evaluation Matrix](EVALUATION_MATRIX.md) begins translating the thesis into testable gates. [Governance Accessibility for Advanced Agents and AGI](GOVERNANCE_ACCESSIBILITY.md) extends the framework into the architecture of advanced autonomous systems.
