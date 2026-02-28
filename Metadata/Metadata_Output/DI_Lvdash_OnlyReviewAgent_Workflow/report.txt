# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 76%**
**Total Agents Compared: 1**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI Databricks LvdashJson Review Agent | 76% | Medium | role/goal/backstory removed, model changed, maxToken moved, expectedOutput missing | Validate instruction fields removal and runtime behavior |

---

## Workflow Names

**Workflow Name (AAVA 1.0):** DI_Lvdash_OnlyReviewAgent_Workflow
**Workflow Name (AAVA 2.0):** DI Lvdash OnlyReviewAgent Workflow

---

## 2. Workflow-Level Comparison

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 6094 | id | 2112 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_Lvdash_OnlyReviewAgent_Workflow | name | DI Lvdash OnlyReviewAgent Workflow | Matched (Case Normalization) | Minor formatting differences | Low | No change needed |
| Description | description | Reviews the Lvdash.Json File created by Lvdash Generate Agent | description | Reviews the Lvdash.Json File created by Lvdash Generate Agent | Matched | Identical values | Low | No change needed |
| Audit | createdAt | 2025-08-14T04:56:41.969+00:00 | createdAt | 2025-11-05T10:47:34.617114 | Modified | Timestamp changed | Low | Expected for new workflow version |
| Agents List | pipeLineAgents | Present | workflowAgents | Present | Renamed + Matched (Normalized) | Field renamed but structure preserved | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | Present | Renamed + Modified | Field renamed and structure changed | Medium | Align configuration structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Update memory configuration access |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Confirm removal is acceptable |
| Domain Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | High | Confirm removal is acceptable |
| Project Metadata | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | High | Confirm removal is acceptable |
| Team Metadata | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | High | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | sushal.devasari@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | sushal.devasari@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | sushal.devasari@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T10:47:35.821803 | Low | Standard audit field |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Standard deletion handling |
| parentId | Parent workflow reference | -1 | Medium | Understand workflow hierarchy |
| realmId | Realm/tenant identifier | 32 | Medium | Ensure multi-tenancy is handled |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|---------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align configuration structure |
| managerLlm | Not available | Present but empty | Medium | Configure manager LLM if needed |
| enableAgenticMemory | Top-level field | Moved to workflowConfigs | Medium | Update memory configuration access |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 1
**AAVA 2.0 total agents:** 1
**Coverage:** Same agent count

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Databricks_LvdashJson_Review_Agent | DI Databricks LvdashJson Review Agent | Matched (Case Normalization) | Underscore to space conversion |

---

## 6. Agent Configuration Differences

## Agent: DI Databricks LvdashJson Review Agent

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model configuration change |
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Medium | Field moved to agentDetails |
| maxIter | 0 | Not Present | Medium | Validate iteration limit removal |
| maxRpm | 0 | Not Present | Medium | Validate rate limit removal |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout changed |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

---

## 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | toolReferences: [] | Low | Field renamed but empty |
| userTools | [] | toolReferences: [] | Low | Field renamed but empty |

---

## 6.1.4 Knowledge Base Comparison

Not Available

---

## 6.1.5 Guardrails Comparison

Not Available