# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 78.3%**
**Total Agents Compared: 3**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_AbInitio_Documentation | 72.1% | Medium | role/goal/backstory removed, model changed, expectedOutput format modified | Validate agent behavior without role/goal/backstory fields |
| DI_AbInitio_To_PySpark_EMR_Glue_Analyzer | 84.6% | Medium | role/goal/backstory removed, description matched, model deployment changed | Confirm model deployment compatibility |
| DI_AbInitio_To_PySpark_EMR_Glue_Plan | 78.2% | Medium | role/goal/backstory removed, model configs modified, description matched | Test agent functionality with new model configuration |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_AbInitio_To_PySpark_EMR_Glue_Doc&Analyze
**Workflow Name (AAVA 2.0):** DI AbInitio To PySpark EMR Glue Doc&Analyze

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 8573 | id | 8479 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_AbInitio_To_PySpark_EMR_Glue_Doc&Analyze | name | DI AbInitio To PySpark EMR Glue Doc&Analyze | Matched (Normalized) | Minor formatting differences | Low | No change |
| Description | description | Analyzing and Documenting the Abinitio Code | description | Analyzing and Documenting the Abinitio Code | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-12-15T05:32:13.282+00:00 | createdAt | 2026-01-16T05:31:23.502392 | Matched | Different timestamp as expected | Low | No change |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm, enableAgenticMemory} | Renamed + Modified | Enhanced configuration structure | Medium | Align configuration handling |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Low | Update configuration access |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm removal is acceptable |
| Domain Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal is acceptable |
| Project Metadata | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User audit trail | nishanth.janarthanan@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | Modification audit trail | nishanth.janarthanan@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | Approval audit trail | nishanth.janarthanan@ascendion.com | Medium | Ensure approval workflow is handled |
| modifiedAt | Modification timestamp | 2026-01-16T11:06:11.312693 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2026-01-16T05:31:25.305308 | Low | Standard audit field |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Standard deletion handling |
| parentId | Workflow hierarchy | -1 | Low | Standard hierarchy field |
| realmId | Multi-tenancy support | 1 | Medium | Ensure tenant isolation is handled |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|---------|-----------------|
| workflowConfigs | Not available | Present with managerLlm array | Medium | Align configuration structure |
| managerLlm | Direct object | Array of objects with ID | High | Update LLM configuration handling |
| enableAgenticMemory | Top-level field | Nested in workflowConfigs | Low | Update configuration access path |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents maintained

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_AbInitio_Documentation | DI_AbInitio_Documentation | Matched | Exact match |
| DI_AbInitio_To_PySpark_EMR_Glue_Analyzer | DI_AbInitio_To_PySpark_EMR_Glue_Analyzer | Matched | Exact match |
| DI_AbInitio_To_PySpark_EMR_Glue_Plan | DI_AbInitio_To_PySpark_EMR_Glue_Plan | Matched | Exact match |

---

## 6. Agent Configuration Differences

## Agent: DI_AbInitio_Documentation

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | anthropic.claude-4-sonnet | model | High | Update model reference |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Confirm removal is acceptable |
| maxRpm | 0 | Not Present | Medium | Confirm removal is acceptable |
| maxExecutionTime | 0 | Not Present | Medium | Confirm removal is acceptable |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: DI_AbInitio_To_PySpark_EMR_Glue_Analyzer

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | anthropic.claude-4-sonnet | model | High | Update model reference |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Confirm removal is acceptable |
| maxRpm | 0 | Not Present | Medium | Confirm removal is acceptable |
| maxExecutionTime | 0 | Not Present | Medium | Confirm removal is acceptable |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: DI_AbInitio_To_PySpark_EMR_Glue_Plan

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | anthropic.claude-4-sonnet | model | High | Update model reference |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Confirm removal is acceptable |
| maxRpm | 0 | Not Present | Medium | Confirm removal is acceptable |
| maxExecutionTime | 0 | Not Present | Medium | Confirm removal is acceptable |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available