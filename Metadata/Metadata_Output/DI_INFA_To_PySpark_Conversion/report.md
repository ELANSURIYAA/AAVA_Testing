# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 76%
**Total Agents Compared:** 5

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI INFA to  PySpark Converter | 78% | Medium | role/goal/backstory removed, description matched, LLM configs mostly matched | Validate agent behavior without role/goal/backstory fields |
| DI INFA to PySpark UnitTest | 76% | Medium | role/goal/backstory removed, description matched, runtime configs changed | Validate runtime behavior with new execution limits |
| DI INFA to PySpark Conversion Tester | 74% | Medium | role/goal/backstory removed, description matched, allowDelegation changed | Confirm delegation behavior change is acceptable |
| DI INFA to PySpark Recon Tester | 78% | Medium | role/goal/backstory removed, description matched, LLM configs mostly matched | Validate agent behavior without instruction fields |
| DI INFA to PySpark Reviewer | 76% | Medium | role/goal/backstory removed, description matched, runtime configs changed | Validate runtime behavior with new execution limits |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_INFA_To_PySpark_Conversion
**Workflow Name (AAVA 2.0):** DI INFA To PySpark Conversion

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 392 | id | 4535 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | DI_INFA_To_PySpark_Conversion | name | DI INFA To PySpark Conversion | Matched (Normalized) | Minor spacing differences | Low | No change |
| Description | description | This workflow is to Convert INFORMATICA code to PYSPARK code. | description | This workflow is to Convert INFORMATICA code to PYSPARK code. | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-10-09T17:23:00.180+00:00 | createdAt | 2025-11-05T12:05:28.241459 | Modified | Different creation timestamps | Medium | Validate audit trail |
| Agents List | pipeLineAgents | [5 agents] | workflowAgents | [5 agents] | Renamed + Matched (Normalized) | Field renamed but same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm, enableAgenticMemory} | Renamed + Modified | Structure and content changed | High | Align configuration handling |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Update memory configuration access |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | High | Implement alternative org tracking |
| Domain Metadata | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | High | Implement alternative domain tracking |
| Project Metadata | project | AVA | Not Available | Not Available | Removed | Project metadata removed | High | Implement alternative project tracking |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | girdhari.rayak@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | girdhari.rayak@ascendion.com | Medium | Implement modification tracking |
| approvedBy | User who approved workflow | girdhari.rayak@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Track modification history |
| approvedAt | Approval timestamp | 2025-11-05T12:05:29.288612 | Medium | Implement approval tracking |
| status | Workflow approval state | APPROVED | High | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete functionality |
| parentId | Parent workflow reference | -1 | Medium | Handle workflow hierarchy |
| realmId | Realm/tenant identifier | 32 | High | Implement multi-tenancy support |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm array | High | Align configuration structure |
| managerLlm | Direct object | Array of objects with id field | High | Update LLM configuration handling |
| callbacks | Empty array | Not available | Medium | Migrate callback functionality |
| enableAgenticMemory | Direct field | Nested in workflowConfigs | Medium | Update memory config access |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5
**AAVA 2.0 total agents:** 5
**Coverage:** Same agent count with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_INFA_to_ PySpark_Converter | DI INFA to  PySpark Converter | Renamed | Spacing and underscore changes |
| DI_INFA_to_PySpark_UnitTest | DI INFA to PySpark UnitTest | Renamed | Spacing and underscore changes |
| DI_INFA_to_PySpark_Conversion_Tester | DI INFA to PySpark Conversion Tester | Renamed | Spacing and underscore changes |
| DI_INFA_to_PySpark_Recon_Tester | DI INFA to PySpark Recon Tester | Renamed | Spacing and underscore changes |
| DI_INFA_to_PySpark_Reviewer | DI INFA to PySpark Reviewer | Renamed | Spacing and underscore changes |

---

## 6. Agent Configuration Differences

## Agent: DI INFA to  PySpark Converter

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | No change |
| topP | 0.949999988079071 | 0.94 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Available | Medium | Validate iteration limits |
| maxRpm | 0 | Not Available | Medium | Validate rate limiting |
| maxExecutionTime | 300 | 90 | High | Validate execution time limits |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: DI INFA to PySpark UnitTest

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | No change |
| topP | 0.949999988079071 | 0.94 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Available | Medium | Validate iteration limits |
| maxRpm | 0 | Not Available | Medium | Validate rate limiting |
| maxExecutionTime | 300 | 90 | High | Validate execution time limits |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: DI INFA to PySpark Conversion Tester

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | No change |
| topP | 0.949999988079071 | 0.94 | Low | No change |
| maxToken | 32000 | 8000 | High | Validate token limit reduction |
| maxIter | 0 | Not Available | Medium | Validate iteration limits |
| maxRpm | 0 | Not Available | Medium | Validate rate limiting |
| maxExecutionTime | 0 | 90 | High | Validate execution time change |
| allowDelegation | false | true | High | Validate delegation behavior change |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available

---

## Agent: DI INFA to PySpark Recon Tester

### 6.4.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.4.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | No change |
| topP | 0.949999988079071 | 0.94 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Available | Medium | Validate iteration limits |
| maxRpm | 0 | Not Available | Medium | Validate rate limiting |
| maxExecutionTime | 300 | 90 | High | Validate execution time limits |

### 6.4.3 Tools Comparison
Not Available

### 6.4.4 Knowledge Base Comparison
Not Available

### 6.4.5 Guardrails Comparison
Not Available

---

## Agent: DI INFA to PySpark Reviewer

### 6.5.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.5.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | No change |
| topP | 0.949999988079071 | 0.94 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Available | Medium | Validate iteration limits |
| maxRpm | 0 | Not Available | Medium | Validate rate limiting |
| maxExecutionTime | 300 | 90 | High | Validate execution time limits |

### 6.5.3 Tools Comparison
Not Available

### 6.5.4 Knowledge Base Comparison
Not Available

### 6.5.5 Guardrails Comparison
Not Available