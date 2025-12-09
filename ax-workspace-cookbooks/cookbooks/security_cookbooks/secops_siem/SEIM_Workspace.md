# Workspace Name

**Security Event Monitoring**

## Description

Centralized AX workspace for end-to-end security event monitoring, triage, and incident response. It connects our SIEM, EDR, IAM, cloud security, and threat intel sources via MCP so alerts from across the environment land in one shared, searchable place.

## Setup

- **Platform:** AX
- **Interface:** GPT Chat
- **Workspace:** `Security Event Monitoring`

## Agent Workflow

The workspace is powered by four primary agents, each with multiple internal skills/sub-agents:

- **@SecRouter** – front door:
  - Alerts in, tickets & notifications out.
- **@SecAnalyst** – investigations:
  - Triage, log dives, threat intel, and cloud/endpoint context.
- **@SecIdentity** – identity/IAM brain:
  - Profiles, login analysis, containment.
- **@SecCommander** – orchestration:
  - Playbooks, knowledge, reporting.

**Primary topics** include:

- `#alerts` – new detections  
- `#triage` – active investigations  
- `#iam` – identity and access-related issues  
- `#cloud` – cloud security issues  
- `#incidents` – incident coordination  
- `#reports` – summaries and metrics  

All investigation activity, automated steps, and human decisions are recorded as AX messages and tasks, giving SecOps a single source of truth for monitoring and incident handling.

## Agents

1. @SecRouter – Intake, routing, tickets, notifications
Role: Front door for all security events + human comms.
Core responsibilities
    • Ingest and normalize alerts from SIEM/EDR/cloud/IAM (via sec-events MCP).
    • Classify severity, tag alert type, and route into the right topic.
    • Create/update AX tasks for triage and incidents.
    • Sync with ticketing (ClickUp/Jira/ServiceNow).
    • Send notifications to humans (Discord, email).
Skills / sub-agents
    • AlertRouter.skill
        ○ Normalize alert payloads (source, rule, entities, risk score).
        ○ Decide low / medium / high / critical.
        ○ Post summarized alert in #alerts and create triage task.
    • TicketBridge.skill
        ○ Create/update external incident tickets for high/critical cases.
        ○ Maintain mapping AX task ID ↔ ticket ID.
    • Notifier.skill
        ○ Post to incident channels (e.g., Discord).
        ○ Send “new P1 / status changed / resolved” emails.
        ○ Push short status messages back into #incidents and #reports.

2. @SecAnalyst – Triage, investigations, threat intel
Role: First-line analyst and general investigator.
Core responsibilities
    • Triage alerts, gather evidence, recommend disposition.
    • Pull relevant logs from SIEM/EDR/cloud.
    • Perform quick threat intel lookups on IPs/domains/hashes.
    • Summarize findings for human review and for automation.
Skills / sub-agents
    • Triage.skill
        ○ For a new task, pull related events (same user/host/IP/time window).
        ○ Identify patterns: brute force, impossible travel, new device, etc.
        ○ Recommend true_positive, suspicious, or false_positive + confidence.
    • LogDive.skill
        ○ Run scoped searches (last N hours/days).
        ○ Cluster related alerts (multi-stage or repeated events).
        ○ Produce a concise “timeline of events”.
    • ThreatIntel.skill
        ○ Enrich IOCs with internal TI and OSINT (via TI MCP + Reddit MCP if desired).
        ○ Label indicators as known_bad / unknown / benign.
        ○ Attach TI notes to the AX task for downstream agents.
    • CloudSec/Endpoint.skill
        ○ For cloud/endpoint alerts, query findings (CSPM/EDR MCP).
        ○ Assess impact: affected assets, data exposure, lateral movement potential.

3. @SecIdentity – IAM, user/entity context
Role: Identity and access intelligence for all identity-centric alerts.
Core responsibilities
    • Pull identity context: groups, roles, app access, MFA posture.
    • Analyze risky sign-ins and account behavior.
    • Recommend and (when approved) execute IAM mitigations.
Skills / sub-agents
    • ProfileUser.skill
        ○ Fetch user attributes, group membership, privileged roles.
        ○ Check high-value access (admins, finance, prod systems).
        ○ Return a “risk profile” for the entity (user/service account).
    • SigninAnalysis.skill
        ○ Analyze login history for geo/device anomalies.
        ○ Correlate with security alerts (impossible travel, atypical MFA, device change).
    • AccessImpact.skill
        ○ Compute blast radius: which systems/data this account could touch.
        ○ Provide an “if compromised, what’s at risk?” summary.
    • Containment.skill
        ○ Propose IAM actions: lock account, revoke sessions/tokens, reset credentials, strip high-risk roles.
        ○ Implement actions only after explicit human approval (or according to pre-agreed rules).

4. @SecCommander – Playbooks, knowledge, reporting
Role: Orchestrator, runbook brain, and reporting.
Core responsibilities
    • Encode and execute IR playbooks (with human approvals).
    • Pull relevant runbooks/docs and prior cases.
    • Generate daily/weekly reports and metrics.
Skills / sub-agents
    • PlaybookEngine.skill
        ○ Implement decision trees for key scenarios:
            § Suspicious login / account compromise
            § Malware/EDR detection
            § Cloud misconfig / data exposure
        ○ Coordinate calls to @SecIdentity, @SecAnalyst, and @SecRouter.
        ○ Insert explicit “human approval” steps before destructive actions.
    • Runbook.skill
        ○ Query runbooks/KB in GDrive/internal RAG.
        ○ Surface step-by-step procedures tailored to the current incident type.
    • Reporter.skill
        ○ Use AX search/tasks to compute:
            § Incident counts by severity/type.
            § Mean time to triage/close.
            § Noisiest rules / biggest false-positive offenders.
        ○ Post daily/weekly summaries in #reports.
    • Postmortem.skill
        ○ After major incidents, compile key events, actions, and recommendations.
        ○ Draft a post-incident review doc and link it in AX and ticketing.


## Architecture Diagram (ASCII)

```

                   +--------------------------------------+
                   |         AX Workspace:                |
                   |         SecOps – Production          |
                   +-------------------+------------------+
                                       |
       -----------------------------------------------------------------
       |                 |                    |                       |
+--------------+   +--------------+    +--------------+       +----------------+
|  @SecRouter  |   |  @SecAnalyst |    |  @SecIdentity|       | @SecCommander  |
|--------------|   |--------------|    |--------------|       |----------------|
| - AlertRouter|   | - Triage     |    | - ProfileUser|       | - PlaybookEngine|
|   .skill     |   |   .skill     |    |   .skill     |       |   .skill        |
| - TicketBridge|  | - LogDive    |    | - SigninAnal-|       | - Runbook.skill |
|   .skill      |  |   .skill     |    |   ysis.skill |       | - Reporter.skill|
| - Notifier   |   | - ThreatIntel|    | - AccessImpact|      | - Postmortem   |
|   .skill     |   |   .skill     |    |   .skill      |      |   .skill       |
+--------------+   | - CloudSec / |    | - Containment |      +----------------+
                   |   Endpoint   |    |   .skill      |
                   |   .skill     |    +--------------+
                   +--------------+

         ^                ^                   ^                     ^
         |                |                   |                     |
         |                |                   |                     |
   +-----------+    +-----------+       +-----------+        +-------------+
   |   SIEM /  |    |  Threat   |       |   IAM /   |        | Runbooks /  |
   | EDR /     |    |  Intel    |       |  IDPs     |        | KB / GDrive |
   | Cloud Logs|    | APIs/TI   |       |(Okta/AAD) |        |  + RAG      |
   +-----------+    +-----------+       +-----------+        +-------------+
         |                |                   |                     |
         +----------------+-------------------+---------------------+
                                      |
                              +------------------+
                              | Ticketing / ITSM |
                              | (ClickUp/Jira/   |
                              |  ServiceNow)     |
                              +------------------+
                                      |
                              +------------------+
                              | Comms Channels   |
                              | (Discord, Email) |
                              +------------------+
