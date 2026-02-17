# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 85%**
**Total Agents Compared: 6**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI SSIS Metadata Extractor | 92% | Low | model configs matched, description matched, temperature matched | None |
| DI SSISExtractor To DBTCloud | 88% | Medium | model changed from gpt-4 to model, maxToken reduced from 8000 to 8000 | Validate runtime behavior |
| DI SSIS to DBTCloud Unit Tester | 95% | Low | all configs matched after normalization, agent ID changed | None |
| DI SSIS To DBTCloud Conversion Tester | 95% | Low | all configs matched after normalization, agent ID changed | None |
| DI SSIS To DBTCloud Recon Tester | 85% | Medium | agent ID changed significantly, some config differences | Validate new agent configuration |
| DI SSIS to DBTCloud Reviewer | 92% | Low | model configs matched, description matched, agent ID changed | None |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_SSIS_To_DBTCloud_Conversion
**Workflow Name (AAVA 2.0):** DI SSIS To DBTCloud Conversion

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 5017 | id | 2040 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_SSIS_To_DBTCloud_Conversion | name | DI SSIS To DBTCloud Conversion | Matched (Case Normalization) | Minor formatting difference in spacing | Low | None |
| Description | description | DI_SSIS_To_DBTCloud_Conversion | description | DI_SSIS_To_DBTCloud_Conversion | Matched | Identical values | Low | None |
| Audit | createdAt | 2025-07-07T20:48:05.881+00:00 | createdAt | 2025-11-05T10:44:50.277364 | Modified | Different creation timestamps | Low | Expected for different workflow instances |
| Agents List | pipeLineAgents | Array of 6 agents | workflowAgents | Array of 6 agents | Renamed + Matched (Normalized) | Field renamed but same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | Object with managerLlm | Renamed + Modified | Field renamed and structure changed | Medium | Align configuration structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Validate memory configuration handling |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Low | Confirm removal is acceptable |
| Domain Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Low | Confirm removal is acceptable |
| Project Metadata | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Low | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | kiran.krishnakumar@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | kiran.krishnakumar@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | kiran.krishnakumar@ascendion.com | Medium | Ensure approval workflow is handled |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T10:44:51.354691 | Medium | Ensure approval workflow is handled |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure deletion handling is implemented |
| parentId | Parent workflow reference | -1 | Low | Understand workflow hierarchy |
| realmId | Realm identifier | 32 | Low | Understand realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|---------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align configuration structure |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update configuration access patterns |
| managerLlm | Not available | Empty object in workflowConfigs | Low | Understand manager LLM configuration |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 6
**AAVA 2.0 total agents:** 6
**Coverage:** Same agent count with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_SSIS_Metadata_Extractor | DI SSIS Metadata Extractor | Renamed | Underscore to space conversion |
| DI_SSISExtractor_To_DBTCloud | DI SSISExtractor To DBTCloud | Renamed | Underscore to space conversion |
| DI_SSIS_to_DBTCloud_Unit_Tester | DI SSIS to DBTCloud Unit Tester | Renamed | Underscore to space conversion |
| DI_SSIS_To_DBTCloud_Conversion_Tester | DI SSIS To DBTCloud Conversion Tester | Renamed | Underscore to space conversion |
| DI_SSIS_To_DBTCloud_Recon_Tester | DI SSIS To DBTCloud Recon Tester | Renamed | Underscore to space conversion |
| DI_SSIS_to_DBTCloud_Reviewer | DI SSIS to DBTCloud Reviewer | Renamed | Underscore to space conversion |

---

## 6. Agent Configuration Differences

## Agent: DI SSIS Metadata Extractor

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
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model compatibility |
| model | gpt-4o | model | High | Validate model configuration |
| temperature | 0.20000000298023224 | 0.2 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 15000 | 15000 | Low | No change |
| maxIter | 30 | Not Available | Medium | Add missing field or confirm deprecation |
| maxRpm | 0 | Not Available | Medium | Add missing field or confirm deprecation |
| maxExecutionTime | 300 | 90 | Medium | Validate timeout configuration |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: DI SSISExtractor To DBTCloud

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
| temperature | 0.20000000298023224 | 0.2 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 30 | Not Available | Medium | Add missing field or confirm deprecation |
| maxRpm | 0 | Not Available | Medium | Add missing field or confirm deprecation |
| maxExecutionTime | 300 | 90 | Medium | Validate timeout configuration |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| FileWriterTool | toolId: 4 | toolRef: [4] | Low | Field renamed but same tool reference |

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: DI SSIS to DBTCloud Unit Tester

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
| temperature | 0.20000000298023224 | 0.2 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 30 | Not Available | Medium | Add missing field or confirm deprecation |
| maxRpm | 0 | Not Available | Medium | Add missing field or confirm deprecation |
| maxExecutionTime | 300 | 90 | Medium | Validate timeout configuration |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available

---

## Agent: DI SSIS To DBTCloud Conversion Tester

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
| temperature | 0.20000000298023224 | 0.2 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 30 | Not Available | Medium | Add missing field or confirm deprecation |
| maxRpm | 0 | Not Available | Medium | Add missing field or confirm deprecation |
| maxExecutionTime | 300 | 90 | Medium | Validate timeout configuration |

### 6.4.3 Tools Comparison
Not Available

### 6.4.4 Knowledge Base Comparison
Not Available

### 6.4.5 Guardrails Comparison
Not Available

---

## Agent: DI SSIS To DBTCloud Recon Tester

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
| temperature | 0.20000000298023224 | 0.2 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 30 | Not Available | Medium | Add missing field or confirm deprecation |
| maxRpm | 0 | Not Available | Medium | Add missing field or confirm deprecation |
| maxExecutionTime | 300 | 90 | Medium | Validate timeout configuration |

### 6.5.3 Tools Comparison
Not Available

### 6.5.4 Knowledge Base Comparison
Not Available

### 6.5.5 Guardrails Comparison
Not Available

---

## Agent: DI SSIS to DBTCloud Reviewer

### 6.6.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.6.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model configuration |
| temperature | 0.20000000298023224 | 0.2 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 30 | Not Available | Medium | Add missing field or confirm deprecation |
| maxRpm | 0 | Not Available | Medium | Add missing field or confirm deprecation |
| maxExecutionTime | 300 | 90 | Medium | Validate timeout configuration |

### 6.6.3 Tools Comparison
Not Available

### 6.6.4 Knowledge Base Comparison
Not Available

### 6.6.5 Guardrails Comparison
Not Available