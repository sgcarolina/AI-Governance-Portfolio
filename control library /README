# Cohere AI Platform — AI Governance Controls Framework

**Platform:** Cohere (Command, Embed, Rerank, North, Compass)
**Context:** Financial Services | Aligned to NIST AI RMF & SR 11-7
**Reference:** NIST SP 800-53 Rev 5
**Date:** June 2026
**Total Controls:** 20 across 10 categories

---

## 1. Identity & Access Management

---

**Control ID —** COHERE-IAM-01

**Control Name —** Role-Based Access Control for Cohere Endpoints

**NIST SP 800-53 Control —** AC-2: Account Management

**Type —** Preventive | **Priority —** High

**Frameworks —** SR 11-7, ISO 27001, NIST CSF

**Linked Risks —** API key exposure, Shadow AI deployment

**Implementation Statement —**
The AI Governance and IAM Team implements COHERE-IAM-01 by restricting access to Cohere API endpoints to authorized personnel based on documented business need and job function. The organization uses a centralized IAM platform (e.g., Okta or Azure AD) with role-based access controls to enforce least-privilege access across developer, data scientist, and governance reviewer roles. This occurs upon onboarding, role change, and quarterly entitlement reviews. Results are reviewed by the AI Governance Lead and IAM Owner. Evidence includes access review reports, user entitlement exports, role assignment records, and API credential provisioning logs.

---

**Control ID —** COHERE-IAM-02

**Control Name —** Multi-Factor Authentication for North Platform Access

**NIST SP 800-53 Control —** IA-5: Authenticator Management

**Type —** Preventive | **Priority —** High

**Frameworks —** ISO 27001, NIST CSF, SOC 2

**Linked Risks —** API key exposure, Cross-tenant data leakage

**Implementation Statement —**
The IT Security Team implements COHERE-IAM-02 by requiring multi-factor authentication for all users accessing the Cohere North enterprise agent platform. The organization uses enterprise identity provider federation (Okta or Azure AD) to enforce MFA at the authentication layer and log all access events to the enterprise SIEM. This occurs at every login event and is reviewed for anomalous patterns on a continuous basis. Results are reviewed by the IT Security Lead and AI Governance Lead. Evidence includes MFA enrollment reports, authentication logs, anomaly alerts, and identity provider configuration exports.

---

## 2. Data Protection

---

**Control ID —** COHERE-DP-01

**Control Name —** PII Scrubbing Before RAG Pipeline Ingestion

**NIST SP 800-53 Control —** PT-2: Personally Identifiable Information Processing Purposes

**Type —** Preventive | **Priority —** High

**Frameworks —** GLBA, CCPA, NIST Privacy Framework

**Linked Risks —** Member PII ingested into RAG pipelines, Data residency violations

**Implementation Statement —**
The Data Engineering Team implements COHERE-DP-01 by deploying a named entity recognition (NER) pipeline upstream of all document ingestion workflows that feed Cohere Embed or Rerank. The organization uses an automated PII detection and redaction tool to identify and tokenize SSNs, account numbers, and member identifiers before documents enter the retrieval pipeline. This occurs at every ingestion event and is validated through quarterly effectiveness testing. Results are reviewed by the Privacy Officer and AI Governance Lead. Evidence includes PII scan logs, redaction reports, ingestion pipeline configuration documentation, and quarterly validation test results.

---

**Control ID —** COHERE-DP-02

**Control Name —** Data Residency Enforcement via Private Deployment

**NIST SP 800-53 Control —** SC-28: Protection of Information at Rest

**Type —** Preventive | **Priority —** High

**Frameworks —** GLBA, CCPA, ISO 27001

**Linked Risks —** Data residency violations for regulated member data, Cross-tenant data leakage

**Implementation Statement —**
The Cloud Infrastructure and AI Governance Teams implement COHERE-DP-02 by deploying Cohere via a US-region private VPC or on-premises Model Vault for all workloads that involve member data. The organization uses Cohere's Model Vault deployment architecture to ensure member data does not leave defined geographic boundaries required under GLBA and enterprise data governance policy. This occurs at initial deployment and is revalidated after any infrastructure change or contract renewal. Results are reviewed by the Chief Information Security Officer and Privacy Officer. Evidence includes VPC configuration exports, data flow diagrams, deployment architecture documentation, and residency validation records.

---

**Control ID —** COHERE-DP-03

**Control Name —** Data Processing Addendum Execution and Annual Review

**NIST SP 800-53 Control —** SA-9: External System Services

**Type —** Preventive | **Priority —** High

**Frameworks —** GLBA, CCPA, SOC 2

**Linked Risks —** Model training on enterprise prompts, Insufficient vendor AI risk transparency

**Implementation Statement —**
The Legal and Vendor Management Teams implement COHERE-DP-03 by executing a Data Processing Addendum (DPA) with Cohere prior to any production deployment. The organization uses the enterprise vendor contract management system to track DPA execution status, renewal dates, and key contractual obligations including prohibitions on training data use and data sharing. This occurs prior to initial deployment and is reviewed annually at contract renewal. Results are reviewed by the General Counsel, Privacy Officer, and AI Governance Lead. Evidence includes the executed DPA, contract management system records, annual review documentation, and legal sign-off records.

---

## 3. Human Oversight

---

**Control ID —** COHERE-HO-01

**Control Name —** Human Approval for High-Risk AI Outputs

**NIST SP 800-53 Control —** CP-2: Contingency Plan / SI-12: Information Management and Retention

**Type —** Preventive | **Priority —** High

**Frameworks —** NIST AI RMF, EU AI Act, SR 11-7, ECOA

**Linked Risks —** Automation bias in AI-assisted decisioning, Accountability gaps when AI and human decisions intersect

**Implementation Statement —**
The AI Governance Team implements COHERE-HO-01 by defining consequential decision thresholds for each Cohere-powered workflow and requiring documented human sign-off before any action affecting a member is taken. The organization uses workflow routing rules and human review queues built into each AI-assisted application to enforce the approval gate. This occurs at every instance where a Cohere output meets or exceeds the defined risk threshold and is tracked monthly through override rate and escalation frequency reporting. Results are reviewed by the AI Governance Lead and Business Process Owner. Evidence includes workflow configuration documentation, human approval logs, override rate reports, and escalation records.

---

**Control ID —** COHERE-HO-02

**Control Name —** User Feedback and Output Flagging Mechanism

**NIST SP 800-53 Control —** SI-2: Flaw Remediation

**Type —** Detective | **Priority —** Medium

**Frameworks —** NIST AI RMF MANAGE, SR 11-7

**Linked Risks —** Insufficient override and feedback mechanisms, Hallucinated outputs damaging member trust

**Implementation Statement —**
The Product and AI Governance Teams implement COHERE-HO-02 by embedding a structured flagging interface (thumbs down, category selection) into every Cohere-powered application used by staff. The organization uses a centralized feedback intake system to route flagged outputs to the AI Governance Team within 24 hours of submission. This occurs on a continuous basis and is aggregated monthly for inclusion in model performance reporting. Results are reviewed by the AI Governance Lead and Model Owner. Evidence includes flagging interface configuration records, feedback intake logs, monthly aggregation reports, and model performance review documentation.

---

## 4. Monitoring & Logging

---

**Control ID —** COHERE-ML-01

**Control Name —** Prompt and Completion Audit Logging

**NIST SP 800-53 Control —** AU-2: Event Logging

**Type —** Detective | **Priority —** High

**Frameworks —** SR 11-7, ISO 27001, SOC 2, NIST CSF

**Linked Risks —** Prompt injection and adversarial input attacks, Shadow AI deployment, API key exposure

**Implementation Statement —**
The IT Security and AI Governance Teams implement COHERE-ML-01 by enabling comprehensive logging of all Cohere API requests, prompts, and completions across every production integration. The organization uses the enterprise SIEM platform to ingest, store, and monitor Cohere logs with a minimum 12-month retention period and automated alerting on anomalous volume, error spikes, and after-hours access. This occurs on a continuous basis with log reviews triggered by defined alert thresholds and following any security incident. Results are reviewed by the IT Security Lead and AI Governance Lead. Evidence includes SIEM ingestion configuration, log retention policy documentation, alert rule definitions, and incident response records.

---

**Control ID —** COHERE-ML-02

**Control Name —** Model Performance and Drift Monitoring

**NIST SP 800-53 Control —** CA-7: Continuous Monitoring

**Type —** Detective | **Priority —** High

**Frameworks —** SR 11-7, NIST AI RMF MANAGE

**Linked Risks —** Model drift degrading output quality over time, Automation bias in AI-assisted decisioning

**Implementation Statement —**
The AI Governance and Data Science Teams implement COHERE-ML-02 by establishing baseline performance metrics for each Cohere production use case and implementing automated monitoring with thresholds that trigger governance review when exceeded. The organization uses a model monitoring platform to track accuracy, hallucination rate, and retrieval precision on a continuous basis with formal quarterly performance assessments aligned to SR 11-7 ongoing monitoring requirements. This occurs continuously with quarterly formal reviews. Results are reviewed by the Model Validator and AI Governance Lead. Evidence includes baseline metric documentation, monitoring dashboard exports, threshold breach alerts, quarterly performance assessment reports, and remediation action logs.

---

**Control ID —** COHERE-ML-03

**Control Name —** Bias and Fairness Monitoring for Member-Facing Use Cases

**NIST SP 800-53 Control —** RA-3: Risk Assessment

**Type —** Detective | **Priority —** High

**Frameworks —** ECOA, CFPB, EU AI Act, NIST AI RMF

**Linked Risks —** Biased or discriminatory AI outputs affecting members, Hallucinated outputs damaging member trust

**Implementation Statement —**
The AI Governance and Fair Lending Teams implement COHERE-ML-03 by conducting bias evaluation tests against protected class proxies including race, gender, age, and national origin prior to deployment and quarterly in production for all member-facing Cohere use cases. The organization uses a bias testing framework aligned to ECOA and fair lending requirements to assess model outputs for disparate impact. This occurs pre-deployment and quarterly thereafter, with findings above defined thresholds escalated immediately to the Fair Lending Team and Chief Risk Officer. Results are reviewed by the AI Governance Lead, Fair Lending Officer, and Model Validator. Evidence includes bias test methodology documentation, test result reports, escalation records, and remediation action logs.

---

## 5. Third-Party Risk

---

**Control ID —** COHERE-TPR-01

**Control Name —** Vendor Security Assessment and Annual Reassessment

**NIST SP 800-53 Control —** SR-6: Supplier Assessments and Reviews

**Type —** Detective | **Priority —** Medium

**Frameworks —** SR 11-7, NIST AI RMF, ISO 27001

**Linked Risks —** Vendor concentration and single-provider dependency, Insufficient vendor AI risk transparency, Fourth-party risk via cloud infrastructure

**Implementation Statement —**
The Vendor Risk Management Team implements COHERE-TPR-01 by maintaining a vendor risk dossier for Cohere that includes current SOC 2 Type II, ISO 27001, and ISO 42001 certifications, penetration test summaries, SLA documentation, and AI risk practice disclosures. The organization uses the enterprise vendor risk management platform to track dossier completeness, certification expiration dates, and reassessment due dates. This occurs annually and is triggered additionally by any major Cohere platform update or security incident. Results are reviewed by the Chief Risk Officer and AI Governance Lead. Evidence includes the Cohere vendor risk dossier, certification copies, reassessment reports, and risk acceptance or escalation documentation.

---

**Control ID —** COHERE-TPR-02

**Control Name —** Fourth-Party Cloud Infrastructure Risk Tracking

**NIST SP 800-53 Control —** SR-3: Supply Chain Controls and Plans

**Type —** Detective | **Priority —** Medium

**Frameworks —** NIST CSF, ISO 27001, SR 11-7

**Linked Risks —** Fourth-party risk via Cohere's cloud infrastructure partners, Vendor concentration and single-provider dependency

**Implementation Statement —**
The Vendor Risk Management and Business Continuity Teams implement COHERE-TPR-02 by mapping Cohere's cloud infrastructure dependencies — including AWS, Azure, GCP, and Oracle — in the enterprise fourth-party risk register and assessing provider concentration risk. The organization uses the enterprise BCM platform to include Cohere-dependent processes in continuity planning and recovery runbook documentation. This occurs annually and recovery runbooks are tested semi-annually. Results are reviewed by the Chief Risk Officer, Business Continuity Lead, and AI Governance Lead. Evidence includes the fourth-party risk register entries, BCM plan documentation, recovery runbook test results, and concentration risk assessment records.

---

## 6. Responsible AI

---

**Control ID —** COHERE-RAI-01

**Control Name —** AI Use Case Risk Classification Before Deployment

**NIST SP 800-53 Control —** RA-2: Security Categorization

**Type —** Preventive | **Priority —** High

**Frameworks —** NIST AI RMF, EU AI Act, SR 11-7

**Linked Risks —** Regulatory examination readiness gap, AI Act and emerging regulatory non-compliance, Biased or discriminatory AI outputs

**Implementation Statement —**
The AI Governance Team implements COHERE-RAI-01 by applying the enterprise AI risk classification framework to all proposed Cohere use cases prior to production deployment. The organization uses a standardized risk classification intake form aligned to NIST AI RMF MAP and EU AI Act Annex III criteria to assign a risk tier (high, limited, or minimal) and route high-risk use cases to the AI Governance Committee for approval. This occurs at the initiation of every new Cohere use case or material modification to an existing one. Results are reviewed by the AI Governance Committee and Chief Risk Officer. Evidence includes completed risk classification intake forms, committee approval records, use case registry entries, and escalation documentation.

---

**Control ID —** COHERE-RAI-02

**Control Name —** AI Transparency Disclosure for Member-Facing Interactions

**NIST SP 800-53 Control —** PT-5: Privacy Notice

**Type —** Preventive | **Priority —** Medium

**Frameworks —** CFPB, EU AI Act, NIST AI RMF GOVERN

**Linked Risks —** Negative public perception of AI adoption, Hallucinated outputs damaging member trust

**Implementation Statement —**
The Product, Legal, and AI Governance Teams implement COHERE-RAI-02 by adding a visible AI disclosure label to all member-facing Cohere-powered interfaces and updating terms of service to include AI interaction disclosure language. The organization uses UI design standards and a pre-deployment compliance checklist to verify disclosure requirements are met before any member-facing Cohere application goes live. This occurs at deployment of each member-facing use case and is reviewed annually for continued adequacy. Results are reviewed by the Chief Compliance Officer, Privacy Officer, and AI Governance Lead. Evidence includes UI design documentation showing disclosure placement, terms of service versions, pre-deployment checklist records, and annual review sign-off documentation.

---

## 7. Incident Response

---

**Control ID —** COHERE-IR-01

**Control Name —** AI Incident Classification and Response Playbook

**NIST SP 800-53 Control —** IR-8: Incident Response Plan

**Type —** Corrective | **Priority —** High

**Frameworks —** NIST AI RMF MANAGE, NIST CSF, SR 11-7, ISO 27001

**Linked Risks —** Prompt injection and adversarial input attacks, Member PII ingested into RAG pipelines, Biased or discriminatory AI outputs, Integration failure between Cohere and legacy systems

**Implementation Statement —**
The AI Governance and IT Security Teams implement COHERE-IR-01 by developing and maintaining an AI-specific incident response playbook covering prompt injection, PII exposure, model output failures, and bias events. The organization uses the enterprise incident response management platform to classify, assign, track, and close AI incidents with defined severity tiers, escalation paths, and communication templates integrated into the enterprise IR process. This occurs on a continuous basis for incident detection and response, with tabletop exercises conducted semi-annually to validate playbook effectiveness. Results are reviewed by the Chief Information Security Officer, Chief Risk Officer, and AI Governance Lead. Evidence includes the AI incident response playbook, incident tickets, tabletop exercise reports, escalation records, and after-action documentation.

---

**Control ID —** COHERE-IR-02

**Control Name —** Model Rollback and Contingency Procedure

**NIST SP 800-53 Control —** CP-10: System Recovery and Reconstitution

**Type —** Corrective | **Priority —** Medium

**Frameworks —** SR 11-7, NIST AI RMF MANAGE

**Linked Risks —** Model drift degrading output quality, Integration failure between Cohere and legacy systems

**Implementation Statement —**
The AI Governance and Engineering Teams implement COHERE-IR-02 by documenting rollback procedures for each Cohere-powered workflow, including manual fallback paths to human-handled processes. The organization uses version-controlled deployment configurations and defined performance degradation thresholds to trigger the rollback decision process automatically. This occurs whenever performance monitoring thresholds are breached and rollback capability is tested quarterly. Results are reviewed by the AI Governance Lead, Model Owner, and Engineering Lead. Evidence includes rollback procedure documentation, threshold definition records, quarterly rollback test results, and incident records where rollback was executed.

---

## 8. Compliance & Regulatory

---

**Control ID —** COHERE-CR-01

**Control Name —** SR 11-7 Model Inventory Registration for Cohere Deployments

**NIST SP 800-53 Control —** PM-5: System Inventory

**Type —** Preventive | **Priority —** High

**Frameworks —** SR 11-7, OCC, NIST AI RMF

**Linked Risks —** Regulatory examination readiness gap, Model drift degrading output quality, Accountability gaps when AI and human decisions intersect

**Implementation Statement —**
The AI Governance and Model Risk Management Teams implement COHERE-CR-01 by registering each Cohere-powered use case in the enterprise model inventory prior to production deployment with documented model purpose, inputs, outputs, data sources, known limitations, model owner, and assigned validator. The organization uses the enterprise model risk management platform to maintain inventory records and track validation status, ongoing monitoring cadence, and review dates aligned to SR 11-7 requirements. This occurs at the initiation of every new Cohere use case and is updated upon any material model change. Results are reviewed by the Model Risk Officer and Chief Risk Officer. Evidence includes model inventory records, model documentation packages, validation reports, and ongoing monitoring schedules.

---

**Control ID —** COHERE-CR-02

**Control Name —** ISO 42001 Gap Assessment and Remediation Tracking

**NIST SP 800-53 Control —** CA-2: Control Assessments

**Type —** Corrective | **Priority —** Medium

**Frameworks —** ISO 42001, NIST AI RMF GOVERN

**Linked Risks —** ISO 42001 alignment gap, Regulatory examination readiness gap

**Implementation Statement —**
The AI Governance Team implements COHERE-CR-02 by conducting a structured gap assessment of the enterprise AI governance program against ISO 42001 AI management system controls. The organization uses a gap assessment workbook to document findings, assign remediation owners, set target completion dates, and track progress against the remediation roadmap. This occurs annually and is reported to the AI Governance Committee quarterly. Results are reviewed by the Chief Risk Officer and AI Governance Committee. Evidence includes the completed ISO 42001 gap assessment workbook, remediation roadmap, quarterly progress reports, and AI Governance Committee meeting minutes reflecting status updates.

---

## 9. Model Governance

---

**Control ID —** COHERE-MG-01

**Control Name —** Model Validation and Conceptual Soundness Review

**NIST SP 800-53 Control —** SA-11: Developer Testing and Evaluation

**Type —** Detective | **Priority —** High

**Frameworks —** SR 11-7, NIST AI RMF MAP

**Linked Risks —** Model drift degrading output quality, Automation bias in AI-assisted decisioning, Biased or discriminatory AI outputs

**Implementation Statement —**
The Model Risk Management Team implements COHERE-MG-01 by conducting initial model validation for each Cohere production use case including conceptual soundness review, outcome analysis, sensitivity testing, and documentation of known limitations. The organization uses the enterprise model validation framework to assign an independent validator — separate from the model development team — in compliance with SR 11-7 independence requirements. This occurs prior to each production deployment and following any material model change. Results are reviewed by the Model Risk Officer and Chief Risk Officer. Evidence includes model validation reports, conceptual soundness assessments, outcome analysis results, validator independence documentation, and model risk committee approval records.

---

**Control ID —** COHERE-MG-02

**Control Name —** RAG Retrieval Quality and Grounding Controls

**NIST SP 800-53 Control —** SI-10: Information Input Validation

**Type —** Detective | **Priority —** Medium

**Frameworks —** NIST AI RMF, CFPB, SR 11-7

**Linked Risks —** Hallucinated outputs damaging member trust, Unstructured data governance in RAG pipelines

**Implementation Statement —**
The AI Governance and Data Engineering Teams implement COHERE-MG-02 by implementing confidence thresholds for all Cohere retrieval-augmented generation responses and routing low-confidence outputs to human agents rather than displaying them to members. The organization uses the Cohere North platform's retrieval configuration settings and an enterprise content audit process to maintain verified, current, and authorized retrieval source documentation. This occurs continuously for confidence threshold enforcement and quarterly for retrieval source audits. Results are reviewed by the AI Governance Lead, Model Owner, and Data Owner. Evidence includes confidence threshold configuration records, retrieval source audit reports, routing logs showing low-confidence escalations, and quarterly review documentation.

---

## 10. Change Management

---

**Control ID —** COHERE-CM-01

**Control Name —** AI Change Control and Pre-Production Testing Gate

**NIST SP 800-53 Control —** CM-3: Configuration Change Control

**Type —** Preventive | **Priority —** High

**Frameworks —** SR 11-7, NIST AI RMF, ISO 27001

**Linked Risks —** Model drift degrading output quality, Shadow AI deployment outside governance framework, Integration failure between Cohere and legacy systems

**Implementation Statement —**
The AI Governance and Engineering Teams implement COHERE-CM-01 by requiring all changes to Cohere-powered workflows — including model version updates, prompt modifications, and integration changes — to pass through the enterprise change control process with a mandatory AI governance review gate for high-risk use cases. The organization uses the enterprise change management platform to track change requests, regression test results, governance approvals, and production deployment records. This occurs prior to every production change and is enforced through change advisory board review for high-risk use cases. Results are reviewed by the Change Advisory Board, AI Governance Lead, and Engineering Lead. Evidence includes change request tickets, regression test reports, governance approval records, and production deployment logs.

---

**Control ID —** COHERE-CM-02

**Control Name —** Shadow AI Detection and Governance Intake Enforcement

**NIST SP 800-53 Control —** CM-8: System Component Inventory

**Type —** Corrective | **Priority —** Medium

**Frameworks —** NIST AI RMF GOVERN, SR 11-7

**Linked Risks —** Shadow AI deployment outside governance framework, Vendor concentration and single-provider dependency

**Implementation Statement —**
The AI Governance Team implements COHERE-CM-02 by publishing an approved AI tools list and governance intake form accessible to all business units and enforcing API key provisioning for Cohere exclusively through the AI Governance Team. The organization uses network traffic analysis and procurement review processes to conduct quarterly shadow AI audits and identify unauthorized Cohere deployments. This occurs quarterly for scheduled audits and on a triggered basis when unauthorized activity is detected. Results are reviewed by the Chief Risk Officer and AI Governance Lead. Evidence includes the approved AI tools list, intake form submission records, API key provisioning logs, quarterly audit reports, and remediation records for unauthorized deployments resolved within the 30-day remediation window.

---

## NIST SP 800-53 Rev 5 Control Mapping Summary

| Control ID | Control Name | NIST 800-53 Control |
|------------|--------------|---------------------|
| COHERE-IAM-01 | Role-Based Access Control for Cohere Endpoints | AC-2: Account Management |
| COHERE-IAM-02 | Multi-Factor Authentication for North Platform Access | IA-5: Authenticator Management |
| COHERE-DP-01 | PII Scrubbing Before RAG Pipeline Ingestion | PT-2: PII Processing Purposes |
| COHERE-DP-02 | Data Residency Enforcement via Private Deployment | SC-28: Protection of Information at Rest |
| COHERE-DP-03 | Data Processing Addendum Execution and Annual Review | SA-9: External System Services |
| COHERE-HO-01 | Human Approval for High-Risk AI Outputs | SI-12: Information Management and Retention |
| COHERE-HO-02 | User Feedback and Output Flagging Mechanism | SI-2: Flaw Remediation |
| COHERE-ML-01 | Prompt and Completion Audit Logging | AU-2: Event Logging |
| COHERE-ML-02 | Model Performance and Drift Monitoring | CA-7: Continuous Monitoring |
| COHERE-ML-03 | Bias and Fairness Monitoring for Member-Facing Use Cases | RA-3: Risk Assessment |
| COHERE-TPR-01 | Vendor Security Assessment and Annual Reassessment | SR-6: Supplier Assessments and Reviews |
| COHERE-TPR-02 | Fourth-Party Cloud Infrastructure Risk Tracking | SR-3: Supply Chain Controls and Plans |
| COHERE-RAI-01 | AI Use Case Risk Classification Before Deployment | RA-2: Security Categorization |
| COHERE-RAI-02 | AI Transparency Disclosure for Member-Facing Interactions | PT-5: Privacy Notice |
| COHERE-IR-01 | AI Incident Classification and Response Playbook | IR-8: Incident Response Plan |
| COHERE-IR-02 | Model Rollback and Contingency Procedure | CP-10: System Recovery and Reconstitution |
| COHERE-CR-01 | SR 11-7 Model Inventory Registration for Cohere Deployments | PM-5: System Inventory |
| COHERE-CR-02 | ISO 42001 Gap Assessment and Remediation Tracking | CA-2: Control Assessments |
| COHERE-MG-01 | Model Validation and Conceptual Soundness Review | SA-11: Developer Testing and Evaluation |
| COHERE-MG-02 | RAG Retrieval Quality and Grounding Controls | SI-10: Information Input Validation |
| COHERE-CM-01 | AI Change Control and Pre-Production Testing Gate | CM-3: Configuration Change Control |
| COHERE-CM-02 | Shadow AI Detection and Governance Intake Enforcement | CM-8: System Component Inventory |

---

## Regulatory Framework Reference

| Framework | Relevance |
|-----------|-----------|
| NIST SP 800-53 Rev 5 | Primary security and privacy control catalog — all 20 controls mapped |
| SR 11-7 | Model risk management — inventory, validation, ongoing monitoring |
| NIST AI RMF | GOVERN, MAP, MEASURE, MANAGE functions across all control categories |
| GLBA | Member financial data protection and privacy requirements |
| CCPA | Consumer data rights and consent obligations |
| EU AI Act | High-risk AI classification, bias testing, human oversight mandates |
| ISO 42001 | AI management system standard — vendor benchmark and internal gap analysis |
| ISO 27001 | Information security controls for AI infrastructure |
| SOC 2 Type II | Vendor trust services criteria — security, availability, confidentiality |
| ECOA | Fair lending and adverse action requirements for AI-assisted decisions |
| CFPB | Consumer financial protection in AI-driven member interactions |
| OCC | Federal banking examination readiness for model risk programs |
| NIST CSF | Cybersecurity framework for operational and infrastructure risk |

---

*This controls framework was produced as part of an AI Governance portfolio. It is intended for educational and professional demonstration purposes.*
