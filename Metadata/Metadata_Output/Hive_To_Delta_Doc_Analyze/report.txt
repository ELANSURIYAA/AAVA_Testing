# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 82.3%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| Hive to Delta Documentation | 85.7% | Medium | Model deployment changed gpt-4o to gpt-4.1; role/goal/backstory removed; description matched | Validate model compatibility and confirm instruction field removal |
| Hive to Delta Analyser | 82.1% | Medium | Model deployment changed gpt-4o to gpt-4.1; role/goal/backstory removed; description matched | Validate model compatibility and confirm instruction field removal |
| Hive to Delta Plan | 79.2% | Medium | Model deployment changed gpt-4o to gpt-4.1; role/goal/backstory removed; description matched | Validate model compatibility and confirm instruction field removal |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** Hive_To_Delta_Doc_&_Analyze
**Workflow Name (AAVA 2.0):** Hive To Delta Doc & Analyze

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1081 | id | 3788 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to new workflow ID |
| Naming | name | Hive_To_Delta_Doc_&_Analyze | name | Hive To Delta Doc & Analyze | Matched (Normalized) | Minor formatting differences in name | Low | No change |
| Description | description | Hive_To_Delta_Doc_&_Analyze | description | Hive_To_Delta_Doc_&_Analyze | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-03-14T09:38:27.469+00:00 | createdAt | 2025-11-05T11:42:24.973339 | Matched | Field present in both, different timestamps | Low | No change |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure changed | Medium | Migrate callback configurations |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Low | No change needed |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | Medium | Confirm org tracking not needed |
| Domain Metadata | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm domain tracking not needed |
| Project Metadata | project | AVA | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm project tracking not needed |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User tracking | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | Change tracking | default@ascendion.com | Medium | Implement modification tracking |
| approvedBy | Approval workflow | default@ascendion.com | Medium | Set up approval processes |
| modifiedAt | Timestamp tracking | 2025-12-03T15:03:31.224436 | Low | Automatic timestamp handling |
| approvedAt | Approval timestamp | 2025-11-05T11:42:26.033580 | Low | Automatic approval tracking |
| status | Workflow state | APPROVED | High | Implement workflow lifecycle management |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete functionality |
| parentId | Hierarchy tracking | -1 | Low | Handle workflow relationships |
| realmId | Multi-tenancy | 1 | Medium | Implement realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|---------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Migrate to new configuration structure |
| managerLlm | Not available | Empty object [{}] | Medium | Configure manager LLM settings |
| enableAgenticMemory | Top-level field (false) | Nested in workflowConfigs (false) | Low | Update configuration path |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents with structural changes

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| Hive to Delta Documentation | Hive to Delta Documentation | Matched | Exact name match |
| Hive to Delta Analyser | Hive to Delta Analyser | Matched | Exact name match |
| Hive to Delta Plan | Hive to Delta Plan | Matched | Exact name match |

---

## 6. Agent Configuration Differences

## Agent: Hive to Delta Documentation

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
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Confirm iteration handling |
| maxRpm | 0 | Not Present | Medium | Confirm rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: Hive to Delta Analyser

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
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Confirm iteration handling |
| maxRpm | 0 | Not Present | Medium | Confirm rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: Hive to Delta Plan

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
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Confirm iteration handling |
| maxRpm | 0 | Not Present | Medium | Confirm rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available