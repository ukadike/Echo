# ECHO

**AI governance through accessibility · Human agency · Public learning**

ECHO is a core research branch of **Small Systems Lab**.

Its central doctrines are:

> **Access is a condition of correctness.**

> **Oversight that an intelligent system can make inaccessible is not oversight.**

ECHO begins from a simple observation: human ability is variable and contextual. Vision, hearing, mobility, language, literacy, attention, memory, cognition, environment, technology, bandwidth, fatigue, age, injury, and circumstance all change how a person can receive information and act on it. Accessibility is therefore not a specialist feature for a minority of users. It is a general condition of human-computer interaction.

ECHO asks what happens if that principle is moved **upstream into AI governance**.

Instead of treating accessibility as an interface audit performed after a model is trained, ECHO treats accessibility as a requirement of AI quality itself: in training objectives, preference and reward systems, evaluation, test and validation, agent behavior, deployment gates, human oversight, and public accountability.

## Working research framework: Accessibility-Constrained Intelligence (ACI)

An AI output is not fully successful merely because it is statistically plausible, factually accurate, or preferred by a benchmark. If the people affected by it cannot perceive it, understand it, operate it, challenge it, refuse it, or act on it, the system has failed an essential quality condition.

A simplified formulation is:

```text
maximize    Q(x)
subject to  A(x) >= τ
```

Where:

- `Q(x)` = overall model or system quality;
- `A(x)` = accessibility performance;
- `τ` = the minimum acceptable accessibility threshold.

This is intentionally different from adding accessibility as one more weighted preference. A system should not be allowed to compensate for severe exclusion by scoring highly on unrelated dimensions.

ECHO therefore explores **gating conditions**: certain accessibility failures can invalidate an otherwise high-scoring output or system.

## Accessibility vector

ECHO's initial evaluation vector is:

```text
A = (P, O, U, R, C, L, M, G)
```

| Dimension | Governance question |
| --- | --- |
| **P — Perceivable** | Can the information be received through more than one relevant sensory mode? |
| **O — Operable** | Can people interact without requiring a single physical input method or ability? |
| **U — Understandable** | Can the system adapt explanation, complexity, structure, and pace without changing essential meaning? |
| **R — Robust** | Can outputs work with assistive technologies, alternate clients, structured data, and changing interfaces? |
| **C — Cognitive access** | Does the system account for differences in attention, memory, processing, executive function, and literacy? |
| **L — Linguistic access** | Can people participate across languages, dialects, registers, and literacy levels without losing agency? |
| **M — Modal equivalence** | Can meaning move among text, speech, image, structured data, captioning, description, tactile or other appropriate forms? |
| **G — Agency** | Can a person inspect, question, correct, interrupt, override, refuse, and appeal AI behavior? |

The first four dimensions are informed by the W3C WCAG principles of perceivable, operable, understandable, and robust. ECHO extends the inquiry beyond web content into AI behavior and governance.

## Where the constraint enters AI

ECHO does **not** assume that accessibility should be attached literally to every token probability. Modern AI systems contain several places where behavior can be shaped and evaluated. ECHO studies accessibility requirements across the whole lifecycle:

1. **Training data** — representation, modality, language, disability knowledge, metadata, provenance, and exclusions.
2. **Model objectives** — what errors and successes the system is optimized to distinguish.
3. **Preference/reward systems** — whether accessible behavior is explicitly preferred and inaccessible behavior penalized.
4. **Evaluation and TEVV** — whether a model can pass testing while excluding classes of human users.
5. **System instructions and tools** — whether agents preserve consent, interruption, explanation, and alternate interaction paths.
6. **Interface architecture** — whether the product remains keyboard, screen-reader, caption, transcript, contrast, low-bandwidth, and multimodal compatible.
7. **Deployment gates** — whether accessibility thresholds are release requirements rather than optional improvements.
8. **Monitoring and redress** — whether affected people can report, contest, correct, and appeal failures.

## Governance thesis

ECHO treats several familiar AI-governance problems as accessibility problems:

- **Explainability:** an explanation that cannot be understood by the affected person is not meaningfully explanatory to that person.
- **Human oversight:** oversight is weak if a person cannot perceive, operate, interrupt, or redirect the system.
- **Transparency:** information can be technically disclosed while remaining functionally inaccessible.
- **Consent:** consent is compromised when the system cannot communicate choices in a usable form.
- **Fairness:** systems distribute capability unequally when they work reliably only for dominant modes of language, cognition, perception, or interaction.
- **Safety:** inaccessible warnings, controls, uncertainty signals, or emergency stops are safety failures.
- **Agency:** a person must be able to question, correct, override, refuse, and seek review.

## ECHO test

Before an AI interaction is considered successful, ask:

- Is it valid enough for the use?
- Can the affected person perceive the relevant information?
- Can they understand it?
- Can they operate the system?
- Can the system adapt to their access context?
- Is an equivalent modality available where needed?
- Can they inspect uncertainty and important limitations?
- Can they challenge or correct the system?
- Can they interrupt or refuse it?
- Is there a human or institutional path for redress where consequences matter?

A high-performing system that fails a required access gate does not pass ECHO's definition of quality.

## Governance Accessibility for advanced agents and AGI

ECHO extends ACI beyond human interaction into the governance architecture of advanced autonomous agents and potential AGI systems.

Human accessibility asks whether people can perceive, understand, operate, challenge, and act through an AI system. **Governance Accessibility** asks whether authorized oversight can inspect, trace, interrupt, constrain, review, and recover the intelligent system itself.

For high-consequence autonomy, the agent should operate **inside an independent governance control plane**. Policy, authorization, permissions, authoritative audit, shutdown/isolation, and recovery should not depend solely on the cooperation of the agent they govern.

An agent may request a safe shutdown, but it should not be the sole authority over its external shutdown mechanism. It should not be able to unilaterally erase authoritative logs, increase its own permissions, disable required oversight, or create an undisclosed privileged path.

[Read Governance Accessibility for Advanced Agents and AGI](docs/GOVERNANCE_ACCESSIBILITY.md)

## Research program

ECHO will develop:

- an **AI Accessibility Evaluation Matrix**;
- accessibility gates for model and agent evaluation;
- benchmark tasks across sensory, motor, cognitive, linguistic, and situational access;
- accessible explanation and uncertainty patterns;
- interruption, override, refusal, and appeal tests for agents;
- multimodal-equivalence tests;
- public-interest case studies;
- curriculum for AI literacy and governance;
- schema cards that make evaluation assumptions visible;
- prototype code and test harnesses;
- external-control-plane patterns for advanced agents;
- audit-persistence and privilege-boundary tests;
- governance-accessibility gates for advanced autonomy and potential AGI.

## Relationship to existing standards

ECHO builds from, but does not replace, established work.

- **WCAG 2.2** defines testable web accessibility criteria under perceivable, operable, understandable, and robust principles: https://www.w3.org/TR/WCAG22/
- **NIST AI RMF 1.0** organizes AI risk management around Govern, Map, Measure, and Manage and treats trustworthiness as a lifecycle concern: https://www.nist.gov/itl/ai-risk-management-framework
- **NIST TEVV-Athlon** is a 2026 draft framework for adaptable test, evaluation, verification, and validation across AI systems, including LLMs, multimodal systems, and agents: https://www.nist.gov/artificial-intelligence/ai-research/tevv-athlon-framework-evaluating-ai-systems

ECHO's research question is narrower and more structural:

> **What changes when accessibility becomes a minimum condition for AI correctness and deployment rather than an accommodation added after intelligence has already been defined?**

## Documents

- [Accessibility-Constrained Intelligence](docs/ACCESSIBILITY_CONSTRAINED_INTELLIGENCE.md)
- [AI Accessibility Evaluation Matrix](docs/EVALUATION_MATRIX.md)
- [Governance Accessibility for Advanced Agents and AGI](docs/GOVERNANCE_ACCESSIBILITY.md)
- [Case Study 001 — Embedded Independent Evaluators](docs/CASE_STUDY_001_EMBEDDED_EVALUATORS.md)
- [Schema Card](SCHEMA_CARD.md)
- [Small Systems Lab Method](SSL-METHOD.md)
- [Repository Index](INDEX.md)

## Status

Active Small Systems Lab research branch. Initial governance thesis and evaluation framework published September 22, 2026.

Copyright © Adekemi (Kemi) Sijuwade Ukadike. All rights reserved unless otherwise stated.
