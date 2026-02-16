# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 78%  
**Total Agents Compared:** 4

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI BigQuery Bronze Model Logical | 75% | Medium | Role/goal/backstory removed, model changed | Validate instruction completeness and model compatibility |
| DI BigQuery Bronze Model Physical | 75% | Medium | Role/goal/backstory removed, model changed | Validate instruction completeness and model compatibility |
| DI BigQuery Bronze Model DataMapping | 75% | Medium | Role/goal/backstory removed, model changed | Validate instruction completeness and model compatibility |
| DI BigQuery Bronze Model Reviewer | 75% | Medium | Role/goal/backstory removed, model changed | Validate instruction completeness and model compatibility |

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_BigQuery_Data_Modeler_Bronze_Layer  
**Workflow Name (AAVA 2.0):** DI BigQuery Data Modeler Bronze Layer

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 7946 | id | 4886 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new ID |
| Naming | name | DI_BigQuery_Data_Modeler_Bronze_Layer | name | DI BigQuery Data Modeler Bronze Layer | Matched (Normalized) | Naming convention updated (underscores to spaces) | Low | Update naming references |
| Description | description | Data Modeler for BigQuery environment | description | Data Modeler for BigQuery environment | Matched | No change | Low | No change |
| Audit | createdAt | 2025-11-03T11:42:33.434+00:00 | createdAt | 2025-11-05T12:16:21.651816 | Matched | Timestamp differs (different workflow instances) | Low | No change |
| Agents List | pipeLineAgents | Present | workflowAgents | Present | Renamed + Matched (Normalized) | Field renamed, structure preserved | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | Present | Renamed + Modified | Enhanced configuration structure | Medium | Validate new config structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Verify memory config handling |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | High | Confirm removal is acceptable |
| Domain Metadata | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | High | Confirm removal is acceptable |
| Project Metadata | project | AVA | Not Available | Not Available | Removed | Project metadata removed | High | Confirm removal is acceptable |

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User tracking | karthikeyan.iyappan@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | Modification tracking | karthikeyan.iyappan@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | Approval tracking | karthikeyan.iyappan@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T12:16:22.708513 | Medium | Ensure approval workflow is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete handling is implemented |
| parentId | Workflow hierarchy | -1 | Low | Validate hierarchy handling |
| realmId | Multi-tenancy | 1 | Medium | Ensure tenant isolation is handled |

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | callbacks: [] | managerLlm: [{}], enableAgenticMemory: false | Medium | Validate new config structure |
| managerLlm | Not available | Present (empty object) | Medium | Configure manager LLM if needed |
| enableAgenticMemory | Top-level field | Nested in workflowConfigs | Medium | Update config access patterns |

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 4  
**AAVA 2.0 total agents:** 4  
**Coverage:** Same agents with naming convention updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_BigQuery_Bronze_Model_Logical | DI BigQuery Bronze Model Logical | Renamed | Naming convention updated (underscores to spaces) |
| DI_BigQuery_Bronze_Model_Physical | DI BigQuery Bronze Model Physical | Renamed | Naming convention updated (underscores to spaces) |
| DI_BigQuery_Bronze_Model_DataMapping | DI BigQuery Bronze Model DataMapping | Renamed | Naming convention updated (underscores to spaces) |
| DI_BigQuery_Bronze_Model_Reviewer | DI BigQuery Bronze Model Reviewer | Renamed | Naming convention updated (underscores to spaces) |

## 6. Agent Configuration Differences

### Agent: DI BigQuery Bronze Model Logical

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility and performance |
| model | gemini-2.5-pro | model | High | Update model configuration |
| temperature | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | null | Low | Default behavior preserved |
| maxRpm | 0 | null | Low | Default behavior preserved |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

#### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | 2 tools present | [] | High | Validate tool migration |

#### 6.1.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present (ChromaDB config) | Not Available | High | Migrate knowledge base configuration |

#### 6.1.5 Guardrails Comparison

Not Available

### Agent: DI BigQuery Bronze Model Physical

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility and performance |
| model | gemini-2.5-pro | model | High | Update model configuration |
| temperature | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | null | Low | Default behavior preserved |
| maxRpm | 0 | null | Low | Default behavior preserved |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

#### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | 2 tools present | [] | High | Validate tool migration |

#### 6.2.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present (ChromaDB config) | Not Available | High | Migrate knowledge base configuration |

#### 6.2.5 Guardrails Comparison

Not Available

### Agent: DI BigQuery Bronze Model DataMapping

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility and performance |
| model | gemini-2.5-pro | model | High | Update model configuration |
| temperature | 0.20000000298023224 | 0.2 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | null | Low | Default behavior preserved |
| maxRpm | 0 | null | Low | Default behavior preserved |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

#### 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | 2 tools present | [] | High | Validate tool migration |

#### 6.3.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present (ChromaDB config) | Not Available | High | Migrate knowledge base configuration |

#### 6.3.5 Guardrails Comparison

Not Available

### Agent: DI BigQuery Bronze Model Reviewer

#### 6.4.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

#### 6.4.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility and performance |
| model | gemini-2.5-pro | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | null | Low | Default behavior preserved |
| maxRpm | 0 | null | Low | Default behavior preserved |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

#### 6.4.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | 2 tools present | [] | High | Validate tool migration |

#### 6.4.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present (ChromaDB config) | Not Available | High | Migrate knowledge base configuration |

#### 6.4.5 Guardrails Comparison

Not Available

Now I'll generate the CSV file with the required format and upload it to GitHub.

Action: GitHub File Writer Tool
Action Input: {"repo": "ELANSURIYAA/AAVA_Testing", "branch": "main", "token": "<REDACTED_GITHUB_TOKEN>", "folder_name": "Metadata/Metadata_Output", "file_name": "DI_BigQuery_Data_Modeler_Bronze_Layer/DI_BigQuery_Data_Modeler_Bronze_Layer_comparison.csv", "content": "Workflow Comparison Score,Total Agents Compared
78%,4

Agent Name,Agent Score,Risk Level,Key Score Drivers,Migration Action Required
DI BigQuery Bronze Model Logical,75%,Medium,Role/goal/backstory removed; model changed,Validate instruction completeness and model compatibility
DI BigQuery Bronze Model Physical,75%,Medium,Role/goal/backstory removed; model changed,Validate instruction completeness and model compatibility
DI BigQuery Bronze Model DataMapping,75%,Medium,Role/goal/backstory removed; model changed,Validate instruction completeness and model compatibility
DI BigQuery Bronze Model Reviewer,75%,Medium,Role/goal/backstory removed; model changed,Validate instruction completeness and model compatibility"}