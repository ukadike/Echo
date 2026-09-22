# Schema Card — ECHO

## Project name

ECHO

## Parent

Small Systems Lab (SSL)

## Role

Core AI governance, accessibility, public learning, and human-agency research branch.

## Central doctrine

> **Access is a condition of correctness.**

> **Oversight that an intelligent system can make inaccessible is not oversight.**

## Purpose

ECHO studies what changes when accessibility is treated as a governing condition of AI quality rather than an accommodation added after model development.

Its working framework, **Accessibility-Constrained Intelligence (ACI)**, translates accessibility principles into model and system requirements spanning data, training objectives, preference and reward systems, evaluation/TEVV, agent architecture, interfaces, deployment gates, monitoring, and redress.

AI literacy and public education remain part of ECHO, but they now support this larger governance mission.

## Core research question

What changes when an AI system is not allowed to count an interaction as successful if the affected person cannot appropriately perceive, understand, operate, challenge, interrupt, refuse, correct, or act on it?

## Evaluation vector

```text
A = (P, O, U, R, C, L, M, G)
```

- **P:** Perceivable
- **O:** Operable
- **U:** Understandable
- **R:** Robust
- **C:** Cognitive access
- **L:** Linguistic access
- **M:** Modal equivalence
- **G:** Agency

## Constraint model

```text
maximize    Q(x)
subject to  A(x) >= τ
```

Important dimensions can be designated as non-compensable deployment gates.

## Governance Accessibility

For advanced autonomous agents and potential AGI systems, ECHO adds a system-level governance envelope around the human-access vector.

The governed agent should not be the sole authority over policy, permission expansion, authoritative audit, external shutdown/isolation, consequential-action authorization, or recovery mechanisms.

ECHO treats inspectability, traceability, external interruptibility, authority visibility, human/institutional reviewability, durable auditability, and recoverability as governance-access properties.

Primary document: docs/GOVERNANCE_ACCESSIBILITY.md.

## Interfaces

- Static GitHub Pages site.
- Markdown research documents.
- GitHub issues for corrections and public contribution.
- Future evaluation schemas and test harnesses.

## Inputs

- accessibility standards and research;
- AI model/system behavior;
- model and agent evaluations;
- affected-user testing;
- accessibility failures;
- governance frameworks;
- public-interest case studies.

## Outputs

- ACI framework;
- AI Accessibility Evaluation Matrix;
- Governance Accessibility framework for advanced agents and potential AGI;
- benchmark and TEVV proposals;
- schema cards;
- research publications;
- public curriculum;
- prototype test harnesses;
- governance recommendations.

## Human governance

AI may assist research, drafting, coding, analysis, and testing. Human judgment remains authoritative for ECHO's published claims, thresholds, interpretations, and policy recommendations.

## Accessibility commitments

ECHO's own publishing and prototypes should use:

- semantic HTML;
- keyboard operability;
- screen-reader-compatible structures;
- captions and transcripts;
- text alternatives;
- high contrast;
- reflow/zoom support;
- plain-language alternatives when appropriate;
- low-bandwidth delivery;
- visible focus;
- multimodal equivalents;
- explicit privacy and upload warnings.

## Reference frameworks

- W3C WCAG 2.2 — https://www.w3.org/TR/WCAG22/
- NIST AI RMF — https://www.nist.gov/itl/ai-risk-management-framework
- NIST TEVV-Athlon (2026 draft) — https://www.nist.gov/artificial-intelligence/ai-research/tevv-athlon-framework-evaluating-ai-systems

## Related SSL branches

- **Accessible by Design** — accessibility research, audits, tools, and prototyping.
- **Omoluabi** — human-governed editorial intelligence, evidence, provenance, and public accountability.
- **Earth Sensors Lab** — accessible STEAM and multimodal scientific learning.
- **UMADA** — speculative research environment for future civic and technological systems.

ECHO is the place where accessibility becomes a formal AI-governance and evaluation thesis across those domains.

## Status

Active core branch. ACI v0.2, Evaluation Matrix v0.2, and Governance Accessibility v0.1 published September 22, 2026.
