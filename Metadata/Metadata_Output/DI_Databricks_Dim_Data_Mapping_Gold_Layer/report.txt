# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Name (AAVA 1.0):** DI_Databricks_Dim_Data_Mapping_Gold_Layer
**Workflow Name (AAVA 2.0):** DI Databricks Dim Data Mapping Gold Layer

* **Workflow Comparison Score:** 76%
* **Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI Databricks Gold Dim Transformation Recommender | 72% | Medium | model changed from anthropic.claude-4-sonnet to model, maxIter/maxRpm removed, role/goal/backstory removed | Validate model compatibility and runtime behavior |
| DI Databricks Gold Dim Transformation Data Mapping | 76% | Medium | model changed, embedding configs removed, maxIter/maxRpm removed, role/goal/backstory removed | Validate model compatibility and embedding functionality |
| DI Databricks Gold Data Mapping Reviewer | 80% | Medium | model changed, maxIter/maxRpm removed, role/goal/backstory removed | Validate model compatibility and runtime behavior |

---

## 2. Workflow-Level Comparison

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 6301 | id | 4671 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | DI_Databricks_Dim_Data_Mapping_Gold_Layer | name | DI Databricks Dim Data Mapping Gold Layer | Matched (Normalized) | Spacing differences normalized | Low | No change |
| Description | description | This workflow is for recommending and creating the gold dimension data mapping | description | This workflow is for recommending and creating the gold dimension data mapping | Matched | Identical values | Low | No change |
| Audit | createdAt | 2025-08-25T04:57:12.024+00:00 | createdAt | 2025-11-05T12:09:45.017665 | Modified | Different creation timestamps | Low | Expected for different workflow instances |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed but same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {"managerLlm": [{}], "enableAgenticMemory": false} | Renamed + Modified | Enhanced configuration structure | High | Configure manager LLM settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Confirm memory settings in workflowConfigs |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Add missing organizational context |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | High | Add missing organizational context |
| Domain | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | High | Add missing domain context |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | High | Add missing domain context |
| Project | project | AVA | Not Available | Not Available | Removed | Project metadata removed | High | Add missing project context |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | High | Add missing project context |
| Team | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | High | Add missing team context |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | High | Add missing team context |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm level context handling |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | elansuriyaa.p@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Automatic timestamp handling |
| approvedAt | Approval timestamp | 2025-11-05T12:09:46.071167 | Medium | Ensure approval process is configured |
| status | Workflow approval state | APPROVED | High | Ensure workflow lifecycle management |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete functionality |
| parentId | Parent workflow reference | -1 | Medium | Ensure workflow hierarchy handling |
| realmId | Realm identifier | 32 | Medium | Ensure realm context is properly set |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | High | Configure manager LLM settings and validate memory configuration |
| managerLlm | Not available | Empty object {} | High | Define manager LLM configuration |
| enableAgenticMemory | Top-level field (false) | Nested in workflowConfigs (false) | Medium | Validate memory configuration location |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agent count, all agents preserved

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Databricks_Gold_Dim_Transformation_Recommender | DI Databricks Gold Dim Transformation Recommender | Matched (Normalized) | Underscore to space normalization |
| DI_Databricks_Gold_Dim_Transformation_Data_Mapping | DI Databricks Gold Dim Transformation Data Mapping | Matched (Normalized) | Underscore to space normalization |
| DI_Databricks_Gold_Data_Mapping_Reviewer | DI Databricks Gold Data Mapping Reviewer | Matched (Normalized) | Underscore to space normalization |

---

## 6. Agent Configuration Differences

## Agent: DI Databricks Gold Dim Transformation Recommender

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility and performance |
| model | anthropic.claude-4-sonnet | model | High | Validate model compatibility and performance |
| temperature | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Present | Medium | Add missing field or confirm removal is acceptable |
| maxRpm | 50 | Not Present | Medium | Add missing field or confirm removal is acceptable |
| maxExecutionTime | 400 | 90 | High | Validate reduced execution time impact |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | 2 tools (DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z) | [] | High | Add missing user tools or confirm removal |

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI Databricks Gold Dim Transformation Data Mapping

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility and performance |
| model | anthropic.claude-4-sonnet | model | High | Validate model compatibility and performance |
| temperature | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Present | Medium | Add missing field or confirm removal is acceptable |
| maxRpm | 50 | Not Present | Medium | Add missing field or confirm removal is acceptable |
| maxExecutionTime | 400 | 90 | High | Validate reduced execution time impact |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | 2 tools (DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z) | [] | High | Add missing user tools or confirm removal |

### 6.2.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present (AzureOpenAI configuration) | Not Present | High | Add missing embedding configuration or confirm removal |

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DI Databricks Gold Data Mapping Reviewer

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility and performance |
| model | anthropic.claude-4-sonnet | model | High | Validate model compatibility and performance |
| temperature | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Present | Medium | Add missing field or confirm removal is acceptable |
| maxRpm | 50 | Not Present | Medium | Add missing field or confirm removal is acceptable |
| maxExecutionTime | 400 | 90 | High | Validate reduced execution time impact |

### 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | 2 tools (DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z) | [] | High | Add missing user tools or confirm removal |

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available