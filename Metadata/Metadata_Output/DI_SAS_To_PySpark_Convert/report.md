# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 82%  
**Total Agents Compared:** 5

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI SAS To PySpark Converter | 88% | Medium | Role/goal/backstory removed, description matched, LLM configs matched | Validate instruction field removal impact |
| DI SAS To PySpark UnitTest | 85% | Medium | Role/goal/backstory removed, description matched, LLM configs matched | Validate instruction field removal impact |
| DI SAS To PySpark ConversionTester | 82% | Medium | Role/goal/backstory removed, description modified, model changed | Validate model change and instruction updates |
| DI SAS To PySpark Recon Tester | 78% | Medium | Role/goal/backstory removed, description matched, model configs matched | Validate instruction field removal impact |
| DI SAS To PySpark Reviewer | 77% | Medium | Role/goal/backstory removed, description matched, model configs matched | Validate instruction field removal impact |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_SAS_To_PySpark_Convert  
**Workflow Name (AAVA 2.0):** DI SAS To PySpark Convert

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 580 | id | 2601 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | DI_SAS_To_PySpark_Convert | name | DI SAS To PySpark Convert | Matched (Case Normalization) | Minor spacing differences | Low | No change |
| Description | description | SAS to PySpark Converter_Unit Tester_Conversion tester_Recon tester_ Reviewer | description | SAS to PySpark Converter_Unit Tester_Conversion tester_Recon tester_ Reviewer | Matched | Identical values | Low | No change |
| Audit | createdAt | 2025-07-17T06:19:54.948+00:00 | createdAt | 2025-11-05T11:07:32.551574 | Modified | Different timestamps | Low | Expected for different instances |
| Agents List | pipeLineAgents | Array[5] | workflowAgents | Array[5] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | Object with managerLlm | Renamed + Modified | Enhanced configuration structure | Medium | Align configuration handling |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Low | Update configuration access |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Handle org context externally |
| Domain Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Handle domain context externally |
| Project Metadata | project | Conversions | Not Available | Not Available | Removed | Project metadata removed | Medium | Handle project context externally |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User tracking | elansuriyaa.p@ascendion.com | Medium | Implement user context handling |
| modifiedBy | Change tracking | elansuriyaa.p@ascendion.com | Medium | Implement modification tracking |
| approvedBy | Approval workflow | elansuriyaa.p@ascendion.com | Medium | Implement approval process |
| modifiedAt | Change timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T11:07:33.624702 | Low | Standard audit field |
| status | Workflow state | APPROVED | Medium | Implement workflow lifecycle |
| isDeleted | Soft delete flag | false | Low | Standard deletion handling |
| parentId | Hierarchy tracking | -1 | Low | Standard hierarchy field |
| realmId | Multi-tenancy | 32 | Medium | Implement realm-based access |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm array | Medium | Align configuration structure |
| managerLlm | Direct object | Array of objects with ID | Medium | Update LLM configuration handling |
| enableAgenticMemory | Direct field | Nested in workflowConfigs | Low | Update configuration access path |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5  
**AAVA 2.0 total agents:** 5  
**Coverage:** Same agent count, all agents preserved

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_SAS_To_PySpark_Converter | DI SAS To PySpark Converter | Renamed | Naming convention updated |
| DI_SAS_To_PySpark_UnitTest | DI SAS To PySpark UnitTest | Renamed | Naming convention updated |
| DI_SAS_To_PySpark_ConversionTester | DI SAS To PySpark ConversionTester | Renamed | Naming convention updated |
| DI_SAS_To_PySpark_Recon_Tester | DI SAS To PySpark Recon Tester | Renamed | Naming convention updated |
| DI_SAS_To_PySpark_Reviewer | DI SAS To PySpark Reviewer | Renamed | Naming convention updated |

---

## 6. Agent Configuration Differences

## Agent: DI SAS To PySpark Converter

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Present | Low | No change |

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model reference change |
| temperature | 0.30000001192092896 | 0.3 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | No change (normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | null | Low | No change |
| maxRpm | 0 | null | Low | No change |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout change |
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

## Agent: DI SAS To PySpark UnitTest

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Present | Low | No change |

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model reference change |
| temperature | 0.30000001192092896 | 0.3 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | No change (normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | null | Low | No change |
| maxRpm | 0 | null | Low | No change |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout change |
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

## Agent: DI SAS To PySpark ConversionTester

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Medium | Validate description changes |
| expectedOutput | Present | Present | Low | No change |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | anthropic.claude-3-7-sonnet | gpt-4.1 | High | Validate model deployment change |
| model | claude-3.7sonnet | model | High | Validate model change |
| temperature | 0.30000001192092896 | 0.3 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | No change (normalized) |
| maxToken | 20000 | 8000 | Medium | Validate token limit reduction |
| maxIter | 0 | null | Low | No change |
| maxRpm | 0 | null | Low | No change |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout change |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available

---

## Agent: DI SAS To PySpark Recon Tester

### 6.4.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Present | Low | No change |

### 6.4.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model reference change |
| temperature | 0.30000001192092896 | 0.3 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | No change (normalized) |
| maxToken | 20000 | 8000 | Medium | Validate token limit reduction |
| maxIter | 0 | null | Low | No change |
| maxRpm | 0 | null | Low | No change |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout change |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.4.3 Tools Comparison
Not Available

### 6.4.4 Knowledge Base Comparison
Not Available

### 6.4.5 Guardrails Comparison
Not Available

---

## Agent: DI SAS To PySpark Reviewer

### 6.5.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Present | Low | No change |

### 6.5.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model reference change |
| temperature | 0.30000001192092896 | 0.3 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | No change (normalized) |
| maxToken | 30000 | 8000 | High | Validate significant token limit reduction |
| maxIter | 0 | null | Low | No change |
| maxRpm | 0 | null | Low | No change |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout change |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.5.3 Tools Comparison
Not Available

### 6.5.4 Knowledge Base Comparison
Not Available

### 6.5.5 Guardrails Comparison
Not Available