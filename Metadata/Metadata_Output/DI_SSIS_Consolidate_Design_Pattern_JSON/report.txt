# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 76%
**Total Agents Compared:** 1

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI SSIS Consolidate Design Pattern JSON | 76% | Medium | modelDeploymentName changed, role/goal/backstory removed, maxToken modified | Validate model behavior and confirm instruction field removal |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_SSIS_Consolidate_Design_Pattern_JSON
**Workflow Name (AAVA 2.0):** DI SSIS Consolidate Design Pattern JSON

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 3327 | id | 1976 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_SSIS_Consolidate_Design_Pattern_JSON | name | DI SSIS Consolidate Design Pattern JSON | Matched (Normalized) | Minor spacing differences normalized | Low | No change |
| Description | description | 
DI_SSIS_Consolidate_Design_Pattern_JSON | description | 
DI_SSIS_Consolidate_Design_Pattern_JSON | Matched | Values identical | Low | No change |
| Audit | createdAt | 2025-06-23T06:05:22.435+00:00 | createdAt | 2025-11-05T10:42:23.546531 | Matched | Field present in both, values differ by timestamp | Low | No change |
| Agents List | pipeLineAgents | [1 agent] | workflowAgents | [1 agent] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure changed | High | Align configuration structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Confirm removal is acceptable |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm removal is acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm removal is acceptable |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal is acceptable |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm removal is acceptable |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal is acceptable |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm removal is acceptable |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm removal is acceptable |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm removal is acceptable |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who modified workflow | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | elansuriyaa.p@ascendion.com | Medium | Ensure approval workflow is handled |
| modifiedAt | Modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T10:42:24.752691 | Low | Standard audit field |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure deletion handling is implemented |
| parentId | Parent workflow reference | -1 | Low | Standard hierarchy field |
| realmId | Realm identifier | 32 | Medium | Ensure realm context is handled |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | callbacks: [] | managerLlm: [{}], enableAgenticMemory: false | High | Align configuration structure and validate manager LLM settings |
| enableAgenticMemory | Top-level field: false | Nested in workflowConfigs: false | Medium | Update configuration access patterns |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 1
**AAVA 2.0 total agents:** 1
**Coverage:** Same agent count

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_SSIS_Consolidate_Design_Pattern_JSON | DI SSIS Consolidate Design Pattern JSON | Matched (Normalized) | Spacing differences normalized |

---

## 6. Agent Configuration Differences

## Agent: DI SSIS Consolidate Design Pattern JSON

---

## 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

## 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | anthropic.claude-3-7-sonnet | gpt-4.1 | High | Validate model behavior change |
| model | claude-3.7sonnet | model | High | Validate model behavior change |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Confirm removal is acceptable |
| maxRpm | 0 | Not Present | Medium | Confirm removal is acceptable |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout behavior change |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

---

## 6.1.3 Tools Comparison

Not Available

---

## 6.1.4 Knowledge Base Comparison

Not Available

---

## 6.1.5 Guardrails Comparison

Not Available