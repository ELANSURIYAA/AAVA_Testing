# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Name (AAVA 1.0):** DI_Databricks_Data_Engineer Silver Layer  
**Workflow Name (AAVA 2.0):** DI Databricks Data Engineer Silver Layer

* **Workflow Comparison Score:** 67%
* **Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_Databricks_Silver_DE_Pipeline | 65% | Medium | Model changed (Claude-4 to GPT-4.1), maxRpm/maxIter removed, role/goal/backstory removed | Validate model compatibility and restore missing agent instruction fields |
| DI_Databricks_Pyspark_Unit_Test_Case | 68% | Medium | Model changed (Claude-4 to GPT-4.1), maxRpm/maxIter removed, role/goal/backstory removed | Validate model compatibility and restore missing agent instruction fields |
| DI_Databricks_DE_Pipeline_Reviewer | 69% | Medium | Model changed (Claude-4 to GPT-4.1), maxRpm/maxIter removed, role/goal/backstory removed | Validate model compatibility and restore missing agent instruction fields |

---

## 2. Workflow-Level Comparison

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 6270 | id | 4670 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new field name and ID |
| Naming | name | DI_Databricks_Data_Engineer Silver Layer | name | DI Databricks Data Engineer Silver Layer | Matched (Case Normalization) | Minor formatting difference in spacing | Low | No change needed |
| Description | description | Generate a PySpark script to cleanse, validate, and standardize the Bronze layer data before storing it in the Silver layer for analytical processing. | description | Generate a PySpark script to cleanse, validate, and standardize the Bronze layer data before storing it in the Silver layer for analytical processing. | Matched | Identical values | Low | No change |
| Audit | createdAt | 2025-08-22T08:15:22.319+00:00 | createdAt | 2025-11-05T12:09:43.545068 | Modified | Different creation timestamps | Medium | Validate timestamp handling |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed but same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {"managerLlm": [{}], "enableAgenticMemory": false} | Renamed + Modified | Field renamed and structure changed | High | Migrate callback configurations |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Update memory configuration handling |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | High | Implement governance metadata replacement |
| Domain Metadata | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | High | Implement governance metadata replacement |
| Project Metadata | project | AVA | Not Available | Not Available | Removed | Project metadata removed | High | Implement governance metadata replacement |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created the workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified the workflow | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved the workflow | elansuriyaa.p@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification timestamps are tracked |
| approvedAt | Approval timestamp | 2025-11-05T12:09:44.589081 | Medium | Ensure approval timestamps are tracked |
| status | Workflow approval state | APPROVED | High | Implement workflow lifecycle management |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete functionality |
| parentId | Parent workflow reference | -1 | Low | Implement workflow hierarchy if needed |
| realmId | Realm/tenant identifier | 32 | Medium | Implement multi-tenancy support |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|---------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | High | Implement workflow-level configuration management |
| managerLlm | Not available | Empty object {} | Medium | Define manager LLM configuration structure |
| enableAgenticMemory | Top-level field (false) | Nested in workflowConfigs (false) | Medium | Update memory configuration access pattern |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3  
**AAVA 2.0 total agents:** 3  
**Coverage:** Same agent count with structural changes

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Databricks_Silver_DE_Pipeline | DI Databricks Silver DE Pipeline | Matched (Case Normalization) | Minor spacing differences |
| DI_Databricks_Pyspark_Unit_Test_Case | DI Databricks Pyspark Unit Test Case | Matched (Case Normalization) | Minor spacing differences |
| DI_Databricks_DE_Pipeline_Reviewer | DI Databricks DE Pipeline Reviewer | Matched (Case Normalization) | Minor spacing differences |

---

## 6. Agent Configuration Differences

## Agent: DI_Databricks_Silver_DE_Pipeline

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility and performance |
| model | anthropic.claude-4-sonnet | model | High | Update model configuration |
| temperature | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Available | Medium | Restore missing configuration or confirm removal |
| maxRpm | 50 | Not Available | Medium | Restore missing configuration or confirm removal |
| maxExecutionTime | 400 | 90 | High | Validate execution time reduction impact |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | 2 tools (DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z) | [] | High | Restore missing tools or confirm removal |

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI_Databricks_Pyspark_Unit_Test_Case

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility and performance |
| model | anthropic.claude-4-sonnet | model | High | Update model configuration |
| temperature | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Available | Medium | Restore missing configuration or confirm removal |
| maxRpm | 50 | Not Available | Medium | Restore missing configuration or confirm removal |
| maxExecutionTime | 600 | 90 | High | Validate execution time reduction impact |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | 2 tools (DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z) | [] | High | Restore missing tools or confirm removal |

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DI_Databricks_DE_Pipeline_Reviewer

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility and performance |
| model | anthropic.claude-4-sonnet | model | High | Update model configuration |
| temperature | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| topP | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Available | Medium | Restore missing configuration or confirm removal |
| maxRpm | 50 | Not Available | Medium | Restore missing configuration or confirm removal |
| maxExecutionTime | 600 | 90 | High | Validate execution time reduction impact |

### 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | 2 tools (DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z) | [] | High | Restore missing tools or confirm removal |

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available