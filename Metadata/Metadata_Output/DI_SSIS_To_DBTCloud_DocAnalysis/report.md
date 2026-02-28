# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 68%**
**Total Agents Compared: 3**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_SSIS_Documentation | 0% | High Risk | Agent completely removed from AAVA 2.0 | Confirm removal is acceptable or add missing agent |
| DI SSIS To DBTCloud Analyzer | 85% | Medium Risk | role/goal/backstory removed, maxIter/maxRpm nullified | Validate instruction field removal, confirm runtime parameter changes |
| DI SSIS To DBTCloud Plan | 85% | Medium Risk | role/goal/backstory removed, maxIter/maxRpm nullified | Validate instruction field removal, confirm runtime parameter changes |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_SSIS_To_DBTCloud_Doc&Analysis
**Workflow Name (AAVA 2.0):** DI SSIS To DBTCloud Doc&Analysis

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 5007 | id | 2036 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_SSIS_To_DBTCloud_Doc&Analysis | name | DI SSIS To DBTCloud Doc&Analysis | Matched (Normalized) | Minor formatting difference in name | Low | No change |
| Description | description | SSIS Package Documentation, Analyzer and Plan | description | SSIS Package Documentation, Analyzer and Plan | Matched | Identical values | Low | No change |
| Audit | createdAt | 2025-07-07T16:56:13.170+00:00 | createdAt | 2025-11-05T10:44:42.361949 | Modified | Creation timestamp changed | Medium | Validate audit trail |
| Agents List | pipeLineAgents | 3 agents | workflowAgents | 2 agents | Renamed + Modified | Field renamed and agent count reduced | High | Validate agent removal |
| Workflow Config | callbacks | [] | workflowConfigs | Present with managerLlm | Renamed + Modified | Field renamed and structure changed | Medium | Align configuration structure |
| Memory Config | enableAgenticMemory | false | enableAgenticMemory | false | Matched | Same value in workflowConfigs | Low | No change |
| Org/Domain/Project | org/orgId/domain/domainId/project/projectId/team/teamId/levelId | Present | Not Available | Not Available | Removed | Organizational metadata removed | High | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | kiran.krishnakumar@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | kiran.krishnakumar@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | kiran.krishnakumar@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T10:44:43.451935 | Medium | Ensure approval workflow is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete functionality is implemented |
| parentId | Parent workflow reference | -1 | Low | Validate parent-child relationships |
| realmId | Realm identifier | 32 | Medium | Ensure realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm structure | Medium | Align configuration defaults |
| managerLlm | Not available | Empty object in workflowConfigs | Medium | Configure manager LLM settings |
| enableAgenticMemory | Root level field | Nested in workflowConfigs | Low | Update configuration access path |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 2
**Coverage:** 1 agent removed, 2 agents retained with modifications

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_SSIS_Documentation | Not Available | Removed | First agent completely removed |
| DI_SSIS_To_DBTCloud_Analyzer | DI SSIS To DBTCloud Analyzer | Renamed | Naming convention updated |
| DI_SSIS_To_DBTCloud_Plan | DI SSIS To DBTCloud Plan | Renamed | Naming convention updated |

---

## 6. Agent Configuration Differences

## Agent: DI_SSIS_Documentation

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Confirm removal is acceptable |
| goal | Present | Not Available | High | Confirm removal is acceptable |
| backstory | Present | Not Available | High | Confirm removal is acceptable |
| description | Present | Not Available | High | Confirm removal is acceptable |
| expectedOutput | Present | Not Available | High | Confirm removal is acceptable |

### 6.1.2 LLM Configuration Comparison

**Not Available** - Agent completely removed from AAVA 2.0

### 6.1.3 Tools Comparison

**Not Available** - Agent completely removed from AAVA 2.0

### 6.1.4 Knowledge Base Comparison

**Not Available** - Agent completely removed from AAVA 2.0

### 6.1.5 Guardrails Comparison

**Not Available** - Agent completely removed from AAVA 2.0

---

## Agent: DI SSIS To DBTCloud Analyzer

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Confirm removal is acceptable |
| goal | Present | Not Available | High | Confirm removal is acceptable |
| backstory | Present | Not Available | High | Confirm removal is acceptable |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.20000000298023224 | 0.2 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 30 | null | Medium | Validate runtime parameter change |
| maxRpm | 0 | null | Medium | Validate runtime parameter change |
| maxExecutionTime | 300 | 90 | Medium | Validate timeout reduction |

### 6.2.3 Tools Comparison

**Not Available** - No tools configured in either version

### 6.2.4 Knowledge Base Comparison

**Not Available** - No knowledge base configured in either version

### 6.2.5 Guardrails Comparison

**Not Available** - No guardrails configured in either version

---

## Agent: DI SSIS To DBTCloud Plan

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Confirm removal is acceptable |
| goal | Present | Not Available | High | Confirm removal is acceptable |
| backstory | Present | Not Available | High | Confirm removal is acceptable |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.20000000298023224 | 0.2 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 30 | null | Medium | Validate runtime parameter change |
| maxRpm | 0 | null | Medium | Validate runtime parameter change |
| maxExecutionTime | 300 | 90 | Medium | Validate timeout reduction |

### 6.3.3 Tools Comparison

**Not Available** - No tools configured in either version

### 6.3.4 Knowledge Base Comparison

**Not Available** - No knowledge base configured in either version

### 6.3.5 Guardrails Comparison

**Not Available** - No guardrails configured in either version