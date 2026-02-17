# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 72%
**Total Agents Compared:** 1

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI ECL Consolidated Design Pattern JSON | 72% | Medium | model changed (gpt-4o to gpt-4.1), maxToken changed (4000 to string), role/goal/backstory removed | Validate runtime behavior and confirm instruction field removal |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_ECL_Consolidated_Design_Pattern_JSON_WF
**Workflow Name (AAVA 2.0):** DI ECL Consolidated Design Pattern JSON WF

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1603 | id | 1816 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new ID |
| Naming | name | DI_ECL_Consolidated_Design_Pattern_JSON_WF | name | DI ECL Consolidated Design Pattern JSON WF | Matched (Normalized) | Name formatting normalized | Low | No change |
| Description | description | Give ECL Consolidated Design Pattern JSON format | description | Give ECL Consolidated Design Pattern JSON format | Matched | Values identical | Low | No change |
| Audit | createdAt | 2025-04-25T05:35:00.058+00:00 | createdAt | 2025-11-05T10:36:09.986844 | Modified | Creation timestamp changed | Low | Expected for new workflow version |
| Agents List | pipeLineAgents | [1 agent] | workflowAgents | [1 agent] | Renamed + Matched (Normalized) | Field renamed, agent count same | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure changed | Medium | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Update memory configuration location |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Confirm removal is acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | High | Confirm removal is acceptable |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | High | Confirm removal is acceptable |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | High | Confirm removal is acceptable |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | High | Confirm removal is acceptable |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | High | Confirm removal is acceptable |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | High | Confirm removal is acceptable |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | High | Confirm removal is acceptable |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | elansuriyaa.p@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T10:36:11.116899 | Medium | Ensure approval process is configured |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Standard deletion handling |
| parentId | Parent workflow reference | -1 | Medium | Understand workflow hierarchy |
| realmId | Realm identifier | 32 | Medium | Ensure realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Configure new workflow settings |
| managerLlm | Not available | Empty object [{}] | Medium | Configure manager LLM settings |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update memory configuration location |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 1
**AAVA 2.0 total agents:** 1
**Coverage:** Same agent count

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_ECL_Consolidated_Design_Pattern_JSON | DI ECL Consolidated Design Pattern JSON | Renamed | Naming convention updated (underscores to spaces) |

---

## 6. Agent Configuration Differences

## Agent: DI ECL Consolidated Design Pattern JSON

---

## 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

## 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility and performance |
| model | gpt-4o | model | High | Validate model name change impact |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change |
| maxToken | 4000 | 4000 | Matched (Normalized) | No change |
| maxIter | 0 | Not Present | Medium | Confirm default behavior |
| maxRpm | 0 | Not Present | Medium | Confirm default behavior |
| maxExecutionTime | 0 | 90 | Modified | Validate timeout configuration |
| allowDelegation | true | true | Matched | No change |
| allowCodeExecution | false | false | Matched | No change |
| isSafeCodeExecution | true | true | Matched | No change |

---

## 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Matched | No change |
| userTools | [] | Not Present | Medium | Confirm userTools removal |

---

## 6.1.4 Knowledge Base Comparison

Not Available

---

## 6.1.5 Guardrails Comparison

Not Available