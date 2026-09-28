---
status: Draft
targetDate: 2026-09-30
period: Q3 FY26
tshirt: M
discovery_current_state_assessment: 0
---

# Produce a complete, validated inventory of everything in JIRA and Tempo that must be migrated, replicated or retired, so later workstreams plan against facts rather than assumptions

## Release Information
**Product/Module:** Frontier Toolset (OneStack Roll Out)
**Version:** 1.0

## Headline
Comprehensive JIRA and Tempo Inventory Assessment: The factual foundation for Frontier migration planning.

## Summary
We are conducting a complete, validated inventory of all configurations, workflows, custom fields, integrations, and user data across JIRA and Tempo to establish a single source of truth for the Frontier migration effort. This inventory will document what must be migrated, what can be replicated in new systems, and what should be retired. By replacing assumptions with facts, we enable downstream workstreams to plan against validated data rather than guesswork.

## Problem Statement
Migration initiatives typically fail because teams make decisions based on incomplete or outdated assumptions about existing system content. Without a validated inventory, workstreams duplicate effort discovering what already exists, contradict each other on scope, and make costly re-work decisions mid-project. The longer the inventory remains undone, the longer downstream work remains blocked or speculative.

## Solution
We will conduct a systematic audit of JIRA and Tempo, cataloging every configuration element, workflow state, custom field, automation rule, user permission, integration, and data dependency. The inventory will be validated against live systems, gaps will be resolved, and findings will be documented in a structured format that all downstream workstreams can query and trust. This becomes the shared source of truth for migration decisions.

## Key Features
- Complete configuration audit of JIRA instance (workflows, fields, schemes, permissions, custom apps)
- Complete configuration audit of Tempo instance (time tracking rules, resource management settings, billing integrations)
- Data volume assessment (active users, historical records, attachment sizes)
- Dependency mapping (which systems feed into JIRA/Tempo; which systems consume their output)
- Validated gap resolution (all discrepancies between audit findings and system records resolved)
- Migration categorization (each item tagged as: migrate, replicate, retire, or investigate further)

## Customer Benefits
- Downstream workstreams receive validated, fact-based scope instead of making duplicate discovery efforts
- Migration planning becomes deterministic rather than exploratory, reducing re-work and scope creep
- Blockers and unknowns surface early, allowing proactive mitigation planning
- Executive stakeholders gain confidence in migration feasibility and timeline estimates
- Technical teams avoid mid-project surprises caused by undocumented configurations or data dependencies

## Customer Quote (Imagined)
> "We thought we knew what was in our JIRA

---
> ⚠️ This response was truncated because it exceeded the token limit. Use **Fit to limit** for a complete compressed version, or click **Continue generating** to extend it.