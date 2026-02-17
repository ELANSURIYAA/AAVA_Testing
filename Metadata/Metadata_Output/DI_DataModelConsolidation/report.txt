# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Name (AAVA 1.0):** DI_DataModelConsolidation
**Workflow Name (AAVA 2.0):** DI DataModelConsolidation

* **Workflow Comparison Score:** 84%
* **Total Agents Compared:** 2

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI DataModelConsolidation Analyzer | 88% | Medium | agentId changed, name normalized, role/goal/backstory removed, maxToken removed | Validate agent identity mapping and confirm instruction field removal |
| DI DataModelConsolidation Recommender | 80% | Medium | agentId changed, name normalized, role/goal/backstory removed, maxToken removed | Validate agent identity mapping and confirm instruction field removal |

---

## 2. Workflow-Level Comparison

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 2469 | id | 1894 | Renamed + Modified | Field renamed and value changed | High | Update workflow ID references |
| Naming | name | DI_DataModelConsolidation | name | DI DataModelConsolidation | Matched (Normalized) | Space added in name | Low | No change |
| Description | description | Analyze DDLs of data pipeline layers across EDW, Lakehouse, determine the best model for enhancements | description | Analyze DDLs of data pipeline layers across EDW, Lakehouse, determine the best model for enhancements | Matched | Identical values | Low | No change |
| Audit | createdAt | 2025-06-03T18:59:01.228+00:00 | createdAt | 2025-11-05T10:39:12.851427 | Matched | Field exists in both but values differ | Medium | Validate timestamp differences |
| Agents List | pipeLineAgents | Array[2] | workflowAgents | Array[2] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | Object with managerLlm | Renamed + Modified | Structure and content changed | High | Migrate callback configurations |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field removed in AAVA 2.0 | Medium | Confirm memory config removal |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational fields removed | Medium | Migrate org metadata handling |
| Domain Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain fields removed | Medium | Migrate domain metadata handling |
| Project Metadata | project | AllProjects | Not Available | Not Available | Removed | Project fields removed | Medium | Migrate project metadata handling |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User audit trail | muneeswara.pandian@ascendion.com | Medium | Implement user tracking |
| modifiedBy | Modification audit | muneeswara.pandian@ascendion.com | Medium | Implement modification tracking |
| approvedBy | Approval workflow | muneeswara.pandian@ascendion.com | Medium | Implement approval process |
| modifiedAt | Modification timestamp | 2025-12-03T15:03:31.224436 | Low | Add modification timestamps |
| approvedAt | Approval timestamp | 2025-11-05T10:39:14.064732 | Low | Add approval timestamps |
| status | Workflow state | APPROVED | High | Implement workflow status management |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete functionality |
| parentId | Hierarchy support | -1 | Low | Add parent-child relationships |
| realmId | Multi-tenancy | 32 | Medium | Implement realm-based isolation |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm | High | Implement workflow-level LLM configuration |
| enableAgenticMemory | Present (false) | Nested under workflowConfigs | Medium | Migrate memory configuration structure |
| callbacks | Empty array | Not available | Medium | Migrate callback mechanism to workflowConfigs |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 2
**AAVA 2.0 total agents:** 2
**Coverage:** Same agent count, renamed agents

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_DataModelConsolidation_Analyzer | DI DataModelConsolidation Analyzer | Renamed | Underscore replaced with space |
| DI_DataModelConsolidation_Recommender | DI DataModelConsolidation Recommender | Renamed | Underscore replaced with space |

---

## 6. Agent Configuration Differences

## Agent: DI DataModelConsolidation Analyzer

---

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision difference |
| topP | 0.949999988079071 | 0.94 | Low | Normalized precision difference |
| maxToken | 16000 | 16000 | Low | No change |
| maxIter | 0 | null | Medium | Validate null vs zero handling |
| maxRpm | 0 | null | Medium | Validate null vs zero handling |
| maxExecutionTime | 0 | 90 | High | Execution timeout changed significantly |

---

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | FileWriterTool (toolId: 4) | toolRef: [4] | Medium | Validate tool reference structure |
| userTools | [] | Not Available | Medium | Confirm userTools removal |

---

### 6.1.4 Knowledge Base Comparison

Not Available

---

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI DataModelConsolidation Recommender

---

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision difference |
| topP | 0.949999988079071 | 0.94 | Low | Normalized precision difference |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 15 | null | High | Iteration limit removed |
| maxRpm | 0 | null | Medium | Validate null vs zero handling |
| maxExecutionTime | 0 | 90 | High | Execution timeout changed significantly |

---

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | toolRef: [] | Low | Empty tool arrays match |
| userTools | [] | Not Available | Medium | Confirm userTools removal |

---

### 6.2.4 Knowledge Base Comparison

Not Available

---

### 6.2.5 Guardrails Comparison

Not Available