# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

# 1. Metadata Comparison Score Summary

* **Workflow Comparison Score: 78%**
* **Total Agents Compared: 3**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| Hive to BigQuery Documentation | 85% | Low | Model deployment changed; description matched; LLM configs mostly preserved | Validate new model deployment |
| Hive to BigQuery Analyzer | 82% | Low | Model deployment changed; description matched; expected output removed | Validate model behavior and add expected output format |
| Hive to BigQuery Planner | 67% | Medium | Model deployment changed; description matched; expected output removed | Validate model behavior and add expected output format |

---

# 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** Hive_to_BigQuery_doc&analyze
**Workflow Name (AAVA 2.0):** Hive to BigQuery doc&analyze

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1435 | id | 4131 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new workflow ID |
| Naming | name | Hive_to_BigQuery_doc&analyze | name | Hive to BigQuery doc&analyze | Matched (Normalized) | Minor formatting differences | Low | No change |
| Description | description | hive to bigquery doc and analyze | description | hive to bigquery doc and analyze | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-04-03T04:34:19.487+00:00 | createdAt | 2025-11-05T11:52:46.214509 | Modified | Different creation timestamps | Low | Expected for new workflow version |
| Agents List | pipeLineAgents | Present | workflowAgents | Present | Renamed + Matched (Normalized) | Field renamed, content structure preserved | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | Present | Renamed + Modified | Field renamed and enhanced structure | High | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Verify memory settings in new structure |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Low | Confirm removal acceptable |
| Domain Metadata | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | Low | Confirm removal acceptable |
| Project Metadata | project | AVA | Not Available | Not Available | Removed | Project metadata removed | Low | Confirm removal acceptable |

---

# 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User tracking | default@ascendion.com | Medium | Ensure user attribution is handled |
| modifiedBy | Change tracking | default@ascendion.com | Medium | Implement change tracking |
| approvedBy | Approval workflow | default@ascendion.com | Medium | Configure approval process |
| modifiedAt | Timestamp tracking | 2025-12-03T15:03:31.224436 | Low | Automatic timestamp handling |
| approvedAt | Approval timestamp | 2025-11-05T11:52:47.263102 | Low | Automatic approval tracking |
| status | Workflow state | APPROVED | High | Implement workflow lifecycle |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete logic |
| parentId | Hierarchy tracking | -1 | Low | Handle workflow relationships |
| realmId | Multi-tenancy | 1 | Medium | Configure realm-based access |

---

# 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|---------|-----------------|
| workflowConfigs | Not available | Present with managerLlm | High | Configure manager LLM settings |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update memory configuration access |
| callbacks | Empty array | Not available | Medium | Migrate callback functionality to workflowConfigs |

---

# 5. Agent Inventory Summary

## 5.1 Agent Count & Coverage

**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents with naming updates

## 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|--------|
| Hive_to_BigQuery_Documentation | Hive to BigQuery Documentation | Renamed | Underscore to space conversion |
| Hive_to_BigQuery_Analyzer | Hive to BigQuery Analyzer | Renamed | Underscore to space conversion |
| Hive_to_BigQuery_Planner | Hive to BigQuery Planner | Renamed | Underscore to space conversion |

---

# 6. Agent Configuration Differences

## Agent: Hive to BigQuery Documentation

---

## 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

---

## 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Add missing field or confirm removal |
| maxRpm | 0 | Not Available | Medium | Add missing field or confirm removal |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |

---

## 6.1.3 Tools Comparison

**Not Available** - No tools configured in either version

---

## 6.1.4 Knowledge Base Comparison

**Not Available** - No knowledge base configured in either version

---

## 6.1.5 Guardrails Comparison

**Not Available** - No guardrails configured in either version

---

## Agent: Hive to BigQuery Analyzer

---

## 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

---

## 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Add missing field or confirm removal |
| maxRpm | 0 | Not Available | Medium | Add missing field or confirm removal |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |

---

## 6.2.3 Tools Comparison

**Not Available** - No tools configured in either version

---

## 6.2.4 Knowledge Base Comparison

**Not Available** - No knowledge base configured in either version

---

## 6.2.5 Guardrails Comparison

**Not Available** - No guardrails configured in either version

---

## Agent: Hive to BigQuery Planner

---

## 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

---

## 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Add missing field or confirm removal |
| maxRpm | 0 | Not Available | Medium | Add missing field or confirm removal |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |

---

## 6.3.3 Tools Comparison

**Not Available** - No tools configured in either version

---

## 6.3.4 Knowledge Base Comparison

**Not Available** - No knowledge base configured in either version

---

## 6.3.5 Guardrails Comparison

**Not Available** - No guardrails configured in either version