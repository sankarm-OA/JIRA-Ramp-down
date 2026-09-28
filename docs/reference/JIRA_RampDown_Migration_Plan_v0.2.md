# Executive Summary

JIRA and Tempo have historically underpinned engineering backlog management, sprint tracking, workflow management and the majority of engineering metrics reported to the CTO office. The organisation has selected Strawberry Moon and OneStack as the strategic platforms for engineering tracking, reporting and metrics management going forward.

This plan reviews every metric in the FY27 CTO Metrics Master List, identifies which are sourced from JIRA and/or Tempo, and sets out a structured, risk-managed Ramp-Down and migration programme so that no metric, workflow or historical record is lost in the transition. The plan is structured as a Master Epic with ten supporting Features (workstreams), each broken into Stories/Tasks suitable for direct import into OneStack. The full task-level backlog is provided as a companion Excel workbook (JIRA\_RampDown\_OneStack\_Backlog.xlsx).

Of the 33 metrics in the Master List, 12 are sourced wholly or partly from JIRA or Tempo and are the direct subject of this migration. A further eight tools (Sonarqube, Harness, Grafana, ServiceNow, TruRisk/Qualys, AttackForge, GitHub and CISO reporting) have workflow touchpoints with JIRA that must be re-pointed but do not require metric re-platforming in themselves.

# Scope and Objectives

## Master Epic

JIRA Ramp-Down & Migration to Strawberry Moon / OneStack

Decommission JIRA and Tempo as the engineering backlog, sprint, workflow and metrics platform, and fully re-platform engineering tracking, reporting and metrics management onto Strawberry Moon and OneStack, with zero loss of historical data, no gap in metric continuity, and no disruption to live delivery.

**Success Criteria**

* 100% of the JIRA/Tempo-sourced metrics in the CTO Metrics Master List are reproduced in Strawberry Moon/OneStack and validated within an agreed tolerance against the last JIRA-reported cycle.
* All active projects, backlogs, epics, sprints and historical worklogs are migrated with a documented reconciliation of item counts and key fields.
* Every integration currently wired to JIRA or Tempo (Sonarqube, Harness, Grafana, ServiceNow, TruRisk/Qualys, AttackForge, GitHub, CISO reporting) is re-pointed and verified with zero broken pipelines.
* Tempo is fully retired with an equivalent time-tracking/effort-logging capability live in the target platform(s).
* All engineering squads are trained and actively working in the target platform(s), evidenced by adoption metrics.
* A minimum 4-sprint parallel run is completed and formally signed off by the CTO office and Engineering leadership before JIRA is set to read-only.
* JIRA and Tempo are decommissioned in line with data retention and audit obligations, with no P1/P2 incident attributable to the migration.

## In Scope

* All JIRA projects, boards, workflows and backlogs currently used for engineering delivery.
* All Tempo time-tracking and effort-logging data and configuration.
* All 12 JIRA/Tempo-sourced engineering metrics in the FY27 CTO Metrics Master List.
* All integrations between JIRA/Tempo and adjacent toolchains (Sonarqube, Harness, Grafana, ServiceNow, TruRisk/Qualys, AttackForge, GitHub, CISO reporting).
* User training, change management and adoption support for all impacted engineering staff.

## Out of Scope

* Metrics sourced independently of JIRA/Tempo (Sonarqube, Harness, Grafana, ServiceNow, TruRisk/Qualys, AttackForge, CISO, GitHub) — these are re-pointed, not re-platformed.
* The Vista AI-proposed metrics not yet tracked anywhere (listed separately below) — these are a forward design input for OneStack/Strawberry Moon, not a migration item.
* Non-engineering JIRA usage outside the CTO organisation, unless subsequently confirmed in scope.

# Current State Assessment: Metrics Inventory

The table below lists every metric in the FY27 CTO Metrics Master List that is sourced wholly or partly from JIRA or Tempo. These are the metrics this migration must reproduce and validate.

| **Metric**                                       | **Category**                   | **Source** | **Frequency** | **Unit**  | **FY27 Goal** |
| ------------------------------------------------ | ------------------------------ | ---------- | ------------- | --------- | ------------- |
| Say-Do Ratio                                     | Engineering Excellence         | JIRA       | Fortnightly   | %         | >85%          |
| Velocity (Story Points)                          | Engineering Excellence         | JIRA       | Fortnightly   | #         | Trend         |
| Outstanding Defects                              | Engineering Excellence         | JIRA       | Daily         | #         | n/a           |
| P1 and P2 Incidents                              | Engineering Excellence         | JIRA       | Daily         | #         | n/a           |
| Defect Inflow / Outflow                          | Engineering Excellence         | JIRA       | Daily         | #         | n/a           |
| Automation Test Coverage                         | Engineering Excellence         | JIRA       | Daily         | %         | >80%          |
| Defect Leakage\*                                 | Engineering Excellence         | JIRA       | Daily         | %         | \<5%          |
| L\&D Hours Spend YTD                             | Engineering Excellence         | JIRA/Tempo | Monthly       | %         | Trend         |
| Test Execution Time                              | Engineering Excellence         | Tempo      | Daily         | #         | n/a           |
| Cycle Time (Ready to Done - Development)         | Vista AI - Productivity Impact | JIRA       | n/a           | avg. days | Trend         |
| Escaped Defects                                  | Vista AI - Productivity Impact | JIRA       | n/a           | %         | \<5%          |
| % of Effort Allocated to New Feature Development | Vista AI - Business Impact     | JIRA/Tempo | n/a           | %         | Trend         |

## Adjacent Toolchain Integrations

These tools are not being migrated, but each has a JIRA touchpoint that must be re-pointed to the target platform(s) so their metrics keep flowing without interruption.

| **Tool**       | **Metrics Served**                                       | **JIRA/Tempo Touchpoint**                                    |
| -------------- | -------------------------------------------------------- | ------------------------------------------------------------ |
| Sonarqube      | Code Smells, Unit Test Coverage (Overall & New Code)     | Quality-gate links surfaced against JIRA issue keys/branches |
| Harness        | Deployment Frequency (Success Rate), Change Failure Rate | Deployment pipelines linked to JIRA release/issue keys       |
| Grafana        | Uptime, Downtime, Vista AI Utilisation metrics           | Dashboards may embed JIRA panels or issue-key annotations    |
| ServiceNow     | SLA Violations, MTTR                                     | Incident-to-JIRA-issue linkage for engineering follow-up     |
| TruRisk/Qualys | Vulnerability Risk Score (Overall, CTO)                  | Remediation tickets raised/tracked in JIRA                   |
| AttackForge    | Pentest Critical/High Findings Overdue                   | Findings tracked to remediation via JIRA tickets             |
| GitHub         | Throughput (PRs/Issues Closed)                           | PR-to-issue linkage and branch naming conventions            |
| CISO Reporting | MFA Adoption                                             | Action items tracked via JIRA for remediation                |

## Note on Vista AI-Proposed Metrics

The 'Vista AI-proposed' metrics (% AI-generated code, code suggestion acceptance rate, tasks assigned to agents/agent PRs, unit AI consumption cost per PR, cumulative hours/cost saved) are not currently tracked in JIRA and carry no migration burden, but should be scoped into OneStack/Strawberry Moon's reporting model from day one so they are not built against a platform about to be retired.

# Recommended Workstreams (Features)

Ten workstreams are recommended under the Master Epic. Each is structured as a Feature in OneStack, with its own objective, success criteria and Stories/Tasks. The full task list, owners, dependencies and acceptance criteria for every workstream are provided in the companion Excel backlog; a summary of each workstream's tasks is given below.

## WS-01 — Discovery & Current State Assessment

**Phase:** Phase 1 - Current State Assessment **Owner Area:** Engineering Platform / DevEx Team

Produce a complete, validated inventory of everything in JIRA and Tempo that must be migrated, replicated or retired, so later workstreams plan against facts rather than assumptions.

**Success Criteria**

* Signed-off inventory of all JIRA projects, boards, workflows, custom fields, automation rules and permission schemes.
* Signed-off inventory of all Tempo accounts, categories and worklog structures.
* Every metric in the CTO Metrics Master List mapped to its exact JIRA/Tempo query, field, or JQL logic.
* All downstream integrations and dashboards consuming JIRA/Tempo data identified and owned.

**Stories / Tasks**

| **ID**   | **Task**                                                                               | **Owner**                | **Deliverable**                                                                                          | **Priority** | **Dependencies**   |
| -------- | -------------------------------------------------------------------------------------- | ------------------------ | -------------------------------------------------------------------------------------------------------- | ------------ | ------------------ |
| WS01-T01 | Inventory all JIRA projects, issue types, workflows and screen schemes                 | JIRA Administrators      | JIRA configuration inventory register                                                                    | P1           | None               |
| WS01-T02 | Inventory custom fields, JQL filters, dashboards and automation rules                  | JIRA Administrators      | Automation & custom field catalogue                                                                      | P1           | WS01-T01           |
| WS01-T03 | Inventory Tempo accounts, worklog categories and time-tracking configuration           | Tool Administrators      | Tempo configuration inventory                                                                            | P1           | None               |
| WS01-T04 | Map every FY27 metric to its exact JIRA/Tempo data source, field and calculation logic | Metrics & Analytics Team | Metric-to-source traceability matrix                                                                     | P1           | WS01-T01, WS01-T03 |
| WS01-T05 | Identify all third-party integrations and dashboards consuming JIRA/Tempo data         | DevOps / Toolchain Team  | Integration dependency map (Sonarqube, Harness, Grafana, ServiceNow, TruRisk, AttackForge, GitHub, CISO) | P1           | WS01-T01           |
| WS01-T06 | Assess JIRA/Tempo licensing, contract end dates and data-retention obligations         | PMO / Vendor Management  | Licensing & retention position paper                                                                     | P2           | None               |
| WS01-T07 | Baseline current metric values for the last 4 reporting cycles                         | Metrics & Analytics Team | Baseline metrics snapshot                                                                                | P2           | WS01-T04           |

## WS-02 — Target Platform Foundation Build (Strawberry Moon & OneStack)

**Phase:** Phase 1 - Current State Assessment / Phase 2 groundwork **Owner Area:** Engineering Platform / DevEx Team

Stand up Strawberry Moon and OneStack with the project structures, workflows, fields and permission model needed to receive migrated data and run live sprints.

**Success Criteria**

* Strawberry Moon and OneStack instances are provisioned and configured to mirror the agreed target operating model.
* Workflow, issue-type and field schemes are approved by Engineering leadership before any data migration begins.
* Permission and access model is validated against the current JIRA permission scheme with no regressions.

**Stories / Tasks**

| **ID**   | **Task**                                                                                   | **Owner**                               | **Deliverable**                              | **Priority** | **Dependencies**   |
| -------- | ------------------------------------------------------------------------------------------ | --------------------------------------- | -------------------------------------------- | ------------ | ------------------ |
| WS02-T01 | Define target operating model: project/board structure, issue hierarchy and sprint cadence | Engineering Platform Team               | Target operating model document              | P1           | WS-01              |
| WS02-T02 | Configure OneStack/Strawberry Moon projects, issue types and workflow schemes              | OneStack/Strawberry Moon Administrators | Configured non-production instance           | P1           | WS02-T01           |
| WS02-T03 | Rebuild custom fields, statuses and automation rules in the target platform                | OneStack/Strawberry Moon Administrators | Field and automation parity checklist        | P1           | WS01-T02, WS02-T02 |
| WS02-T04 | Configure permission schemes, roles and access groups                                      | OneStack/Strawberry Moon Administrators | Access control matrix                        | P1           | WS02-T02           |
| WS02-T05 | Configure sprint boards, backlogs and estimation settings                                  | OneStack/Strawberry Moon Administrators | Live sprint board per squad (non-production) | P2           | WS02-T02           |
| WS02-T06 | Build engineering metrics/reporting dashboards natively in OneStack/Strawberry Moon        | Metrics & Analytics Team                | Draft metrics dashboard set                  | P1           | WS01-T04, WS02-T02 |

## WS-03 — Historical Data Migration

**Phase:** Phase 2 - Data Migration **Owner Area:** Data Migration / Integration Engineering

Migrate historical issues, epics, sprints, comments, attachments and worklogs from JIRA and Tempo into the target platform(s) without data loss.

**Success Criteria**

* Migrated record counts reconcile against source JIRA/Tempo counts within an agreed variance.
* Historical velocity, burndown and defect trend data is available in the target platform for at least the prior 12 months.
* Traceability is preserved between legacy JIRA keys and new OneStack/Strawberry Moon identifiers.

**Stories / Tasks**

| **ID**   | **Task**                                                                                | **Owner**                | **Deliverable**                        | **Priority** | **Dependencies**                       |
| -------- | --------------------------------------------------------------------------------------- | ------------------------ | -------------------------------------- | ------------ | -------------------------------------- |
| WS03-T01 | Select and configure a migration tool/ETL pipeline for JIRA to OneStack/Strawberry Moon | Integration Engineering  | Migration tooling decision record      | P1           | WS-01                                  |
| WS03-T02 | Run a pilot migration on one representative squad/project                               | Integration Engineering  | Pilot migration report                 | P1           | WS03-T01, WS02-T02                     |
| WS03-T03 | Migrate historical issues, epics, links and comments for all remaining projects         | Integration Engineering  | Migrated issue data in target platform | P1           | WS03-T02                               |
| WS03-T04 | Migrate historical sprint data (velocity, scope-change, burndown history)               | Integration Engineering  | Historical sprint/velocity data set    | P1           | WS03-T03                               |
| WS03-T05 | Migrate Tempo worklogs and time-tracking history                                        | Integration Engineering  | Migrated worklog data set              | P1           | WS01-T03, WS03-T01                     |
| WS03-T06 | Migrate attachments and embedded documentation                                          | Integration Engineering  | Migrated attachment set                | P2           | WS03-T03                               |
| WS03-T07 | Establish legacy JIRA-key to new-ID cross-reference mapping                             | Integration Engineering  | Key-mapping reference table            | P2           | WS03-T03                               |
| WS03-T08 | Run full data reconciliation and sign-off                                               | Data Migration Lead / QA | Data migration reconciliation report   | P1           | WS03-T03, WS03-T04, WS03-T05, WS03-T06 |

## WS-04 — Metrics & Reporting Re-platforming

**Phase:** Phase 3 - Reporting & Metrics Transition **Owner Area:** Metrics & Analytics Team

Rebuild every JIRA/Tempo-sourced engineering metric in Strawberry Moon/OneStack and prove it reports the same answer as JIRA before JIRA is retired.

**Success Criteria**

* All 12 JIRA/Tempo-sourced metrics are live in OneStack/Strawberry Moon dashboards.
* Each metric is validated against its JIRA baseline within an agreed tolerance for at least 2 consecutive reporting cycles.
* FY27 goals/benchmarks are carried over and visible against each metric in the new platform.

**Stories / Tasks**

| **ID**   | **Task**                                                                            | **Owner**                               | **Deliverable**                        | **Priority** | **Dependencies**                                 |
| -------- | ----------------------------------------------------------------------------------- | --------------------------------------- | -------------------------------------- | ------------ | ------------------------------------------------ |
| WS04-T01 | Rebuild Say-Do Ratio and Velocity (Story Points) reporting                          | Metrics & Analytics Team                | Say-Do Ratio & Velocity dashboard      | P1           | WS03-T04, WS02-T06                               |
| WS04-T02 | Rebuild Outstanding Defects, Defect Inflow/Outflow and Defect Leakage reporting     | Metrics & Analytics Team                | Defect metrics dashboard               | P1           | WS03-T03, WS02-T06                               |
| WS04-T03 | Rebuild P1/P2 Incident reporting                                                    | Metrics & Analytics Team                | Incident metrics dashboard             | P1           | WS03-T03, WS05 (ServiceNow)                      |
| WS04-T04 | Rebuild Automation Test Coverage reporting                                          | Metrics & Analytics Team                | Automation coverage dashboard          | P2           | WS03-T03                                         |
| WS04-T05 | Rebuild L\&D Hours Spend YTD and % Effort to New Feature Development reporting      | Metrics & Analytics Team                | Effort-allocation dashboard            | P2           | WS03-T05                                         |
| WS04-T06 | Rebuild Cycle Time (Ready to Done) and Escaped Defects reporting (Vista AI metrics) | Metrics & Analytics Team                | Vista AI productivity-impact dashboard | P2           | WS03-T03, WS03-T04                               |
| WS04-T07 | Rebuild Test Execution Time reporting (Tempo-sourced)                               | Metrics & Analytics Team                | Test execution time dashboard          | P3           | WS03-T05                                         |
| WS04-T08 | Carry over FY27 goals/benchmarks and RAG thresholds for every metric                | Metrics & Analytics Team                | FY27 benchmark configuration           | P2           | WS04-T01, WS04-T02, WS04-T04, WS04-T05, WS04-T06 |
| WS04-T09 | Independent QA review of every rebuilt metric's calculation logic                   | Metrics & Analytics QA / Internal Audit | Metrics QA sign-off log                | P1           | WS04-T01 to WS04-T08                             |

## WS-05 — Toolchain & Integration Migration

**Phase:** Phase 4 - Tool & Integration Migration **Owner Area:** DevOps / Toolchain Team

Re-point every integration currently wired to JIRA (Sonarqube, Harness, Grafana, ServiceNow, TruRisk/Qualys, AttackForge, GitHub, CISO reporting) to Strawberry Moon/OneStack with no broken pipelines.

**Success Criteria**

* Every integration identified in WS-01 is re-pointed, tested and signed off by its owning team.
* No CI/CD pipeline, quality gate or security workflow references a JIRA issue key that no longer resolves.
* Webhook and API credentials for JIRA/Tempo are rotated out only after all consumers are confirmed migrated.

**Stories / Tasks**

| **ID**   | **Task**                                                                                       | **Owner**                                  | **Deliverable**                               | **Priority** | **Dependencies**     |
| -------- | ---------------------------------------------------------------------------------------------- | ------------------------------------------ | --------------------------------------------- | ------------ | -------------------- |
| WS05-T01 | Re-point Sonarqube quality-gate links and issue-key annotations                                | DevOps / Toolchain Team                    | Updated Sonarqube integration config          | P2           | WS03-T07             |
| WS05-T02 | Re-point Harness deployment pipelines and release/issue-key linkage                            | DevOps / Toolchain Team                    | Updated Harness pipeline config               | P1           | WS03-T07             |
| WS05-T03 | Update Grafana dashboards embedding JIRA panels or issue annotations                           | DevOps / Toolchain Team                    | Updated Grafana dashboards                    | P2           | WS03-T07             |
| WS05-T04 | Re-point ServiceNow incident-to-issue linkage                                                  | DevOps / Toolchain Team + ServiceNow Admin | Updated ServiceNow integration                | P1           | WS03-T07, WS02-T02   |
| WS05-T05 | Re-point TruRisk/Qualys and AttackForge remediation-ticket workflows                           | Security/InfoSec + DevOps                  | Updated security remediation workflow         | P1           | WS02-T02             |
| WS05-T06 | Update GitHub PR-to-issue linkage and branch naming conventions                                | DevOps / Toolchain Team                    | Updated GitHub integration/branching standard | P2           | WS03-T07             |
| WS05-T07 | Update CISO MFA-adoption action-item tracking workflow                                         | Security/InfoSec                           | Updated CISO reporting workflow               | P3           | WS02-T02             |
| WS05-T08 | Decommission JIRA/Tempo API credentials and webhooks once all consumers are confirmed migrated | DevOps / Toolchain Team                    | Credential rotation log                       | P2           | WS05-T01 to WS05-T07 |

## WS-06 — Time Tracking Migration (Tempo Decommission)

**Phase:** Phase 4 - Tool & Integration Migration **Owner Area:** Engineering Platform Team / Finance Ops

Replace Tempo with a native or equivalent time-tracking and effort-logging capability in the target platform(s), preserving cost-centre and L\&D reporting.

**Success Criteria**

* Time-tracking categories (including the dedicated L\&D/BUD code) are replicated in the target platform.
* Squads can log time in the target platform with no dependency on Tempo from cut-over.
* Cost-centre and effort-allocation reporting continues without a gap in trend data.

**Stories / Tasks**

| **ID**   | **Task**                                                                       | **Owner**                               | **Deliverable**                      | **Priority** | **Dependencies**   |
| -------- | ------------------------------------------------------------------------------ | --------------------------------------- | ------------------------------------ | ------------ | ------------------ |
| WS06-T01 | Select and configure the target platform's time-tracking/effort-logging module | Engineering Platform Team               | Configured time-tracking module      | P1           | WS01-T03           |
| WS06-T02 | Migrate Tempo account/category structure and cost-centre mappings              | Engineering Platform Team               | Migrated time-tracking configuration | P1           | WS06-T01           |
| WS06-T03 | Pilot time logging with one squad for two sprints                              | Engineering Platform Team + Pilot Squad | Pilot time-logging report            | P2           | WS06-T02           |
| WS06-T04 | Roll out time-tracking module to all squads with guidance material             | Engineering Platform Team               | Time-tracking quick-reference guide  | P2           | WS06-T03           |
| WS06-T05 | Validate L\&D Hours and % Effort Allocation metrics against Tempo baseline     | Metrics & Analytics Team                | Time-tracking validation report      | P1           | WS06-T04, WS04-T05 |

## WS-07 — User Training & Change Management

**Phase:** Phase 5 - User Training & Change Management **Owner Area:** PMO / Change Management

Prepare every engineering user, squad lead and stakeholder to work confidently in Strawberry Moon/OneStack, and manage the organisational change involved in retiring a tool used daily for years.

**Success Criteria**

* A communications and training plan is delivered against all impacted user groups.
* A network of platform champions is established across squads before parallel run begins.
* Adoption metrics (active usage, support tickets, sentiment) show a stabilising trend before JIRA is set read-only.

**Stories / Tasks**

| **ID**   | **Task**                                                                           | **Owner**                                           | **Deliverable**                                 | **Priority** | **Dependencies** |
| -------- | ---------------------------------------------------------------------------------- | --------------------------------------------------- | ----------------------------------------------- | ------------ | ---------------- |
| WS07-T01 | Develop the migration communications plan and stakeholder map                      | PMO / Change Management                             | Communications plan                             | P1           | WS-01            |
| WS07-T02 | Produce training materials and quick-reference guides for OneStack/Strawberry Moon | PMO / Change Management + Engineering Platform Team | Training pack (guides, videos, FAQs)            | P1           | WS02-T05         |
| WS07-T03 | Recruit and enable a platform-champion network across squads                       | PMO / Change Management                             | Champion network roster and enablement sessions | P2           | WS07-T01         |
| WS07-T04 | Run live training sessions and office hours ahead of parallel run                  | PMO / Change Management                             | Training session calendar and attendance log    | P1           | WS07-T02         |
| WS07-T05 | Establish a support model (help desk / Slack channel) for migration queries        | PMO / Change Management + Engineering Platform Team | Support model and escalation path               | P2           | WS07-T01         |
| WS07-T06 | Track adoption and sentiment throughout parallel run                               | PMO / Change Management                             | Adoption & sentiment tracker                    | P2           | WS07-T04, WS-08  |

## WS-08 — Parallel Run & Validation

**Phase:** Phase 6 - Parallel Run & Validation **Owner Area:** Engineering Platform Team / Metrics & Analytics Team

Run JIRA/Tempo and Strawberry Moon/OneStack side by side for a defined period to prove data, process and metric parity before committing to read-only transition.

**Success Criteria**

* A minimum 4-sprint parallel run is completed across all in-scope squads.
* All 12 JIRA/Tempo-sourced metrics reconcile within tolerance for the full parallel-run period.
* No P1/P2 incident is attributable to running both platforms in parallel.
* Formal go/no-go sign-off is obtained from the CTO office and Engineering leadership.

**Stories / Tasks**

| **ID**   | **Task**                                                                                                  | **Owner**                       | **Deliverable**                            | **Priority** | **Dependencies**             |
| -------- | --------------------------------------------------------------------------------------------------------- | ------------------------------- | ------------------------------------------ | ------------ | ---------------------------- |
| WS08-T01 | Define parallel-run scope, duration, squads and success thresholds                                        | Engineering Platform Team + PMO | Parallel-run plan                          | P1           | WS-03, WS-04, WS-06          |
| WS08-T02 | Operate both platforms concurrently for the defined parallel-run period                                   | All Squads                      | Dual-logged sprint data                    | P1           | WS08-T01                     |
| WS08-T03 | Reconcile all 12 JIRA/Tempo-sourced metrics daily/weekly/monthly (per their frequency) throughout the run | Metrics & Analytics Team        | Parallel-run reconciliation log            | P1           | WS08-T02, WS-04              |
| WS08-T04 | Log, triage and resolve discrepancies found during parallel run                                           | Engineering Platform Team       | Discrepancy tracker with resolution status | P1           | WS08-T03                     |
| WS08-T05 | Validate all re-pointed integrations under live parallel conditions                                       | DevOps / Toolchain Team         | Integration validation report              | P1           | WS-05, WS08-T02              |
| WS08-T06 | Prepare and present go/no-go sign-off pack to the CTO office and Engineering leadership                   | PMO / Engineering Platform Team | Go/no-go decision pack                     | P1           | WS08-T03, WS08-T04, WS08-T05 |

## WS-09 — JIRA Read-Only Transition

**Phase:** Phase 7 - JIRA Read-Only Transition **Owner Area:** JIRA Administrators / Engineering Platform Team

Move JIRA and Tempo to a read-only historical archive state once parallel run is successfully signed off, with all live work fully committed to the target platform(s).

**Success Criteria**

* JIRA and Tempo are set to read-only for all users with no further write access.
* All open work has been confirmed migrated or closed before read-only cut-over.
* A documented archive access process exists for historical lookups.

**Stories / Tasks**

| **ID**   | **Task**                                                                                  | **Owner**                 | **Deliverable**               | **Priority** | **Dependencies**   |
| -------- | ----------------------------------------------------------------------------------------- | ------------------------- | ----------------------------- | ------------ | ------------------ |
| WS09-T01 | Confirm all open issues, sprints and worklogs are closed or migrated before cut-over      | Engineering Platform Team | Cut-over readiness checklist  | P1           | WS-08 sign-off     |
| WS09-T02 | Set JIRA and Tempo permissions to read-only for all users                                 | JIRA Administrators       | Read-only JIRA/Tempo instance | P1           | WS09-T01           |
| WS09-T03 | Publish an archive access process for historical lookups                                  | Engineering Platform Team | Archive access guide          | P2           | WS09-T02, WS03-T07 |
| WS09-T04 | Monitor for read-only period issues (broken integrations, user requests for write access) | Engineering Platform Team | Read-only period issue log    | P2           | WS09-T02           |

## WS-10 — Final Decommissioning & Closeout

**Phase:** Phase 8 - Final JIRA Decommissioning **Owner Area:** PMO / Vendor Management / Engineering Platform Team

Formally decommission JIRA and Tempo, close out licensing, archive required data per retention policy, and capture lessons learned.

**Success Criteria**

* JIRA and Tempo licences are terminated or downsized in line with the retention decision from WS-01.
* A compliant data archive is retained per statutory/audit requirements.
* A retrospective is completed and lessons learned are documented.

**Stories / Tasks**

| **ID**   | **Task**                                                                           | **Owner**                       | **Deliverable**                                 | **Priority** | **Dependencies**   |
| -------- | ---------------------------------------------------------------------------------- | ------------------------------- | ----------------------------------------------- | ------------ | ------------------ |
| WS10-T01 | Export and archive required historical data per the retention decision             | Engineering Platform Team       | Compliant data archive                          | P1           | WS01-T06, WS09-T03 |
| WS10-T02 | Terminate or downsize JIRA and Tempo licences                                      | PMO / Vendor Management         | Licence termination confirmation                | P1           | WS10-T01           |
| WS10-T03 | Decommission any remaining JIRA/Tempo infrastructure, plugins and service accounts | DevOps / Toolchain Team         | Decommissioning checklist                       | P2           | WS10-T02, WS05-T08 |
| WS10-T04 | Conduct a migration retrospective and publish lessons learned                      | PMO / Engineering Platform Team | Retrospective report                            | P3           | WS10-T01, WS10-T02 |
| WS10-T05 | Close the programme and hand over ongoing ownership of Strawberry Moon/OneStack    | PMO                             | Programme closure report and ownership handover | P2           | WS10-T04           |

# Metrics Validation Approach

Validating that every existing JIRA-based metric is available and accurately reported through Strawberry Moon and OneStack is the single most important quality gate in this programme. The approach is:

* Traceability first: every metric is mapped to its exact JIRA/Tempo data source and calculation logic before any rebuild begins (WS01-T04).
* Rebuild and self-check: each metric is rebuilt natively in the target platform and sanity-checked against its own historical trend (WS-04 stories).
* Independent QA: a reviewer independent of the person who rebuilt the metric signs off its calculation logic against the traceability matrix (WS04-T09).
* Parallel calculation: during the parallel-run phase, every metric is calculated from both JIRA/Tempo and the target platform for the same period and the variance is logged (WS08-T03).
* Tolerance and escalation: any metric outside the agreed tolerance (default +/-2%, adjustable per metric) is triaged and resolved before it is treated as production-ready (WS08-T04).
* Formal sign-off: no metric is considered migrated until it has held within tolerance for at least two consecutive reporting cycles and has been included in the go/no-go pack (WS08-T06).

The full per-metric validation task list — including the specific rebuild task, validation method, tolerance and sign-off owner for each of the 12 metrics — is provided in the 'Metrics Validation' tab of the companion Excel backlog.

# Phased Migration Approach

The programme is sequenced into eight phases. Each phase has a defined exit gate; a phase does not start in earnest until its dependencies have cleared, though early workstreams can run with some overlap where risk allows (for example, target platform foundation work can begin once discovery is substantially — not necessarily fully — complete).

| **Phase** | **Name**                                     | **Workstreams** | **Objective**                                                                                | **Exit Criteria**                                                                           |
| --------- | -------------------------------------------- | --------------- | -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Phase 1   | Current State Assessment & Target Foundation | WS-01, WS-02    | Understand everything JIRA/Tempo currently does and stand up the target platform structures. | Signed-off inventories, metric traceability matrix and an approved target operating model.  |
| Phase 2   | Data Migration                               | WS-03           | Move historical issues, sprints and worklogs into the target platform without loss.          | Full data reconciliation report signed off by every squad lead.                             |
| Phase 3   | Reporting & Metrics Transition               | WS-04           | Rebuild and QA every JIRA/Tempo-sourced metric in the target platform.                       | All 12 metrics validated within tolerance and independently QA'd.                           |
| Phase 4   | Tool & Integration Migration                 | WS-05, WS-06    | Re-point all adjacent toolchain integrations and retire Tempo.                               | Every integration re-pointed and signed off; time-tracking live in the target platform.     |
| Phase 5   | User Training & Change Management            | WS-07           | Get every engineering user trained, supported and ready to work in the target platform.      | Training completed, champion network active, support model live.                            |
| Phase 6   | Parallel Run & Validation                    | WS-08           | Prove parity between JIRA/Tempo and the target platform under live conditions.               | Minimum 4-sprint parallel run completed with formal go/no-go sign-off.                      |
| Phase 7   | JIRA Read-Only Transition                    | WS-09           | Freeze JIRA/Tempo as a read-only historical archive.                                         | Read-only cut-over completed with a 2-week stabilisation period showing no critical issues. |
| Phase 8   | Final JIRA Decommissioning                   | WS-10           | Formally close licences, archive data and close the programme.                               | Licences terminated, compliant archive in place, retrospective published, programme closed. |

# Dependencies

* Target platform (Strawberry Moon/OneStack) licensing, environments and admin access must be provisioned before WS-02 can begin.
* The metric-to-source traceability matrix (WS01-T04) is a hard dependency for all of WS-04 and WS-08.
* Data migration (WS-03) must complete for a project before that project's metrics can be validated (WS-04) or enter parallel run (WS-08).
* Integration re-pointing (WS-05) depends on the legacy-to-new key mapping produced in WS-03.
* Read-only transition (WS-09) cannot begin until parallel run (WS-08) has a formal go decision.
* Final decommissioning (WS-10) depends on the retention position paper (WS01-T06) and a stable read-only period (WS-09).

# Risks and Mitigations

| **Risk**                                                                                                                             | **Impact** | **Likelihood** | **Mitigation**                                                                                                                                      |
| ------------------------------------------------------------------------------------------------------------------------------------ | ---------- | -------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| Metric definitions drift during rebuild, producing numbers that look plausible but are not equivalent to the JIRA-sourced originals. | High       | Medium         | Mandatory metric-to-source traceability matrix (WS01-T04) and independent QA sign-off (WS04-T09) before any metric is treated as live.              |
| Historical data loss or corruption during migration (issues, worklogs, attachments).                                                 | High       | Medium         | Pilot migration on a representative project, full reconciliation report and sign-off per squad before proceeding to full migration.                 |
| Third-party integrations (Sonarqube, Harness, ServiceNow, security tooling) break silently when JIRA is retired.                     | High       | Medium         | Complete integration inventory up front, staged re-pointing with owner sign-off, and validation during parallel run before credentials are revoked. |
| User resistance or productivity dip from squads used to JIRA's established muscle memory.                                            | Medium     | High           | Early champion network, hands-on training, and a visible support channel through parallel run.                                                      |
| Parallel-run fatigue: squads dual-logging in JIRA and the target platform lose discipline, corrupting the validation data.           | Medium     | Medium         | Keep parallel run to the minimum viable duration (4 sprints), automate reconciliation where possible, and escalate non-compliance early.            |
| Licensing overlap costs from running JIRA/Tempo and Strawberry Moon/OneStack concurrently for longer than planned.                   | Medium     | Medium         | Fix a contractual notice-period-aware decommission date in WS-01 and track parallel-run duration against it weekly.                                 |
| Compliance/audit retention requirements are not fully understood, risking premature data deletion.                                   | High       | Low            | Formal retention position paper (WS01-T06) agreed with Legal/Compliance before any decommissioning step.                                            |
| Read-only cut-over is triggered while open work items still exist in JIRA.                                                           | Medium     | Low            | Mandatory cut-over readiness checklist (WS09-T01) with zero-open-items gate before read-only is applied.                                            |

# Acceptance Criteria by Workstream

Summary acceptance position for each workstream; detailed, story-level acceptance criteria are held in the companion Excel backlog.

| **Workstream**                                                        | **Acceptance Position**                                                                                                                               |
| --------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| WS-01 — Discovery & Current State Assessment                          | Signed-off inventory of all JIRA projects, boards, workflows, custom fields, automation rules and permission schemes. (see backlog for full criteria) |
| WS-02 — Target Platform Foundation Build (Strawberry Moon & OneStack) | Strawberry Moon and OneStack instances are provisioned and configured to mirror the agreed target operating model. (see backlog for full criteria)    |
| WS-03 — Historical Data Migration                                     | Migrated record counts reconcile against source JIRA/Tempo counts within an agreed variance. (see backlog for full criteria)                          |
| WS-04 — Metrics & Reporting Re-platforming                            | All 12 JIRA/Tempo-sourced metrics are live in OneStack/Strawberry Moon dashboards. (see backlog for full criteria)                                    |
| WS-05 — Toolchain & Integration Migration                             | Every integration identified in WS-01 is re-pointed, tested and signed off by its owning team. (see backlog for full criteria)                        |
| WS-06 — Time Tracking Migration (Tempo Decommission)                  | Time-tracking categories (including the dedicated L\&D/BUD code) are replicated in the target platform. (see backlog for full criteria)               |
| WS-07 — User Training & Change Management                             | A communications and training plan is delivered against all impacted user groups. (see backlog for full criteria)                                     |
| WS-08 — Parallel Run & Validation                                     | A minimum 4-sprint parallel run is completed across all in-scope squads. (see backlog for full criteria)                                              |
| WS-09 — JIRA Read-Only Transition                                     | JIRA and Tempo are set to read-only for all users with no further write access. (see backlog for full criteria)                                       |
| WS-10 — Final Decommissioning & Closeout                              | JIRA and Tempo licences are terminated or downsized in line with the retention decision from WS-01. (see backlog for full criteria)                   |

# Implementation Roadmap and Prioritisation

The recommended sequencing prioritises discovery and metric traceability first (the highest-risk unknowns), followed by data migration and metrics rebuild, then integration and time-tracking migration in parallel, training running continuously from Phase 1 onward, and a conservative minimum four-sprint parallel run before any read-only or decommissioning step. Actual calendar dates should be calibrated to the organisation's sprint cadence and change-freeze windows (for example, avoiding cut-over during year-end reporting).

| **Sequence** | **Phase**                                              | **Priority** | **Key Dependency Gate**                                      |
| ------------ | ------------------------------------------------------ | ------------ | ------------------------------------------------------------ |
| 1            | Phase 1 — Current State Assessment & Target Foundation | P1           | None — starts immediately                                    |
| 2            | Phase 2 — Data Migration                               | P1           | Target platform foundation built (Phase 1 exit)              |
| 3            | Phase 3 — Reporting & Metrics Transition               | P1           | Data migration substantially complete per project            |
| 4            | Phase 4 — Tool & Integration Migration                 | P1/P2        | Legacy-to-new key mapping available (WS-03)                  |
| 5            | Phase 5 — User Training & Change Management            | P1           | Runs continuously from Phase 1; intensifies ahead of Phase 6 |
| 6            | Phase 6 — Parallel Run & Validation                    | P1           | Phases 2-4 complete for in-scope squads                      |
| 7            | Phase 7 — JIRA Read-Only Transition                    | P1           | Formal go decision from Phase 6                              |
| 8            | Phase 8 — Final JIRA Decommissioning                   | P2           | Stable read-only period; retention sign-off                  |

# Governance and Ownership

A steering group comprising the CTO office, Engineering leadership, the Engineering Platform Team lead, the Metrics & Analytics lead and PMO should meet at each phase-exit gate to review readiness against the exit criteria above and formally approve progression to the next phase. Workstream owners are named against each Feature; individual Story/Task owners are named in the companion Excel backlog for direct assignment in OneStack.