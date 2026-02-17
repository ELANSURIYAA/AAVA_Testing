# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 78%
**Total Agents Compared:** 5

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| Postgres to PySpark Converter | 72% | Medium | Model changed (o3-mini to gpt-4.1), role/goal/backstory removed, maxIter/maxRpm nullified | Validate model compatibility and confirm instruction field removal |
| Postgres to PySpark Unit Testing | 75% | Medium | Model changed (gpt-4o to gpt-4.1), role/goal/backstory removed, maxIter changed (5 to null) | Validate model compatibility and iteration limits |
| Postgres to PySpark Conversion Tester | 78% | Medium | Model changed (gpt-4o to gpt-4.1), role/goal/backstory removed, maxIter nullified | Validate model compatibility and confirm instruction field removal |
| Postgres to PySpark Reconciliation | 78% | Medium | Model changed (gpt-4o to gpt-4.1), role/goal/backstory removed, maxIter nullified | Validate model compatibility and confirm instruction field removal |
| Postgres to PySpark Reviewer | 75% | Medium | Model changed (gpt-4o to gpt-4.1), role/goal/backstory removed, maxIter changed (5 to null) | Validate model compatibility and iteration limits |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** Postgres_to_Pyspark_Convert
**Workflow Name (AAVA 2.0):** Postgres to Pyspark Convert

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 776 | id | 3807 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | Postgres_to_Pyspark_Convert | name | Postgres to Pyspark Convert | Matched (Normalized) | Minor formatting difference | Low | No change needed |
| Description | description | Postgres to Pyspark conversion | description | Postgres to Pyspark conversion | Matched | Exact match | Low | No change needed |
| Audit | createdAt | 2025-03-04T13:44:08.856+00:00 | createdAt | 2025-11-05T11:42:59.764034 | Modified | Different creation timestamp | Low | Expected for new workflow instance |
| Agents List | pipeLineAgents | [5 agents] | workflowAgents | [5 agents] | Renamed + Matched (Normalized) | Field renamed but same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm, enableAgenticMemory} | Renamed + Modified | Field renamed and structure changed | High | Migrate callback configurations |
| Memory Config | enableAgenticMemory | false | workflowConfigs.enableAgenticMemory | false | Modified | Moved to nested structure | Medium | Update configuration access |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Confirm removal acceptable |
| Domain Metadata | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | High | Confirm removal acceptable |
| Project Metadata | project | AVA | Not Available | Not Available | Removed | Project metadata removed | High | Confirm removal acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Ensure approval workflow is handled |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T11:43:00.811324 | Low | Standard audit field |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure deletion handling is implemented |
| parentId | Parent workflow reference | -1 | Low | Handle workflow versioning |
| realmId | Realm identifier | 1 | Medium | Ensure multi-tenancy is handled |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| managerLlm | Direct pipeline property | Nested in workflowConfigs | High | Update configuration access patterns |
| workflowConfigs | Not available | Present with structured config | Medium | Align with new configuration model |
| enableAgenticMemory | Direct pipeline property | Nested in workflowConfigs | Medium | Update memory configuration access |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5
**AAVA 2.0 total agents:** 5
**Coverage:** Same agent count with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| Postgres_to_PySpark_Converter | Postgres to PySpark Converter | Renamed | Naming convention updated |
| Postgres_to_PySpark_Unit_Testing | Postgres to PySpark Unit Testing | Renamed | Naming convention updated |
| Postgres_to_PySpark_Conversion_Tester | Postgres to PySpark Conversion Tester | Renamed | Naming convention updated |
| Postgres_to_PySpark_Reconciliation | Postgres to PySpark Reconciliation | Renamed | Naming convention updated |
| Postgres_to_PySpark_Reviewer | Postgres to PySpark Reviewer | Renamed | Naming convention updated |

---

## 6. Agent Configuration Differences

## Agent: Postgres to PySpark Converter

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
| modelDeploymentName | o3-mini | gpt-4.1 | High | Validate model compatibility |
| model | o3-mini | model | High | Validate model compatibility |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized values match |
| topP | 0.949999988079071 | 0.94 | Low | Minor precision difference |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Medium | Validate iteration limits |
| maxRpm | 0 | null | Medium | Validate rate limits |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout settings |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: Postgres to PySpark Unit Testing

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
| model | gpt-4o | model | High | Validate model compatibility |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized values match |
| topP | 0.949999988079071 | 0.94 | Low | Minor precision difference |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 5 | null | High | Validate iteration limits |
| maxRpm | 0 | null | Medium | Validate rate limits |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout settings |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: Postgres to PySpark Conversion Tester

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
| model | gpt-4o | model | High | Validate model compatibility |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized values match |
| topP | 0.949999988079071 | 0.94 | Low | Minor precision difference |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Medium | Validate iteration limits |
| maxRpm | 0 | null | Medium | Validate rate limits |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout settings |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available

---

## Agent: Postgres to PySpark Reconciliation

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
| model | gpt-4o | model | High | Validate model compatibility |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized values match |
| topP | 0.949999988079071 | 0.94 | Low | Minor precision difference |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Medium | Validate iteration limits |
| maxRpm | 0 | null | Medium | Validate rate limits |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout settings |

### 6.4.3 Tools Comparison
Not Available

### 6.4.4 Knowledge Base Comparison
Not Available

### 6.4.5 Guardrails Comparison
Not Available

---

## Agent: Postgres to PySpark Reviewer

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
| model | gpt-4o | model | High | Validate model compatibility |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized values match |
| topP | 0.949999988079071 | 0.94 | Low | Minor precision difference |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 5 | null | High | Validate iteration limits |
| maxRpm | 0 | null | Medium | Validate rate limits |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout settings |

### 6.5.3 Tools Comparison
Not Available

### 6.5.4 Knowledge Base Comparison
Not Available

### 6.5.5 Guardrails Comparison
Not Available