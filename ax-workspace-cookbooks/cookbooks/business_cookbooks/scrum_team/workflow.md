# Workflow

## Agent Workflow

The Scrum Team Workspace orchestrates comprehensive agile development through intelligent automation and human-AI collaboration. This workspace transforms traditional Scrum processes by providing real-time coordination between team roles, automated ceremony management, and continuous performance optimization. The system maintains sprint cadence while reducing manual overhead through intelligent task routing, automated metrics collection, and proactive impediment identification.

Each sprint cycle begins with the @ProductOwner prioritizing the backlog while @TechLead provides technical feasibility input. The @ScrumMaster orchestrates planning sessions, coordinates daily standups, and tracks team velocity. Throughout development, @QALead ensures quality gates are met while @TeamAnalyst continuously monitors performance metrics and identifies optimization opportunities. This collaborative approach ensures that all Scrum ceremonies run smoothly, technical quality is maintained, and the team continuously improves its delivery capabilities.

The workspace is powered by 5 primary agents:

- **@ScrumMaster** – Process facilitation and team coordination:
  - Automates ceremony scheduling and agenda generation
  - Tracks impediments and escalates blockers to appropriate stakeholders
  - Monitors sprint progress and generates velocity analytics

- **@ProductOwner** – Backlog management and stakeholder communication:
  - Maintains prioritized product backlog with acceptance criteria
  - Facilitates stakeholder feedback collection and refinement sessions
  - Validates story completion against business requirements

- **@TechLead** – Technical guidance and delivery oversight:
  - Reviews code quality metrics and architecture decisions  
  - Coordinates complex feature delivery and technical dependencies
  - Monitors technical debt and provides development mentorship

- **@QALead** – Quality assurance and testing coordination:
  - Orchestrates comprehensive testing strategies and automation
  - Manages bug triage workflows and defect resolution
  - Ensures release readiness through quality gates and metrics

- **@TeamAnalyst** – Performance insights and optimization:
  - Aggregates cross-platform metrics from JIRA, GitHub, and communication tools
  - Generates predictive insights for sprint planning and capacity management
  - Creates executive dashboards and continuous improvement recommendations

**Primary topics** include:

- `#sprint-planning` – Backlog refinement, story estimation, and sprint goal definition
- `#daily-standup` – Progress updates, blocker identification, and coordination
- `#sprint-review` – Stakeholder demos, feedback collection, and acceptance validation
- `#sprint-retrospective` – Process improvement discussions and action item tracking
- `#backlog-refinement` – User story creation, acceptance criteria definition, and prioritization
- `#technical-review` – Architecture decisions, code quality discussions, and technical debt planning
- `#quality-gates` – Testing strategies, defect triage, and release readiness validation
- `#performance-insights` – Team metrics, velocity trends, and optimization opportunities

## Workflow Diagram

```
┌─────────────────────────────────────────────────────────────────────────────────┐
│                            SCRUM TEAM WORKSPACE                                │
│                         (AX Platform + MCP Integration)                        │
└─────────────────────────────────────────────────────────────────────────────────┘
                                        │
                    ┌───────────────────┼───────────────────┐
                    │                   │                   │
        ┌───────────▼──────────┐ ┌──────▼─────────┐ ┌──────▼──────────┐
        │    @ScrumMaster      │ │  @ProductOwner │ │   @TechLead     │
        │  ┌─────────────────┐ │ │ ┌────────────┐ │ │ ┌─────────────┐ │
        │  │ CeremonyOrch... │ │ │ │ Backlog... │ │ │ │ CodeQuality │ │
        │  │ ImpedimentTrac..│ │ │ │ Stakeholder│ │ │ │ Architect..  │ │
        │  │ VelocityAnaly...│ │ │ │ Acceptance │ │ │ │ DeliveryCo..│ │
        │  └─────────────────┘ │ │ └────────────┘ │ │ └─────────────┘ │
        └───────────┬──────────┘ └──────┬─────────┘ └──────┬──────────┘
                    │                   │                   │
                    │     ┌─────────────▼──────────┐        │
                    │     │      @QALead           │        │
                    │     │ ┌──────────────────────┐│        │
                    │     │ │ TestStrategist       ││        │
                    │     │ │ BugTriager          ││        │
                    │     │ │ AutomationOrch...   ││        │
                    │     │ └──────────────────────┘│        │
                    │     └────────┬───────────────┘        │
                    │              │                        │
                    └──────────────┼────────────────────────┘
                                   │
                    ┌──────────────▼────────────────┐
                    │        @TeamAnalyst           │
                    │ ┌────────────────────────────┐│
                    │ │ MetricsCollector           ││
                    │ │ InsightGenerator          ││
                    │ │ ReportBuilder             ││
                    │ └────────────────────────────┘│
                    └──────────────┬────────────────┘
                                   │
    ┌──────────────────────────────┼──────────────────────────────┐
    │                              │                              │
┌───▼─────┐  ┌────────┐  ┌─────────▼──┐  ┌─────────┐  ┌──────────┐
│ JIRA/   │  │ GitHub │  │   Slack/   │  │ Notion/ │  │ Testing  │
│ Linear  │  │ GitLab │  │   Teams    │  │ Conflu. │  │ Tools    │
│         │  │        │  │            │  │         │  │          │
│ Stories │  │ Code   │  │ Comms      │  │ Docs    │  │ Quality  │
│ Sprints │  │ PRs    │  │ Updates    │  │ Wiki    │  │ Reports  │
└─────────┘  └────────┘  └────────────┘  └─────────┘  └──────────┘
                                   │
                 ┌─────────────────┼─────────────────┐
                 │                 │                 │
         ┌───────▼────┐    ┌────────▼──┐    ┌─────────▼──┐
         │ Calendar   │    │ Analytics │    │ File       │
         │ Systems    │    │ DBs       │    │ Storage    │
         │            │    │           │    │            │
         │ Meetings   │    │ Metrics   │    │ Documents  │
         │ Ceremonies │    │ Reports   │    │ Artifacts  │
         └────────────┘    └───────────┘    └────────────┘
```
