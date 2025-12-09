# Workflow Diagram

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
