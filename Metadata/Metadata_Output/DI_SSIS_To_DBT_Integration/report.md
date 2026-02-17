# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 72%
**Total Agents Compared:** 1

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI SSIS To DBT Fivetran | 72% | Medium | role/goal/backstory removed, model changed, maxIter/maxRpm nullified | Validate instruction completeness and runtime behavior |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_SSIS_To_DBT_Integration
**Workflow Name (AAVA 2.0):** DI SSIS To DBT Integration

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 4976 | id | 2034 | Renamed + Modified | Field renamed and ID value changed | High | Update references to new workflow ID |
| Naming | name | DI_SSIS_To_DBT_Integration | name | DI SSIS To DBT Integration | Matched (Case Normalization) | Minor formatting difference in name | Low | No change |
| Description | description | This will convert the SSIS to DBT | description | This will convert the SSIS to DBT | Matched | Same description | Low | No change |
| Audit | createdAt | 2025-09-23T16:32:44.204+00:00 | createdAt | 2025-11-05T10:44:35.842097 | Modified | Different creation timestamp | Medium | Validate workflow versioning |
| Agents List | pipeLineAgents | Present | workflowAgents | Present | Renamed + Matched (Normalized) | Field renamed but agents present | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | Present | Renamed + Modified | Field renamed and structure changed | Medium | Align configuration structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Check workflowConfigs.enableAgenticMemory |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | Medium | Confirm removal acceptable |
| Domain Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal acceptable |
| Project Metadata | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | karthikeyan.iyappan@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified | karthikeyan.iyappan@ascendion.com | Medium | Ensure modification tracking |
| approvedBy | User who approved workflow | karthikeyan.iyappan@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T10:44:37.040915 | Low | Standard audit field |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle handling |
| isDeleted | Soft delete flag | false | Low | Standard deletion handling |
| parentId | Parent workflow reference | -1 | Low | Workflow hierarchy support |
| realmId | Realm identifier | 1 | Low | Multi-tenancy support |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm | Medium | Align configuration defaults |
| enableAgenticMemory | Top-level field (false) | Nested in workflowConfigs (false) | Medium | Update configuration access path |
| callbacks | Empty array | Not available | Low | Confirm callback removal acceptable |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 1
**AAVA 2.0 total agents:** 1
**Coverage:** Same agent count

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_SSIS_To_DBT_Fivetran | DI SSIS To DBT Fivetran | Matched (Case Normalization) | Minor formatting difference |

---

## 6. Agent Configuration Differences

## Agent: DI SSIS To DBT Fivetran

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility and performance |
| model | gemini-2.5-pro | model | High | Update model reference |
| temperature | 0.20000000298023224 | 0.2 | Matched (Normalized) | No change |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change |
| maxToken | 8000 | 8000 | Matched | No change |
| maxIter | 30 | null | Modified | Validate iteration limits |
| maxRpm | 100 | null | Modified | Validate rate limiting |
| maxExecutionTime | 1800 | 90 | Modified | Validate timeout settings |
| allowDelegation | true | true | Matched | No change |
| allowCodeExecution | false | false | Matched | No change |
| isSafeCodeExecution | true | true | Matched | No change |

---

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Available | Low | Confirm empty tools acceptable |
| userTools | 3 tools present | Not Available | High | Migrate tool configurations |
| DI_Github_File_Writer_Z | Present | Not Available | High | Ensure tool availability |
| DI_Fivetran_DBT_API_Trigger_Tool | Present | Not Available | High | Ensure tool availability |
| DI_GitHub_File_Reader_Z | Present | Not Available | High | Ensure tool availability |
| toolReferences | Not Available | [] | Low | New tool reference structure |

---

### 6.1.4 Knowledge Base Comparison

Not Available

---

### 6.1.5 Guardrails Comparison

Not Available