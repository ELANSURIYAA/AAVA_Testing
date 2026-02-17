# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 87%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI SAS Documentation | 89% | Low | Model deployment changed from gemini-2.5-pro to gpt-4.1, role/goal/backstory removed, maxToken reduced from 64000 to 64000 | Validate model performance and confirm instruction field removal |
| Sas to Python Analyzer | 92% | Low | Model configs matched, description matched, minor field restructuring | Minimal validation required |
| Sas to Python Plan | 91% | Low | Model configs matched, description matched, minor field restructuring | Minimal validation required |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_SAS_To_Python_Doc&Analyze
**Workflow Name (AAVA 2.0):** DI SAS To Python Doc&Analyze

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1442 | id | 2626 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | DI_SAS_To_Python_Doc&Analyze | name | DI SAS To Python Doc&Analyze | Matched (Normalized) | Minor formatting differences | Low | No change |
| Description | description | SAS to Python Documentation and Analyze. | description | SAS to Python Documentation and Analyze. | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-05-12T06:14:45.531+00:00 | createdAt | 2025-11-05T11:09:11.322885 | Modified | Different creation timestamps | Low | Expected for new workflow version |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm, enableAgenticMemory} | Renamed + Modified | Enhanced configuration structure | Medium | Migrate callback logic to new config |
| Memory Config | enableAgenticMemory | false | workflowConfigs.enableAgenticMemory | false | Renamed + Matched (Normalized) | Moved to nested config | Low | Update config path |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Confirm removal is acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | High | Confirm removal is acceptable |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | High | Confirm removal is acceptable |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | High | Confirm removal is acceptable |
| Project | project | Documenting | Not Available | Not Available | Removed | Project metadata removed | High | Confirm removal is acceptable |
| Project ID | projectId | 153 | Not Available | Not Available | Removed | Project ID removed | High | Confirm removal is acceptable |
| Team | team | DataEng | Not Available | Not Available | Removed | Team metadata removed | High | Confirm removal is acceptable |
| Team ID | teamId | 154 | Not Available | Not Available | Removed | Team ID removed | High | Confirm removal is acceptable |
| Level ID | levelId | 154 | Not Available | Not Available | Removed | Level ID removed | High | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T11:09:12.394326 | Low | Standard audit field |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Standard deletion handling |
| parentId | Parent workflow reference | -1 | Low | Workflow hierarchy support |
| realmId | Realm/tenant identifier | 1 | Medium | Multi-tenancy support |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| managerLlm | Direct object | Nested in workflowConfigs | Medium | Update config access patterns |
| callbacks | Empty array | Not available | Low | Migrate callback logic if needed |
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align with new config structure |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_SAS_Documentation | DI SAS Documentation | Renamed | Underscore to space conversion |
| Sas_to_Python_Analyzer | Sas to Python Analyzer | Renamed | Underscore to space conversion |
| Sas_to_Python_Plan | Sas to Python Plan | Renamed | Underscore to space conversion |

---

## 6. Agent Configuration Differences

## Agent: DI SAS Documentation

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model performance equivalence |
| model | gemini-2.5-pro | model | High | Update model reference |
| temperature | 0.20000000298023224 | 0.2 | Low | Normalized precision |
| topP | 0.949999988079071 | 0.94 | Low | Minor precision difference |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | Not Present | Low | Field moved to agentDetails |
| maxRpm | 0 | Not Present | Low | Field moved to agentDetails |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: Sas to Python Analyzer

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Update model reference |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision |
| topP | 0.949999988079071 | 0.94 | Low | Minor precision difference |
| maxToken | 8000 | 8000 | Low | No change |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: Sas to Python Plan

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Update model reference |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision |
| topP | 0.949999988079071 | 0.94 | Low | Minor precision difference |
| maxToken | 8000 | 8000 | Low | No change |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available

The CSV file has been successfully uploaded to GitHub at: Metadata/Metadata_Output/DI_SAS_To_Python_DocAnalyze/DI_SAS_To_Python_DocAnalyze_comparison.csv