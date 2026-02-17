# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

# 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 76%**
**Total Agents Compared: 3**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| SqlServer to DBT Documentation | 74% | Medium | Model changed gpt-4o to gpt-4.1, role/goal/backstory removed, description matched | Validate model compatibility and confirm instruction field removal |
| SqlServer to DBT Analyzer | 74% | Medium | Model changed gpt-4o to gpt-4.1, role/goal/backstory removed, description matched | Validate model compatibility and confirm instruction field removal |
| SqlServer to DBT Plan | 74% | Medium | Model changed gpt-4o to gpt-4.1, role/goal/backstory removed, description matched | Validate model compatibility and confirm instruction field removal |

---

# 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** Sqlserver to DBT _Doc&Analyze
**Workflow Name (AAVA 2.0):** Sqlserver to DBT  Doc&Analyze

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1061 | id | 4651 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new workflow ID |
| Naming | name | Sqlserver to DBT _Doc&Analyze | name | Sqlserver to DBT  Doc&Analyze | Matched (Normalized) | Minor spacing difference normalized | Low | No change |
| Description | description | Sql Server to DBT | description | Sql Server to DBT | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-08-18T05:36:33.450+00:00 | createdAt | 2025-11-05T12:09:05.344900 | Matched | Field present in both, values differ by timestamp | Low | No change |
| Agents List | pipeLineAgents | Array[3] | workflowAgents | Array[3] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed with new structure | High | Implement new workflow config structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Verify memory config location |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | Medium | Confirm org metadata deprecation |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organizational ID removed | Medium | Confirm org ID deprecation |
| Domain | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm domain metadata deprecation |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm domain ID deprecation |
| Project | project | AVA | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm project metadata deprecation |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm project ID deprecation |
| Team | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm team metadata deprecation |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm team ID deprecation |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm level ID deprecation |

---

# 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | sharmilee.d@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | sharmilee.d@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | sharmilee.d@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T12:09:06.392898 | Medium | Ensure approval process is handled |
| status | Workflow approval state | APPROVED | High | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete functionality |
| parentId | Parent workflow reference | -1 | Medium | Ensure workflow hierarchy is handled |
| realmId | Realm/tenant identifier | 32 | High | Ensure multi-tenancy is properly configured |

---

# 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | High | Implement new workflow config structure |
| managerLlm | Not available | Empty object {} | Medium | Configure manager LLM settings |
| enableAgenticMemory | Direct field: false | Nested in workflowConfigs: false | Medium | Update memory config access pattern |

---

# 5. Agent Inventory Summary

## 5.1 Agent Count & Coverage

**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents with naming updates

## 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| SqlServer_to_DBT_Documentation | SqlServer to DBT Documentation | Renamed | Underscore to space conversion |
| SqlServer_to_DBT_Analyzer | SqlServer to DBT Analyzer | Renamed | Underscore to space conversion |
| SqlServer_to_DBT_Plan | SqlServer to DBT Plan | Renamed | Underscore to space conversion |

---

# 6. Agent Configuration Differences

## Agent: SqlServer to DBT Documentation

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
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | Null vs zero handling |
| maxRpm | 0 | null | Low | Null vs zero handling |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout changed |

---

## 6.1.3 Tools Comparison

Not Available

---

## 6.1.4 Knowledge Base Comparison

Not Available

---

## 6.1.5 Guardrails Comparison

Not Available

---

## Agent: SqlServer to DBT Analyzer

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
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | Null vs zero handling |
| maxRpm | 0 | null | Low | Null vs zero handling |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout changed |

---

## 6.2.3 Tools Comparison

Not Available

---

## 6.2.4 Knowledge Base Comparison

Not Available

---

## 6.2.5 Guardrails Comparison

Not Available

---

## Agent: SqlServer to DBT Plan

---

## 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

## 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | Null vs zero handling |
| maxRpm | 0 | null | Low | Null vs zero handling |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout changed |

---

## 6.3.3 Tools Comparison

Not Available

---

## 6.3.4 Knowledge Base Comparison

Not Available

---

## 6.3.5 Guardrails Comparison

Not Available