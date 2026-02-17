# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 76.2%**
**Total Agents Compared: 3**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI SSIS Documentation | 88.5% | Low | Model configs matched, description matched, role/goal/backstory removed | Validate instruction field removal impact |
| DI SSIS to PySpark Analyzer | 72.3% | Medium | Model configs matched, maxIter removed, expectedOutput field missing | Add missing runtime configs and validate output format |
| DI SSIS to PySpark Plan | 68.0% | Medium | Model configs matched, maxIter removed, expectedOutput field missing | Add missing runtime configs and validate output format |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_SSIS_to_PySpark_Doc&Analyze
**Workflow Name (AAVA 2.0):** DI SSIS to PySpark Doc&Analyze

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 960 | id | 2625 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_SSIS_to_PySpark_Doc&Analyze | name | DI SSIS to PySpark Doc&Analyze | Matched (Normalized) | Minor formatting differences | Low | No change |
| Description | description | Analyzing and Documenting the SSIS code | description | Analyzing and Documenting the SSIS code | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-07-02T04:10:07.099+00:00 | createdAt | 2025-11-05T11:09:05.578669 | Modified | Different creation timestamps | Low | No change |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure changed | Medium | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Low | Update memory configuration location |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm org metadata handling |
| Domain Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm domain metadata handling |
| Project Metadata | project | Documenting | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm project metadata handling |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | elansuriyaa.p@ascendion.com | Medium | Ensure approval workflow is configured |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Automatic timestamp handling |
| approvedAt | Approval timestamp | 2025-11-05T11:09:06.650446 | Low | Automatic timestamp handling |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Ensure deletion handling is configured |
| parentId | Parent workflow reference | -1 | Low | Ensure hierarchy handling if needed |
| realmId | Realm/tenant identifier | 32 | Medium | Ensure multi-tenancy is configured |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Configure workflow-level LLM settings |
| managerLlm | Not available | Empty object {} | Medium | Define manager LLM configuration |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Low | Update memory configuration location |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_SSIS_Documentation | DI SSIS Documentation | Renamed | Underscore to space conversion |
| DI_SSIS_to_PySpark_Analyzer | DI SSIS to PySpark Analyzer | Renamed | Underscore to space conversion |
| DI_SSIS_to_PySpark_Plan | DI SSIS to PySpark Plan | Renamed | Underscore to space conversion |

---

## 6. Agent Configuration Differences

## Agent: DI SSIS Documentation

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | No change |
| topP | 0.949999988079071 | 0.94 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 30 | Not Present | Medium | Add missing runtime config |
| maxRpm | 0 | Not Present | Low | Add missing runtime config |
| maxExecutionTime | 300 | 90 | Medium | Validate timeout change |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: DI SSIS to PySpark Analyzer

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | No change |
| topP | 0.949999988079071 | 0.94 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 15 | Not Present | Medium | Add missing runtime config |
| maxRpm | 0 | Not Present | Low | Add missing runtime config |
| maxExecutionTime | 300 | 90 | Medium | Validate timeout change |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: DI SSIS to PySpark Plan

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Not Present | Not Present | Low | No change |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | No change |
| topP | 0.949999988079071 | 0.94 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 15 | Not Present | Medium | Add missing runtime config |
| maxRpm | 0 | Not Present | Low | Add missing runtime config |
| maxExecutionTime | 300 | 90 | Medium | Validate timeout change |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available