# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 73%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI Databricks Gold Aggregated Transformation Recommender | 68% | Medium | Model changed, role/goal/backstory removed, maxIter/maxRpm removed | Validate model compatibility and add missing instruction fields |
| DI Databricks Gold Aggregated Transformation Data Mapping | 71% | Medium | Model changed, role/goal/backstory removed, embedding removed | Validate model compatibility and confirm embedding removal |
| DI Databricks Gold Model Reviewer | 75% | Medium | Model changed, role/goal/backstory removed, maxExecutionTime reduced | Validate model compatibility and execution time impact |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_Databricks_Aggregated_Data_Mapping_Gold_Layer
**Workflow Name (AAVA 2.0):** DI Databricks Aggregated Data Mapping Gold Layer

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 6306 | id | 4672 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_Databricks_Aggregated_Data_Mapping_Gold_Layer | name | DI Databricks Aggregated Data Mapping Gold Layer | Matched (Case Normalization) | Underscores replaced with spaces | Low | Update naming conventions |
| Description | description | This workflow is for recommending and creating the gold Fact data mapping | description | This workflow is for recommending and creating the gold Fact data mapping | Matched | Identical description | Low | No change |
| Audit | createdAt | 2025-08-25T06:36:23.955+00:00 | createdAt | 2025-11-05T12:09:46.226473 | Modified | Different creation timestamps | Low | Expected for different workflow instances |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {"managerLlm":[{}],"enableAgenticMemory":false} | Renamed + Modified | Field renamed and structure enhanced | Medium | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Low | Check workflowConfigs.enableAgenticMemory |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm org tracking approach |
| Domain Metadata | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm domain tracking approach |
| Project Metadata | project | AVA | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm project tracking approach |
| Team Metadata | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm team tracking approach |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Implement user tracking |
| modifiedBy | User who last modified | elansuriyaa.p@ascendion.com | Medium | Implement modification tracking |
| approvedBy | User who approved workflow | elansuriyaa.p@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Implement modification tracking |
| approvedAt | Approval timestamp | 2025-11-05T12:09:47.290560 | Medium | Implement approval tracking |
| status | Workflow approval state | APPROVED | High | Implement workflow lifecycle |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete logic |
| parentId | Parent workflow reference | -1 | Low | Implement workflow hierarchy |
| realmId | Realm identifier | 32 | Medium | Implement realm-based access |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Configure manager LLM settings |
| managerLlm | Not available | Empty object {} | Medium | Define manager LLM configuration |
| enableAgenticMemory | Top-level field (false) | Nested in workflowConfigs (false) | Low | Update configuration structure |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agent count with structural changes

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Databricks_Gold_Aggregated_Transformation_Recommender | DI Databricks Gold Aggregated Transformation Recommender | Renamed | Underscores replaced with spaces |
| DI_Databricks_Gold_Aggregated_Transformation_Data_Mapping | DI Databricks Gold Aggregated Transformation Data Mapping | Renamed | Underscores replaced with spaces |
| DI_Databricks_Gold_Model_Reviewer | DI Databricks Gold Model Reviewer | Renamed | Underscores replaced with spaces |

---

## 6. Agent Configuration Differences

## Agent: DI Databricks Gold Aggregated Transformation Recommender

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
| model | anthropic.claude-4-sonnet | model | High | Update model configuration |
| temperature | 0.10000000149011612 | 0.1 | Low | Matched (Normalized) |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Present | Medium | Add missing field or confirm removal |
| maxRpm | 50 | Not Present | Medium | Add missing field or confirm removal |
| maxExecutionTime | 400 | 90 | High | Validate execution time reduction |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] (empty) | Not Present | Low | Confirm tools structure |
| userTools | 2 tools present | Not Present | High | Migrate tool references |
| toolReferences | Not Available | [] (empty) | Medium | Validate new tool structure |

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI Databricks Gold Aggregated Transformation Data Mapping

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
| model | anthropic.claude-4-sonnet | model | High | Update model configuration |
| temperature | 0.10000000149011612 | 0.1 | Low | Matched (Normalized) |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Present | Medium | Add missing field or confirm removal |
| maxRpm | 50 | Not Present | Medium | Add missing field or confirm removal |
| maxExecutionTime | 400 | 90 | High | Validate execution time reduction |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] (empty) | Not Present | Low | Confirm tools structure |
| userTools | 2 tools present | Not Present | High | Migrate tool references |
| toolReferences | Not Available | [] (empty) | Medium | Validate new tool structure |

### 6.2.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present (AzureOpenAI config) | Not Present | High | Migrate embedding configuration |

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DI Databricks Gold Model Reviewer

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
| model | anthropic.claude-4-sonnet | model | High | Update model configuration |
| temperature | 0.10000000149011612 | 0.1 | Low | Matched (Normalized) |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Present | Medium | Add missing field or confirm removal |
| maxRpm | 50 | Not Present | Medium | Add missing field or confirm removal |
| maxExecutionTime | 600 | 90 | High | Validate significant execution time reduction |

### 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] (empty) | Not Present | Low | Confirm tools structure |
| userTools | 2 tools present | Not Present | High | Migrate tool references |
| toolReferences | Not Available | [] (empty) | Medium | Validate new tool structure |

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available

Now I need to create the CSV file with the required format and upload it to GitHub.

Action: GitHub File Writer Tool
Action Input: {"repo": "ELANSURIYAA/AAVA_Testing", "branch": "main", "token": "<REDACTED_GITHUB_TOKEN>", "folder_name": "Metadata/Metadata_Output", "file_name": "DI_Databricks_Aggregated_Data_Mapping_Gold_Layer/DI_Databricks_Aggregated_Data_Mapping_Gold_Layer_comparison.csv", "content": "Workflow Comparison Score,Total Agents Compared
73%,3

Agent Name,Agent Score,Risk Level,Key Score Drivers,Migration Action Required
DI Databricks Gold Aggregated Transformation Recommender,68%,Medium,Model changed role/goal/backstory removed maxIter/maxRpm removed,Validate model compatibility and add missing instruction fields
DI Databricks Gold Aggregated Transformation Data Mapping,71%,Medium,Model changed role/goal/backstory removed embedding removed,Validate model compatibility and confirm embedding removal
DI Databricks Gold Model Reviewer,75%,Medium,Model changed role/goal/backstory removed maxExecutionTime reduced,Validate model compatibility and execution time impact"}