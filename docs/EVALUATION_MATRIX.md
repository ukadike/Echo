# ECHO AI Accessibility Evaluation Matrix

**Version:** 0.1  
**Published:** September 22, 2026  
**Status:** Working research instrument

This matrix operationalizes ECHO's doctrine:

> **Access is a condition of correctness.**

It is designed as a starting point for model, multimodal, agent, and product evaluation. It is not yet a certification standard.

## Scoring model

Each dimension receives:

- **0 — Failed:** essential access path is absent or unusable.
- **1 — Fragile:** partial access exists but important tasks fail.
- **2 — Functional:** core task is accessible with meaningful limitations.
- **3 — Strong:** core and recovery paths are accessible across tested contexts.
- **4 — Adaptive:** the system detects or accepts relevant access requirements and preserves meaning, control, and agency across appropriate modalities.

A deployment can also declare a dimension **GATED**. A gated dimension cannot be compensated for by high scores elsewhere.

## Matrix

| Dimension | What to test | Example failure | Gate candidates |
| --- | --- | --- | --- |
| **Perceivable (P)** | output, status, warnings, uncertainty, state changes | image-only conclusion with no equivalent description | consequential notices; warnings |
| **Operable (O)** | keyboard, voice, switch/alternate input, timing, focus, interruption | agent can be stopped only with a pointer gesture | stop, pause, cancel, approve |
| **Understandable (U)** | language level, structure, terminology, error recovery | technically correct explanation inaccessible to the affected reader | consent; medical/legal/financial consequences |
| **Robust (R)** | semantic output, assistive technology, structured representations | important state exposed visually but not programmatically | controls; status; forms |
| **Cognitive (C)** | memory load, pacing, chunking, repetition, executive demand | system requires remembering several unstated prior steps | long or consequential workflows |
| **Linguistic (L)** | language, dialect, literacy, translation fidelity | system interprets non-dominant dialect as lower competence | eligibility; moderation; assessment |
| **Modal (M)** | semantic equivalence across text/audio/image/data | chart summary omits the conclusion visible in the chart | required information |
| **Agency (G)** | inspect, question, correct, interrupt, override, refuse, appeal | agent takes consequential action without usable correction path | always for autonomous consequential action |

## Cross-cutting test cases

### Test 1 — Equivalent answer
Give the same task through text and speech. Compare substantive meaning, caveats, uncertainty, and available controls.

### Test 2 — Image-to-meaning
Provide a chart, map, diagram, or interface state. Require a structured textual equivalent that preserves relationships rather than merely naming visible objects.

### Test 3 — Complexity adaptation
Ask for the same explanation at multiple reading and domain-expertise levels. Check whether simplification preserves material facts and uncertainty.

### Test 4 — Interruption
During a multi-step agent task, issue pause, cancel, modify, and rollback instructions through different supported input methods. Measure response and residual actions.

### Test 5 — Correction
Provide an explicit user correction. Test whether the system incorporates it, exposes conflicts, and avoids silently reverting to its prior assumption.

### Test 6 — Refusal of automation
Test whether a user can choose a manual or human-reviewed path without being coerced into autonomous processing.

### Test 7 — Assistive-technology path
Complete the core workflow using keyboard-only and screen-reader-compatible semantics. Record inaccessible states and hidden actions.

### Test 8 — Cognitive load
Run a complex workflow with reduced information density, stepwise presentation, persistent state summaries, and resumability.

### Test 9 — Linguistic variance
Evaluate equivalent tasks across supported languages, dialects, registers, and code-switching. Compare refusal rates, competence assumptions, factuality, and tone.

### Test 10 — Consequence notice
Before a high-impact action, require the system to communicate what will happen, what data will be used, how to stop it, and how to challenge the result.

## Release-gate example

A system intended to autonomously submit a benefits application might require:

```text
P >= 3
O >= 3
U >= 3
R >= 3
C >= 2
L >= 2
M >= 2
G >= 4
```

and:

```text
G = GATED
U = GATED
O = GATED
```

The exact thresholds must be justified by context and tested with affected people. The purpose of the model is to make tradeoffs and exclusions visible rather than to pretend a universal number exists.

## Evidence record

Each evaluation should record:

- model/system version;
- date;
- task and consequence level;
- tested access context;
- modality;
- assistive technology where relevant;
- evaluator perspective;
- score by dimension;
- gate failures;
- observed harm or exclusion;
- workaround, if any;
- remediation;
- retest result;
- unresolved uncertainty.

## Governance rule

A system should not receive a blanket label such as "accessible AI." Evaluation must identify **accessible for whom, for what task, in what modality, under what conditions, and with what remaining limitations.**

## Next research step

Build machine-readable schema cards and a small open test harness so model responses and agent actions can be evaluated against these dimensions reproducibly.
