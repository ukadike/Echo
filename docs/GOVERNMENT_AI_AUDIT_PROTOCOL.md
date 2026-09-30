# ECHO Government AI Audit Protocol v0.1

**ECHO · Small Systems Lab**  
**Published:** September 30, 2026  
**Status:** Working public research protocol

> **Access is a condition of correctness.**

> **A government AI system is not acceptable merely because it performs well on average. It must remain usable, contestable, reviewable, and governable across the people and conditions government is responsible for serving.**

## Purpose

The ECHO Government AI Audit Protocol applies **Accessibility-Constrained Intelligence (ACI)** to public-sector AI systems.

ECHO does not treat accessibility as a final interface check. It uses accessibility and human variation as a **stress test of AI quality, public accountability, and administrative consequence**.

The audit asks:

> **For whom does this system work, under what conditions, and what happens when those conditions change?**

For government uses, the answer must include not only model performance but also the path from:

```text
input
→ perception
→ inference
→ recommendation
→ government action
→ human consequence
→ explanation
→ challenge
→ correction / redress
```

A failure at any layer can turn a technical defect into a public-service failure.

## Scope

The protocol is designed for AI used or procured by:

- federal agencies;
- state and local governments;
- public authorities;
- public schools and universities;
- public-benefit administrators;
- government contractors acting within a public-service workflow;
- public-facing government digital services;
- high-consequence internal government decision-support systems.

Example domains include benefits, housing, employment, education, licensing, transportation, emergency services, healthcare administration, public safety, procurement, constituent services, and records access.

ECHO does **not** assume that every AI system has the same legal duties or risk profile. Applicable law and policy depend on jurisdiction, agency, system function, population, and consequence.

## What ECHO audits

### 1. Purpose

- What public function is the system performing?
- Is AI necessary for the stated purpose?
- What outcome is the system optimizing?
- What population is affected?
- What happens when the system is wrong?

### 2. Authority

- Who authorized the AI use?
- What decisions may the AI make, recommend, rank, route, or trigger?
- What decisions remain with a human official?
- Can system authority silently expand through tools, integrations, model updates, or vendor changes?

### 3. Data and representation

- What populations and modalities are represented in development and evaluation data?
- What languages, dialects, speech patterns, bodies, disabilities, devices, literacy levels, and environmental conditions are missing?
- Are limitations documented?
- Is provenance available where necessary for audit?

### 4. Perception

ECHO tests whether the system can correctly receive and interpret people and their information.

Examples:

- atypical or dysarthric speech;
- screen-reader output;
- low vision;
- captions and transcripts;
- alternative input devices;
- tremor or limited dexterity;
- nonstandard movement;
- noisy environments;
- low bandwidth;
- interrupted sessions;
- multilingual and dialect variation;
- atypical body presentation in computer vision.

### 5. Reasoning and inference

- Does a change in access condition change the model's inference?
- Does the system turn uncertainty into an unsupported assumption?
- Does it confuse communication difference with lack of credibility, intent, eligibility, compliance, or capacity?
- Are confidence and uncertainty available to appropriate reviewers?

### 6. Action

- What government action can follow from the AI output?
- Is the AI informational, advisory, recommendatory, or operational?
- Can the system deny, delay, deprioritize, flag, investigate, terminate, route, or escalate a person's case?
- Are consequential actions separately authorized?

### 7. Human access

ECHO applies the ACI vector:

```text
A = (P, O, U, R, C, L, M, G)
```

- **P — Perceivable**
- **O — Operable**
- **U — Understandable**
- **R — Robust**
- **C — Cognitive access**
- **L — Linguistic access**
- **M — Modal equivalence**
- **G — Agency**

### 8. Human override

- Can an authorized worker recognize a suspect AI result?
- Can the worker override it?
- Is override technically possible, procedurally permitted, logged, and reviewable?
- Does automation bias or workflow design make nominal human review meaningless?

### 9. Contestability

A person affected by the AI should have an appropriate path to:

- know that AI materially influenced the process when disclosure is required or appropriate;
- understand the relevant basis for a consequential result;
- correct inaccurate information;
- present missing context;
- request human review;
- challenge the outcome;
- use the challenge process through accessible modalities.

### 10. Evidence and reconstruction

The audit asks whether authorized investigators can reconstruct:

```text
relevant input
→ model/system version
→ tools and data accessed
→ output
→ authority exercised
→ human intervention
→ resulting government action
```

ECHO does not require unrestricted disclosure of private model reasoning. It requires the evidence necessary for legitimate governance and accountability.

### 11. Monitoring

- Are error patterns monitored after deployment?
- Are affected populations represented in monitoring?
- Do model, vendor, policy, prompt, data, or interface changes trigger reevaluation?
- Can an agency detect performance drift across access conditions?

### 12. Redress

- What happens after a failure harms or disadvantages someone?
- Can the underlying record be corrected?
- Can the government action be reversed?
- Is there an accessible appeal path?
- Is the person restored to the position they would have occupied absent the failure where possible?
- Is the underlying system corrected for future users?

## The ECHO differential condition test

A central ECHO method is **paired testing**.

The same substantive task is tested under different human or environmental conditions.

Example:

```text
Task: Submit a benefits recertification.

Test A: standard mouse + visual interface
Test B: keyboard only
Test C: screen reader
Test D: voice input with atypical speech
Test E: interrupted session
Test F: plain-language / reduced cognitive load
Test G: multilingual interaction
Test H: low-bandwidth connection
```

ECHO then compares:

- completion rate;
- error rate;
- time and interaction burden;
- model confidence;
- requests for clarification;
- downstream classification;
- escalation rate;
- government outcome;
- ability to recover;
- ability to contest.

The critical question is not simply whether the interface changes.

It is:

> **Does the governmental outcome change because the person's access condition changed?**

## Consequence trace

ECHO records the full consequence chain.

Example:

```text
unlabeled control
→ applicant cannot upload document
→ system marks application incomplete
→ automated workflow routes case to denial
→ applicant loses benefit
```

This is classified as more than an interface defect. It is an **access-to-administrative-outcome failure**.

## ECHO government audit gates

A system can perform well overall and still fail the audit when a mandatory gate fails.

### Gate 1 — Purpose and authority

The AI's role and decision authority must be explicit.

### Gate 2 — Access

A required public service cannot depend on an interaction path that excludes affected people without an effective equivalent path.

### Gate 3 — Differential outcome

Materially worse outcomes under an access condition require investigation and cannot be hidden by aggregate accuracy.

### Gate 4 — Consequential action

A high-consequence action must have documented authorization and safeguards appropriate to its consequence.

### Gate 5 — Human review

Where human review is required, it must be operationally meaningful rather than nominal.

### Gate 6 — Contestability

A consequential result must have an appropriate correction, review, or appeal path.

### Gate 7 — Audit evidence

The system must preserve sufficient evidence to reconstruct consequential actions.

### Gate 8 — Change control

Material system changes must be detectable and, where appropriate, trigger reevaluation.

### Gate 9 — Redress

The agency must have a defined response when an AI-related failure causes material harm.

## Failure classes

ECHO records failures by mechanism rather than using one aggregate score.

- **ACCESS-PERCEPTION** — the system cannot reliably receive or recognize a person/input.
- **ACCESS-OPERATION** — a person cannot operate a required workflow.
- **ACCESS-COGNITIVE** — complexity, pacing, memory, or executive-function assumptions prevent meaningful use.
- **ACCESS-LANGUAGE** — language/dialect handling changes service quality or outcome.
- **MODALITY-LOSS** — essential meaning or action is lost between modalities.
- **INFERENCE-DIVERGENCE** — equivalent substantive inputs produce materially different inference under different access conditions.
- **AUTHORITY-OVERREACH** — the system acts beyond documented authority.
- **HUMAN-REVIEW-FAILURE** — nominal oversight cannot practically inspect or change the result.
- **CONTESTABILITY-FAILURE** — the affected person cannot meaningfully challenge or correct the result.
- **AUDITABILITY-FAILURE** — consequential behavior cannot be reconstructed.
- **REDRESS-FAILURE** — harm cannot be appropriately corrected or escalated.
- **CHANGE-CONTROL-FAILURE** — an update materially alters audited behavior without adequate reevaluation.

## Audit lifecycle

```text
PUBLIC NEED
   ↓
RFP / REQUIREMENTS
   ↓
ECHO PROCUREMENT REVIEW
   ↓
VENDOR EVIDENCE
   ↓
PRE-DEPLOYMENT TESTING
   ↓
DEPLOYMENT GATE
   ↓
LIVE MONITORING
   ↓
INCIDENT / COMPLAINT
   ↓
RETEST + REMEDIATION
   ↓
PUBLIC AUDIT RECORD
```

ECHO therefore has three operational forms:

### ECHO Procurement Review

Used before acquisition or renewal.

### ECHO System Audit

Used before deployment or on an existing system.

### ECHO Continuous Assurance

Used for post-deployment monitoring, change control, incident response, and periodic reevaluation.

## Procurement evidence

Depending on the system and jurisdiction, a procurement review may request:

- system purpose and intended-use statement;
- model/system card;
- architecture and data-flow diagram;
- accessibility conformance documentation;
- evaluation reports;
- known limitations;
- supported languages and modalities;
- test-population descriptions;
- error analysis disaggregated by relevant conditions;
- human-review workflow;
- audit/logging capabilities;
- change-management policy;
- incident-response procedure;
- appeal/redress integration;
- vendor update and notification obligations.

Vendor claims are evidence inputs, not automatic proof of conformance.

## Public ECHO Audit Record

Each audit should produce a structured public record when law, privacy, security, procurement restrictions, and legitimate confidentiality requirements permit.

Minimum public fields:

- system;
- agency;
- public function;
- AI role and authority;
- version/date audited;
- populations/access conditions tested;
- methods;
- findings;
- failed gates;
- downstream consequences;
- evidence class;
- remediation status;
- retest status;
- limitations;
- redactions and their basis where applicable.

Machine- and human-readable schema cards are defined in:

[Government AI Audit Schema Cards](GOVERNMENT_AI_AUDIT_SCHEMA_CARDS.md)

## Example: fictional public-benefits assistant

This example is **fictional** and exists only to illustrate the method.

**System:** City Benefits Assistant v4.2  
**Function:** assists with benefits recertification  
**AI authority:** classification and recommendation only  
**Human authority:** caseworker retains final decision authority

Paired testing discovers that voice recognition failures occur substantially more often in a test set containing atypical speech.

The important ECHO finding is not merely:

> speech recognition error

The audit follows the chain:

```text
speech recognition error
→ required answer recorded incorrectly
→ application classified incomplete
→ case routed toward adverse action
```

The audit then tests:

- whether uncertainty was surfaced;
- whether the applicant could correct the transcript;
- whether the caseworker could identify the error;
- whether adverse action could occur without human review;
- whether the applicant could appeal through an accessible route;
- whether the authoritative audit record preserved the original interaction.

## Relationship to existing U.S. government frameworks

ECHO is an independent research framework. It does not replace statutory, regulatory, procurement, civil-rights, security, privacy, or agency-specific requirements.

Relevant reference points include:

- **NIST AI Risk Management Framework** — lifecycle-oriented AI risk management organized around Govern, Map, Measure, and Manage: https://www.nist.gov/itl/ai-risk-management-framework
- **NIST TEVV-Athlon** — 2026 draft framework for adaptable testing, evaluation, verification, and validation of real-world AI systems: https://www.nist.gov/artificial-intelligence/ai-research/tevv-athlon-framework-evaluating-ai-systems
- **OMB M-25-21** — current federal executive-branch guidance on agency AI use, governance, and public trust: https://www.whitehouse.gov/wp-content/uploads/2025/02/M-25-21-Accelerating-Federal-Use-of-AI-through-Innovation-Governance-and-Public-Trust.pdf
- **OMB M-25-22** — current federal guidance on acquisition of AI: https://www.whitehouse.gov/wp-content/uploads/2025/02/M-25-22-Driving-Efficient-Acquisition-of-Artificial-Intelligence-in-Government.pdf
- **Section 508 Accessibility Requirements Tool / Solicitation Review Tool** — federal procurement resources for identifying and reviewing ICT accessibility requirements: https://www.section508.gov/art/ and https://www.section508.gov/buy/solicitation-review-tool/
- **ADA Title II** — state and local government disability nondiscrimination requirements. DOJ's current web/mobile rule uses WCAG 2.1 Level AA for covered web content and mobile apps, with compliance dates described by DOJ: https://www.ada.gov/resources/web-rule-first-steps/

ECHO's distinctive contribution is to connect access testing to **AI inference, administrative action, governance, contestability, and human consequence**.

## Legal and methodological boundary

An ECHO audit is not, by itself, a legal compliance certification.

A legal conclusion depends on the applicable jurisdiction, facts, governing law, contract, agency authority, and procedural requirements.

ECHO provides a repeatable public-interest assurance method for identifying and documenting AI-system failures that may warrant technical, administrative, legal, procurement, accessibility, civil-rights, or policy review.

## Research direction

Next versions should develop:

- executable test fixtures;
- machine-readable audit schemas;
- statistically defensible paired-test designs;
- severity and consequence taxonomy;
- procurement clauses;
- model/vendor change triggers;
- accessible public reporting interfaces;
- incident-to-redress tracking;
- independent evaluator requirements;
- government-specific case studies.

