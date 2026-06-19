## Control Library: Atlassian Rovo

| | |
|---|---|
| **Platform** | Atlassian Rovo
| **Developer** | Atlassian
| **Framework** | NIST 800-53 Rev 5 |
| **Prepared For** | Reverend Dr. Vernon Masters, Beaumont Church of Healing (501(c)(3)) |
| **Prepared By** | Raquel Blue, AI Governance Lead |
| **Date** | 18 June 2026 |
| **Related Document(s)** | Risk Assessment: Atlassian Rovo |

### 1. Security Controls

| Control ID | Control Requirement | Control Implementation Statement | Risk Addressed | Control Owner
|------------|---------------------|----------------------------------|----------------|--------------|
| ROVO-001 | Account Management | The Identity Management Team implements AC-2 by establishing, modifying, and reviewing Rovo user profiles based on authorized role matrices. The organization uses the Atlassian Admin Centralized Identity Directory to map role scopes. This occurs upon account creation and during mandatory user access updates. Results are reviewed by the IT Security Director. Evidence includes role assignment blueprints and current user directory listings. | RSK-SEC-01 | Identity Management Team |
|ROVO-002 | Automated Account Management | The Systems Administration Team implements AC-2(1) by automatically generating and offboarding Rovo user profiles based on active employment changes. The organization uses Atlassian Access automated provisioning scripts linked to Okta** to synchronize directories. This occurs instantaneously upon an HR directory modification trigger. Results are reviewed by the IT Security Director. Evidence includes API sync logs and automated lifecycle provisioning rules. | RSK-SEC-01 | Systems Administration Team |
| ROVO-003 | Automatic Disable Inactive Accounts | The Identity Management Team implements AC-2(3) by revoking access for stagnant workspace credentials. The organization uses Atlassian Access Domain Policies to enforce access thresholds. This occurs automatically via a daily system script execution at 12:00 AM CST if an account is inactive for a consecutive period of 30 days. Results are reviewed by the Systems Administrator. Evidence includes domain inactivity policy screenshots and disabled account log registries. | RSK-SEC-02 | Identity Management Team |
| ROVO-004 | Automated Audit Action | The IT Security Team implements AC-2(4) by detecting and blocking unvetted permission shifts inside the cloud tenant. The organization uses Atlassian Access Guardrails alerts to monitor privilege states. This occurs automatically in real-time upon any privilege escalation event. Results are reviewed by the AI Governance Lead. Evidence includes automated alert rule configurations and sample security ticket logs.| RSK-SEC-01 | IT Security Team |
| ROVO-005 | Access Enforcement | The Information Security Team implements AC-3 by enforcing strict querying and access perimeters between distinct user partitions. The organization uses Atlassian Data-Level Role-Based Access Control (RBAC) policies to deny unauthorized information lookup. This occurs persistently on a continuous runtime verification basis. Results are reviewed by the AI Governance Lead. Evidence includes system-enforced RBAC permission matrices and access restriction logic screenshots. | RSK-SEC-01, RSK-SEC-03 | Information Security Team |
| ROVO-006 | Separation of Duties | The IT Security Director implements AC-5 by separating the responsibilities of configuring automation mechanics from system deployment authorization paths. The organization uses Jira Service Management structural workflow rules to enforce validation thresholds. This occurs upon any modification to a Rovo agent template or script. Results are reviewed by the Chief Operations Officer. Evidence includes Jira workflow permission diagrams and configuration change ticket records. | RSK-SEC-03 | IT Security Director |
| ROVO-007 | Keast Privilege | The Systems Administration Team implements AC-6 by restricting standard accounts from modifying structural AI parameters. The organization uses Atlassian Access organization-level restrictions to enforce operational boundaries. This occurs persistently during all active software sessions. Results are reviewed by the IT Security Director. Evidence includes scoped access policy parameters and global permission configuration panels. | RSK-SEC-01, RSK-03 | Systems Administration Team |
| ROVO-008 | Authorize Privileged Access | The IT Security Director implements AC-6(1) by ensuring that access to the overarching platform configurations requires executive validation. The organization uses a Secondary Administrative Credential and Formal Sign-off mechanism to enforce verification boundaries. This occurs prior to the elevation of any account to Super-Admin status. Evidence includes signed administrative authorization memos and elevated privilege logs. | RSK-SEC-01 | IT Security Director |
| ROVO-009 | Non-Privileged Accounts for Non-Privileged Function | The Systems Administration Team implements AC-6(2) by separating administrative operations from standard daily communication interactions. The organization uses a Dual-Account Policy Registry to separate profiles. This occurs persistently during all standard operating hours for all IT personnel. Results are reviewed by the IT Security Director. Evidence includes dual-account registry listings and active administrative session logs. | RSK-SEC-03 | Systems Administration Team |
| ROVO-010 | Session Termination | The Endpoint Management Team implements AC-12 by enforcing strict connectivity exposure windows on all local and mobile terminals. The organization uses Atlassian Access Portal Configuration Profiles to drop idle connections. This occurs automatically upon reaching exactly 30 minutes of total user inactivity. Results are reviewed by the Systems Administrator. Evidence includes global portal timeout parameters and active session termination event logs. | RSK-SEC-02 | Endpoint Management Team |
| ROVO-011 | Identification and Authentication | The Network Operations Team implements IA-2 by verifying the unique identity of each internal user before interaction can occur. The organization uses Okta Single Sign-On (SSO) to handle authentication routing. This occurs at every distinct user login attempt. Results are reviewed by the IT Security Director. Evidence includes MFA platform configuration parameters and enforced authentication policy records. | RSK-SEC-02 | Network Operations Team |
| ROVO-012 | MFA for Network Access | The Network Operations Team implements IA-2(1) by intercepting external connection paths to the collaboration environment. The organization uses Phishing-Resistant Multi-Factor Authentication (MFA) tokens to authenticate accounts. This occurs at every network login instance originating from both internal and external domains. Results are reviewed by the IT Security Director. Evidence includes SSO MFA enforcement policy dashboards and token registration logs. | RSK-SEC-02 | Network Operations Team |
| ROVO-013 | MFA for Local/Mobile Access | The Endpoint Management Team implements IA-2(2) by protecting mobile and remote hardware endpoints from physical or unauthorized access. The organization uses Mobile Device Management (MDM) profiles to mandate biometric verification (FaceID/TouchID) and local hardware challenge tokens. This occurs at device unlock and upon launching mobile Atlassian applications. Results are reviewed by the Systems Administrator. Evidence includes MDM local authentication policy scripts and endpoint compliance logs. | RSK-SEC-01, RSK-SEC-02 | Endpoint Management Team |

### 2. Privacy Risks 

| Control ID | Control Requirement | Control Implementation Statement | Risk Addressed | Control Owner
|------------|---------------------|----------------------------------|----------------|--------------|
| ROVO-014 | Information Flow Enforcement | The Data Infrastructure Team implements AC-4 by enforcing strict, folder-level parsing boundaries across linked document repositories. The organization uses Atlassian Connected Application API Source Exclusions to programmatically isolate target directories. This occurs on a continuous processing basis and during weekly connector health checks. Results are reviewed by the Data Privacy Officer. Evidence includes API connector configuration scripts and explicitly excluded folder path manifests. | RSK-PRV-01 | Data Infrastructure Team |
| ROVO-015 | Information Flow Control | The Information Security Team implements AC-4(4) by restricting data transmission paths leaving our verified collaboration tenant. The organization uses Atlassian Access cross-org sharing restrictions to drop unauthorized text-block migrations. This occurs automatically at the API routing layer during any cross-system data movement attempt. Results are reviewed by the Data Privacy Officer. Evidence includes cross-org data sharing policy rulesets and blocked transfer logs. | RSK-PRV-01 | Information Security Team |
| ROVO-16 | Authority to Process PII | The Legal and Compliance Team implements PT-2 by validating the operational necessity and legal parameters governing automated dataset search. The organization uses an Internal Privacy Impact Assessment (PIA) and Data Mapping Registry to clear directories. This occurs prior to connecting any new software repository to the ecosystem and is reassessed annually. Results are reviewed by the AI Governance Lead. Evidence includes completed and signed Privacy Impact Assessment documents and updated data processing inventories. | RSK-PRV-02 | Legal and Compliance Team |
| ROVO-017 | PII Quality and Integrity | The Data Privacy Officer implements PT-4 by preventing confidential demographic elements from leaking into unstructured search summaries. The organization uses automated data classification masking tools to scrub indexing records. This occurs automatically at the processing engine layer upon the generation of any cross-system summary text. Results are reviewed by the AI Governance Lead. Evidence includes data masking script rulesets, dynamic redaction log histories, and masked query feedback output checks. | RSK-PRV-01, RSK-PRV-03 | Data Privacy Officer |














