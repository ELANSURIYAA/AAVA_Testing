# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 73%**
**Total Agents Compared: 3**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_BigQuery_Gold_Fact_DE_Pipeline | 68% | Medium | Role/goal/backstory removed, model changed, GitHub tools removed | Validate instruction completeness and tool availability |
| DI_BigQuery_Unit_Test_Case | 72% | Medium | Role/goal/backstory removed, model changed, tools removed | Validate instruction completeness and tool availability |
| DI_BigQuery_DE_Pipeline_Reviewer | 79% | Medium | Role/goal/backstory removed, model changed, tools removed | Validate instruction completeness and tool availability |

---

**Workflow Name (AAVA 1.0):** DI_BigQuery_Fact_Data_Engineer_Gold_Layer
**Workflow Name (AAVA 2.0):** DI BigQuery Fact Data Engineer Gold Layer

## 2. Workflow-Level Comparison

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 8001 | id | 2539 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to use new ID |
| Naming | name | DI_BigQuery_Fact_Data_Engineer_Gold_Layer | name | DI BigQuery Fact Data Engineer Gold Layer | Matched (Case Normalization) | Minor formatting differences | Low | No change needed |
| Description | description | BigQuery Gold fact layer pipeline | description | BigQuery Gold fact layer pipeline | Matched | Values identical | Low | No change needed |
| Audit | createdAt | 2025-11-03T18:06:47.304+00:00 | createdAt | 2025-11-05T11:03:22.895867 | Modified | Creation timestamp changed | Low | Expected for new workflow instance |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed but agent count preserved | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Enhanced configuration structure | Medium | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Low | Check workflowConfigs.enableAgenticMemory |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Ensure org context is maintained elsewhere |
| Domain Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Ensure domain context is maintained elsewhere |
| Project Metadata | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Ensure project context is maintained elsewhere |
| Team Metadata | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Medium | Ensure team context is maintained elsewhere |

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | karthikeyan.iyappan@ascendion.com | Medium | Ensure user attribution is captured |
| modifiedBy | User who last modified workflow | karthikeyan.iyappan@ascendion.com | Medium | Implement modification tracking |
| approvedBy | User who approved workflow | karthikeyan.iyappan@ascendion.com | High | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Track modification history |
| approvedAt | Approval timestamp | 2025-11-05T11:03:23.973375 | High | Implement approval tracking |
| status | Workflow approval state | APPROVED | High | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete functionality |
| parentId | Parent workflow reference | -1 | Low | Handle workflow versioning |
| realmId | Realm/tenant identifier | 1 | Medium | Ensure multi-tenancy support |

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|---------|-----------------|
| workflowConfigs | callbacks: [] | managerLlm: [{}], enableAgenticMemory: false | Medium | Configure manager LLM settings |
| enableAgenticMemory | Top-level field: false | Nested in workflowConfigs: false | Low | Update configuration access path |

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_BigQuery_Gold_Fact_DE_Pipeline | DI BigQuery Gold Fact DE Pipeline | Renamed | Underscore to space conversion |
| DI_BigQuery_Unit_Test_Case | DI BigQuery Unit Test Case | Renamed | Underscore to space conversion |
| DI_BigQuery_DE_Pipeline_Reviewer | DI BigQuery DE Pipeline Reviewer | Renamed | Underscore to space conversion |

## 6. Agent Configuration Differences

### Agent: DI_BigQuery_Gold_Fact_DE_Pipeline

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
| model | gemini-2.5-pro | model | High | Update model reference |
| temperature | 0.30000001192092896 | 0.3 | Low | Values equivalent after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values equivalent after normalization |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | null | Low | Equivalent values |
| maxRpm | 0 | null | Low | Equivalent values |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout increased |
| allowDelegation | false | false | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

#### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| DI_Github_File_Writer_Z | Present | Not Available | High | Ensure GitHub write functionality is available |
| DI_GitHub_File_Reader_Z | Present | Not Available | High | Ensure GitHub read functionality is available |
| toolReferences | userTools (2 tools) | [] (empty) | High | Restore required tools or confirm removal |

#### 6.1.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present (AzureOpenAI config) | Not Available | High | Ensure knowledge base access is maintained |
| chroma_end_point | http://chromadb.da.svc.cluster.local | Not Available | High | Restore knowledge base connectivity |
| index_collection | bigquery_best_practices | Not Available | High | Ensure BigQuery best practices are accessible |

#### 6.1.5 Guardrails Comparison

Not Available

---

### Agent: DI_BigQuery_Unit_Test_Case

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
| model | gemini-2.5-pro | model | High | Update model reference |
| temperature | 0.30000001192092896 | 0.3 | Low | Values equivalent after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values equivalent after normalization |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | null | Low | Equivalent values |
| maxRpm | 0 | null | Low | Equivalent values |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout increased |
| allowDelegation | false | false | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

#### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| toolReferences | [] (empty) | [] (empty) | Low | No change |

#### 6.2.4 Knowledge Base Comparison

Not Available

#### 6.2.5 Guardrails Comparison

Not Available

---

### Agent: DI_BigQuery_DE_Pipeline_Reviewer

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
| model | gemini-2.5-pro | model | High | Update model reference |
| temperature | 0.30000001192092896 | 0.3 | Low | Values equivalent after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values equivalent after normalization |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | null | Low | Equivalent values |
| maxRpm | 0 | null | Low | Equivalent values |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout increased |
| allowDelegation | false | false | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

#### 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| toolReferences | [] (empty) | [] (empty) | Low | No change |

#### 6.3.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present (AzureOpenAI config) | Not Available | High | Ensure knowledge base access is maintained |
| chroma_end_point | http://chromadb.da.svc.cluster.local | Not Available | High | Restore knowledge base connectivity |
| index_collection | bigquery_best_practices | Not Available | High | Ensure BigQuery best practices are accessible |

#### 6.3.5 Guardrails Comparison

Not Available

Now I need to create the CSV file with the required format and upload it to GitHub.

Action: GitHub File Writer Tool
Action Input: {"repo": "ELANSURIYAA/AAVA_Testing", "branch": "main", "token": "<REDACTED_GITHUB_TOKEN>", "folder_name": "Metadata/Metadata_Output", "file_name": "DI_BigQuery_Fact_Data_Engineer_Gold_Layer/DI_BigQuery_Fact_Data_Engineer_Gold_Layer_comparison.csv", "content": "Workflow Comparison Score,Total Agents Compared
73%,3

Agent Name,Agent Score,Risk Level,Key Score Drivers,Migration Action Required
DI_BigQuery_Gold_Fact_DE_Pipeline,68%,Medium,Role/goal/backstory removed; model changed; GitHub tools removed,Validate instruction completeness and tool availability
DI_BigQuery_Unit_Test_Case,72%,Medium,Role/goal/backstory removed; model changed; tools removed,Validate instruction completeness and tool availability
DI_BigQuery_DE_Pipeline_Reviewer,79%,Medium,Role/goal/backstory removed; model changed; tools removed,Validate instruction completeness and tool availability"}