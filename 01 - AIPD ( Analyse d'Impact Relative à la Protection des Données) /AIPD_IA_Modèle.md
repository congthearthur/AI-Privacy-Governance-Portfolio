Cadre juridique :
- RGPD – art. 35 (Analyse d’Impact / AIPD)
- Lignes directrices CEPD WP248 rev.01
- AI Act (UE) – art. 27 : analyse des impacts sur les droits fondamentaux (FRIA)


ENGLISH VERSION: 

# DATA PROTECTION IMPACT ASSESSMENT (DPIA) + PDPL DOSSIER (HYBRID AI SYSTEM)
**Primary Standards:** GDPR (Art. 35) + EDPB Guidelines (WP 248 rev.01)  
**PDPL Alignment:** Vietnam Personal Data Protection Law (Law No. 91/2025/QH15) — DPIA dossier + cross-border dossier + breach workflow  
**Compatibility:** EU AI Act (High-Risk Systems) — FRIA annex  

---

## 0. EVIDENCE PACK INDEX (AUDIT-READY)
> **Release Gate:** No Pilot/Production until every item below is attached or formally risk-accepted by Controller + DPO.

| Evidence ID | Artifact | Location/Link | Owner | Status |
|---|---|---|---|---|
| EP-01 | Data Flow Diagram (Hybrid) | [link] | Eng Lead | [ ] |
| EP-02 | Processing Activities Register (PDPL-R) | [link] | Compliance | [ ] |
| EP-03 | External Recipients & Sub-processors Register | [link] | Procurement/Legal | [ ] |
| EP-04 | Consent Records Export (sample) + Evidence Format Spec | [link] | Product/Compliance | [ ] |
| EP-05 | DSR Register Export (sample) | [link] | Support/Compliance | [ ] |
| EP-06 | Egress Logs Export (sample) | [link] | Eng/Sec | [ ] |
| EP-07 | Deletion & Destruction Proof (jobs + logs) | [link] | Eng/Sec | [ ] |
| EP-08 | Incident Register Template + Tabletop Record | [link] | Sec/DPO | [ ] |
| EP-09 | Vendor “No Training / Retention” Proof Pack | [link] | Legal/Procurement | [ ] |
| EP-10 | PDPL Dossier Submission Evidence (DPIA + Cross-border) | [link] | DPO | [ ] |

---

## 0. DOCUMENT CONTROL + PDPL DOSSIER METADATA (AUDIT-CRITICAL)
**System Name:** [Name of the AI System]  
**Deployment Mode:** **HYBRID** (VN primary storage + foreign AI sub-processors for inference/rerank as permitted)  
**Controller:** [Tenant / Customer Name (e.g., Law Firm)]  
**Processor:** [Your Company Name]  
**DPO / Compliance Owner:** [Name]  
**CISO Owner:** [Name]  
**Date:** YYYY-MM-DD  
**Version:** 2.1 (WP248 + PDPL Hybrid Dossier — Audit Hardened)  
**Status:** [ ] Draft  [ ] Validation  [ ] Approved  
**Lifecycle Stage:** [ ] Design (Prior to Processing) [ ] Pilot [ ] Production [ ] Periodic Review  
**AI Act Classification:** [ ] Prohibited [ ] High Risk [ ] Limited Risk [ ] Minimal Risk  

### 0.1 PDPL 60-DAY CLOCK (MANDATORY)
> PDPL requires the impact assessment dossier to be established/stored and the original copy sent within **60 days** from the **first day of processing**.

- **First Day of Processing (T0):** YYYY-MM-DD  
- **PDPL DPIA Dossier Deadline (T0 + 60 days):** YYYY-MM-DD  
- **Submission Status:** [ ] Not started  [ ] In progress  [ ] Submitted  
- **Competent PDPL Authority / Recipient:** [Name]  
  - **Determination Rule:** [e.g., based on principal place of business / sector / instruction from Controller]  
- **Submission Method:** [Portal / Email / Physical / Other]  
- **Submission Evidence:** [Link to receipt / acknowledgement / courier proof]  
- **Submission Ref No.:** [______]

### 0.2 PDPL DOSSIER UPDATE RULES (MANDATORY)
> PDPL dossier updates: update **every 6 months when changes occur** and **immediately update** in specific cases.

- **Next Scheduled Review (6-month cadence when changes occur):** YYYY-MM-DD  
- **Immediate Update Triggers (PDPL):**
  - [ ] Organizational restructure/termination/dissolution/bankruptcy  
  - [ ] Change of **personal data protection service provider** (incl. AI vendor / reranker / hosting provider supporting personal data processing)  
  - [ ] Change in business line/profession/service related to processing activities  

**Update Log (append-only):**
| Version | Date | Trigger | Summary of Change | Owner | Approver | Evidence Link |
|---|---|---|---|---|---|---|
| 2.1 | YYYY-MM-DD | Initial | Initial PDPL Hybrid Dossier | [Owner] | [Approver] | [link] |
| __ | __ | __ | __ | __ | __ | __ |

### 0.3 HYBRID CROSS-BORDER DOSSIER LINK (MANDATORY)
- **Cross-border Transfer Dossier Annex:** **Annex PDPL-X** (required for HYBRID)  
- **First Cross-border Transfer Date (T0x):** YYYY-MM-DD  
- **Cross-border Dossier Deadline (T0x + 60 days):** YYYY-MM-DD  
- **Cross-border Submission Evidence:** [Link]  

### 0.4 BREACH CLOCK + 72-HOUR WORKFLOW LINK (MANDATORY)
> PDPL requires notification within **72 hours from discovery** if harms may occur; incident register required; processor notifies controller promptly.

- **Incident & Breach Response Pack:** **Annex PDPL-Y**  
- **Incident Register Location:** [Link / system module]  
- **Authority Notification Template:** [Link]  
- **Processor → Controller Notification Template:** [Link]  

---

## 1. TRIGGER ASSESSMENT (GDPR/WP248) + PDPL SCOPE CHECK

### 1.1 GDPR TRIGGER ASSESSMENT (WP29 CRITERIA & NATIONAL LISTS)
**Reference:** WP 248 rev.01, Section III.B.a (Pages 8-11)

#### A. National Jurisdiction Check (Art 35(4) & 35(5))
- [ ] Blacklist Check: Processing operation on National DPA “Blacklist” (Art 35(4)) → If YES, DPIA mandatory.  
- [ ] Whitelist Check: Processing operation on National DPA “Whitelist” (Art 35(5)) → If YES, DPIA not required (unless conditions unmet).  
- [ ] Sector-specific DPIA frameworks checked (e.g., health/finance/energy).  

#### B. GDPR “High Risk” Determination (Art 35(1))
| WP29 Criterion (Risk Indicator) | Applicability |
|---|---|
| 1. Evaluation or scoring | [ ] Yes |
| 2. Automated decision-making with legal/significant effect | [ ] Yes |
| 3. Systematic monitoring | [ ] Yes |
| 4. Sensitive data | [ ] Yes |
| 5. Large scale processing | [ ] Yes |
| 6. Matching/combining datasets exceeding expectations | [ ] Yes |
| 7. Vulnerable data subjects | [ ] Yes |
| 8. Innovative use/new tech (AI/LLMs) | [x] Yes (AI System) |
| 9. Preventing rights/service access | [ ] Yes |

#### C. Joint Controllership (Art 26)
- [ ] Sole Controller  
- [ ] Joint Controller (roles defined in attached arrangement)  
- [ ] Safeguard: DPIA sharing does not compromise trade secrets/IP (e.g., weights).  

### 1.2 PDPL SCOPE & APPLICABILITY (HYBRID)
- [ ] System processes personal data as defined under PDPL.  
- [ ] Processing includes AI / cloud / big data components → PDPL requires security/authz and AI risk classification measures.  
- [x] HYBRID uses non-VN sub-processors for inference/rerank → Cross-border Transfer Dossier required (Annex PDPL-X).  
- [ ] PDPL “processing without consent” is used only under documented exception path with proof + monitoring (see §3.2).  

---

## 2. SYSTEMATIC DESCRIPTION & ASSETS (WP248) + HYBRID DATA-FLOW PROOF

### 2.1 Functional Description
- **Nature & Scope:** [Describe what the AI does, scale, number of users, tenant model].  
- **Context:** [Internal tool / client-facing chatbot / legal assistant].  
- **Purposes:** [Legal analysis, contract drafting, compliance Q&A, etc.].  
- **Decision Role:** [ ] Advisory only  [ ] Decision support  [ ] Automated decision-making  

### 2.2 Data Flow Diagram (MANDATORY AUDIT ARTIFACT)
Attach a one-page diagram showing:  
**Ingress → VN Storage → Retrieval/RAG → Risk Gate → Redaction → Cross-border Egress → Response → Logging → Retention/Deletion**  
- **Diagram link:** [____]  

### 2.3 Asset Inventory (Hardware, Software, People)
**Software Assets**
- Model(s): [LLM name/version], reranker(s): [vendor], embeddings: [model]  
- Orchestration: [LangGraph / toolchain]  
- Vector store: [pgvector / Qdrant]  
- Policy engine: [risk gate/redaction module]  

**Hardware & Network**
- Primary hosting in VN: [VN region / on-prem]  
- External calls: [LLM endpoint region], [reranker endpoint region]  
- Transmission: TLS 1.3, mTLS optional, API gateway enforced.  

**Human Assets**
- Roles: [Admin, Support, DPO, Security, Tenant Admin]  
- Privileged access requires MFA + approvals: [Yes/No]  

**Paper Assets**
- [x] None (fully digital)  
- [ ] Scanned documents (describe): ______________________  

### 2.4 Data Categories + Classification (MANDATORY FOR PDPL RISK GATE)
- **Basic personal data:** [e.g., name, email, phone, ID no.]  
- **Sensitive personal data:** [e.g., biometrics, location, health, political, financial]  
- **Special categories (GDPR Art 9):** [Yes/No]  
- **Criminal offence/conviction data (GDPR Art 10):** [Yes/No]  

**Classification method**
- Rule-based detectors + ML classifier + manual override (admin-only).  
- Output tags: `BASIC | SENSITIVE | SPECIAL | CRIMINAL | UNKNOWN`

---

## 3. LAWFUL BASIS, NECESSITY, PROPORTIONALITY + PDPL CONSENT MODEL

### 3.1 GDPR Lawfulness (Art 6 / Art 9 / Art 10)
- **Phase 1 (Training, if applicable):** [ ] Consent [ ] Legitimate Interest [ ] Contract [ ] N/A  
- **Phase 2 (Inference/Usage):** [ ] Consent [ ] Contract [ ] Public Task [ ] Legitimate Interest  

If Legitimate Interest:
- Specific interest pursued: ______________________________  
- Balancing test summary: [link]  
- Opt-out / objection mechanism: [link]  

Sensitive/special data basis (Art 9(2)): ______________________________  
Criminal data authorising law + safeguards (Art 10 + national law): ______________________________  

### 3.2 PDPL CONSENT & “NO-CONSENT EXCEPTION” (AUDIT-CRITICAL)
**Default rule:** processing requires **explicit and verifiable consent** per purpose unless a documented PDPL exception applies.

#### A. Consent Capture (Per Purpose)
- [ ] Clear purpose list shown to data subject.  
- [ ] Active opt-in (no silence, no pre-ticked boxes).  
- [ ] Consent record stored with: `subject_id`, `purposes`, `timestamp`, `policy_version`, `method`, `evidence_pointer`.

#### B. Consent Evidence Format (MANDATORY, AUDIT-PROOF)
**Consent evidence must be reproducible and exportable.** Minimum fields:

| Field | Description |
|---|---|
| consent_event_id | Unique immutable ID |
| subject_id | Data subject reference |
| tenant_id | Controller/tenant reference |
| purposes | Array of purposes consented |
| policy_version | Privacy notice / consent text version |
| captured_at | Timestamp (server-side) |
| capture_method | UI checkbox / signed / API |
| ip_device | IP + device/browser hash (optional if policy) |
| evidence_pointer | Link/hash to UI snapshot or event log |
| withdrawn_at | Timestamp if withdrawn |

**Release Gate:** No production if consent records cannot be exported in this schema.

#### C. Withdrawal
- [ ] Withdrawal triggers immediate effect for future processing (§5.2 + §6).  
- [ ] Withdrawal event is logged and linked to consent_event_id.

#### D. Processing Without Consent (EXCEPTION PATH ONLY)
If used:
- [ ] Legal basis category selected from PDPL exception list (document exact basis).  
- [ ] Justification required (free text) + restricted approver role required.  
- [ ] Monitoring mechanism in place (periodic review + audit trail + complaint channel).  
- [ ] Technical enforcement: feature flag + strict scope limits.

**Release Gate:** No-consent mode cannot be enabled in production without DPO + Controller approval and recorded justification.

### 3.3 Necessity & Proportionality (Why AI?)
Could the objective be achieved without AI?
- [ ] No → Justify: ______________________________  
- [ ] Yes → Justify why AI still proportionate: ______________________________  

**Data minimization**
- [ ] Only necessary inputs processed (prompt constraints + UI guidance).  
- [ ] Conversation history cap: **[X] turns** / **[Y] tokens**.  
- [ ] Retrieval context cap: **[N] chunks**; least-privilege snippets only.  

---

## 4. RECIPIENTS, SUB-PROCESSORS, RETENTION + HYBRID EGRESS REGISTER

### 4.1 Roles & Qualification (GDPR)
- [ ] Controller  
- [ ] Joint Controller (Art 26, arrangement attached)  
- [ ] Processor (Art 28, DPA attached)

### 4.2 External Recipients Register (RELEASE GATE)
No pilot/production until every external recipient is completed and approved:

| Recipient | Service | Role (C/JC/P) | GDPR instrument | PDPL role | Cross-border? | Region(s) | Vendor retention (0/30/90) | Training use allowed? (Y/N) | Proof pack link | Approved |
|---|---|---:|---|---|---:|---|---:|---:|---|---|
| [LLM vendor] | Inference | P | Art 28 | Sub-processor | Y | [US/EU/SG] | [__] | [N] | [EP-09 link] | [ ] |
| [Reranker] | Rerank | P | Art 28 | Sub-processor | Y | [__] | [__] | [N] | [EP-09 link] | [ ] |
| [Cloud VN] | Hosting | P | Art 28 | Sub-processor | N | VN | [__] | N/A | [EP-09 link] | [ ] |

### 4.3 Retention Policy (SYSTEM-WIDE)
- User documents: [TTL e.g., 24h]  
- Embeddings/vectors: [TTL / purge conditions]  
- Prompts: [retention days, redaction]  
- Outputs: [retention days]  
- Logs/audit: [retention days; tamper resistance]  
- Backups: [retention + deletion propagation policy]

### 4.4 Deletion/Destruction Completeness Checklist (MANDATORY)
> Auditors will test completeness: deletion must include **raw + derived** data.

When deletion/destruction is requested, confirm:

- [ ] Raw documents deleted  
- [ ] Embeddings/vectors deleted  
- [ ] Retrieval caches cleared (RAG cache / context cache)  
- [ ] Citations store entries removed (where applicable)  
- [ ] Conversation messages removed (subject to retention policy)  
- [ ] Search indexes updated to remove artifacts  
- [ ] Backup deletion propagation policy executed (document timeframe)  
- [ ] Non-restoration assured (cryptographic erasure / secure wipe)  

**Deletion Evidence:** link to job logs + sample execution trace: [EP-07 link]

### 4.5 HYBRID DATA EGRESS REGISTER (MANDATORY)
Every external AI call must create an immutable egress log entry.

**Egress log fields**
- request_id, tenant_id, timestamp  
- vendor/service, region  
- data categories sent (prompt / snippets / metadata)  
- redaction mode applied (`NONE | BASIC_REDACT | STRONG_REDACT`)  
- risk_level (`LOW | MED | HIGH`)  
- vendor retention expectation (0/30/90)  
- “no training” attestation flag  
- outcome (allowed/blocked), reason  

**Measurable minimization caps (MANDATORY)**
- **Max external payload tokens:** ≤ [T] tokens  
- **Max external retrieved chunks:** ≤ [N] chunks  
- **Max external fields allowed:** [list]  
- **Redaction coverage target:** ≥ [__]% of detected identifiers removed  

**Release Gate:** No external call allowed without egress logging enabled and caps enforced.

---

## 5. DATA SUBJECT RIGHTS (GDPR) + PDPL RIGHTS EXECUTION (OPERATIONAL)

### 5.1 Rights Checklist (GDPR)
| Right | Measures Implemented |
|---|---|
| Information (Art 13/14) | [ ] Transparency notice + AI label |
| Access & portability (Art 15/20) | [ ] Export user data (JSON/CSV) |
| Rectification & erasure (Art 16/17) | [ ] Remove source docs + delete derived artifacts |
| Objection & restriction (Art 18/21) | [ ] Opt-out for training + stop generation |
| Automated decision review (Art 22) | [ ] Human-in-the-loop for significant effects |

### 5.2 PDPL RIGHTS EXECUTION (MANDATORY)
**DSR Intake**
- Channel(s): [portal/email/hotline]  
- Identity verification steps: [____]  
- SLA target: [____]

**Execution Controls**
- Withdrawal/restriction: processing freeze + block embedding/retrieval/egress.  
- Correction: update data at source + propagate to derived stores.  
- Deletion/destruction: execute §4.4 checklist and record evidence.

**Evidence**
- DSR register: `dsr_requests` with timestamps, actions, closure proof (EP-05)

---

## 6. PDPL AI RISK CLASSIFICATION GATE (MANDATORY FOR HYBRID)

### 6.1 Risk Tiering Model (ENFORCEMENT)
- **RISK-LOW:** no identifiers; general legal analysis → HYBRID allowed  
- **RISK-MED:** identifiers present → HYBRID only with redaction; else VN-only  
- **RISK-HIGH:** sensitive categories / high harm potential → VN-only or BLOCK unless strict basis + extra safeguards

### 6.2 Routing Outcomes (Deterministic)
- `VN_ONLY` — VN-hosted models/services only  
- `HYBRID_REDACTED` — external calls permitted after redaction + caps  
- `BLOCK` — refuse processing; request safer input / alternate workflow

### 6.3 Override Policy (RESTRICTED)
- Requires DPO + Controller approval + justification + time-bound scope + monitoring  
- Every override logged (who/when/why) and reviewed monthly.

### 6.4 Guardrails for Hybrid External Calls
- Redaction before egress (PII stripping + sensitive removal).  
- Prompt injection defenses (tool isolation, allowlists, output filters).  
- Citation-only / grounded mode for legal outputs where required.  
- No vendor training use (contract + config + proof).

---

## 7. RISK ASSESSMENT (EDPB TAXONOMY) + HYBRID-SPECIFIC SCENARIOS

### 7.1 Risk Register
| Risk ID | Source | Scenario | Impact Type | Severity | Likelihood | Risk Level |
|---|---|---|---|---|---|---|
| R1 | External attacker | Model inversion / data extraction | Illegitimate access | High | Low | Medium |
| R2 | External user | Prompt injection bypassing controls | Integrity / misuse | High | Medium | High |
| R3 | System/model | Hallucination/bias leading to harm | Discrimination / speech | High | High | Critical |
| R4 | Infrastructure | Availability/DoS | Availability | Low | Medium | Low |
| R5 | Government/legal | Foreign jurisdiction access risk | Illegitimate access | Medium | Low | Medium |
| R6 | Hybrid egress | Excessive context sent externally | Privacy breach | High | Medium | High |
| R7 | Tenant isolation | Cross-tenant leakage | Privacy breach | High | Low | Medium |

---

## 8. MEASURES TO TREAT RISKS (SECURITY + FUNDAMENTAL RIGHTS) + PDPL EVIDENCE

### 8.1 Security & Integrity Measures
| Risks | Measures | Residual Risk | Approved |
|---|---|---|---|
| R1, R5, R6 | Redaction; TLS; AES at rest; key mgmt; egress caps | Low/Med | [ ] |
| R2 | Guardrails; input validation; sandbox tools; red-team schedule | Medium | [ ] |
| R4 | Rate limiting; autoscaling; WAF; monitoring | Low | [ ] |
| R7 | Tenant isolation (RLS/tenant_id); authz checks; tests | Low | [ ] |

### 8.2 Fundamental Rights Safeguards
| Risks | Measures | Residual Risk | Approved |
|---|---|---|---|
| R3 | Grounded RAG with citations; refusal on uncertainty | Medium | [ ] |
| R3 | Human oversight for significant effects | Low | [ ] |
| R3 | Contestability, explanation, redress workflow | Low | [ ] |

**Criticality check**
- [ ] No significant/irreversible consequence residual risk  
- [ ] Yes → STOP → consult authority / regulator (GDPR Art 36 / PDPL escalation path)

---

## 9. MONITORING, REVIEW, AUDIT + PDPL UPDATE CADENCE (HYBRID)

### 9.1 Re-assessment Triggers
- Model drift below threshold  
- New capabilities (plugins, browsing, new tools, new data categories)  
- Purpose expansion / new intent  
- Regulatory change (PDPL guidance / AI Act updates)  
- PDPL immediate update triggers:
  - Organizational restructure/termination/dissolution/bankruptcy  
  - Change of personal data protection service provider  
  - Change in business line/service related to processing

### 9.2 Periodicity
- GDPR/WP248 review: every [12] months  
- PDPL dossier review: every 6 months when changes occur + immediate triggers

### 9.3 Compliance Audit Checklist (Release Gate)
- [ ] Data flow verification matches §2.2 diagram (EP-01)  
- [ ] Retention + deletion jobs proven via logs (EP-07)  
- [ ] Egress register active for all external calls (EP-06)  
- [ ] Risk gate enforced + override logs reviewed (EP-06)  
- [ ] DSR execution tested (withdraw/restrict/delete) (EP-05)  
- [ ] Incident workflow tested (tabletop) (EP-08)  
- [ ] Vendor proof pack complete (no-train/retention) (EP-09)

---

## 10. SIGN-OFF, ACCOUNTABILITY + PUBLICATION
**DPO Advice:** [ ] Compliant  [ ] Not compliant (mitigations required)  
**Controller Decision:** [ ] Proceed  [ ] Stop  [ ] Proceed with documented risk acceptance  
**Processor Confirmation:** [ ] Implemented controls per dossier  [ ] Pending  
**CISO Validation:** [ ] Validated  [ ] Pending  
**Date:** ____________________  

**Transparency Decision**
- [ ] Full DPIA confidential  
- [ ] Publish public summary: [link]

---

# ANNEX PDPL-R — PROCESSING ACTIVITIES REGISTER (RoPA-STYLE) (MANDATORY FOR AUDIT)
> Maintain one register per tenant/controller.

| Activity ID | Purpose | Data subjects | Data categories | Sources | Processing ops | Storage location(s) | Recipients/subprocessors | Cross-border? | Retention | Security controls | Legal basis (GDPR/PDPL) | Notes |
|---|---|---|---|---|---|---|---|---:|---|---|---|---|
| PA-01 | [____] | [____] | [BASIC/SENSITIVE] | [user upload] | [retrieve, summarize] | [VN DB] | [LLM vendor] | Y | [TTL] | [TLS/AES/RBAC] | [____] | [____] |

---

# ANNEX PDPL-X — CROSS-BORDER TRANSFER IMPACT ASSESSMENT DOSSIER (HYBRID)

## X.1 Scope
This annex documents cross-border transfers arising from HYBRID processing (foreign LLM/reranker endpoints, foreign logging/monitoring, foreign support access).

## X.2 First Transfer Date + 60-Day Deadline
- First cross-border transfer date (T0x): YYYY-MM-DD  
- Dossier deadline (T0x + 60 days): YYYY-MM-DD  
- Submission evidence: [EP-10 link]

## X.3 Transfers Register (MANDATORY)
| Vendor/Subprocessor | Service | Region | Data categories sent | Purpose | Safeguards | Vendor retention (0/30/90) | Training use allowed? | Egress logs | Approved |
|---|---|---|---|---|---|---:|---:|---|---|
| [LLM] | inference | [__] | prompt+snippets | legal answer | redaction+TLS+caps | [__] | N | yes | [ ] |

## X.4 Safeguards (ENFORCEABLE + MEASURABLE)
- Minimization: only necessary snippets; cap chunks/tokens  
- **Max external payload tokens:** ≤ [T]  
- **Max external retrieved chunks:** ≤ [N]  
- Strong redaction for identifiers and sensitive categories  
- Encryption in transit  
- Access controls + audit trails  
- “No training use” by vendor (contract + config + proof)

## X.5 PDPL Exceptions Handling (TIGHTENED)
- [ ] Exception applies  
  - **Exception ID/Description:** ____________________  
  - **Legal reasoning:** ____________________  
  - **Evidence:** ____________________  
  - **Approver:** ____________________  
- [ ] No exception applies → full dossier obligations apply

## X.6 Updates (PDPL cadence)
Updates required per §0.2 triggers and §9.1.

---

# ANNEX PDPL-Y — INCIDENT REGISTER + 72-HOUR NOTIFICATION PACK

## Y.1 Incident Timestamps
- Discovery time (T0i): ______  
- 72-hour deadline (T0i + 72h): ______  
- Time-to-triage decision (max): **≤ 4 hours**  
- Initial containment time: ______  

## Y.2 “Harm May Occur” Triage Rule (MANDATORY)
Notification is triggered when the violation **may cause harm**. Use the rubric below:

**Likely harm indicators (any = escalate):**
- Sensitive data exposure  
- Identity/credential exposure  
- Large-scale exposure (volume/tenants)  
- Evidence of unauthorized access/exfiltration  
- Risk of financial, reputational, or physical harm  
- Regulatory/legal impact (court, law firm confidential matters)

**Decision owner:** CISO + DPO + Controller representative  
**Decision evidence:** record rationale in incident register.

## Y.3 Incident Record (MINIMUM FIELDS)
- Incident ID, tenant(s) affected, systems affected  
- Data categories impacted, estimated scale  
- Harm likelihood assessment + triage rationale  
- Actions taken: containment, remediation, prevention  
- Authority notification: time/method/evidence  
- Processor → Controller notification: time/evidence  
- Postmortem link

## Y.4 Templates
- Authority notice template: [link]  
- Controller notice template: [link]  
- Internal postmortem template: [link]

## Y.5 Tabletop Exercise
- Last exercise date: ______  
- Findings: ______  
- Actions closed: [ ] Yes [ ] No

---

# ANNEX — EU AI ACT FUNDAMENTAL RIGHTS IMPACT ASSESSMENT (FRIA) (ALIGNED)

## FRIA-1 Deployment context
- Use setting: [internal/external/public-facing/B2B/public authority]  
- Primary function: [assist/triage/scoring/decision support]  
- Significant effects: [ ] No  [ ] Yes → specify: ______  
- Affected persons: [customers/employees/patients/students/public]  
- Interfaces: [chatbot/API/portal/mobile/back-office]  
- Geo scope: [EU/non-EU] | Languages: [__]

## FRIA-2 Fundamental rights screened
- Non-discrimination / Equality  
- Freedom of expression / Access to information  
- Privacy / Data protection  
- Right to remedy / Contestability  
- Human dignity / Vulnerable persons  
- Surveillance / Profiling

## FRIA-3 Stakeholders & affected groups
- Users: ______  
- Affected persons: ______  
- Vulnerable groups: [ ] No  [ ] Yes → ______  
- Redress channel: ______  
- Consultation: [ ] Yes  [ ] No → justification: ______

## FRIA-4 Safeguards & governance
- Human oversight for significant effects  
- Contestability & explanation procedures  
- Grounded outputs / citations  
- Security + access controls  
- Continuous monitoring and reassessment

## FRIA-5 Conclusion
- [ ] Deployable with ongoing monitoring  
- [ ] Not deployable until mitigations complete

### FRIA–DPIA Cross-Reference Table
- **Non-discrimination / Equality:** DPIA Section 5 (Risk R3), Section 6.B  
- **Freedom of Expression / Information:** DPIA Section 5, Section 6.B  
- **Privacy & Personal Data Protection:** DPIA Sections 2–3, Section 6.A  
- **Right to an Effective Remedy / Contestability:** DPIA Section 6.B, Section 3.D  
- **Human Dignity / Vulnerable Persons:** DPIA Section 1.B (Criterion 7), Section 5  
- **Surveillance / Profiling:** DPIA Section 1.B (Criteria 1–3), Section 5  
  

---


FRENCH VERSION :

# ANALYSE D’IMPACT RELATIVE À LA PROTECTION DES DONNÉES (AIPD / DPIA) – SYSTÈME D’IA
**Norme :** RGPD (art. 35) & Lignes directrices du CEPD (WP 248 rev.01)  
**Compatibilité :** AI Act (UE) – Systèmes d’IA à haut risque  

**Nom du système :** [Nom du système d’IA]  
**Responsable du traitement :** [Nom de l’organisation]  
**Date :** AAAA-MM-JJ  
**Version :** 1.6 (Conforme WP248 – version “patchée”)  
**Statut :** [ ] Brouillon  [ ] Validation  [ ] Approuvé  
**Phase du cycle de vie :** [ ] Conception (avant traitement) [ ] Pilote [ ] Production [ ] Revue périodique (itérative)  
**Classification AI Act :** [ ] Interdit [ ] Haut risque [ ] Risque limité [ ] Risque minimal  

---

## 1. ÉVALUATION DU DÉCLENCHEMENT (CRITÈRES WP29 & LISTES NATIONALES)
[cite_start]*Référence : WP 248 rev.01, Section III.B.a (pages 8–11)* [cite: 124, 140]

### A. Vérification de la juridiction nationale (art. 35(4) & 35(5) RGPD)
*Avant d’évaluer les critères, vérifier les exigences nationales spécifiques.*  
* [cite_start][ ] **Vérification “Blacklist” :** Cette opération figure-t-elle sur une **liste nationale** publiée par une autorité de contrôle rendant l’AIPD obligatoire (art. 35(4)) ? [cite: 197]  
  * *Si OUI, l’AIPD est **obligatoire**, indépendamment des critères ci-dessous.*  
* [cite_start][ ] **Vérification “Whitelist” :** Cette opération figure-t-elle sur une **liste nationale** publiant des traitements pour lesquels l’AIPD n’est pas requise (art. 35(5)) ? [cite: 209]  
  * *Si OUI, l’AIPD **n’est pas requise** (sauf conditions spécifiques non remplies).*  
* [ ] Référentiels sectoriels AIPD vérifiés (ex. énergie, santé) ?  

### B. Détermination du “risque élevé” au sens du RGPD (art. 35(1))  
[cite_start]*Note : cette évaluation vise les risques pour les “droits et libertés” au sens du RGPD.* [cite: 76]

**Test d’applicabilité :** Le traitement satisfait-il **au moins un** des critères ci-dessous ?  
*Note : la présence de **2 critères ou plus** crée une forte présomption d’AIPD requise. [cite_start]Toutefois, une AIPD peut être obligatoire avec **un seul** critère, notamment en cas de “surveillance systématique” ou d’“usage innovant”, lorsque des risques élevés sont inhérents.* [cite: 187, 189]

*Clarification :* Conformément à WP 248 rev.01, l’usage d’une technologie innovante **ne constitue pas automatiquement** un risque élevé ; l’évaluation reste **contextuelle** et fondée sur la nature, l’étendue, le contexte et les finalités du traitement.  
*(WP 248 rev.01, Section III.B, pages 8–11)*

| Critère WP29 (indicateur de risque) | Applicabilité à ce système d’IA |
| :--- | :--- |
| **1. [cite_start]Évaluation ou notation** (ex. scoring de crédit, prédiction comportementale) [cite: 141] | [ ] Oui |
| **2. [cite_start]Décision automatisée** à effet juridique / significatif (art. 22) [cite: 143] | [ ] Oui |
| **3. [cite_start]Surveillance systématique** (ex. surveillance, espaces publics) [cite: 147] | [ ] Oui |
| **4. [cite_start]Données sensibles** (art. 9 : santé, biométrie, opinions, etc.) [cite: 150] | [ ] Oui |
| **5. [cite_start]Traitement à grande échelle** (volume, durée, étendue géographique) [cite: 164] | [ ] Oui |
| **6. [cite_start]Rapprochement / combinaison de jeux de données** au-delà des attentes raisonnables [cite: 171] | [ ] Oui |
| **7. [cite_start]Personnes concernées vulnérables** (enfants, salariés, patients) [cite: 172] | [ ] Oui |
| **8. [cite_start]Usage innovant / nouvelle technologie** (IA, LLM, IoT, reconnaissance faciale) [cite: 174] | [x] **Oui (système d’IA)** |
| **9. [cite_start]Empêchement d’exercice de droits / d’accès à un service** (ex. refus de prêt) [cite: 184] | [ ] Oui |

### C. Responsabilité conjointe (art. 26)
*Agissons-nous seuls ou conjointement ?*  
* [ ] Responsable du traitement unique  
* [cite_start][ ] Co-responsables (rôles définis dans un accord joint) [cite: 112]  
  * [cite_start]**Vérification de sauvegarde :** le partage d’informations pour l’AIPD ne compromet-il pas les secrets d’affaires ou la propriété intellectuelle (ex. poids du modèle) ? [cite: 116]

---

## 2. DESCRIPTION SYSTÉMATIQUE & ACTIFS
[cite_start]*Référence : Annexe 2 CEPD – “description systématique… nature, portée, contexte, finalités… actifs… destinataires”* [cite: 392, 396]

### A. Description fonctionnelle 
* **Nature & portée :** [Décrire ce que fait l’IA et l’échelle de déploiement].  
* **Contexte :** [Décrire l’environnement : ex. outil RH interne / chatbot public].  
* **Finalités :** [Préciser le résultat attendu : ex. automatisation du tri des demandes].  

### B. Inventaire des actifs (matériels, logiciels, humains)
[cite_start]*Exigé par l’Annexe 2 WP 248 : “les actifs sur lesquels reposent les données personnelles”* [cite: 396]  
* **Actifs logiciels (le modèle) :**  
  * Architecture : (ex. Transformer / LLM, Random Forest).  
  * Frameworks d’entraînement : (ex. PyTorch, TensorFlow).  
* **Actifs matériels & réseau :**  
  * Hébergement : (ex. AWS région Paris, cluster GPU on-prem).  
  * Canaux de transmission : (ex. API chiffrée TLS 1.3).  
* **Actifs humains :**  
  * Droits d’accès : (ex. Data Scientists, Prompt Engineers, RH).  
* **Actifs papier :**  
  * [ ] N/A (100% numérique) ou [ ] Documents physiques numérisés.  

### C. Destinataires & durées de conservation  
* [cite_start]**Destinataires (qui accède aux données ?) :** [cite: 394]  
  * [ ] Fournisseur IA / sous-traitant (ex. OpenAI, Anthropic)  
  * [ ] Fournisseur cloud (ex. AWS, Azure, GCP)  
  * [ ] Partenaires d’intégration (ex. Zapier, CRM)  
  * [ ] Support interne / administrateurs IT
* [cite_start]**Qualification juridique des acteurs (RGPD)**  
* [ ] Responsable du traitement  
* [ ] Co-responsable du traitement (art. 26 RGPD – accord de répartition joint)  
* [ ] Sous-traitant (art. 28 RGPD)

Pour chaque destinataire externe :
**Gate de validation (obligatoire) :**  
Aucune mise en production, validation ou approbation de la présente AIPD n’est autorisée **tant que chaque destinataire externe mentionné ci-dessus ne dispose pas d’une ligne complète dans le tableau ci-dessous**, comprenant notamment :
- la qualification juridique (Responsable / Co-responsable / Sous-traitant),
- l’instrument RGPD applicable (art. 26 ou art. 28),
- l’existence d’un transfert hors UE (le cas échéant),
- et la confirmation des garanties contractuelles.

Cette exigence s’applique à **l’ensemble des destinataires externes**, y compris les fournisseurs d’IA, les fournisseurs cloud et les partenaires d’intégration.

| Destinataire | Rôle (Responsable / Co-responsable / Sous-traitant) | Instrument RGPD (art. 26 / art. 28) | Transfert hors UE ? (O/N) | Observations |
| :--- | :--- | :--- | :--- | :--- |
| [Fournisseur IA] | [ ] R / [ ] CR / [ ] ST | [ ] 26 / [ ] 28 | [ ] O / [ ] N | [CCT / DPF / TIA si O] |
| [Fournisseur cloud] | [ ] R / [ ] CR / [ ] ST | [ ] 26 / [ ] 28 | [ ] O / [ ] N | [...] |

- Qualification retenue : Responsable / Co-responsable / Sous-traitant  
- Base juridique correspondante : art. 26 ou art. 28 RGPD  
- Contrat en place :  
  * [ ] Accord de co-responsabilité (art. 26)  
  * [ ] Contrat de sous-traitance + instructions documentées (art. 28(3))  
  * [ ] Droit d’audit / documentation sécurité disponible
* [cite_start]**Politique de conservation :** [cite: 403]  
  * Prompts en entrée : [ex. conservés 30 jours puis supprimés]  
  * Sorties / réponses : [ex. conservées 1 an sur le compte utilisateur]  
  * Logs : [ex. conservation glissante 90 jours]  

---

## 3. NÉCESSITÉ, PROPORTIONNALITÉ & DROITS
[cite_start]*Référence : Annexe 2 CEPD – “nécessité et proportionnalité… mesures contribuant aux droits”* [cite: 398, 404]

### A. Licéité du traitement (art. 6)
* **Phase 1 : Entraînement (si applicable) :** 
[ ] Consentement [ ] Intérêt légitime [ ] Contrat [ ] N/A  
* **Phase 2 : Inférence (utilisation) :**  
  * [ ] Consentement  
  * [ ] Contrat  
  * [ ] Mission d’intérêt public  
  * [ ] Intérêt légitime  
    * [cite_start]**PRÉCISION OBLIGATOIRE :** *décrire l’intérêt poursuivi (art. 35(7)(a))* [cite: 35]  
    * _________________________________________________________________________  
    * *(Exemples : détection de fraude, sécurité réseau, optimisation du service)*  
    
**Données sensibles / catégories particulières (art. 9 RGPD) :**  
- [ ] Non  
- [ ] Oui → **Condition art. 9(2) retenue :** ________________________________  
  *(ex. consentement explicite (9(2)(a)), droit du travail/protection sociale (9(2)(b)), intérêts vitaux (9(2)(c)), organismes à but non lucratif (9(2)(d)), données manifestement rendues publiques (9(2)(e)), actions en justice (9(2)(f)), intérêt public important (9(2)(g)), soins de santé (9(2)(h)), santé publique (9(2)(i)), recherche/statistiques (9(2)(j)) — à préciser)*

**Données relatives aux infractions / condamnations (art. 10 RGPD) :**  
- [ ] Non  
- [ ] Oui → **Base légale / texte d’autorisation (art. 10 + droit national) :** ________________________________  
  *(Préciser la disposition de droit national applicable et les garanties associées, notamment restrictions d’accès et règles de conservation.)*
Bạn đã nói:

**Sources de données traitées :**  
- **Entraînement :** [ ] Données internes  [ ] Données publiques  [ ] Données fournies par un tiers  [ ] N/A  
- **Inférence :** [ ] Données saisies par l’utilisateur  [ ] Données métier  [ ] Logs techniques

**Réutilisation des prompts / réponses à des fins d’entraînement ou d’amélioration du modèle :**  
- [ ] **Non** — Les prompts et réponses ne sont pas réutilisés pour l’entraînement ou l’amélioration du modèle.  
- [ ] **Oui** — Réutilisation limitée selon les modalités suivantes :
  - **Périmètre / finalité :** [ex. amélioration de la sécurité / qualité / fine-tuning / analyses]
  - **Catégories de données concernées :** [prompts / réponses / métadonnées]
  - **Durée de conservation :** [ex. X jours / anonymisation immédiate]
  - **Mécanisme d’opposition (opt-out) :** [ex. paramètre utilisateur / clause contractuelle / option de compte]
  - **Garanties mises en œuvre :** [ex. anonymisation, agrégation, exclusion des données sensibles]

*Remarque :* Toute réutilisation des prompts ou réponses à des fins d’entraînement doit être couverte par une base juridique adéquate (art. 6 RGPD) et, le cas échéant, par les conditions applicables aux art. 9 et/ou 10 RGPD.

### B. Évaluation de proportionnalité (Pourquoi l’IA ?)
* **Nécessité :** l’objectif pourrait-il être atteint sans IA (ex. règles déterministes) ?  
  * [ ] Non (justification : complexité du langage / motifs nécessite inférence).  
  * [ ] Oui (si oui, l’usage d’une IA à haut risque peut être disproportionné).  
* [cite_start]**Minimisation des données (art. 5(1)(c)) :** [cite: 402]  
  * [ ] Seules les entrées strictement nécessaires au prompt sont traitées.  
  * [ ] L’historique de contexte est limité à [X] tours.  

### C. Codes de conduite & certifications (art. 40/42)
[cite_start]*Référence : WP 248 p.16 – “codes de conduite… certifications… à prendre en compte”* [cite: 284, 286]  
* **Applicabilité :**  
  * [ ] Aucun code approuvé applicable à ce jour.  
  * [ ] Adhésion à un code de conduite approuvé (Nom : ____________________).  
  * [ ] Adhésion à un mécanisme de certification approuvé (Nom : ____________________).  

### D. Checklist des droits des personnes concernées
[cite_start]*Référence : Annexe 2 WP 248 – mesures contribuant aux droits des personnes concernées* [cite: 404]

| Droit | Mesure mise en œuvre dans le système d’IA |
| :--- | :--- |
| [cite_start]**Information (art. 13/14)** [cite: 405] | [ ] Notice de transparence affichée. Mention “Système d’IA” visible. |
| [cite_start]**Accès & portabilité (art. 15/20)** [cite: 406] | [ ] Export de l’historique (JSON/CSV). |
| [cite_start]**Rectification & effacement (art. 16/17)** [cite: 407] | [ ] **Stratégie RAG :** suppression des sources du moteur de recherche / base de récupération pour empêcher les citations (les poids du modèle ne peuvent pas être modifiés). |
| [cite_start]**Opposition & limitation (art. 18/21)** [cite: 408] | [ ] Opt-out pour l’entraînement futur. [ ] Bouton d’arrêt de génération. |
| **Réexamen d’une décision automatisée (art. 22)** | [ ] Intervention humaine pour contester les décisions. |

### E. Transferts internationaux (Chapitre V)  
* [cite_start]**Les données sortent-elles de l’EEE ?** [cite: 409]  
  * [ ] Non (résidence des données en région UE).  
  * [ ] Oui (transfert vers États-Unis / pays tiers).  
* **Mécanisme de transfert :**  
  * [ ] Décision d’adéquation (ex. EU–US Data Privacy Framework).  
  * [ ] Clauses contractuelles types (CCT/SCC) + **Évaluation d’impact du transfert (TIA)**.  

---

## 4. PROCESSUS DE CONSULTATION
[cite_start]*Référence : Annexe 2 CEPD – “parties prenantes impliquées”* [cite: 417]

* [cite_start]**Avis du DPO (art. 35(2)) :** le DPO a-t-il examiné l’AIPD ? [cite: 418]  
  * [ ] Oui  [ ] En attente  
* [cite_start]**Avis des personnes concernées (art. 35(9)) :** des avis ont-ils été recueillis ? [cite: 419]  
  * [ ] Oui (sondage / focus group)  
  * [cite_start][ ] Non. **(OBLIGATOIRE : justifier)** [ex. confidentialité / effort disproportionné (WP 248 p.15)] [cite: 256]  
* [cite_start]**Assistance du sous-traitant (art. 28(3)(f)) :** [cite: 251]  
  * [ ] Documentation sécurité / fiche système du fournisseur analysée.  
  * [ ] Rôles & responsabilités définis contractuellement (accord art. 28(3) en place).  

---

## 5. ÉVALUATION DES RISQUES (TAXONOMIE CEPD)
[cite_start]*Référence : Annexe 2 CEPD – “origine, nature, particularité, gravité… sources de risque prises en compte”* [cite: 411, 412]

[cite_start]**Indication :** les “droits et libertés” incluent la vie privée, mais aussi la liberté d’expression, la non-discrimination, la liberté de circulation, etc. [cite: 77]

| ID risque | Source du risque | Scénario | Type d’impact (droits fondamentaux) | Gravité | Probabilité | Niveau |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **R1** | Attaquant externe | **Inversion de modèle :** extraction de données perso via prompts | Accès illégitime (vie privée) | Élevée | Faible | **Moyen** |
| **R2** | Utilisateur externe | **Injection de prompt :** contournement des garde-fous | Modification indésirable | Élevée | Moyenne | **Élevé** |
| **R3** | Système / modèle | **Hallucination / biais :** invention de faits ou discrimination | **Non-discrimination / liberté d’expression** | Élevée | Élevée | **Critique** |
| **R4** | Infrastructure | **Disponibilité / DoS :** surcharge ou indisponibilité | Disparition temporaire | Faible | Moyenne | **Faible** |
| **R5** | Autorité publique | Accès cloud (ex. CLOUD Act) | Accès illégitime (vie privée) | Moyenne | Faible | **Moyen** |

---

## 6. MESURES ENVISAGÉES POUR TRAITER LES RISQUES
[cite_start]*Référence : Annexe 2 CEPD – “mesures envisagées pour traiter ces risques”* [cite: 416]

### A. Mesures de sécurité & d’intégrité (art. 32 RGPD)
*Mesures visant principalement la confidentialité, l’intégrité et la disponibilité des données personnelles.*

| ID risque | Mesures de sécurité (techniques & organisationnelles) | Risque résiduel | Approuvé ? |
| :--- | :--- | :--- | :--- |
| **R1, R5** | **Anonymisation / pseudonymisation :** suppression du PII avant appel API. **Chiffrement :** TLS en transit, AES au repos. | Faible | [x] |
| **R2** | **Sécurité modèle & prompts :** garde-fous (NeMo/Llama), validation d’entrée, red teaming régulier. | Moyen | [ ] |
| **R4** | **Contrôles de disponibilité :** rate limiting, monitoring, protection DoS. | Faible | [ ] |

---

### B. Mesures de sauvegarde des droits fondamentaux
*Mesures visant principalement les risques pour les droits et libertés des personnes concernées (Annexe 2 WP 248).*

| ID risque | Sauvegardes des droits (procédurales & centrées humain) | Risque résiduel | Approuvé ? |
| :--- | :--- | :--- | :--- |
| **R3** | **Ancrage (RAG) :** sorties limitées à des sources vérifiées ; citations imposées pour réduire hallucination/biais. | Moyen | [ ] |
| **R3** | **Supervision humaine (art. 22) :** revue humaine obligatoire pour décisions à effet juridique / significatif. | Faible | [x] |
| **R3** | **Contestabilité & explication :** procédure de demande d’explication / contestation des résultats. | Faible | [x] |

[cite_start]**TEST DE CRITICALITÉ :** un risque résiduel implique-t-il des conséquences “significatives ou irréversibles” (ex. menace vitale, licenciement, préjudice financier majeur) que la personne ne peut surmonter ? [cite: 334]  
* [ ] Non  
* [cite_start][ ] Oui → **STOP.** Consultation préalable de l’autorité de contrôle **obligatoire** (art. 36). [cite: 335]

---

## 7. PLAN DE SUIVI & DE RÉEXAMEN
[cite_start]*Référence : WP 248 rev.01 (p.13) – “réexamen… au moins en cas de changement du risque”* [cite: 309]

**Déclencheurs de réévaluation :**
1. **Dérive du modèle :** baisse de performance sous un seuil défini.  
2. **Nouvelles capacités :** activation de plugins, accès internet, nouvelles catégories de données.  
3. [cite_start]**Extension de finalité :** nouveau cas d’usage (ex. support client → profilage commercial). [cite: 217]  
4. [cite_start]**Changement contextuel :** nouvelle législation (ex. AI Act), nouvelles lignes directrices, évolution de l’acceptabilité sociale.  
5. **Périodicité :** revue tous les [12] mois.  

**Audit de conformité (art. 35(11)) :**
* [ ] **Vérification des flux :** les flux réels correspondent à la description (Section 2).  
* [ ] **Vérification des politiques :** exécution effective des durées de conservation/suppression.  
* [ ] Revue itérative : mise à jour en cas de changement de la nature, portée, contexte ou finalités.  
* [ ] **Intégration art. 25 (Privacy by Design/Default) :** résultats AIPD implémentés dans la conception (exigences, architecture, paramètres par défaut) et validés avant mise en production.  
* [ ] **Gate de release :** aucune mise en production sans clôture des items art. 25 ou acceptation formelle du risque par le Responsable + DPO.  
* [ ] **Responsabilité (art. 24) :** le Responsable confirme que les conclusions AIPD sont reflétées dans les politiques, procédures et contrôles internes.  

---

## 8. VALIDATION & PUBLICATION
[cite_start]*Référence : Annexe 2 CEPD – “documenter les décisions prises”* [cite: 359]

* **Avis du DPO :**
  * [ ] Conforme  
  * [ ] Risques résiduels élevés ; [cite_start]**consulter l’autorité de contrôle (art. 36)** [cite: 335]  
* **Justification du Responsable (en cas d’écart avec l’avis DPO / personnes concernées) :**
  * [ ] N/A (consensus)  
  * [cite_start][ ] Justification de l’écart : *[à renseigner – requis WP 248 p.15]* [cite: 255]  
* **Décision de transparence :**
  [cite_start]*Référence : WP 248 p.18 – “publier un résumé peut favoriser la confiance”* [cite: 313]  
  * [ ] AIPD complète confidentielle  
  * [ ] Résumé public publié (lien/emplacement : __________)  
* **Décision du Responsable :** [ ] Poursuivre (si risque résiduel faible/moyen OU consultation effectuée)  [ ] Stop  
* **Validation RSSI (CISO) :** [ ] Validée  
* **Date :** ____________________  

---

## ANNEXE. AI ACT (UE) – ANALYSE D’IMPACT SUR LES DROITS FONDAMENTAUX (FRIA)

Cette annexe constitue l’**analyse d’impact sur les droits fondamentaux (FRIA)** exigée au titre de 
l’**article 27 de l’AI Act (UE)** pour les systèmes d’IA à haut risque.

La FRIA est fondée sur et réutilise la présente **AIPD / DPIA (art. 35 RGPD)**, conformément à 
une approche fondée sur les risques et centrée sur les droits fondamentaux.

### FRIA-1. Contexte de déploiement (usage réel)
- **Contexte d’usage :** [interne / externe / public / B2B / administration]
- **Fonction principale :** [ex. recommandation, tri, assistance, scoring, décision]
- **Décisions à effet significatif :** [ ] Non  [ ] Oui → préciser : ________________________
- **Population concernée :** [clients / salariés / patients / élèves / grand public]
- **Environnement & secteur :** [ex. RH, finance, santé, éducation, services publics]
- **Canaux / interfaces :** [chatbot, API, portail, mobile, back-office]
- **Portée géographique :** [UE / hors UE]  | **Langues :** [___]

### FRIA-2. Droits fondamentaux examinés (screening)
Les risques potentiels ont été examinés au regard des droits fondamentaux, notamment :
- **Non-discrimination / égalité**
- **Liberté d’expression / accès à l’information**
- **Vie privée & protection des données**
- **Droit à un recours effectif / contestabilité**
- **Dignité humaine & protection des personnes vulnérables**
- **Surveillance / profilage**

Pour chaque droit, l’évaluation s’appuie sur :
- les scénarios de risque (Section 5 de l’AIPD/DPIA),
- les mesures de traitement des risques (Section 6),
- et le plan de suivi (Section 7).

### FRIA-3. Parties prenantes & groupes affectés
- **Utilisateurs du système :** [ex. agents internes / clients / partenaires]
- **Personnes affectées :** [ex. candidats, salariés, clients, usagers]
- **Groupes potentiellement vulnérables :** [ ] Non  [ ] Oui → préciser : ________________
- **Modalités de recours / contact :** [processus, canal, délai, responsable]
- **Consultation des personnes ou groupes concernés :**  
[ ] **Oui** — Modalités : [ex. enquête, ateliers, tests utilisateurs, représentants]  
[ ] **Non** → **Justification :** [ex. effort disproportionné, contraintes de confidentialité, phase de conception, absence d’impact direct]

*Remarque :* En cas d’absence de consultation, la justification est conforme à l’art. 35(9) RGPD et dûment documentée à des fins de responsabilité.


### FRIA-4. Mesures de sauvegarde & gouvernance
Les sauvegardes et mécanismes de contrôle incluent notamment :
- **Supervision humaine** pour les cas à effets juridiques ou significatifs (art. 22 RGPD) (DPIA §6.B)
- **Contestabilité & explication** (procédure de recours) (DPIA §6.B / §3.D)
- **Mesures anti-biais / anti-hallucination** (ancrage RAG, sources vérifiées, citations) (DPIA §6.B)
- **Mesures de sécurité & intégrité** (chiffrement, contrôle d’accès, monitoring, etc.) (DPIA §6.A)
- **Suivi, audit et réévaluation** en cas de changement de contexte, finalité, ou capacités (DPIA §7)

### FRIA-5. Conclusion FRIA (détermination finale)
Sur la base de cette FRIA, **aucun risque résiduel disproportionné ou irréversible** pour les droits fondamentaux n’a été identifié, après prise en compte des mesures techniques et organisationnelles ainsi que de la supervision humaine.

Le déploiement du système d’IA est donc **considéré comme admissible**, **sous réserve** :
- d’un **suivi continu**,
- d’une **réévaluation** en cas d’évolution de la nature, de la portée, du contexte ou des finalités d’usage,
- et de l’activation des **mécanismes de contestabilité / supervision** lorsque requis.

### Table de correspondance FRIA → DPIA
- **Non-discrimination / égalité** : DPIA Section 5 (R3), Section 6.B  
- **Liberté d’expression / information** : DPIA Section 5, Section 6.B  
- **Vie privée & données personnelles** : DPIA Sections 2–3, Section 6.A  
- **Droit à un recours / contestabilité** : DPIA Section 6.B, Section 3.D  
- **Dignité / vulnérabilité** : DPIA Section 1.B (critère 7), Section 5  
- **Surveillance / profilage** : DPIA Section 1.B (critères 1–3), Section 5  


---


