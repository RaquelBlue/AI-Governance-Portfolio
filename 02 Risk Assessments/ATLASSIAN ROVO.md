## AI Risk Assessment: Atlassian Rovo

| | |
|---|---|
| **Platform** | Atlassian Rovo
| **Developer** | Atlassian
| **Framework** | NIST 800-53 Rev 5 |
| **Prepared For** | Reverend Dr. Vernon Masters, Beaumont Church of Healing (501(c)(3)) |
| **Prepared By** | Raquel Blue, AI Governance Lead |
| **Date** | 11 June 2026 |
| **Related Document(s)** | Platform Assessment: Atlassian Rovo |

## 1. Purpose and Scope

This formal risk assessment maps out the explicit threat vectors introduced by Atlassian Rovo to Beaumont Church of Healing operations, 
alongside concrete, mandatory mitigation controls and assigned risk owners.

**Out of Scope:** Applications as part of Atlassian's larger ecosystem which Rovo is embedded, but not acting as standalone software.

## 2. Methodology

## 3. Risk Register

### 3.1 Security Risk

| RSK-SEC-01 | Unauthorized Privilege Escalation | Likelihood | 
|---------|---------|-------------|
| Staff may independently adjust agent knowledge access on a case-by-case basis without secondary verification. | Rogue internal actors, disgruntled staff, or compromised standard user accounts exploit weak administrative session management or configuration gaps to alter global AI engine parameters or gain unauthorized entry into Rovo Studio developer suites. Subversion of organizational security policies, unauthorized creation of rogue AI agents, unexpected data access drift, and systemic breakdown of workspace configuration baselines. | MEDIUM |
| **Owner** | **Proposed Mitigation** | **Impact** |
| IT Security Director | Enforce strict Atlassian organization-level restrictions to block standard users from modifying base LLM permissions or agent knowledge access. Deploy Atlassian Access Guardrails alerts configured to automatically generate a high-priority security ticket in real-time whenever an account is granted Rovo Studio developer privileges. All administrative console functions strictly require a secondary administrative credential and formal sign-off from executive leadership. **Targeted Controls: AC-2, AC-2(4), AC-6, AC-6(1)** | HIGH |

| RSK-SEC-02 | Identity Theft | Likelihood | 
|---------|---------|-------------|
| Exposure of the workspace to the public internet and unmanaged mobile device access expands the physical attack surface, creating multi-vector entry points. | Threat actors deploy automated credential stuffing or targeted phishing campaigns against church personnel to hijack valid active directory profiles. Full cloud tenant compromise, programmatic exfiltration of internal repositories, identity spoofing within communication channels, and total loss of access control integrity. | HIGH |
| **Owner** | **Proposed Mitigation** | **Impact** |
| IT Security Director | Enforce mandatory phishing-resistant Multi-Factor Authentication (MFA) via Okta for all network access. Integrate Mobile Device Management (MDM) workspace profiles to mandate biometric verification (FaceID/TouchID) and device-level authentication before mobile Atlassian apps open. Configure portal profiles to automatically terminate open browser sessions and connected workspaces upon reaching exactly 30 minutes of user inactivity. **Targeted Controls: IA-2, IA-2(1), IA-2(2), AC-12** | CRITICAL |

| RSK-SEC-03 | Data Manipulation | Likelihood | 
|---------|---------|-------------|
| Staff can execute conversational queries to view or manipulate highly sensitive cross-departmental information that they are not formally authorized to access. | A single developer or administrator builds, modifies, and approves a custom Rovo agent without independent oversight. Inadvertent insider exposure, bypassing of corporate data silos, unauthorized modification of financial or organizational project paths, and collapse of internal accountability mechanisms. | MEDIUM |
| **Owner** | **Proposed Mitigation** | **Impact** |
| IT Security Director | Enforce strict task boundaries through Jira Service Management structural workflow rules guaranteeing an individual who programs a Rovo agent is technically blocked from approving its production deployment. Implement data-level Role-Based Access Control (RBAC) to ensure cross-departmental paths cannot be indexed or parsed by unauthorized profiles at runtime. Mandate that IT personnel utilize standard, non-privileged user accounts for routine daily operations, reserving administrative profiles strictly for verified structural modifications. **Targeted Controls: AC-5, AC-6(2), AC-3** | HIGH |

| RSK-SEC-04 | Failure of Least Privilege | Likelihood | 
|---------|---------|-------------|
| Rovo automatically respects the active permissions of the user querying it, meaning over-privileged accounts act as an immediate conduit for widespread data discovery across the entire enterprise index. | Standard user accounts are provisioned with over-permissive default settings or inherit legacy administrative rights over time. Non-administrative staff gain immediate, unintended visibility into restricted corporate folders, systemic privilege creep, and increased severity of impact if a standard account is compromised. | HIGH |
| **Owner** | **Proposed Mitigation** | **Impact** |
| IT Security Director | Implement a strict Zero-Trust Default Deny posture across the Atlassian directory. Conduct automated bi-weekly user permission audits via Atlassian Access to prune inherited or unused access rights, ensuring conversational visibility matches current, documented job descriptions. **Targeted Controls: AC-6** | HIGH |

### 3.2 Privacy Risks

| RSK-PRV-01 | Cross-Domain Data Spillage | Likelihood | 
|---------|---------|-------------|
| Rovo's automated enterprise search connects to shared cloud repositories (such as Google Workspace or Microsoft OneDrive) to build its semantic index. | Without strict technical boundaries, the AI will pull, cross-pollinate, and expose highly sensitive records—including pastoral counseling files, confession logs, bereavement details, and minor PII (ages 5–18) from youth ministries—into the general search pool accessible by standard staff. Catastrophic breach of pastoral confidentiality, legal exposure regarding minor data protection laws, and a total compromise of internal data privacy guardrails. | HIGH |
| **Owner** | **Proposed Mitigation** | **Impact** |
| Data Privacy Officer | Deploy Atlassian Connected Application API Source Exclusions to programmatically block and isolate counseling, confessional, bereavement, and youth registration directories from ever being indexed by the AI engine. Configure cross-org sharing restrictions to block Rovo from exporting text block data or structural file summaries to unverified third-party apps. Implement automated data classification masking tools to dynamically scrub direct indicators of PII from text summaries generated during cross-system indexing. **Targeted Controls: AC-4, AC-4(4), PT-4** | CRITICAL |

| RSK-PRV-02 | Agentic Autonomy | Likelihood | 
|---------|---------|-------------|
| Connecting live organizational data feeds, records, and sensitive church operations to an automated natural language processing engine without formal, documented privacy reviews or established data-mapping records. | Threat actors prompt the Agent to autonomously audit or summarize records it was never intended to access, allowing for data obfuscation or data poisoning. Regulatory non-compliance, lack of operational transparency, and inability to produce valid data maps during external legal or regulatory reviews. | MEDIUM |
| **Owner** | **Proposed Mitigation** | **Impact** |
| Legal Counsel | The Legal and Compliance Team maintains a mandatory Internal Privacy Impact Assessment (PIA) protocol and an updated Data Mapping Registry. Every data source must be formally cleared and documented before it can be connected to the Atlassian platform, with full reassessments executed annually. **Targeted Controls: PT-2** | MEDIUM |

| RSK-PRV-03 | PII Harvesting | Likelihood | 
|---------|---------|-------------|
| Standard users employ creative conversational structuring or multi-turn prompt loops to trick the AI into aggregating individual, scattered pieces of non-sensitive information from various unmasked folders, reconstituting them into highly classified PII or structured personnel profiles. | Subversion of standard folder-level data masking, unauthorized creation of shadow PII lists, and insider-driven privacy leaks without triggering traditional boundary warnings. | HIGH |
| **Owner** | **Proposed Mitigation** | **Impact** |
| Principal AI Security Engineer | Configure advanced, context-aware content filtering parameters within Rovo Studio. Program the engine's system prompt boundaries to explicitly reject conversational commands that attempt to compile lists of addresses, birthdates, or contact information belonging to church members or minors. **PT-4** | HIGH |

### 3.3 Compliance Risk

| RSK-CMP-01 | Undetected Data Scraping | Likelihood | 
|---------|---------|-------------|
| Unmonitored AI configurations mix data flows across corporate boundaries, threatening the distinct legal and operational separation required between BCoH's 501(c)(3) tax-exempt church structure and its commercial, subsidiary components (such as the funeral home). | Malicious or compromised insiders leverage natural language interfaces to bypass traditional firewall rules, scraping extensive proprietary records without detection. Immediate loss of 501(c)(3) tax-exempt status, piercing of the corporate veil, severe financial penalties, and undetected, widespread intellectual property theft. | HIGH |
| **Owner** | **Proposed Mitigation** | **Impact** |
| Data Privacy Officer | Configure explicit database schema multi-tenancy and logical API exclusions to completely separate the subsidiary funeral home repositories from core church workspaces, ensuring absolute legal and technical data isolation. Deploy the Atlassian Access Guardrails Logging Engine to continuously capture the unique user ID, timestamp, full prompt text, and specific connected file sources for every query. Pipe this log API stream directly into a centralized Splunk SIEM for real-time behavioral correlation mapping and anomaly detection. **Targeted Controls: AU-2, AU-6, AU-6(1), AU-12, AC-4(21)** | CRITICAL |

### 3.4 Third-Party & Vendor Risk

| RSK-TPV-01 | Unauthorized Model Training | Likelihood | 
|---------|---------|-------------|
| Submitting sensitive church data—such as financial ledgers, private executive communications, or strategic planning notes—into an enterprise AI platform that permits user logs to be ingested, analyzed, and recycled by external vendors for public LLM optimization and baseline model re-training. | Permanent loss of corporate data control, intellectual property exposure, and the risk of confidential organizational data appearing in public AI prompt responses worldwide. | HIGH |
| **Owner** | **Proposed Mitigation** | **Impact** |
| Third Party Risk Management Lead | The Procurement Lead executes a mandatory Third-Party Risk Management (TPRM) verification evaluation. BCoH signs a formal Atlassian Enterprise Privacy Agreement that explicitly states all organizational data inputs, conversational logs, and metadata are completely isolated and excluded from LLM optimization and public model training. Contract compliance is re-verified at every annual renewal cycle. **Targeted Controls: SR-3** | CRITICAL |

| RSK-TPV-02 | Shadow System Changes | Likelihood | 
|---------|---------|-------------|
| Cloud service providers deploy automatic, unannounced software updates that introduce experimental AI modules, modify background permissions, or inadvertently alter active indexing connector pathways without IT department review. | Sudden platform instability, unexpected exposure of previously restricted directories, and a breakdown of validated compliance baselines due to shadow feature deployment. | MEDIUM |
| **Owner** | **Proposed Mitigation** | **Impact** |
| Cloud Architect | Leverage the Atlassian Admin Release Track Console to explicitly opt-out of automatic experimental updates, locking the organization's instance exclusively into stable, IT-approved release channels. Deploy Jira Service Management automation rules to automatically log and immediately broadcast high-priority alerts to the IT department the moment an administrator or vendor patch modifies any indexing pathway or API connector. **Targeted Controls: CM-3, CM-3(1), SR-5** | HIGH |

### 3.5 Data Protection Risk

| RSK-DAT-01 | Mass System Erasure | Likelihood | 
|---------|---------|-------------|
| If the AI agent is not restricted, it can execute catastrophic broad state changes and data modifications across connected Jira or Confluence nodes. | Users or compromised accounts exploit Rovo's deep integration tools by issuing creative natural language "bulk actions" (e.g., "delete all closed support tickets from last year" or "clear the outdated registry"). Widespread data corruption, irreversible loss of historical audit or financial logs, massive operational disruption, and prolonged system downtime. | HIGH |
| **Owner** | **Proposed Mitigation** | **Impact** |
| IT Security Director | Formally define broad structural state changes (bulk deletion/modification) as "Privileged Functions". Global engine configurations are hardcoded to automatically reject any conversational request attempting broad destructive actions, locking those tasks exclusively to human administrative tokens. Maintain full data resilience via OwnBackup for Atlassian and nightly Veeam Cloud replication jobs entirely separate from the cloud AI layer, verified by mandatory quarterly sandbox data restoration tests. Enforce a Jira Workflow Transition Validator that blocks any automated agent from shifting project states or adjusting budgets without explicit human cryptographic sign-off. **Targeted Controls: CP-9, CP-9(1), SI-7, AC-6(10)** | CRITICAL |

| RSK-DAT-02 | Data Siphoning | Likelihood | 
|---------|---------|-------------|
| Users leverage semantic search queries to effortlessly aggregate, format, and organize massive, disparate datasets (such as complete church mailing lists, donor ledgers, or asset spreadsheets) and slip them past traditional network-edge Data Loss Prevention firewalls. | Massive data exfiltration, regulatory privacy penalties, corporate espionage, and highly targeted external phishing material creation using stolen internal rosters. | MEDIUM |
| **Owner** | **Proposed Mitigation** | **Impact** |
| Data Privacy Officer | Fully integrate Microsoft Purview Data Loss Prevention (DLP) modules to continuously monitor conversational strings and actively block users attempting massive text data extraction or tabular compilation via chat. Apply permanent AES 256-bit cryptographic encryption protocols systematically to all data at rest within connected databases. Restrict network entry routes using a Cloudflare Enterprise Web Application Firewall (WAF) coupled with strict regional IP whitelisting rules. **Targeted Controls: SC-7, SC-28, SC-38** | HIGH |

### 3.6 Human Oversight Risk

| RSK-HOV-01 | AI Hallucination Blindness | Likelihood | 
|---------|---------|-------------|
| Staff accept hallucinated summaries, mistranslated meeting records, or inaccurate data profiles blindly without manual verification, leading to faulty downstream actions. | Rovo encounters system errors or unhandled syntax exceptions, causing it to inadvertently output internal directory paths, server metadata, or API keys into user-facing chat logs. Exposure of technical system architecture to potential attackers, automated replication of administrative errors, incorrect billing or scheduling, and corrupted decision-making pipelines. | HIGH |
| **Owner** | **Proposed Mitigation** | **Impact** |
| AI Governance Lead | Configure custom Rovo Studio Prompt Filter Templates designed to catch runtime failures, ensuring the system outputs clean, generic error strings to the user while insulating all underlying technical metadata. Establish a mandatory "Human-in-the-Loop" (HITL) gate across all departments; Rovo agents are programmatically restricted from finalizing document alterations, task deletions, or financial adjustments without explicit manual validation from an authorized staff member. **Targeted Controls: SI-11, SI-7** | MEDIUM |

### 3.7 Operational Risk

| RSK-OPS-01 | Prompt Injection | Likelihood | 
|---------|---------|-------------|
| Malicious actors or external users submit weaponized language syntax, hidden characters, or adversarial prompt overrides into open text boxes, attempting to command the underlying LLM to bypass its safety alignment, extract system files, or inject inappropriate content into internal queues. | Unauthorized system behavior, generation of toxic or profane communications within official church channels, and subversion of security guardrails. | HIGH |
| **Owner** | **Proposed Mitigation** | **Impact** |
| Principal AI Security Engineer | Apply Atlassian Studio Input Sanitization Filters to actively scrub natural language text inputs and neutralize adversarial macros before they reach the core processing engine. Run automated analysis scripts continuously to parse conversational logs for offensive terminology, anomalies, or atypical query behaviors. **SI-3** | MEDIUM |

| RSK-OPS-02 | AI Training Gaps | Likelihood | 
|---------|---------|-------------|
| Church staff utilize advanced generative AI tooling without receiving comprehensive training regarding data categorization, safe prompt handling, hallucination detection, or acceptable use boundaries. | Accidental introduction of structural data errors, unintentional privacy violations, disrupted community calendars, and operational downtime caused by user error. | HIGH |
| **Owner** | **Proposed Mitigation** | **Impact** |
| AI Governance Lead | Mandate a comprehensive BCoH AI Acceptable Use Training Certification within the church Learning Management System (LMS). All staff must successfully pass evaluation modules on safe prompt boundaries before account provisioning occurs. Automated LMS compliance reports are pulled bi-weekly, and user access to Atlassian Rovo is automatically suspended if an employee's annual recertification lapses. **AT-3, AT-4** | HIGH |

### 3.8 Reputational Risks

| RSK-REP-01 | Public Trust Erosion | Likelihood | 
|---------|---------|-------------|
| Compromised data, leaked pastoral counseling logs, or accidental public exposure of minor PII (ages 5–18) due to AI system failures escapes into the public domain or media landscape. | Complete erosion of local and national community standing. This results in the abrupt termination of vital corporate sponsorships, a severe reduction in weekly tithes and donations, a dramatic drop-off in virtual and in-person church attendance, and potential litigation. | MEDIUM |
| **Owner** | **Proposed Mitigation** | **Impact** |
| Director of Public Relations | The Church Executive Board publish a transparent, public-facing Faith-Aligned AI Privacy Commitment. This notice explicitly outlines the strict technical exclusion boundaries and API isolation protocols that shield spiritual, bereavement, and counseling files from automated indexing pools. This notice is reviewed annually to preserve institutional transparency and manage community trust vectors. **PT-5** | CRITICAL |
