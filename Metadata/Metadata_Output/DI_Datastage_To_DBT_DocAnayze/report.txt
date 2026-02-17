# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 78%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI DataStage Documentation | 85% | Low | Model configs matched, temperature matched, maxExecutionTime reduced | Validate reduced execution time impact |
| DI DataStage To DBT Analyzer | 72% | Medium | Model configs matched, role/goal/backstory removed, maxExecutionTime reduced | Confirm instruction field removal acceptable |
| DI DataStage To DBT Plan | 78% | Medium | Model configs matched, role/goal/backstory removed, maxExecutionTime reduced | Confirm instruction field removal acceptable |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_Datastage_To_DBT_Doc&Anayze
**Workflow Name (AAVA 2.0):** DI Datastage To DBT Doc&Anayze

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 7758 | id | 2481 | Renamed + Modified | Field renamed and value changed | Medium | Update downstream references |
| Naming | name | DI_Datastage_To_DBT_Doc&Anayze | name | DI Datastage To DBT Doc&Anayze | Matched (Normalized) | Minor formatting differences | Low | None |
| Description | description | DESCRIPTION: The DI_DataStage_to_dbt_Analyzer agent... | description | DESCRIPTION: The DI_DataStage_to_dbt_Analyzer agent... | Matched | Same content | Low | None |
| Audit | createdAt | 2025-10-24T03:43:24.856+00:00 | createdAt | 2025-11-05T11:01:18.662382 | Modified | Different timestamp | Low | Expected for different instances |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Enhanced configuration structure | Medium | Align configuration handling |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Update memory configuration access |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Implement alternative org tracking |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | High | Implement alternative org tracking |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | High | Implement alternative domain tracking |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | High | Implement alternative domain tracking |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | High | Implement alternative project tracking |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | High | Implement alternative project tracking |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | High | Implement alternative team tracking |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | High | Implement alternative team tracking |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Implement alternative level tracking |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Implement user tracking |
| modifiedBy | User who last modified | elansuriyaa.p@ascendion.com | Medium | Implement modification tracking |
| approvedBy | User who approved workflow | elansuriyaa.p@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Implement modification tracking |
| approvedAt | Approval timestamp | 2025-11-05T11:01:19.727655 | Medium | Implement approval workflow |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete handling |
| parentId | Parent workflow reference | -1 | Low | Handle workflow hierarchy |
| realmId | Realm identifier | 32 | Medium | Implement realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align configuration structure |
| managerLlm | Not available | Empty object in workflowConfigs | Medium | Configure manager LLM settings |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update memory configuration access |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_DataStage_Documentation | DI DataStage Documentation | Renamed | Underscore to space conversion |
| DI_DataStage_To_DBT_Analyzer | DI DataStage To DBT Analyzer | Renamed | Underscore to space conversion |
| DI_DataStage_To_DBT_Plan | DI DataStage To DBT Plan | Renamed | Underscore to space conversion |

---

## 6. Agent Configuration Differences

## Agent: DI DataStage Documentation

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.20000000298023224 | 0.2 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 30 | Not Present | Medium | Add missing field or confirm removal |
| maxRpm | 0 | Not Present | Medium | Add missing field or confirm removal |
| maxExecutionTime | 300 | 90 | Medium | Validate reduced execution time |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Present | Low | No change |
| userTools | [DI_GitHub_File_Reader_Z] | Not Present | High | Restore user tools configuration |
| toolReferences | Not Available | [] | Medium | Validate new tool reference structure |

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI DataStage To DBT Analyzer

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
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.20000000298023224 | 0.2 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 30 | Not Present | Medium | Add missing field or confirm removal |
| maxRpm | 0 | Not Present | Medium | Add missing field or confirm removal |
| maxExecutionTime | 300 | 90 | Medium | Validate reduced execution time |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Present | Low | No change |
| userTools | [DI_GitHub_File_Reader_Z] | Not Present | High | Restore user tools configuration |
| toolReferences | Not Available | [] | Medium | Validate new tool reference structure |

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DI DataStage To DBT Plan

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
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.20000000298023224 | 0.2 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 30 | Not Present | Medium | Add missing field or confirm removal |
| maxRpm | 0 | Not Present | Medium | Add missing field or confirm removal |
| maxExecutionTime | 300 | 90 | Medium | Validate reduced execution time |

### 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Present | Low | No change |
| userTools | [DI_GitHub_File_Reader_Z] | Not Present | High | Restore user tools configuration |
| toolReferences | Not Available | [] | Medium | Validate new tool reference structure |

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available

**CSV file has been successfully uploaded to GitHub at:** Metadata/Metadata_Output/DI_Datastage_To_DBT_DocAnayze/DI_Datastage_To_DBT_DocAnayze_comparison.csv

**Tool Response:** ✅ File uploaded successfully to GitHub: Metadata/Metadata_Output/DI_Datastage_To_DBT_DocAnayze/DI_Datastage_To_DBT_DocAnayze_comparison.csv