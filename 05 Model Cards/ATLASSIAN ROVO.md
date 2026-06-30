| | |
|---|---|
| **Platform** | Atlassian Rovo
| **Developer** | Atlassian Corporation 
| **Framework** | NIST 800-53 Rev 5 |
| **Business Owner** | Reverend Dr. Vernon Masters |
| **Technical Owner** | IT Security Director |
| **Prepared For** | Reverend Dr. Vernon Masters, Beaumont Church of Healing (501(c)(3)) |
| **Prepared By** | Raquel Blue, AI Governance Lead |
| **Date** | 28 June 2026 |
| **Related Document(s)** | Platform Assessment: Atlassian Rovo |

## Platform Purpose

Atlassian Rovo is an enterprise-tier organizational intelligence platform driven by generative artificial intelligence,
engineered natively to function inside the organization's collaborative infrastructure. BCoH operates a multifaceted
faith-based infrastructure that manages over 2,000 weekly in-person worship attendees, 5,000 virtual attendees,
and a massive mid-week scripture reading discussion averaging over 10,000 virtual participants. This extensive
community footprint results in thousands of distributed document files, project timelines, and software tickets across
multiple administrative environments. Rovo solves the problem of extensive administrative "busy work," operational 
fragmentation, and information silos by providing three core technical capabilities:

* **Rovo Search:** Synthesizes data across separate software repositories—including Atlassian Jira/Confluence,
Google Workspace (Docs, Sheets, Slides, Drive), and Microsoft 365 (OneDrive, SharePoint, Outlook)—to
instantly locate, aggregate, and summarize documents.

* **Rovo Chat:** Provides an inline conversational natural language processing interface that permits users to ask
complex cross-departmental questions, create Jira tasks, add issue comments, and modify project paths directly
without application-switching fatigue.

* **Rovo Studio & Rovo Agents:** Delivers a no-code agent execution environment where customized virtual
assistants can parse meeting transcripts, automate child-care tracking, compile sponsor status reports, or serve
as virtual desk service assistants via Jira Service Management (JSM) Assist.

The platform will be utilized internally by Executive Leadership, Ministry Directors, Administrative/Operations Staff,
and IT/Facilities Technicians to recover manual searching time and drive smarter, context-driven operational
decisions.

## Operational Use

### Intended Use

Atlassian Rovo is authorized strictly for internal administrative and project management operations. Valid use cases
include:

* Cross-referencing sponsorship contracts in Google Drive with active promotional elements in Jira to generate
status updates for local workshops, kid events (ages 5–18), and scholarship fundraisers.

* Converting recorded planning transcripts from community outreach sessions into actionable tasks and child-
care tracking schedules.

* Deploying Virtual Service Agents through JSM Assist to automate facilities management queues, building
maintenance tracking, and AV electronics configuration tickets for our main location and subsidiary sister
church.

### Prohibited Use
To preserve organizational integrity, the platform is strictly prohibited from the following use cases:

* **No Public or Congregation Access:** Under no condition shall external visitors, guest participants, or the
general public interface with or query Rovo.

* **No Spiritual Guidance Automation:** The platform shall not be used to automate spiritual counseling, sermon
drafting, scriptural interpretation, or confessional guidance.

* **No General External Research:** Standard users are blocked from employing the engine for general academic
research, step-by-step external technical troubleshooting instructions, or any operational task detached from
BCoH's internal documents.

## Data Considerations & Privacy Guidance

Beaumont Church of Healing processes a high volume of spiritually, legally, and financially sensitive records. 
Managing information flow requires rigorous data classification and strict ingestion boundaries.

### Permitted Data

Authorized data elements available for Rovo indexing include general church operations documentation, marketing
calendars, facilities maintenance logs, educational workshop agendas, and aggregated corporate sponsorship
status metrics.

### Restricted & Prohibited Data

Highly sensitive files are strictly prohibited from being ingested, parsed, or summarized by the AI engine. This
includes:

* Personally Identifiable Information (PII) and registration rosters of children (ages 5–18) participating in youth
ministries.

* All 1-on-1 and group support records, including mental health guidance notes, bereavement coaching histories,
and personal growth journal filings.

* Spiritual confessional logs, pastoral consultation notes, and individual financial donor contribution ledgers.

### Governance & Retention Requirements

Regulated data cannot be handled by standard default parameters. Strict data classification protocols must be
enforced at the API layer. Pursuant to 501(c)(3) legal constraints and internal pastoral confidentiality mandates, a
mandatory Internal Privacy Impact Assessment (PIA) must clear every file repository prior to application
connector pairing. Furthermore, to satisfy tax-exempt isolation requirements, the data streams of the commercial
funeral home subsidiary must reside in distinct, logically isolated schemas, fully blocked from general church
search results. All AI interaction summaries must adhere to church data retention policies and must be dynamically
watermarked to protect downstream processing errors.

## Key Organizational Risks

The comprehensive risk assessment identified several critical vulnerabilities introduced by the unconstrained
deployment of Atlassian Rovo:

* **Security Privileged Access Escalation:** Gaps in user directory configurations could allow standard internal
accounts to modify base LLM permissions or independently adjust agent knowledge access scopes, expanding
the technical attack surface.

* **Pastoral & Minor PII Privacy Exposure:** Automated index harvesting making it possible for standard users to
query and accidentally view confidential counseling notes, bereavement logs, or minor registration details (ages
5–18).

* **Regulatory Entity Cross-Contamination:** AI configurations bypassing required technical separation
boundaries between the 501(c)(3) church operations and its subsidiary commercial funeral services, risking
legal piercing of the corporate veil.

* **Data Protection Deletion Loops:** Permitted conversational natural language actions occurring without strict
identity challenges, allowing a user or custom agent to initiate bulk delete or modify actions across entirely
separate departments.

* **Algorithmic Oversight Failure:** AI hallucinations or mistranslated meeting transcripts leading to erroneous
automated task creations, budget alterations, or structural project deletions without manual validation.

* **Reputational & Funding Erosion:** Leaked pastoral files or minor data spillage causing extreme public scrutiny,
leading to the abrupt loss of local/national corporate sponsorships, drop-offs in congregation giving, and
structural damage to BCoH trust vectors.

## Required Controls

Approval of Atlassian Rovo is strictly contingent upon the implementation of the following baseline
controls:

| Control ID | Control Name | Enforcement |
|------------|--------------|-------------|
| ROVO-005 | Access Enforcement | Enforce data-level Role-Based Access Control (RBAC) to ensure that cross-departmental
paths cannot be indexed or parsed by unauthorized personnel at runtime. |
| ROVO-007 | Least Privilege | Enforce Atlassian organization-level restrictions to block standard users from modifying
base LLM permissions or agent knowledge access parameters. |
| ROVO-010 | Session Termination | Configure portal parameters to automatically terminate idle user sessions and open 
workspaces upon reaching exactly 30 minutes of total user inactivity. |
| ROVO-013 | MFA for Network Access | Require Mobile Device Management (MDM) enrollment with mandatory biometric 
verification (FaceID/TouchID) for all mobile Atlassian app connections. |
| ROVO-014 | Information Flow Enforcement | Apply Atlassian Connected Application API Source Exclusions to programmatically
block counseling, confessional, bereavement, and minor files from index engines. |
| ROVO-022 | Segregation of Information Flows | Establish explicit database schema multi-tenancy rules and logical API
isolation boundaries to completely separate commercial funeral repositories from church workspaces. |
| ROVO-032 |Stop Bulk Action | Program global engine directives to reject conversational 
commands attempting "Bulk Delete" or "Bulk Modify" executions, locking these functions behind administrative tokens. |
| ROVO-038 | Privacy Notice | Publish a public, faith-aligned AI Privacy Commitment formally declaring the systematic 
isolation of spiritual and minor data repositories from commercial automation pools. | 


## Human Oversight Requirements

To prevent algorithmic errors or automated workflow destruction, the following human oversight constraints are
mandatory:

* **The Human-in-the-Loop (HITL) Validation Gate:** Rovo agents are programmatically restricted from finalizing
any document alteration, project state shift, ticket deletion, or budget adjustment. A Mandatory Jira Service
Management Workflow Transition Validator requires explicit manual human verification and approval before any
state change is executed.

* **Output & Transcript Review:** All automated text outputs, meeting summaries, and program translations
compiled by Rovo Chat or Agents must be flagged with a prominent metadata tag reading *“Draft Pending
Human Review”* and must be verified by a department manager before distribution.

* **Non-Automated Decisions:** Decisions involving counseling alignment, volunteer scheduling for minors,
financial allocation shifts for fundraisers, and sponsorship tier adjustments shall never be fully automated under
any condition.

## Post-Deployment Monitoring Requirements

Continuous technical and behavioral monitoring must be maintained following initial platform activation:

* **Real-Time SIEM Integration:** All user IDs, timestamps, conversational prompt texts, and touched metadata files
must be captured by the Atlassian Access Guardrails Logging Engine and piped directly via API into a
centralized Splunk SIEM for immediate anomaly analysis.

* **Automated Weekly Log Audits:** The Compliance and Audit Team must execute automated parsing scripts
every Friday evening to scan conversational records for offensive terminology, database query spikes, or
atypical data manipulation attempts.

* **Bi-Weekly LMS Training Sync:** Automated compliance sweeps must cross-reference active user credentials
with the church Learning Management System (LMS) bi-weekly. User access to Rovo must be suspended
automatically if an employee's annual AI Acceptable Use training certification lapses.

## Approval Determination

### **RECOMMENDATION: APPROVE WITH CONDITIONS**

The final determination for the deployment of Atlassian Rovo within the Beaumont Church of Healing is to
**Approve with Conditions**. This recommendation is driven directly by balancing Rovo's significant operational
benefits against the sensitive nature of BCoH's counseling, youth, and financial datasets. 

Rovo delivers administrative relief, projecting immense recovery of manual hours spent tracking event metrics, 
managing facilities requests via JSM Assist across our main site and sister church, and organizing sponsorship 
deliverables. However, because the unconstrained platform natively aggregates data cross-environmentally,
launching the platform without strict boundaries poses a high probability of exposing protected minor 
information and breaking pastoral confidentiality boundaries regarding bereavement and mental health 
filings. This exposure would cause immediate trust erosion, potential loss of 501(c)(3) tax status, 
and the cancellation of vital corporate partnerships.

Deployment is therefore authorized **only** upon the verification of the following baseline conditions prior to
workspace activation:

* **Data Blacklisting Validation:** Verification that all folders containing confessional logs, counseling notes,
bereavement documents, and minor registration forms are programmatically blacklisted via Atlassian API
Source Exclusions (`ROVO-014`).

* **Identity & Endpoint Enforcement:** Implementation of mandatory phishing-resistant network MFA
(`ROVO-012`) and MDM-enforced biometrics for mobile terminals (`ROVO-013`).

* **Destructive Command Neutralization:** Hardcoding of global engine directives to reject conversational bulk
delete or modification requests (`ROVO-032`).

* **Logical Structural Isolation:** Technical verification that the database and folder architecture of the commercial
funeral home subsidiary are isolated in an independent schema (`ROVO-022`) to prevent regulatory boundary
spillage.

* **Human Sign-off Enforcement:** Activation of the Jira Service Management Workflow Transition Validator to
guarantee that no AI agent can modify task states or budget parameters without an active human-in-the-loop
sign-off (`ROVO-033`).
