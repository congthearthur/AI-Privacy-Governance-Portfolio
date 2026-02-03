Cadre juridique :
- RGPD – art. 35 (Analyse d’Impact / AIPD)
- Lignes directrices CEPD WP248 rev.01
- AI Act (UE) – art. 27 : analyse des impacts sur les droits fondamentaux (FRIA)


ENGLISH VERSION: 

# DATA PROTECTION IMPACT ASSESSMENT (DPIA) - AI SYSTEM 
**Standard:** GDPR (Art. 35) & EDPB Guidelines (WP 248 rev.01)
**Compatibility:** EU AI Act (High-Risk Systems)

**System Name:** [Name of the AI System]
**Controller:** [Company Name]
**Date:** YYYY-MM-DD
**Version:** 1.6 (WP248 Compliant - Patched)
**Status:** [ ] Draft  [ ] Validation  [ ] Approved
**Lifecycle Stage:** [ ] Design (Prior to Processing) [ ] Pilot [ ] Production [ ] Periodic Review (Iterative)
**AI Act Classification:** [ ] Prohibited [ ] High Risk [ ] Limited Risk [ ] Minimal Risk

---

## 1. TRIGGER ASSESSMENT (WP29 CRITERIA & NATIONAL LISTS)
[cite_start]*Reference: WP 248 rev.01, Section III.B.a (Pages 8-11)* [cite: 124, 140]

### A. National Jurisdiction Check (Art 35(4) & 35(5))
*Before assessing criteria, check specific national requirements.*
* [cite_start][ ] **Blacklist Check:** Is this processing operation on a National DPA "Blacklist" (Art 35(4))? [cite: 197]
  * *If YES, DPIA is **Mandatory** regardless of the criteria below.*
* [cite_start][ ] **Whitelist Check:** Is this processing operation on a National DPA "Whitelist" (Art 35(5))? [cite: 209]
  * *If YES, DPIA is **Not Required** (unless specific conditions are unmet).*
* [ ] Checked for Sector-Specific DPIA Frameworks (e.g., Energy, Health)? 

### B. GDPR "High Risk" Determination (Art 35(1))
[cite_start]*Note: This assessment determines risk to "rights and freedoms" under GDPR.* [cite: 76]

**Applicability Check:** Does the processing meet **any** of the criteria below?
*Note: Meeting **2+ criteria** strongly presumes a DPIA is required. [cite_start]However, a DPIA may still be mandatory if **only one** criterion is met, particularly for 'Systematic Monitoring' or 'Innovative Use' where high risks are inherent.* [cite: 187, 189]
*Clarification:* In accordance with WP 248 rev.01, the use of innovative technology alone does not automatically constitute a high risk; the assessment remains contextual and based on the nature, scope, context and purposes of the processing.
*(WP 248 rev.01, Section III.B, pages 8–11)*

| WP29 Criterion (Risk Indicator) | Applicability to this AI System |
| :--- | :--- |
| **1. [cite_start]Evaluation or Scoring** (e.g., credit scoring, behavioral prediction) [cite: 141] | [ ] Yes |
| **2. [cite_start]Automated Decision Making** with legal/significant effect (Art 22) [cite: 143] | [ ] Yes |
| **3. [cite_start]Systematic Monitoring** (e.g., surveillance, public area monitoring) [cite: 147] | [ ] Yes |
| **4. [cite_start]Sensitive Data** (Art 9: Health, Biometric, Political, etc.) [cite: 150] | [ ] Yes |
| **5. [cite_start]Large Scale Processing** (Volume, duration, geo-extent) [cite: 164] | [ ] Yes |
| **6. [cite_start]Matching/Combining Datasets** exceeding user expectations [cite: 171] | [ ] Yes |
| **7. [cite_start]Vulnerable Data Subjects** (Children, Employees, Patients) [cite: 172] | [ ] Yes |
| **8. [cite_start]Innovative Use / New Tech** (AI, LLMs, IoT, Facial Recog) [cite: 174] | [x] **Yes (AI System)** |
| **9. [cite_start]Preventing Rights/Service Access** (e.g., loan refusal) [cite: 184] | [ ] Yes |

### C. Joint Controllership (Art 26)
*Are we acting alone or jointly?*
* [ ] Sole Controller
* [cite_start][ ] Joint Controller (Roles defined in attached Arrangement) [cite: 112]
  * [cite_start]**Safeguard Check:** Have we ensured that sharing information for the DPIA does not compromise trade secrets or intellectual property (e.g., model weights)? [cite: 116]

---

## 2. SYSTEMATIC DESCRIPTION & ASSETS
[cite_start]*Reference: EDPB Annex 2 - "Systematic description... nature, scope, context and purposes... assets... recipients"* [cite: 392, 396]

### A. Functional Description
* **Nature & Scope:** [Describe what the AI does and the scale of deployment].
* **Context:** [Describe the environment, e.g., "Internal HR tool" or "Public-facing chatbot"].
* **Purposes:** [Specify the explicit outcome, e.g., "Automating customer triage"].

### B. Asset Inventory (Hardware, Software, People)
[cite_start]*Required by WP 248 Annex 2: "the assets on which personal data rely"* [cite: 396]
* **Software Assets (The Model):**
  * Architecture: (e.g., Transformer / LLM, Random Forest).
  * Training Frameworks: (e.g., PyTorch, TensorFlow).
* **Hardware & Network Assets:**
  * Hosting: (e.g., AWS Paris Region, On-Prem GPU Cluster).
  * Transmission Channels: (e.g., TLS 1.3 Encrypted API calls).
* **Human Assets:**
  * Access Rights: (e.g., Data Scientists, Prompt Engineers, HR Managers).
* **Paper Assets:**
  * [ ] N/A (Full Digital) or [ ] Scanned physical documents.

### C. Recipients & Storage Duration
* [cite_start]**Recipients (Who sees the data?):** [cite: 394]
  * [ ] AI Vendor/Processor (e.g., OpenAI, Anthropic)
  * [ ] Cloud Provider (e.g., AWS, Azure, GCP)
  * [ ] Integration Partners (e.g., Zapier, CRM provider)
  * [ ] Internal Support / IT Admin
* [cite_start]**Legal Qualification of Actors (GDPR)**  
* [ ] Controller  
* [ ] Joint Controller (Art. 26 GDPR – joint arrangement attached)  
* [ ] Processor (Art. 28 GDPR)

For each external recipient:
**Release Gate (Mandatory):**  
No deployment, validation, or approval of this DPIA is permitted **until every external recipient listed above has a fully completed row in the table below**, including:
- role qualification (Controller / Joint Controller / Processor),
- applicable GDPR instrument (Art. 26 or Art. 28),
- transfer status (if applicable),
- and confirmation of contractual safeguards.

This requirement applies to **all external recipients**, including AI vendors, cloud providers, and integration partners.

| Recipient | Role (Controller / Joint / Processor) | GDPR instrument (Art 26 / Art 28) | Transfer? (Y/N) | Notes |
| :--- | :--- | :--- | :--- | :--- |
| [AI vendor] | [ ] C / [ ] JC / [ ] P | [ ] 26 / [ ] 28 | [ ] Y / [ ] N | [SCC/DPF/TIA if Y] |
| [Cloud] | ... | ... | ... | ... |

- Role qualification: Controller / Joint Controller / Processor  
- Applicable legal basis: Art. 26 or Art. 28 GDPR  
- Contractual safeguards in place:
  * [ ] Joint controllership agreement (Art. 26)  
  * [ ] Data Processing Agreement with documented instructions (Art. 28(3))  
  * [ ] Audit rights / security documentation available
* [cite_start]**Retention Policy:** [cite: 403]
  * Input Prompts: [e.g., Retained for 30 days then deleted]
  * Output/Completions: [e.g., Stored in user account for 1 year]
  * Logs: [e.g., 90 days rolling retention]

---

## 3. NECESSITY, PROPORTIONALITY & RIGHTS
[cite_start]*Reference: EDPB Annex 2 - "Necessity and proportionality... measures contributing to rights"* [cite: 398, 404]

### A. Lawfulness of Processing (Art. 6)
* **Phase 1: Training (If applicable):** 
[ ] Consent [ ] Legitimate Interest [ ] Contract [ ] N/A
* **Phase 2: Inference (Usage):**
  * [ ] Consent
  * [ ] Contract
  * [ ] Public Task
  * [ ] Legitimate Interest
    * [cite_start]**MANDATORY SPECIFICATION:** *Describe the specific interest pursued (as required by Art 35(7)(a)):* [cite: 35]
    * _________________________________________________________________________
    * *(Examples: Fraud detection, Network security, Service optimization)*
    
**Special category / sensitive data (Art. 9 GDPR):**  
- [ ] No  
- [ ] Yes → **Art. 9(2) condition relied upon:** ________________________________  
  *(e.g., explicit consent (9(2)(a)), employment/social protection law (9(2)(b)), vital interests (9(2)(c)), not-for-profit bodies (9(2)(d)), data manifestly made public (9(2)(e)), legal claims (9(2)(f)), substantial public interest (9(2)(g)), healthcare (9(2)(h)), public health (9(2)(i)), research/statistics (9(2)(j)) — specify)*

**Criminal offence / conviction data (Art. 10 GDPR):**  
- [ ] No  
- [ ] Yes → **Legal basis / authorising law (Art. 10 + national law):** ________________________________  
  *(Specify the applicable national legal provision and safeguards, including access restrictions and retention controls.)*
  *Additional safeguards implemented (if applicable):* ______________________

**Data Sources Processed:**  
- **Training:** [ ] Internal data  [ ] Publicly available data  [ ] Third-party provided data  [ ] N/A  
- **Inference:** [ ] User-provided data  [ ] Business data  [ ] Technical logs

**Use of prompts / outputs for model training or improvement:**  
- [ ] **No** — Prompts and outputs are not reused for training or model improvement.  
- [ ] **Yes** — Limited reuse under the conditions specified below:
  - **Scope:** [e.g., safety tuning / quality improvement / fine-tuning / analytics]
  - **Data categories involved:** [prompts / outputs / metadata]
  - **Retention period:** [e.g., X days / anonymised immediately]
  - **Opt-out mechanism:** [e.g., user setting / contractual clause / account-level flag]
  - **Safeguards:** [e.g., anonymisation, aggregation, exclusion of special category data]

*Note:* Where prompts or outputs are reused for training, this processing must be reflected in the legal basis (Art. 6 GDPR) and, where applicable, in Art. 9 / Art. 10 conditions.

### B. Proportionality Assessment (Why AI?)
* **Necessity:** Could the objective be achieved without AI (e.g., rules-based software)?
    * [ ] No. (Justification: Complexity of language/pattern matching requires AI inference).
    * [ ] Yes. (If yes, using High-Risk AI may be disproportionate).
* [cite_start]**Data Minimization (Art 5(1)(c)):** [cite: 402]
    * [ ] We only process inputs strictly necessary for the prompt.
    * [ ] Context window history is limited to [X] turns.

### C. Codes of Conduct & Certifications (Art 40/42)
[cite_start]*Reference: WP 248 Page 16 - "Compliance with a code of conduct... Certifications, seals and marks... should be taken into account"* [cite: 284, 286]
* **Applicability:**
    * [ ] No current approved codes.
    * [ ] Adherence to approved Code of Conduct (Name: ____________________).
    * [ ] Adherence to approved Certification Mechanism (Name: ____________________).

### D. Data Subject Rights Checklist
[cite_start]*Reference: WP 248 Annex 2 - Measures contributing to the rights of data subjects* [cite: 404]

| Right | Measure Implemented in AI System |
| :--- | :--- |
| [cite_start]**Information (Art 13/14)** [cite: 405] | [ ] Transparency notice displayed. "AI System" label visible. |
| [cite_start]**Access & Portability (Art 15/20)** [cite: 406] | [ ] User can export chat/transaction history (JSON/CSV). |
| [cite_start]**Rectification & Erasure (Art 16/17)** [cite: 407] | [ ] **RAG Strategy:** Source documents removed from retrieval DB to stop citations (since model weights cannot be edited). |
| [cite_start]**Object & Restriction (Art 18/21)** [cite: 408] | [ ] Opt-out available for future training. [ ] Stop generation button. |
| **Automated Decision Review (Art 22)** | [ ] Human-in-the-loop available for contesting decisions. |

### E. International Transfers (Chapter V)
* [cite_start]**Does data leave the EEA?** [cite: 409]
  * [ ] No (Data residency pinned to EU Region).
  * [ ] Yes (Transfer to US/Third Country).
* **Transfer Mechanism:**
  * [ ] Adequacy Decision (e.g., EU-US Data Privacy Framework).
  * [ ] Standard Contractual Clauses (SCCs) + **Transfer Impact Assessment (TIA)**.

---

## 4. CONSULTATION PROCESS
[cite_start]*Reference: EDPB Annex 2 - "Interested parties are involved"* [cite: 417]

* [cite_start]**Advice of the DPO (Art 35(2)):** Has the DPO reviewed the assessment? [cite: 418]
  * [ ] Yes [ ] Pending.
* [cite_start]**Views of Data Subjects (Art 35(9)):** Have views been sought? [cite: 419]
  * [ ] Yes (Survey/Focus Group)
  * [cite_start][ ] No. **(REQUIRED: Insert Justification):** [e.g., Confidentiality of business plans / Disproportionate effort (WP 248 p.15)]. [cite: 256]
* [cite_start]**Processor Assistance (Art 28(3)(f)):** [cite: 251]
  * [ ] Vendor security documentation/System Card reviewed.
  * [ ] Roles & Responsibilities contractually defined (Art. 28(3) Agreement in place).

---

## 5. RISK ASSESSMENT (EDPB TAXONOMY)
[cite_start]*Reference: EDPB Annex 2 - "Origin, nature, particularity and severity of the risks... risks sources are taken into account"* [cite: 411, 412]

[cite_start]**Guidance on Impact Type:** "Rights and freedoms" include privacy but also freedom of speech, non-discrimination, freedom of movement, etc. [cite: 77]

| Risk ID | Risk Source | Scenario | Impact Type (Fundamental Rights) | Severity | Likelihood | Risk Level |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **R1** | **External Attacker** | **Model Inversion:** Attacker extracts PII via prompting. | Illegitimate Access (Privacy) | High | Low | **Medium** |
| **R2** | **External User** | **Prompt Injection:** Bypassing safety filters. | Undesired Modification | High | Medium | **High** |
| **R3** | **System/Model** | **Hallucination/Bias:** AI invents facts or shows prejudice against protected groups. | **Discrimination / Free Speech** | High | High | **Critical** |
| **R4** | **Infrastructure** | **Availability/DoS:** System overloaded. | Disappearance (Temp) | Low | Medium | **Low** |
| **R5** | **Government** | **Cloud Access:** US Gov access (CLOUD Act). | Illegitimate Access (Privacy) | Medium | Low | **Medium** |

---

## 6. MEASURES TO TREAT RISKS
[cite_start]*Reference: EDPB Annex 2 - "Measures envisaged to treat those risks"* [cite: 416]

### A. Security & Integrity Measures (Art. 32 GDPR)
*Measures primarily addressing confidentiality, integrity and availability of personal data.*

| Risk ID | Security Measures (Technical & Organizational) | Residual Risk | Approved? |
| :--- | :--- | :--- | :--- |
| **R1, R5** | **Anonymization/Pseudonymization:** PII stripped before API call. **Encryption:** TLS in transit, AES at rest. | Low | [x] |
| **R2** | **Model & Prompt Security:** Guardrails (NeMo/Llama), input validation, regular red teaming. | Medium | [ ] |
| **R4** | **Availability Controls:** Rate limiting, monitoring, DoS protection. | Low | [ ] |

---

### B. Fundamental Rights & Safeguard Measures
*Measures primarily addressing risks to rights and freedoms of data subjects (WP 248 Annex 2).*

| Risk ID | Rights Safeguards (Procedural & Human-Centric) | Residual Risk | Approved? |
| :--- | :--- | :--- | :--- |
| **R3** | **Grounding (RAG):** Outputs restricted to verified sources; citations enforced to reduce hallucination and bias. | Medium | [ ] |
| **R3** | **Human Oversight (Art. 22):** Mandatory human review for decisions with legal or similarly significant effects. | Low | [x] |
| **R3** | **Contestability & Explanation:** Users may request explanation or challenge outcomes via defined procedure. | Low | [x] |

[cite_start]**CRITICALITY CHECK:** Does any residual risk involve "significant or irreversible consequences" (e.g., threat to life, layoff, financial jeopardy) that the subject cannot overcome? [cite: 334]
* [ ] No
* [cite_start][ ] Yes -> **STOP.** Prior Consultation with Supervisory Authority is **MANDATORY**. [cite: 335]

---

## 7. MONITORING & REVIEW PLAN
[cite_start]*Reference: WP 248 rev.01 (Page 13) - "Review... at least when there is a change of the risk"* [cite: 309]

**Re-assessment Triggers:**
1. **Model Drift:** Accuracy drops below defined threshold.
2. **New Capabilities:** Enabling plugins, internet access, or new data categories.
3. [cite_start]**Purpose Expansion:** Use of the model for a new intent (e.g., moving from "customer support" to "sales profiling"). [cite: 217]
4. [cite_start]**Contextual Change:** New legislation (e.g., AI Act), regulatory guidance, or shifts in societal acceptance (WP 248 p.13).
5. **Periodicity:** Review every [12] months.

**Compliance Audit (Art 35(11)):**
* [ ] **Data Flow Verification:** Verify actual data flows match the description in Section 2.
* [ ] **Policy Check:** Confirm retention policy (e.g., deletion of prompts) is effectively executing.
* [ ] Iterative Review: This DPIA will be updated if the "Nature, Scope, Context or Purposes" change (Art. 35(11)).
* [ ] **Art. 25 Integration (DPbD/DPbDf):** DPIA outcomes are implemented in system design (requirements, architecture, defaults) and validated before release.
* [ ] **Release Gate:** No production deployment unless Art. 25 integration items are closed or formally risk-accepted by Controller + DPO.
* [ ] **Art. 24 Accountability:** Controller confirms that DPIA findings are reflected in organisational policies, procedures, and controls.

---

## 8. SIGN-OFF & PUBLICATION
[cite_start]*Reference: EDPB Annex 2 - "Document the decisions taken"* [cite: 359]

* **DPO Advice:**
  * [ ] Compliant.
  * [ ] Residual risks high; [cite_start]**Consult Supervisory Authority (Art 36)**. [cite: 335]
* **Controller Rationale (if deviating from DPO or Data Subject views):**
  * [ ] N/A (Consensus reached).
  * [cite_start][ ] Deviation Justification: *[Insert reasoning here - Required by WP 248 p.15]* [cite: 255]
* **Transparency Decision:**
  [cite_start]*Reference: WP 248 Page 18 - "Publishing a summary could foster trust"* [cite: 313]
  * [ ] Full DPIA is Confidential.
  * [ ] Public Summary will be published (Link/Location: __________).
* **Controller Decision:** [ ] Proceed (Only if Residual Risk is Low/Medium OR Consultation Completed) [ ] Stop
* **CISO Validation:** [ ] Validated
* **Date:** ____________________

---
## ANNEX. EU AI ACT – FUNDAMENTAL RIGHTS IMPACT ASSESSMENT (FRIA)

This annex constitutes the **Fundamental Rights Impact Assessment (FRIA)** required 
under **Article 27 of the EU AI Act** for High-Risk AI Systems.

The FRIA reuses and builds upon this **Data Protection Impact Assessment (DPIA) under 
Article 35 GDPR**, in line with the EU risk-based and fundamental-rights-centric approach.

### FRIA-1. Deployment context (real-world use)
- **Use setting:** [internal / external / public-facing / B2B / public authority]
- **Primary function:** [e.g., recommendation, triage, assistance, scoring, decision support]
- **Legally or similarly significant effects:** [ ] No  [ ] Yes → specify: ___________________
- **Affected persons:** [customers / employees / patients / students / general public]
- **Sector & environment:** [e.g., HR, finance, health, education, public services]
- **Interfaces:** [chatbot, API, portal, mobile, back-office]
- **Geographic scope:** [EU / non-EU]  | **Languages:** [___]

### FRIA-2. Fundamental rights screened
Potential impacts were assessed against fundamental rights, including:
- **Non-discrimination / Equality**
- **Freedom of expression / Access to information**
- **Privacy & Personal data protection**
- **Right to an effective remedy / Contestability**
- **Human dignity & protection of vulnerable persons**
- **Surveillance / Profiling**

For each right, the assessment relies on:
- risk scenarios (DPIA Section 5),
- mitigation and safeguards (DPIA Section 6),
- and the monitoring plan (DPIA Section 7).

### FRIA-3. Stakeholders & affected groups
- **System users:** [e.g., internal staff / customers / partners]
- **Affected individuals:** [e.g., candidates, employees, customers, users]
- **Potentially vulnerable groups:** [ ] No  [ ] Yes → specify: ___________________________
- **Redress / contact channel:** [process, channel, timeline, owner]
- **Consultation of affected persons / groups:**  
[ ] **Yes** — Method(s): [e.g., survey, workshop, user testing, representative body]  
[ ] **No** → **Justification:** [e.g., disproportionate effort, confidentiality constraints, early design phase, absence of direct impact]

*Note:* Where consultation was not conducted, the rationale aligns with GDPR Art. 35(9) and is documented for accountability purposes.


### FRIA-4. Safeguards & governance measures
Key safeguards and controls include:
- **Human oversight** for decisions with legal or similarly significant effects (GDPR Art. 22) (DPIA §6.B)
- **Contestability & explanation** via a defined redress procedure (DPIA §6.B / §3.D)
- **Anti-bias / anti-hallucination safeguards** (RAG grounding, verified sources, citations) (DPIA §6.B)
- **Security & integrity measures** (encryption, access control, monitoring, etc.) (DPIA §6.A)
- **Continuous monitoring and reassessment** upon changes in purpose, scope, context, or capabilities (DPIA §7)

### FRIA-5. FRIA conclusion (final determination)
Based on this FRIA, **no residual risks of a disproportionate or irreversible nature** to fundamental rights have been identified, taking into account the implemented technical and organisational measures and human oversight.

The AI system may therefore be **deployed**, **subject to**:
- **continuous monitoring**,
- **reassessment** in case of changes to the nature, scope, context, or purposes of use,
- and activation of **human oversight / contestability mechanisms** where required.

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


