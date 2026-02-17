# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 73%**
**Total Agents Compared: 3**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI DataStage Documentation | 68% | Medium | role/goal/backstory removed, expectedOutput modified, maxExecutionTime reduced | Validate instruction completeness and runtime behavior |
| DI DataStage to PySpark Analyzer | 76% | Medium | role/goal/backstory removed, name normalized, maxExecutionTime reduced | Confirm instruction field removal is acceptable |
| DI DataStage to PySpark Plan | 78% | Medium | role/goal/backstory removed, maxExecutionTime reduced | Validate runtime configuration changes |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_DataStage_To_PySpark_Doc&Analysis
**Workflow Name (AAVA 2.0):** DI DataStage To PySpark Doc&Analysis

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 5501 | id | 2056 | Renamed + Modified | Pipeline ID changed from 5501 to 2056 | High | Update all references to workflow ID |
| Naming | name | DI_DataStage_To_PySpark_Doc&Analysis | name | DI DataStage To PySpark Doc&Analysis | Matched (Normalized) | Naming convention normalized (underscores to spaces) | Low | No change |
| Description | description | DI_DataStage_To_PySpark_Doc&Analysis | description | DI_DataStage_To_PySpark_Doc&Analysis | Matched | Description unchanged | Low | No change |
| Audit | createdAt | 2025-07-24T09:07:36.253+00:00 | createdAt | 2025-11-05T10:45:25.637719 | Modified | Creation timestamp updated | Medium | Validate audit trail consistency |
| Agents List | pipeLineAgents | Array[3] | workflowAgents | Array[3] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Empty callbacks replaced with structured config | Medium | Align workflow configuration handling |
| Memory Config | enableAgenticMemory | false | workflowConfigs.enableAgenticMemory | false | Renamed + Matched (Normalized) | Moved to nested config structure | Low | Update configuration path |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm removal is acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm removal is acceptable |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal is acceptable |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm removal is acceptable |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal is acceptable |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm removal is acceptable |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm removal is acceptable |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm removal is acceptable |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | kiran.krishnakumar@ascendion.com | Medium | Ensure user attribution is handled |
| modifiedBy | User who last modified workflow | kiran.krishnakumar@ascendion.com | Medium | Implement modification tracking |
| approvedBy | User who approved workflow | kiran.krishnakumar@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is handled |
| approvedAt | Approval timestamp | 2025-11-05T10:45:26.830690 | Medium | Implement approval tracking |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Implement soft delete handling |
| parentId | Parent workflow reference | -1 | Low | Handle workflow hierarchy |
| realmId | Realm/tenant identifier | 32 | Medium | Ensure multi-tenancy is handled |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align configuration structure |
| managerLlm | Not available | Empty object array | Medium | Implement manager LLM configuration |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Low | Update configuration path |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents with naming normalization

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_DataStage_Documentation | DI DataStage Documentation | Renamed | Naming convention normalized (underscores to spaces) |
| DI_DataStage_to_PySpark_Analyzer | DI DataStage to PySpark Analyzer | Renamed | Naming convention normalized (underscores to spaces) |
| DI_DataStage_to_PySpark_Plan | DI DataStage to PySpark Plan | Renamed | Naming convention normalized (underscores to spaces) |

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
| model | gpt-4 | model | Medium | Validate model name mapping |
| temperature | 0.20000000298023224 | 0.2 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | No change (normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 30 | Not Present | Medium | Validate iteration limit handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limit handling |
| maxExecutionTime | 300 | 90 | High | Validate reduced execution time impact |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Present | Low | No change |
| userTools | [DI_GitHub_File_Reader_Z] | Not Present | High | Validate tool removal impact |

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: DI DataStage to PySpark Analyzer

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
| model | gpt-4 | model | Medium | Validate model name mapping |
| temperature | 0.20000000298023224 | 0.2 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | No change (normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 30 | Not Present | Medium | Validate iteration limit handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limit handling |
| maxExecutionTime | 300 | 90 | High | Validate reduced execution time impact |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Present | Low | No change |
| userTools | [] | Not Present | Low | No change |

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: DI DataStage to PySpark Plan

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
| model | gpt-4 | model | Medium | Validate model name mapping |
| temperature | 0.20000000298023224 | 0.2 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | No change (normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 30 | Not Present | Medium | Validate iteration limit handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limit handling |
| maxExecutionTime | 300 | 90 | High | Validate reduced execution time impact |

### 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Present | Low | No change |
| userTools | [] | Not Present | Low | No change |

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available

Now I need to create the CSV file with the required format:

Action: GitHub File Writer Tool
Action Input: {"repo": "ELANSURIYAA/AAVA_Testing", "branch": "main", "token": "<REDACTED_GITHUB_TOKEN>", "folder_name": "Metadata/Metadata_Output", "file_name": "DI_DataStage_To_PySpark_DocAnalysis/DI_DataStage_To_PySpark_DocAnalysis_comparison.csv", "content": "Workflow Comparison Score,Total Agents Compared
73%,3

Agent Name,Agent Score,Risk Level,Key Score Drivers,Migration Action Required
DI DataStage Documentation,68%,Medium,role/goal/backstory removed; expectedOutput modified; maxExecutionTime reduced,Validate instruction completeness and runtime behavior
DI DataStage to PySpark Analyzer,76%,Medium,role/goal/backstory removed; name normalized; maxExecutionTime reduced,Confirm instruction field removal is acceptable
DI DataStage to PySpark Plan,78%,Medium,role/goal/backstory removed; maxExecutionTime reduced,Validate runtime configuration changes"}