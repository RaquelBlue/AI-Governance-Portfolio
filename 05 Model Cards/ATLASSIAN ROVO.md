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
