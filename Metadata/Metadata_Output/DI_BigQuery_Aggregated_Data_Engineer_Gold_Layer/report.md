# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 78%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI BigQuery Gold Aggregated DE Pipeline | 75% | Medium | model changed (gemini-2.5-pro to gpt-4.1), role/goal/backstory removed, tools removed | Validate model compatibility and confirm instruction field removal |
| DI BigQuery Unit Test Case | 82% | Medium | model changed (gemini-2.5-pro to gpt-4.1), role/goal/backstory removed, tools removed | Validate model compatibility and confirm instruction field removal |
| DI BigQuery DE Pipeline Reviewer | 77% | Medium | model changed (gemini-2.5-pro to gpt-4.1), role/goal/backstory removed, embedding removed | Validate model compatibility and confirm instruction field removal |

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_BigQuery_Aggregated_Data_Engineer_Gold_Layer
**Workflow Name (AAVA 2.0):** DI BigQuery Aggregated Data Engineer Gold Layer

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 8002 | id | 2540 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to use new ID |
| Naming | name | DI_BigQuery_Aggregated_Data_Engineer_Gold_Layer | name | DI BigQuery Aggregated Data Engineer Gold Layer | Matched (Normalized) | Name normalized (underscores to spaces) | Low | No change needed |
| Description | description | BigQuery Gold aggregated layer pipeline | description | BigQuery Gold aggregated layer pipeline | Matched | Identical values | Low | No change needed |
| Audit | createdAt | 2025-11-03T18:07:50.573+00:00 | createdAt | 2025-11-05T11:03:23.351855 | Modified | Different creation timestamps | Low | Expected for different instances |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure enhanced | Medium | Align configuration structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Update configuration access |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Confirm removal is acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | High | Confirm removal is acceptable |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | High | Confirm removal is acceptable |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | High | Confirm removal is acceptable |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | High | Confirm removal is acceptable |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | High | Confirm removal is acceptable |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | High | Confirm removal is acceptable |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | High | Confirm removal is acceptable |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | High | Confirm removal is acceptable |

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | karthikeyan.iyappan@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified | karthikeyan.iyappan@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | karthikeyan.iyappan@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T11:03:24.432066 | Low | Standard audit field |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure deletion handling is implemented |
| parentId | Parent workflow reference | -1 | Low | Standard hierarchy field |
| realmId | Realm identifier | 1 | Medium | Ensure realm-based access control |

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align configuration structure |
| managerLlm | Not available | Empty object in workflowConfigs | Medium | Define manager LLM configuration |
| enableAgenticMemory | Top-level field (false) | Nested in workflowConfigs (false) | Medium | Update configuration access path |

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_BigQuery_Gold_Aggregated_DE_Pipeline | DI BigQuery Gold Aggregated DE Pipeline | Renamed | Naming convention updated (underscores to spaces) |
| DI_BigQuery_Unit_Test_Case | DI BigQuery Unit Test Case | Renamed | Naming convention updated (underscores to spaces) |
| DI_BigQuery_DE_Pipeline_Reviewer | DI BigQuery DE Pipeline Reviewer | Renamed | Naming convention updated (underscores to spaces) |

## 6. Agent Configuration Differences

### Agent: DI BigQuery Gold Aggregated DE Pipeline

#### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Not Present | Not Present | Low | No change |

#### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility and performance |
| model | gemini-2.5-pro | model | High | Validate model compatibility and performance |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change needed |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change needed |
| maxToken | 64000 | 64000 | Matched | No change needed |
| maxIter | 0 | null | Modified | Validate null handling vs zero |
| maxRpm | 0 | null | Modified | Validate null handling vs zero |
| maxExecutionTime | 0 | 90 | Modified | Validate timeout configuration change |

#### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Available | Medium | Confirm tools removal is acceptable |
| userTools | [DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z] | [] | High | Validate tool removal impact on functionality |

#### 6.1.4 Knowledge Base Comparison

Not Available

#### 6.1.5 Guardrails Comparison

Not Available

### Agent: DI BigQuery Unit Test Case

#### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

#### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility and performance |
| model | gemini-2.5-pro | model | High | Validate model compatibility and performance |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change needed |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change needed |
| maxToken | 64000 | 64000 | Matched | No change needed |
| maxIter | 0 | null | Modified | Validate null handling vs zero |
| maxRpm | 0 | null | Modified | Validate null handling vs zero |
| maxExecutionTime | 0 | 90 | Modified | Validate timeout configuration change |

#### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Available | Low | No change needed |
| userTools | [] | [] | Matched | No change needed |

#### 6.2.4 Knowledge Base Comparison

Not Available

#### 6.2.5 Guardrails Comparison

Not Available

### Agent: DI BigQuery DE Pipeline Reviewer

#### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

#### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility and performance |
| model | gemini-2.5-pro | model | High | Validate model compatibility and performance |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change needed |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change needed |
| maxToken | 64000 | 64000 | Matched | No change needed |
| maxIter | 0 | null | Modified | Validate null handling vs zero |
| maxRpm | 0 | null | Modified | Validate null handling vs zero |
| maxExecutionTime | 0 | 90 | Modified | Validate timeout configuration change |

#### 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Available | Low | No change needed |
| userTools | [] | [] | Matched | No change needed |

#### 6.3.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present (AzureOpenAI configuration) | Not Available | High | Validate knowledge base removal impact |

#### 6.3.5 Guardrails Comparison

Not Available

**Report Generated:** CSV file successfully uploaded to GitHub repository at `Metadata/Metadata_Output/DI_BigQuery_Aggregated_Data_Engineer_Gold_Layer/DI_BigQuery_Aggregated_Data_Engineer_Gold_Layer_comparison.csv`