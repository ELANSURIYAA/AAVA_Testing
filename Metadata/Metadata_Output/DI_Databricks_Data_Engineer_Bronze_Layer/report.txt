# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 78.5%  
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI Databricks Bronze DE Pipeline | 85.2% | Medium | Model changed from claude-4-sonnet to gpt-4.1; role/goal/backstory removed; maxRpm/maxIter/maxExecutionTime modified | Validate runtime behavior and instruction completeness |
| DI Databricks Pyspark Unit Test Case | 76.8% | Medium | Model changed from claude-4-sonnet to gpt-4.1; role/goal/backstory removed; maxExecutionTime reduced significantly | Validate runtime behavior and instruction completeness |
| DI Databricks DE Pipeline Reviewer | 73.5% | Medium | Model changed from claude-4-sonnet to gpt-4.1; role/goal/backstory removed; maxExecutionTime reduced significantly | Validate runtime behavior and instruction completeness |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_Databricks_Data_Engineer_Bronze_Layer  
**Workflow Name (AAVA 2.0):** DI Databricks Data Engineer Bronze Layer

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 6184 | id | 4663 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new ID |
| Naming | name | DI_Databricks_Data_Engineer_Bronze_Layer | name | DI Databricks Data Engineer Bronze Layer | Matched (Case Normalization) | Spacing differences only | Low | No change |
| Description | description | DE Pipeline for Bronze Layer | description | DE Pipeline for Bronze Layer | Matched | Identical values | Low | No change |
| Audit | createdAt | 2025-08-20T09:13:50.352+00:00 | createdAt | 2025-11-05T12:09:28.778112 | Modified | Different timestamps | Low | Expected for different instances |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure changed | High | Align configuration structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field removed from workflow level | Medium | Confirm removal is acceptable |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm removal is acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm removal is acceptable |
| Domain | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal is acceptable |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm removal is acceptable |
| Project | project | AVA | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal is acceptable |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm removal is acceptable |
| Team | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm removal is acceptable |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm removal is acceptable |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | elansuriyaa.p@ascendion.com | Medium | Ensure approval workflow is handled |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T12:09:29.817908 | Medium | Ensure approval workflow is handled |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure deletion handling is implemented |
| parentId | Parent workflow reference | -1 | Low | Understand workflow hierarchy |
| realmId | Realm/tenant identifier | 32 | Medium | Ensure multi-tenancy is handled |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|---------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align configuration defaults |
| managerLlm | Not available | Empty object {} | Medium | Configure manager LLM settings |
| enableAgenticMemory | Workflow level: false | Config level: false | Low | Confirm memory configuration |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3  
**AAVA 2.0 total agents:** 3  
**Coverage:** Same agent count with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Databricks_Bronze_DE_Pipeline | DI Databricks Bronze DE Pipeline | Renamed | Naming convention updated |
| DI_Databricks_Pyspark_Unit_Test_Case | DI Databricks Pyspark Unit Test Case | Renamed | Naming convention updated |
| DI_Databricks_DE_Pipeline_Reviewer | DI Databricks DE Pipeline Reviewer | Renamed | Naming convention updated |

---

## 6. Agent Configuration Differences

## Agent: DI Databricks Bronze DE Pipeline

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | anthropic.claude-4-sonnet | model | High | Validate model compatibility |
| temperature | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Present | Medium | Validate iteration limits |
| maxRpm | 50 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 400 | 90 | High | Validate timeout settings |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Present | Low | Confirm empty tools list |
| userTools | 2 tools (DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z) | Not Present | High | Validate tool availability |

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI Databricks Pyspark Unit Test Case

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | anthropic.claude-4-sonnet | model | High | Validate model compatibility |
| temperature | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Present | Medium | Validate iteration limits |
| maxRpm | 50 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 600 | 90 | High | Validate timeout settings |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Present | Low | Confirm empty tools list |
| userTools | 2 tools (DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z) | Not Present | High | Validate tool availability |

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DI Databricks DE Pipeline Reviewer

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | anthropic.claude-4-sonnet | model | High | Validate model compatibility |
| temperature | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| topP | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Present | Medium | Validate iteration limits |
| maxRpm | 50 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 600 | 90 | High | Validate timeout settings |

### 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Present | Low | Confirm empty tools list |
| userTools | 2 tools (DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z) | Not Present | High | Validate tool availability |

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available