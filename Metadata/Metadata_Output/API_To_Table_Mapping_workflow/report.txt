# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

# 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 73%
**Total Agents Compared:** 2

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| API To Table Mapping | 76% | Medium | role/goal/backstory removed, description matched, LLM configs matched | Validate instruction field removal impact |
| API To Table Mapping Reviewer | 70% | Medium | role/goal/backstory removed, description matched, expectedOutput removed | Validate instruction field removal and output format changes |

---

# 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** API_To_Table_Mapping_workflow
**Workflow Name (AAVA 2.0):** API To Table Mapping workflow

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 5361 | id | 1208 | Renamed + Modified | Field renamed and ID value changed | High | Update all references to use new workflow ID |
| Naming | name | API_To_Table_Mapping_workflow | name | API To Table Mapping workflow | Matched (Normalized) | Minor formatting differences in naming | Low | No change needed |
| Description | description | **Analyze the API Payload:**... | description | **Analyze the API Payload:**... | Matched | Description content identical | Low | No change needed |
| Audit | createdAt | 2025-07-18T03:20:25.217+00:00 | createdAt | 2025-11-05T10:08:32.943097 | Modified | Creation timestamp changed | Medium | Validate audit trail continuity |
| Agents List | pipeLineAgents | Array[2] | workflowAgents | Array[2] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update code references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Enhanced configuration structure | High | Implement new config handling |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Update memory configuration access |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm org context handling |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Update org reference logic |
| Domain | domain | AI Engineering | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm domain context handling |
| Domain ID | domainId | 102 | Not Available | Not Available | Removed | Domain ID removed | Medium | Update domain reference logic |
| Project | project | AI Engg Agents | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm project context handling |
| Project ID | projectId | 103 | Not Available | Not Available | Removed | Project ID removed | Medium | Update project reference logic |
| Team | team | AI and Data Science | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm team context handling |
| Team ID | teamId | 104 | Not Available | Not Available | Removed | Team ID removed | Medium | Update team reference logic |
| Level ID | levelId | 104 | Not Available | Not Available | Removed | Level ID removed | Medium | Update level reference logic |

---

# 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | oral.fredric@ascendion.com | Medium | Implement user tracking |
| modifiedBy | User who last modified | oral.fredric@ascendion.com | Medium | Implement modification tracking |
| approvedBy | User who approved workflow | oral.fredric@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Implement change tracking |
| approvedAt | Approval timestamp | 2025-11-05T10:08:34.161793 | Medium | Implement approval tracking |
| status | Workflow approval state | APPROVED | High | Implement workflow lifecycle |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete logic |
| parentId | Parent workflow reference | -1 | Medium | Implement workflow versioning |
| realmId | Realm/tenant identifier | 32 | High | Implement multi-tenancy |

---

# 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | High | Implement new config structure |
| managerLlm | Not available | Empty object array | Medium | Configure manager LLM settings |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update memory config access path |

---

# 5. Agent Inventory Summary

## 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 2
**AAVA 2.0 total agents:** 2
**Coverage:** Same agent count with structural changes

## 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| API_To_Table_Mapping | API To Table Mapping | Renamed | Underscore to space conversion |
| API_To_Table_Mapping_Reviewer | API To Table Mapping Reviewer | Renamed | Underscore to space conversion |

---

# 6. Agent Configuration Differences

## Agent: API To Table Mapping

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
| model | gpt-4 | model | High | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision difference acceptable |
| topP | 0.949999988079071 | 0.94 | Low | Precision difference acceptable |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 3 | null | Medium | Validate null iteration limit |
| maxRpm | 0 | null | Low | No functional change |
| maxExecutionTime | 0 | 90 | Medium | Validate new timeout setting |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

---

## 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | [] | Not Available | Medium | Confirm userTools removal |
| toolReferences | Not Available | [] | Medium | Validate new tool reference structure |

---

## 6.1.4 Knowledge Base Comparison

Not Available

---

## 6.1.5 Guardrails Comparison

Not Available

---

## Agent: API To Table Mapping Reviewer

---

## 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

## 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision difference acceptable |
| topP | 0.949999988079071 | 0.94 | Low | Precision difference acceptable |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 3 | null | Medium | Validate null iteration limit |
| maxRpm | 0 | null | Low | No functional change |
| maxExecutionTime | 0 | 90 | Medium | Validate new timeout setting |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

---

## 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | [] | Not Available | Medium | Confirm userTools removal |
| toolReferences | Not Available | [] | Medium | Validate new tool reference structure |

---

## 6.2.4 Knowledge Base Comparison

Not Available

---

## 6.2.5 Guardrails Comparison

Not Available