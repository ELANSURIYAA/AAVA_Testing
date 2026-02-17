# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 78%  
**Total Agents Compared:** 1

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI ECL Design Pattern JSON | 78% | Medium | role/goal/backstory removed, model changed from gpt-4o to model, maxExecutionTime added | Validate agent behavior without role/goal/backstory fields, confirm model compatibility |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_ECL_Design_Pattern_JSON_WF  
**Workflow Name (AAVA 2.0):** DI ECL Design Pattern JSON WF

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1602 | id | 1812 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | DI_ECL_Design_Pattern_JSON_WF | name | DI ECL Design Pattern JSON WF | Matched (Normalized) | Minor formatting differences | Low | No change |
| Description | description | Gives ECL Design Pattern in json format | description | Gives ECL Design Pattern in json format | Matched | Identical values | Low | No change |
| Audit | createdAt | 2025-04-24T18:35:52.127+00:00 | createdAt | 2025-11-05T10:36:02.264145 | Matched | Different timestamps as expected | Low | No change |
| Agents List | pipeLineAgents | [1 agent] | workflowAgents | [1 agent] | Renamed + Matched (Normalized) | Field renamed, same structure | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure changed | Medium | Configure new workflow configs |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Update memory configuration location |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | Medium | Confirm removal is acceptable |
| Domain Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal is acceptable |
| Project Metadata | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal is acceptable |
| Team Metadata | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | elansuriyaa.p@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T10:36:03.568225 | Medium | Ensure approval tracking is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete handling is implemented |
| parentId | Parent workflow reference | -1 | Low | Validate parent-child relationships |
| realmId | Realm identifier | 32 | Medium | Ensure realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Configure manager LLM settings |
| enableAgenticMemory | Top-level field (false) | Nested in workflowConfigs (false) | Medium | Update configuration structure |
| callbacks | Empty array | Not available | Low | Confirm callback removal is acceptable |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 1  
**AAVA 2.0 total agents:** 1  
**Coverage:** Same agent count, agent evolved

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_ECL_Design_Pattern_JSON | DI ECL Design Pattern JSON | Matched (Normalized) | Minor formatting differences |

---

## 6. Agent Configuration Differences

### Agent: DI ECL Design Pattern JSON

#### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

#### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility and performance |
| model | gpt-4o | model | High | Validate model compatibility and performance |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Medium | Validate null vs 0 behavior |
| maxRpm | 0 | null | Medium | Validate null vs 0 behavior |
| maxExecutionTime | 0 | 90 | Medium | Validate new timeout setting |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

#### 6.1.3 Tools Comparison

**Not Available** - No tools configured in either version

#### 6.1.4 Knowledge Base Comparison

**Not Available** - No knowledge base configured in either version

#### 6.1.5 Guardrails Comparison

**Not Available** - No guardrails configured in either version