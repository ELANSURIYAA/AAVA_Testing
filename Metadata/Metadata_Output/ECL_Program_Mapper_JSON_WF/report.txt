# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 82%
**Total Agents Compared:** 1

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI ECL Program Mapper JSON | 82% | Medium | Agent name normalized, modelDeploymentName changed from gpt-4o to gpt-4.1, role/goal/backstory removed, maxExecutionTime added | Validate model performance differences, confirm instruction field removal acceptable |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** ECL_Program_Mapper_JSON_WF
**Workflow Name (AAVA 2.0):** ECL Program Mapper JSON WF

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1600 | id | 1817 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to new workflow ID |
| Naming | name | ECL_Program_Mapper_JSON_WF | name | ECL Program Mapper JSON WF | Matched (Normalized) | Naming convention updated with spaces | Low | No change needed |
| Description | description | ECL Program Mapper Workflow | description | ECL Program Mapper Workflow | Matched | Same description maintained | Low | No change |
| Audit | createdAt | 2025-04-25T05:35:43.573+00:00 | createdAt | 2025-11-05T10:36:12.407991 | Matched | Different creation timestamps | Low | Expected for new workflow version |
| Agents List | pipeLineAgents | [1 agent] | workflowAgents | [1 agent] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {"managerLlm":[{}],"enableAgenticMemory":false} | Renamed + Modified | Enhanced configuration structure | Medium | Validate new configuration options |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Low | Check workflowConfigs.enableAgenticMemory |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Ensure org tracking handled elsewhere |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Ensure org ID tracking handled elsewhere |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Ensure domain tracking handled elsewhere |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Ensure domain ID tracking handled elsewhere |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Ensure project tracking handled elsewhere |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Medium | Ensure project ID tracking handled elsewhere |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Medium | Ensure team tracking handled elsewhere |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Medium | Ensure team ID tracking handled elsewhere |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Low | Check if moved to agent level |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | elansuriyaa.p@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T10:36:13.609454 | Low | Standard audit field |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Standard deletion handling |
| parentId | Parent workflow reference | -1 | Low | Workflow versioning support |
| realmId | Realm/tenant identifier | 32 | Medium | Ensure multi-tenancy is handled |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | callbacks: [] | workflowConfigs: {"managerLlm":[{}],"enableAgenticMemory":false} | Medium | Validate new configuration structure |
| managerLlm | Not Available | Present (empty object) | Medium | Configure manager LLM if needed |
| enableAgenticMemory | Top-level: false | Nested in workflowConfigs: false | Low | Update configuration access path |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 1
**AAVA 2.0 total agents:** 1
**Coverage:** Same agent count maintained

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_ECL_Program_Mapper_JSON | DI ECL Program Mapper JSON | Renamed | Naming convention updated with spaces |

---

## 6. Agent Configuration Differences

## Agent: DI ECL Program Mapper JSON

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
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model performance differences |
| model | gpt-4o | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change |
| maxToken | 4000 | 4000 | Matched | No change |
| maxIter | 0 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 0 | 90 | Modified | Validate timeout configuration |
| allowDelegation | true | true | Matched | No change |
| allowCodeExecution | false | false | Matched | No change |
| isSafeCodeExecution | true | true | Matched | No change |

---

## 6.1.3 Tools Comparison

Not Available

---

## 6.1.4 Knowledge Base Comparison

Not Available

---

## 6.1.5 Guardrails Comparison

Not Available