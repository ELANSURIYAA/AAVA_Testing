# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 73%**
**Total Agents Compared: 3**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_BigQuery_Gold_Model_Logical | 68% | Medium | role/goal/backstory removed, model changed | Validate agent behavior without role/goal/backstory |
| DI_BigQuery_Gold_Model_Physical | 68% | Medium | role/goal/backstory removed, model changed | Validate agent behavior without role/goal/backstory |
| DI_BigQuery_Gold_Model_Reviewer | 68% | Medium | role/goal/backstory removed, model changed | Validate agent behavior without role/goal/backstory |

---

**Workflow Name (AAVA 1.0):** DI_BigQuery_Data_Modeler_Gold_Layer
**Workflow Name (AAVA 2.0):** DI BigQuery Data Modeler Gold Layer

## 2. Workflow-Level Comparison

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 7960 | id | 4963 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new ID |
| Naming | name | DI_BigQuery_Data_Modeler_Gold_Layer | name | DI BigQuery Data Modeler Gold Layer | Matched (Normalized) | Spacing normalized | Low | No change needed |
| Description | description | Data Modeler for BigQuery | description | Data Modeler for BigQuery | Matched | Identical values | Low | No change needed |
| Audit | createdAt | 2025-11-02T10:56:01.177+00:00 | createdAt | 2025-11-05T12:18:40.892758 | Modified | Different timestamps | Low | Expected for new workflow |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure changed | High | Validate new config structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Check workflowConfigs.enableAgenticMemory |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm org tracking not needed |
| Domain Metadata | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm domain tracking not needed |
| Project Metadata | project | AVA | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm project tracking not needed |

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | tejas.kharche@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified | tejas.kharche@ascendion.com | Medium | Ensure modification tracking works |
| approvedBy | User who approved workflow | tejas.kharche@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T12:18:41.951922 | Low | Standard audit field |
| status | Workflow approval state | APPROVED | High | Ensure workflow lifecycle management |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete handling |
| parentId | Parent workflow reference | -1 | Medium | Understand workflow hierarchy |

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm | High | Configure manager LLM settings |
| enableAgenticMemory | Top-level field | Nested in workflowConfigs | Medium | Update configuration access |
| callbacks | Empty array | Not present | Low | Confirm callback handling not needed |

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agent count, naming convention updated

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_BigQuery_Gold_Model_Logical | DI BigQuery Gold Model Logical | Renamed | Underscore to space conversion |
| DI_BigQuery_Gold_Model_Physical | DI BigQuery Gold Model Physical | Renamed | Underscore to space conversion |
| DI_BigQuery_Gold_Model_Reviewer | DI BigQuery Gold Model Reviewer | Renamed | Underscore to space conversion |

## 6. Agent Configuration Differences

### Agent: DI BigQuery Gold Model Logical

#### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

#### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility |
| model | gemini-2.5-pro | model | High | Update model configuration |
| temperature | 0.20000000298023224 | 0.2 | Low | Normalized precision |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | null | Low | Equivalent values |
| maxRpm | 0 | null | Low | Equivalent values |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout increase |

#### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | [DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z] | [] | High | Validate tool removal impact |

#### 6.1.4 Knowledge Base Comparison

Not Available

#### 6.1.5 Guardrails Comparison

Not Available

### Agent: DI BigQuery Gold Model Physical

#### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

#### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility |
| model | gemini-2.5-pro | model | High | Update model configuration |
| temperature | 0.20000000298023224 | 0.2 | Low | Normalized precision |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | null | Low | Equivalent values |
| maxRpm | 0 | null | Low | Equivalent values |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout increase |

#### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | [DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z] | [] | High | Validate tool removal impact |

#### 6.2.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | [AzureOpenAI config] | Not Available | High | Validate knowledge base removal |

#### 6.2.5 Guardrails Comparison

Not Available

### Agent: DI BigQuery Gold Model Reviewer

#### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

#### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility |
| model | gemini-2.5-pro | model | High | Update model configuration |
| temperature | 0.20000000298023224 | 0.2 | Low | Normalized precision |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | null | Low | Equivalent values |
| maxRpm | 0 | null | Low | Equivalent values |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout increase |

#### 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | [DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z] | [] | High | Validate tool removal impact |

#### 6.3.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | [AzureOpenAI config] | Not Available | High | Validate knowledge base removal |

#### 6.3.5 Guardrails Comparison

Not Available

Now I need to create the CSV file with the required format:

Action: GitHub File Writer Tool
Action Input: {"repo": "ELANSURIYAA/AAVA_Testing", "branch": "main", "token": "<REDACTED_GITHUB_TOKEN>", "folder_name": "Metadata/Metadata_Output", "file_name": "DI_BigQuery_Data_Modeler_Gold_Layer/DI_BigQuery_Data_Modeler_Gold_Layer_comparison.csv", "content": "Workflow Comparison Score,Total Agents Compared
73%,3

Agent Name,Agent Score,Risk Level,Key Score Drivers,Migration Action Required
DI BigQuery Gold Model Logical,68%,Medium,role/goal/backstory removed; model changed,Validate agent behavior without role/goal/backstory
DI BigQuery Gold Model Physical,68%,Medium,role/goal/backstory removed; model changed,Validate agent behavior without role/goal/backstory
DI BigQuery Gold Model Reviewer,68%,Medium,role/goal/backstory removed; model changed,Validate agent behavior without role/goal/backstory"}