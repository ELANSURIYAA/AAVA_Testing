# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Name (AAVA 1.0):** DI_Databricks_Data_Modeler_Bronze_Layer
**Workflow Name (AAVA 2.0):** DI Databricks Data Modeler Bronze Layer

* **Workflow Comparison Score:** 78%
* **Total Agents Compared:** 4

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_Databricks_Bronze_Model_Logical | 85% | Medium | role/goal/backstory removed, model changed, maxRpm modified | Validate instruction field removal and model compatibility |
| DI_Databricks_Bronze_Model_Physical | 82% | Medium | role/goal/backstory removed, model changed, maxRpm modified | Validate instruction field removal and model compatibility |
| DI_Databricks_Bronze_Model_Data_Mapping | 78% | Medium | role/goal/backstory removed, model changed, maxRpm modified | Validate instruction field removal and model compatibility |
| DI_Databricks_Bronze_Model_Reviewer | 68% | Medium | role/goal/backstory removed, model changed, maxRpm modified | Validate instruction field removal and model compatibility |

---

## 2. Workflow-Level Comparison

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 6176 | id | 4661 | Renamed + Modified | Field renamed and value changed | Medium | Update ID references in dependent systems |
| Naming | name | DI_Databricks_Data_Modeler_Bronze_Layer | name | DI Databricks Data Modeler Bronze Layer | Matched (Case Normalization) | Minor spacing differences | Low | No change needed |
| Description | description | Data Modeler for Databricks environment | description | Data Modeler for Databricks environment | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-08-20T06:56:33.079+00:00 | createdAt | 2025-11-05T12:09:27.269743 | Matched | Field present in both | Low | No change |
| Agents List | pipeLineAgents | Array[4] | workflowAgents | Array[4] | Renamed + Matched (Normalized) | Field renamed but same agent count | Medium | Update agent references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Structure and content changed | High | Validate new configuration format |
| Memory Config | enableAgenticMemory | false | Not Available | - | Removed | Field moved to workflowConfigs | Medium | Confirm removal is acceptable |
| Org Metadata | org | Ascendion | Not Available | - | Removed | Organizational metadata removed | High | Add missing organizational context |
| Domain Metadata | domain | Platform Engineering | Not Available | - | Removed | Domain metadata removed | High | Add missing domain context |
| Project Metadata | project | AVA | Not Available | - | Removed | Project metadata removed | High | Add missing project context |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | elansuriyaa.p@ascendion.com | Medium | Ensure approval workflow is handled |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T12:09:28.309914 | Medium | Ensure approval workflow is handled |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure deletion handling is implemented |
| parentId | Parent workflow reference | -1 | Low | Validate parent-child relationships |
| realmId | Realm identifier | 32 | Medium | Ensure realm context is maintained |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | High | Align configuration structure |
| managerLlm | Not available | Array with empty object | Medium | Validate manager LLM configuration |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update configuration access patterns |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 4
**AAVA 2.0 total agents:** 4
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Databricks_Bronze_Model_Logical | DI Databricks Bronze Model Logical | Matched (Case Normalization) | Underscore to space conversion |
| DI_Databricks_Bronze_Model_Physical | DI Databricks Bronze Model Physical | Matched (Case Normalization) | Underscore to space conversion |
| DI_Databricks_Bronze_Model_Data_Mapping | DI Databricks Bronze Model Data Mapping | Matched (Case Normalization) | Underscore to space conversion |
| DI_Databricks_Bronze_Model_Reviewer | DI Databricks Bronze Model Reviewer | Matched (Case Normalization) | Underscore to space conversion |

---

## 6. Agent Configuration Differences

## Agent: DI_Databricks_Bronze_Model_Logical

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility and performance |
| model | anthropic.claude-4-sonnet | model | High | Validate model compatibility and performance |
| temperature | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Present | Medium | Validate iteration limit handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting behavior |
| maxExecutionTime | 400 | 90 | High | Validate timeout compatibility |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Present | Low | No change needed |
| userTools | 2 tools present | Not Present | High | Validate tool availability and permissions |

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI_Databricks_Bronze_Model_Physical

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility and performance |
| model | anthropic.claude-4-sonnet | model | High | Validate model compatibility and performance |
| temperature | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Present | Medium | Validate iteration limit handling |
| maxRpm | 50 | Not Present | Medium | Validate rate limiting behavior |
| maxExecutionTime | 400 | 90 | High | Validate timeout compatibility |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Present | Low | No change needed |
| userTools | 2 tools present | Not Present | High | Validate tool availability and permissions |

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DI_Databricks_Bronze_Model_Data_Mapping

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility and performance |
| model | anthropic.claude-4-sonnet | model | High | Validate model compatibility and performance |
| temperature | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Present | Medium | Validate iteration limit handling |
| maxRpm | 50 | Not Present | Medium | Validate rate limiting behavior |
| maxExecutionTime | 400 | 90 | High | Validate timeout compatibility |

### 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Present | Low | No change needed |
| userTools | 2 tools present | Not Present | High | Validate tool availability and permissions |

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available

---

## Agent: DI_Databricks_Bronze_Model_Reviewer

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility and performance |
| model | anthropic.claude-4-sonnet | model | High | Validate model compatibility and performance |
| temperature | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Present | Medium | Validate iteration limit handling |
| maxRpm | 50 | Not Present | Medium | Validate rate limiting behavior |
| maxExecutionTime | 400 | 90 | High | Validate timeout compatibility |

### 6.4.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Present | Low | No change needed |
| userTools | 2 tools present | Not Present | High | Validate tool availability and permissions |

### 6.4.4 Knowledge Base Comparison

Not Available

### 6.4.5 Guardrails Comparison

Not Available