# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 73%**
**Total Agents Compared: 3**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_Databricks_Silver_Model_Logical | 75% | Medium | role/goal/backstory removed, model changed | Validate instruction completeness and model compatibility |
| DI_Databricks_Silver_Model_Physical | 75% | Medium | role/goal/backstory removed, model changed | Validate instruction completeness and model compatibility |
| DI_Databricks_Silver_Model_Reviewer | 75% | Medium | role/goal/backstory removed, model changed | Validate instruction completeness and model compatibility |

---

## Workflow Names

**Workflow Name (AAVA 1.0):** DI_Databricks_Data_Modeler_Silver_Layer
**Workflow Name (AAVA 2.0):** DI Databricks Data Modeler Silver Layer

---

## 2. Workflow-Level Comparison

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 6179 | id | 4659 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new ID |
| Naming | name | DI_Databricks_Data_Modeler_Silver_Layer | name | DI Databricks Data Modeler Silver Layer | Matched (Case Normalization) | Minor formatting difference | Low | No change |
| Description | description | Data Modeler for Databricks environment | description | Data Modeler for Databricks environment | Matched | Identical values | Low | No change |
| Audit | createdAt | 2025-08-20T05:57:05.558+00:00 | createdAt | 2025-11-05T12:09:22.654305 | Modified | Different creation timestamps | Low | Expected for different instances |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed but same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure changed | High | Migrate callback configs to workflowConfigs |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Verify memory config location |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational fields removed | Medium | Confirm org metadata deprecation |
| Domain Metadata | domain | Platform Engineering | Not Available | Not Available | Removed | Domain fields removed | Medium | Confirm domain metadata deprecation |
| Project Metadata | project | AVA | Not Available | Not Available | Removed | Project fields removed | Medium | Confirm project metadata deprecation |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User tracking | elansuriyaa.p@ascendion.com | Medium | Ensure user attribution is captured |
| modifiedBy | Change tracking | elansuriyaa.p@ascendion.com | Medium | Implement modification tracking |
| approvedBy | Approval workflow | elansuriyaa.p@ascendion.com | Medium | Set up approval processes |
| modifiedAt | Timestamp tracking | 2025-12-03T15:03:31.224436 | Low | Automatic timestamp handling |
| approvedAt | Approval timestamp | 2025-11-05T12:09:23.702654 | Low | Automatic approval tracking |
| status | Workflow state | APPROVED | High | Implement workflow lifecycle management |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete functionality |
| parentId | Hierarchy tracking | -1 | Low | Handle workflow relationships |
| realmId | Realm association | 32 | Medium | Ensure proper realm assignment |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | High | Migrate existing configs to new structure |
| managerLlm | Not available | Empty object array | Medium | Configure manager LLM settings |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update config access patterns |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Databricks_Silver_Model_Logical | DI Databricks Silver Model Logical | Renamed | Underscore to space conversion |
| DI_Databricks_Silver_Model_Physical | DI Databricks Silver Model Physical | Renamed | Underscore to space conversion |
| DI_Databricks_Silver_Model_Reviewer | DI Databricks Silver Model Reviewer | Renamed | Underscore to space conversion |

---

## 6. Agent Configuration Differences

## Agent: DI Databricks Silver Model Logical

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | anthropic.claude-4-sonnet | model | High | Update model configuration |
| temperature | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Available | Medium | Validate iteration limits |
| maxRpm | 50 | Not Available | Medium | Validate rate limits |
| maxExecutionTime | 300 | 90 | High | Validate timeout settings |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | [DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z] | [] | High | Migrate tool configurations |

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI Databricks Silver Model Physical

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | anthropic.claude-4-sonnet | model | High | Update model configuration |
| temperature | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Available | Medium | Validate iteration limits |
| maxRpm | 50 | Not Available | Medium | Validate rate limits |
| maxExecutionTime | 400 | 90 | High | Validate timeout settings |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | [DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z] | [] | High | Migrate tool configurations |

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DI Databricks Silver Model Reviewer

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | anthropic.claude-4-sonnet | model | High | Update model configuration |
| temperature | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Available | Medium | Validate iteration limits |
| maxRpm | 50 | Not Available | Medium | Validate rate limits |
| maxExecutionTime | 400 | 90 | High | Validate timeout settings |

### 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | [DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z] | [] | High | Migrate tool configurations |

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available

Now I'll create the CSV file with the required format and upload both files to GitHub.

Action: GitHub File Writer Tool
Action Input: {"repo": "ELANSURIYAA/AAVA_Testing", "branch": "main", "token": "<REDACTED_GITHUB_TOKEN>", "folder_name": "Metadata/Metadata_Output", "file_name": "DI_Databricks_Data_Modeler_Silver_Layer/DI_Databricks_Data_Modeler_Silver_Layer_comparison.csv", "content": "Workflow Comparison Score,Total Agents Compared
73%,3

Agent Name,Agent Score,Risk Level,Key Score Drivers,Migration Action Required
DI Databricks Silver Model Logical,75%,Medium,role/goal/backstory removed; model changed,Validate instruction completeness and model compatibility
DI Databricks Silver Model Physical,75%,Medium,role/goal/backstory removed; model changed,Validate instruction completeness and model compatibility
DI Databricks Silver Model Reviewer,75%,Medium,role/goal/backstory removed; model changed,Validate instruction completeness and model compatibility"}