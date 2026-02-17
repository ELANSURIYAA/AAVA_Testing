# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 78%**
**Total Agents Compared: 3**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI SAS Documentation | 85% | Medium | Model changed from gemini-2.5-pro to gpt-4.1; role/goal/backstory removed; name normalized | Validate model behavior and confirm instruction field removal |
| DI SAS To PySpark Analyzer | 78% | Medium | Model deployment matched; role/goal/backstory removed; temperature matched | Confirm removal of instruction fields is acceptable |
| DI SAS To PySpark Plan | 71% | Medium | Model deployment matched; role/goal/backstory removed; temperature matched | Confirm removal of instruction fields is acceptable |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_SAS_To_PySpark_Doc&Analyze
**Workflow Name (AAVA 2.0):** DI SAS To PySpark Doc&Analyze

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 587 | id | 2627 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_SAS_To_PySpark_Doc&Analyze | name | DI SAS To PySpark Doc&Analyze | Matched (Normalized) | Minor formatting differences in name | Low | No change |
| Description | description | SAS to PySpark Documentation, Analysis and Planning | description | SAS to PySpark Documentation, Analysis and Planning | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-10-10T09:23:24.901+00:00 | createdAt | 2025-11-05T11:09:11.322885 | Matched | Field exists in both versions | Medium | Validate timestamp differences |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed but agent count preserved | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure changed | High | Align configuration structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field removed in AAVA 2.0 | Medium | Confirm removal is acceptable |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | Medium | Confirm removal is acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organizational ID removed | Medium | Confirm removal is acceptable |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal is acceptable |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm removal is acceptable |
| Project | project | Documenting | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal is acceptable |
| Project ID | projectId | 153 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm removal is acceptable |
| Team | team | DataEng | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm removal is acceptable |
| Team ID | teamId | 154 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm removal is acceptable |
| Level ID | levelId | 154 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | karthikeyan.iyappan@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified | karthikeyan.iyappan@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | karthikeyan.iyappan@ascendion.com | Medium | Ensure approval workflow is handled |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T11:09:12.400186 | Medium | Ensure approval workflow is handled |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure deletion handling is implemented |
| parentId | Parent workflow reference | -1 | Low | Understand workflow hierarchy |
| realmId | Realm identifier | 1 | Low | Understand realm-based access |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | callbacks: [] | managerLlm: [{}], enableAgenticMemory: false | High | Align configuration structure and validate manager LLM setup |
| enableAgenticMemory | Direct field: false | Nested in workflowConfigs: false | Medium | Update configuration access patterns |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agent count maintained

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_SAS_Documentation | DI SAS Documentation | Renamed | Underscore replaced with space |
| DI_SAS_To_PySpark_Analyzer | DI SAS To PySpark Analyzer | Renamed | Underscores replaced with spaces |
| DI_SAS_To_PySpark_Plan | DI SAS To PySpark Plan | Renamed | Underscores replaced with spaces |

---

## 6. Agent Configuration Differences

## Agent: DI SAS Documentation

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model behavior differences |
| model | gemini-2.5-pro | model | High | Validate model configuration |
| temperature | 0.20000000298023224 | 0.2 | Matched (Normalized) | No change |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change |
| maxToken | 64000 | 64000 | Matched | No change |
| maxIter | 0 | Not Present | Medium | Confirm field removal is acceptable |
| maxRpm | 0 | Not Present | Medium | Confirm field removal is acceptable |
| maxExecutionTime | 0 | 90 | Modified | Validate timeout configuration |
| allowDelegation | false | false | Matched | No change |
| allowCodeExecution | false | false | Matched | No change |
| isSafeCodeExecution | true | true | Matched | No change |

### 6.1.3 Tools Comparison

**Not Available** - No tools configured in either version.

### 6.1.4 Knowledge Base Comparison

**Not Available** - No knowledge base configuration in either version.

### 6.1.5 Guardrails Comparison

**Not Available** - No guardrails configuration in either version.

---

## Agent: DI SAS To PySpark Analyzer

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Matched | No change |
| model | gpt-4 | model | Modified | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change |
| maxToken | 8000 | 8000 | Matched | No change |
| maxIter | 0 | Not Present | Medium | Confirm field removal is acceptable |
| maxRpm | 0 | Not Present | Medium | Confirm field removal is acceptable |
| maxExecutionTime | 0 | 90 | Modified | Validate timeout configuration |
| allowDelegation | true | true | Matched | No change |
| allowCodeExecution | false | false | Matched | No change |
| isSafeCodeExecution | true | true | Matched | No change |

### 6.2.3 Tools Comparison

**Not Available** - No tools configured in either version.

### 6.2.4 Knowledge Base Comparison

**Not Available** - No knowledge base configuration in either version.

### 6.2.5 Guardrails Comparison

**Not Available** - No guardrails configuration in either version.

---

## Agent: DI SAS To PySpark Plan

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Matched | No change |
| model | gpt-4 | model | Modified | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change |
| maxToken | 8000 | 8000 | Matched | No change |
| maxIter | 0 | Not Present | Medium | Confirm field removal is acceptable |
| maxRpm | 0 | Not Present | Medium | Confirm field removal is acceptable |
| maxExecutionTime | 0 | 90 | Modified | Validate timeout configuration |
| allowDelegation | true | true | Matched | No change |
| allowCodeExecution | false | false | Matched | No change |
| isSafeCodeExecution | true | true | Matched | No change |

### 6.3.3 Tools Comparison

**Not Available** - No tools configured in either version.

### 6.3.4 Knowledge Base Comparison

**Not Available** - No knowledge base configuration in either version.

### 6.3.5 Guardrails Comparison

**Not Available** - No guardrails configuration in either version.