# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 73%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI Oracle Documentation | 68% | Medium | role/goal/backstory removed, model changed, maxToken format changed | Validate instruction field removal, confirm model compatibility |
| DI Oracle to Snowflake Analyzer | 72% | Medium | role/goal/backstory removed, model changed, description masked | Validate instruction field removal, confirm model compatibility |
| DI Oracle to Snowflake Plan | 80% | Medium | role/goal/backstory removed, model changed, description preserved | Validate instruction field removal, confirm model compatibility |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_Oracle_to_SF_Doc&Analyze
**Workflow Name (AAVA 2.0):** DI Oracle to SF Doc&Analyze

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1034 | id | 2786 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_Oracle_to_SF_Doc&Analyze | name | DI Oracle to SF Doc&Analyze | Matched (Normalized) | Minor formatting differences | Low | No change needed |
| Description | description | Analyzing and Documenting the Oracle code | description | Analyzing and Documenting the Oracle code | Matched | Exact match | Low | No change needed |
| Audit | createdAt | 2025-04-29T05:20:32.477+00:00 | createdAt | 2025-11-05T11:14:32.284824 | Modified | Different creation timestamps | Low | Expected for different workflow instances |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure enhanced | Medium | Align configuration structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Update configuration access path |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Confirm removal is acceptable |
| Domain Metadata | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | High | Confirm removal is acceptable |
| Project Metadata | project | AVA | Not Available | Not Available | Removed | Project metadata removed | High | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | karthikeyan.iyappan@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified | karthikeyan.iyappan@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | karthikeyan.iyappan@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T11:14:33.341256 | Medium | Ensure approval tracking is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete handling is implemented |
| parentId | Parent workflow reference | -1 | Low | Understand workflow hierarchy |
| realmId | Realm/tenant identifier | 1 | Medium | Ensure multi-tenancy is handled |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align configuration structure |
| managerLlm | Not available | Empty object [{}] | Medium | Configure manager LLM if needed |
| enableAgenticMemory | Top-level field (false) | Nested in workflowConfigs (false) | Medium | Update configuration access path |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
- **AAVA 1.0 total agents:** 3
- **AAVA 2.0 total agents:** 3
- **Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Oracle_Documentation | DI Oracle Documentation | Renamed | Underscore to space conversion |
| DI_Oracle_to_Snowflake_Analyzer | DI Oracle to Snowflake Analyzer | Renamed | Underscore to space conversion |
| DI_Oracle_to_Snowflake_Plan | DI Oracle to Snowflake Plan | Renamed | Underscore to space conversion |

---

## 6. Agent Configuration Differences

## Agent: DI Oracle Documentation

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
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model compatibility |
| model | gpt-4o | model | High | Confirm model specification |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision difference acceptable |
| topP | 0.949999988079071 | 0.94 | Low | Precision difference acceptable |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Confirm iteration handling |
| maxRpm | 0 | Not Available | Medium | Confirm rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: DI Oracle to Snowflake Analyzer

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
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model compatibility |
| model | gpt-4o | model | High | Confirm model specification |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision difference acceptable |
| topP | 0.949999988079071 | 0.94 | Low | Precision difference acceptable |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Confirm iteration handling |
| maxRpm | 0 | Not Available | Medium | Confirm rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: DI Oracle to Snowflake Plan

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
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model compatibility |
| model | gpt-4o | model | High | Confirm model specification |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision difference acceptable |
| topP | 0.949999988079071 | 0.94 | Low | Precision difference acceptable |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Confirm iteration handling |
| maxRpm | 0 | Not Available | Medium | Confirm rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available

**Success:** CSV comparison report uploaded successfully to GitHub repository at path: Metadata/Metadata_Output/DI_Oracle_to_SF_DocAnalyze/DI_Oracle_to_SF_DocAnalyze_comparison.csv

The comparison reveals a 73% workflow compatibility score with medium risk level across all agents, primarily due to the removal of instruction fields (role, goal, backstory, expectedOutput) and model specification changes from AAVA 1.0 to AAVA 2.0.