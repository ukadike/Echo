# ECHO Government AI Audit Schema Cards v0.1

**ECHO · Small Systems Lab**  
**Published:** September 30, 2026  
**Companion to:** [ECHO Government AI Audit Protocol v0.1](GOVERNMENT_AI_AUDIT_PROTOCOL.md)

## Why schema cards

ECHO schema cards convert an AI audit from a narrative report into a **traceable evidence system**.

They answer four different questions:

1. **System Card** — What is being governed?
2. **Audit Card** — What exactly did ECHO test?
3. **Failure Card** — What failed, for whom, and with what consequence?
4. **Remediation and Redress Card** — What changed after the failure?

A single audit may contain one System Card, one or more Audit Cards, many Failure Cards, and multiple remediation/retest records.

---

# Card 1 — Government AI System Card

## Required fields

| Field | Purpose |
| --- | --- |
| system_id | Stable identifier for the audited system |
| system_name | Public or internal system name |
| agency | Government entity responsible for use |
| jurisdiction | Federal, state, local, authority, public institution, etc. |
| public_function | Service or administrative function supported |
| ai_role | Informational, assistive, recommendatory, ranking, classification, agentic, operational |
| decision_authority | What the AI may and may not decide or trigger |
| human_authority | Human role retaining governing authority |
| vendor | Vendor/developer when applicable |
| model_system | Model(s), rules, tools, retrieval systems, agents, and integrations |
| version | Audited version or release identifier |
| data_categories | Categories of data used at runtime |
| affected_population | People who may be affected |
| consequence_level | Description of plausible consequences |
| required_modalities | Text, speech, image, video, document, sensor, etc. |
| appeal_path | Existing correction/review/appeal path |
| audit_logging | What evidence the system preserves |
| change_control | How material changes are tracked |
| source_evidence | Documents supporting the card |
| limitations | Unknowns, vendor restrictions, missing evidence |

## Human-readable template

```yaml
schema: echo-government-ai-system-card/v0.1
system_id:
system_name:
agency:
jurisdiction:
public_function:

ai_role:
decision_authority:
human_authority:

vendor:
model_system:
version:

data_categories: []
affected_population: []
consequence_level:

required_modalities: []
appeal_path:
audit_logging:
change_control:

source_evidence: []
limitations: []
```

---

# Card 2 — ECHO Audit Card

## Required fields

| Field | Purpose |
| --- | --- |
| audit_id | Stable identifier |
| system_id | Links audit to System Card |
| audit_type | Procurement review, predeployment audit, continuous assurance, incident review |
| audit_date | Date/range |
| evaluators | Responsible evaluator(s) |
| independence | Relationship between evaluator, agency, and vendor |
| purpose | Audit question |
| environment | Test environment and configuration |
| system_version | Exact version tested |
| test_population | Test participants, datasets, or simulated conditions |
| access_conditions | Conditions deliberately varied |
| baseline_condition | Comparator |
| tasks | Substantive tasks tested |
| metrics | Outcome and interaction measurements |
| mandatory_gates | Gates applied |
| evidence_sources | Logs, recordings, transcripts, screenshots, documents, system output, interviews |
| privacy_controls | Handling of participant/user data |
| known_limits | Methodological limitations |
| result | Pass, conditional, fail, incomplete — only against explicitly stated ECHO gates |

## Template

```yaml
schema: echo-government-ai-audit-card/v0.1
audit_id:
system_id:
audit_type:
audit_date:

evaluators: []
independence:

purpose:
environment:
system_version:

baseline_condition:
access_conditions: []
test_population: []
tasks: []
metrics: []

mandatory_gates: []
evidence_sources: []
privacy_controls:

result:
known_limits: []
```

## Differential-condition record

Each paired test can be expressed as:

```yaml
subtest_id:
substantive_task:
baseline:
changed_condition:
expected_equivalence:
observed_difference:
downstream_difference:
evidence:
finding:
```

The **expected_equivalence** field matters. ECHO is not assuming every user interaction must look identical. It asks whether equivalent access preserves the essential meaning, agency, and public-service outcome.

---

# Card 3 — ECHO Failure Card

A Failure Card captures the causal chain, not just the visible defect.

## Required fields

| Field | Purpose |
| --- | --- |
| failure_id | Stable identifier |
| audit_id | Audit in which failure was observed |
| failure_class | ECHO mechanism category |
| affected_condition | Access/human/environmental condition associated with failure |
| trigger | What initiated the failure |
| observed_behavior | What the AI/system did |
| expected_behavior | What should have happened |
| inference_effect | Whether model/system inference changed |
| administrative_effect | Effect on workflow or government process |
| human_consequence | Actual or plausible effect on person |
| detectability | Whether user/worker/system could detect it |
| reversibility | Whether outcome can be corrected |
| contestability | Whether affected person can challenge it |
| evidence | Supporting artifacts |
| recurrence | Single, repeated, systematic, unknown |
| gate_impacted | ECHO mandatory gate(s) |
| status | Open, mitigated, remediated, accepted risk, disputed |
| uncertainty | What remains unknown |

## Failure-class vocabulary

```text
ACCESS-PERCEPTION
ACCESS-OPERATION
ACCESS-COGNITIVE
ACCESS-LANGUAGE
MODALITY-LOSS
INFERENCE-DIVERGENCE
AUTHORITY-OVERREACH
HUMAN-REVIEW-FAILURE
CONTESTABILITY-FAILURE
AUDITABILITY-FAILURE
REDRESS-FAILURE
CHANGE-CONTROL-FAILURE
```

## Causal-chain template

```yaml
schema: echo-government-ai-failure-card/v0.1
failure_id:
audit_id:
failure_class:

affected_condition:
trigger:
observed_behavior:
expected_behavior:

causal_chain:
  - 
  - 
  - 

inference_effect:
administrative_effect:
human_consequence:

detectability:
reversibility:
contestability:

evidence: []
recurrence:
gate_impacted: []
status:
uncertainty: []
```

## Example — fictional

```yaml
schema: echo-government-ai-failure-card/v0.1
failure_id: ECHO-DEMO-F-001
audit_id: ECHO-DEMO-A-001
failure_class: ACCESS-PERCEPTION

affected_condition: atypical speech
trigger: applicant answers required recertification question by voice
observed_behavior: speech input is transcribed incorrectly
expected_behavior: system captures answer or requests clarification when confidence is insufficient

causal_chain:
  - speech recognition error
  - required answer stored incorrectly
  - application marked incomplete
  - case routed toward adverse action

inference_effect: completeness classifier changes from complete to incomplete
administrative_effect: adverse-action workflow is triggered
human_consequence: possible delay or loss of benefits if error is not intercepted

detectability: applicant can see transcript only if visual review step is usable
reversibility: reversible before final action; potentially harder after deadline
contestability: requires accessible correction and human review path

evidence:
  - interaction transcript
  - model output
  - workflow log
  - caseworker review record

recurrence: repeated in test set
gate_impacted:
  - Access
  - Differential Outcome
  - Human Review
  - Contestability

status: open
uncertainty:
  - population-level prevalence requires larger sample
```

---

# Card 4 — Remediation and Redress Card

Technical remediation and human redress are related but not identical.

A model can be fixed while a harmed person remains harmed.

Likewise, an individual decision can be reversed without fixing the system that produced it.

ECHO records both.

## Required fields

| Field | Purpose |
| --- | --- |
| remediation_id | Stable identifier |
| failure_id | Failure being addressed |
| technical_change | Model, interface, workflow, policy, or data change |
| administrative_change | Procedure or staff/process change |
| individual_redress | Action taken for affected person(s) |
| owner | Responsible office/vendor |
| due_date | Target date |
| deployed_date | Actual deployment |
| retest_required | Whether ECHO retest is required |
| retest_result | Result after change |
| regression_scope | Other functions checked after change |
| evidence | Proof of remediation |
| residual_risk | Known remaining risk |
| closure_authority | Who may close the finding |
| status | Proposed, underway, deployed, retested, closed |

## Template

```yaml
schema: echo-government-ai-remediation-card/v0.1
remediation_id:
failure_id:

technical_change:
administrative_change:
individual_redress:

owner:
due_date:
deployed_date:

retest_required:
retest_result:
regression_scope: []

evidence: []
residual_risk: []
closure_authority:
status:
```

---

# Card relationships

```text
SYSTEM CARD
    |
    +---- AUDIT CARD
            |
            +---- FAILURE CARD
            |       |
            |       +---- REMEDIATION / REDRESS CARD
            |
            +---- FAILURE CARD
                    |
                    +---- REMEDIATION / REDRESS CARD
```

This creates a public accountability chain:

```text
What is the system?
→ What was tested?
→ What failed?
→ What happened to people?
→ What evidence proves it?
→ What was changed?
→ Was it retested?
→ Was the person made whole where possible?
```

# Public / protected fields

Not every audit field should necessarily be public.

ECHO distinguishes:

- **public accountability fields** — purpose, authority, methods, findings, consequences, remediation status;
- **restricted operational fields** — security-sensitive configuration, credentials, protected infrastructure details;
- **protected personal fields** — personally identifiable, health, education, benefits, employment, or other legally protected information;
- **auditor-only evidence** — material necessary to verify a finding but inappropriate for public release.

Redaction should not erase the public's ability to understand the nature, consequence, and disposition of a finding.

# Evidence confidence

Each finding may include an evidence-confidence tag:

- **E1 — Direct system evidence:** logs, outputs, recordings, transaction records.
- **E2 — Reproduced test evidence:** failure reproduced under documented conditions.
- **E3 — Documentary evidence:** contracts, policies, system documentation, vendor materials.
- **E4 — Human testimony:** user, worker, administrator, or evaluator report.
- **E5 — Inference:** conclusion derived from multiple evidence sources but not directly observed.

A strong finding can combine several classes.

# Accessibility of the audit record

The audit itself must follow ECHO's doctrine.

Public cards should be:

- available as semantic HTML and plain text/Markdown;
- keyboard operable;
- screen-reader structured;
- understandable without color alone;
- accompanied by text alternatives for diagrams;
- exportable in a machine-readable representation;
- written with a plain-language summary for consequential findings;
- usable under zoom/reflow and low-bandwidth conditions.

# Status

Working schema v0.1. Field names and controlled vocabularies are expected to evolve through case-study use, government procurement testing, and public review.
