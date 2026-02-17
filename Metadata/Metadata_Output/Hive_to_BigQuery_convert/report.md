# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 78%**
**Total Agents Compared: 5**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| Hive to BigQuery Converter | 85% | Medium | Model changed from gpt-4o to gpt-4.1; role/goal/backstory removed | Validate model behavior and confirm instruction removal |
| Hive to Bigquery Unit Tester | 82% | Medium | Model changed from gpt-4o to gpt-4.1; role/goal/backstory removed | Validate model behavior and confirm instruction removal |
| Hive to BigQuery Conversion Tester | 80% | Medium | Model changed from gpt-4o to gpt-4.1; role/goal/backstory removed | Validate model behavior and confirm instruction removal |
| Hive to BigQuery Recon Tester | 75% | Medium | Model changed from gpt-4o to gpt-4.1; role/goal/backstory removed | Validate model behavior and confirm instruction removal |
| Hive to BigQuery Reviewer | 73% | Medium | Model changed from gpt-4o to gpt-4.1; role/goal/backstory removed | Validate model behavior and confirm instruction removal |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** Hive_to_BigQuery_convert
**Workflow Name (AAVA 2.0):** Hive to BigQuery convert

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1436 | id | 4132 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | Hive_to_BigQuery_convert | name | Hive to BigQuery convert | Matched (Case Normalization) | Minor formatting difference | Low | No action required |
| Description | description | hive to pyspark convert | description | hive to pyspark convert | Matched | Values identical | Low | No action required |
| Audit | createdAt | 2025-04-03T05:50:37.691+00:00 | createdAt | 2025-11-05T11:52:49.592383 | Modified | Different timestamps | Low | Expected for different workflow instances |
| Agents List | pipeLineAgents | [5 agents] | workflowAgents | [5 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure enhanced | High | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Verify memory settings in new structure |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Implement governance tracking |
| Domain Metadata | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | High | Implement governance tracking |
| Project Metadata | project | AVA | Not Available | Not Available | Removed | Project metadata removed | High | Implement governance tracking |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User tracking | default@ascendion.com | Medium | Implement user attribution |
| modifiedBy | Change tracking | default@ascendion.com | Medium | Implement change management |
| approvedBy | Approval workflow | default@ascendion.com | High | Implement approval process |
| modifiedAt | Timestamp tracking | 2025-12-03T15:03:31.224436 | Medium | Enable change auditing |
| approvedAt | Approval timestamp | 2025-11-05T11:52:50.653143 | High | Track approval lifecycle |
| status | Workflow state | APPROVED | High | Implement status management |
| isDeleted | Soft delete flag | false | Medium | Enable soft delete functionality |
| parentId | Hierarchy tracking | -1 | Medium | Support workflow versioning |
| realmId | Multi-tenancy | 1 | High | Implement tenant isolation |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|---------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | High | Configure manager LLM settings |
| managerLlm | Not available | Empty object [{}] | Medium | Define manager LLM configuration |
| enableAgenticMemory | Top-level field (false) | Nested in workflowConfigs (false) | Medium | Update configuration access patterns |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5
**AAVA 2.0 total agents:** 5
**Coverage:** Same agent count with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| Hive_to_BigQuery_Converter | Hive to BigQuery Converter | Renamed | Underscore to space conversion |
| Hive_to_Bigquery_Unit_Tester | Hive to Bigquery Unit Tester | Renamed | Underscore to space conversion |
| Hive_to_BigQuery_Conversion_Tester | Hive to BigQuery Conversion Tester | Renamed | Underscore to space conversion |
| Hive_to_BigQuery_Recon_Tester | Hive to BigQuery Recon Tester | Renamed | Underscore to space conversion |
| Hive_to_BigQuery_Reviewer | Hive to BigQuery Reviewer | Renamed | Underscore to space conversion |

---

## 6. Agent Configuration Differences

## Agent: Hive to BigQuery Converter

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
| model | gpt-4o | model | High | Verify model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | Null vs zero handling |
| maxRpm | 0 | null | Low | Null vs zero handling |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: Hive to Bigquery Unit Tester

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
| model | gpt-4o | model | High | Verify model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | Null vs zero handling |
| maxRpm | 0 | null | Low | Null vs zero handling |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: Hive to BigQuery Conversion Tester

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
| model | gpt-4o | model | High | Verify model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | Null vs zero handling |
| maxRpm | 0 | null | Low | Null vs zero handling |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available

---

## Agent: Hive to BigQuery Recon Tester

### 6.4.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.4.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Verify model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | Null vs zero handling |
| maxRpm | 0 | null | Low | Null vs zero handling |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |

### 6.4.3 Tools Comparison
Not Available

### 6.4.4 Knowledge Base Comparison
Not Available

### 6.4.5 Guardrails Comparison
Not Available

---

## Agent: Hive to BigQuery Reviewer

### 6.5.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.5.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Verify model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | Null vs zero handling |
| maxRpm | 0 | null | Low | Null vs zero handling |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |

### 6.5.3 Tools Comparison
Not Available

### 6.5.4 Knowledge Base Comparison
Not Available

### 6.5.5 Guardrails Comparison
Not Available