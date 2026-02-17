# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 78%  
**Total Agents Compared:** 1

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI SSIS Design Pattern JSON | 78% | Medium | Model changed (gpt-4o to gpt-4.1), role/goal/backstory removed, maxExecutionTime added | Validate runtime behavior and confirm instruction field removal |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_SSIS_Design_Pattern_JSON  
**Workflow Name (AAVA 2.0):** DI SSIS Design Pattern JSON

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 3324 | id | 1973 | Renamed + Modified | Field renamed and value changed | High | Update references to new workflow ID |
| Naming | name | DI_SSIS_Design_Pattern_JSON | name | DI SSIS Design Pattern JSON | Matched (Normalized) | Minor spacing difference | Low | No change |
| Description | description | SSIS Design Pattern Analysis | description | SSIS Design Pattern Analysis | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-06-23T05:52:15.734+00:00 | createdAt | 2025-11-05T10:42:16.575659 | Modified | Creation timestamp changed | Medium | Validate audit trail |
| Agents List | pipeLineAgents | [1 agent] | workflowAgents | [1 agent] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure changed | Medium | Align configuration structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Update memory configuration access |
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
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | elansuriyaa.p@ascendion.com | Medium | Ensure approval workflow is handled |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification audit trail |
| approvedAt | Approval timestamp | 2025-11-05T10:42:17.766215 | Medium | Ensure approval audit trail |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure deletion handling |
| parentId | Parent workflow reference | -1 | Low | Validate parent-child relationships |
| realmId | Realm identifier | 32 | Low | Validate realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | callbacks: [] | workflowConfigs: {managerLlm: [{}], enableAgenticMemory: false} | Medium | Align configuration structure |
| managerLlm | Not available | Present (empty object) | Medium | Configure manager LLM settings |
| enableAgenticMemory | Top-level field | Nested in workflowConfigs | Medium | Update memory configuration access |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 1  
**AAVA 2.0 total agents:** 1  
**Coverage:** Same agent count

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_SSIS_Design_Pattern_JSON | DI SSIS Design Pattern JSON | Renamed | Spacing normalized |

---

## 6. Agent Configuration Differences

## Agent: DI SSIS Design Pattern JSON

---

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Values match (normalized) |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Medium | Validate null vs 0 behavior |
| maxRpm | 0 | null | Medium | Validate null vs 0 behavior |
| maxExecutionTime | 0 | 90 | High | Execution timeout added |

---

### 6.1.3 Tools Comparison

**Not Available** - No tools configured in either version.

---

### 6.1.4 Knowledge Base Comparison

**Not Available** - No knowledge base configuration in either version.

---

### 6.1.5 Guardrails Comparison

**Not Available** - No guardrails configuration in either version.