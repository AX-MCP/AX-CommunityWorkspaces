# Workflow

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

## Workflow Diagram

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
