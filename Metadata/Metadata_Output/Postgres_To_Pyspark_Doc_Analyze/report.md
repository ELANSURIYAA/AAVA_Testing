# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 87.3%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| Postgres Documentation | 89.2% | Low | Model deployment renamed, maxIter/maxRpm null, role/goal/backstory removed | Validate new model deployment and confirm instruction field removal |
| Postgres to PySpark Analyzer | 87.5% | Medium | Model deployment renamed, maxIter/maxRpm null, role/goal/backstory removed | Validate new model deployment and confirm instruction field removal |
| Postgres to PySpark Plan | 85.2% | Medium | Model deployment renamed, maxIter/maxRpm null, role/goal/backstory removed | Validate new model deployment and confirm instruction field removal |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** Postgres_To_Pyspark_Doc_&_Analyze
**Workflow Name (AAVA 2.0):** Postgres To Pyspark Doc & Analyze

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 851 | id | 3188 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | Postgres_To_Pyspark_Doc_&_Analyze | name | Postgres To Pyspark Doc & Analyze | Matched (Normalized) | Minor formatting differences | Low | No change |
| Description | description | Postgres_To_Pyspark_Doc_&_Analyze | description | Postgres_To_Pyspark_Doc_&_Analyze | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-03-03T05:24:55.395+00:00 | createdAt | 2025-11-05T11:23:52.029061 | Matched | Field exists in both, values differ | Low | No change |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed with new structure | High | Implement new workflow configuration |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Update memory configuration handling |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm removal is acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm removal is acceptable |
| Domain | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal is acceptable |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm removal is acceptable |
| Project | project | AVA | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal is acceptable |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm removal is acceptable |
| Team | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm removal is acceptable |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm removal is acceptable |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Implement user tracking |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Implement modification tracking |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Implement modification tracking |
| approvedAt | Approval timestamp | 2025-11-05T11:23:53.077449 | Medium | Implement approval workflow |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete functionality |
| parentId | Parent workflow reference | -1 | Low | Handle workflow hierarchy |
| realmId | Realm identifier | 1 | Low | Handle multi-tenancy |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align defaults and implement new config structure |
| callbacks | Present (empty array) | Not available | Medium | Migrate callback functionality to workflowConfigs |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| Postgres_Documentation | Postgres Documentation | Matched (Normalized) | Underscore removed |
| Postgres_to_PySpark_Analyzer | Postgres to PySpark Analyzer | Matched (Normalized) | Underscore removed |
| Postgres_to_PySpark_Plan | Postgres to PySpark Plan | Matched (Normalized) | Underscore removed |

---

## 6. Agent Configuration Differences

## Agent: Postgres Documentation

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
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate new model deployment |
| model | gpt-4o | model | High | Validate model configuration change |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 5 | null | Medium | Validate null value impact |
| maxRpm | 0 | null | Medium | Validate null value impact |
| maxExecutionTime | 0 | 90 | Medium | Execution time limit added |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: Postgres to PySpark Analyzer

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
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate new model deployment |
| model | gpt-4o | model | High | Validate model configuration change |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 5 | null | Medium | Validate null value impact |
| maxRpm | 0 | null | Medium | Validate null value impact |
| maxExecutionTime | 0 | 90 | Medium | Execution time limit added |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: Postgres to PySpark Plan

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
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate new model deployment |
| model | gpt-4o | model | High | Validate model configuration change |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 5 | null | Medium | Validate null value impact |
| maxRpm | 0 | null | Medium | Validate null value impact |
| maxExecutionTime | 0 | 90 | Medium | Execution time limit added |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available