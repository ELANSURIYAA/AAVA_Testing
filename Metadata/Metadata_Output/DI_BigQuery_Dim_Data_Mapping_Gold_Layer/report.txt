# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 78%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI BigQuery Gold Dim Transformation Recommender | 76% | Medium | Model changed from gemini-2.5-pro to gpt-4.1, role/goal/backstory removed, allowDelegation changed | Validate model behavior and confirm instruction field removal |
| DI BigQuery Gold Dim Transformation Data Mapping | 80% | Medium | Model changed from gemini-2.5-pro to gpt-4.1, role/goal/backstory removed, allowDelegation changed | Validate model behavior and confirm instruction field removal |
| DI BigQuery Gold Data Mapping Reviewer | 78% | Medium | Model changed from gemini-2.5-pro to gpt-4.1, role/goal/backstory removed, allowDelegation changed | Validate model behavior and confirm instruction field removal |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_BigQuery_Dim_Data_Mapping_Gold_Layer
**Workflow Name (AAVA 2.0):** DI BigQuery Dim Data Mapping Gold Layer

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 7961 | id | 4962 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to use new ID |
| Naming | name | DI_BigQuery_Dim_Data_Mapping_Gold_Layer | name | DI BigQuery Dim Data Mapping Gold Layer | Matched (Normalized) | Name normalized (underscores to spaces) | Low | No change |
| Description | description | This workflow is for recommending and creating the gold dimension data mapping | description | This workflow is for recommending and creating the gold dimension data mapping | Matched | Identical description | Low | No change |
| Audit | createdAt | 2025-11-02T10:53:01.468+00:00 | createdAt | 2025-11-05T12:18:39.542656 | Matched | Field exists in both but different timestamps | Low | No change |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Enhanced configuration structure | Medium | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Low | Use workflowConfigs.enableAgenticMemory |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Implement alternative org tracking |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Implement alternative org tracking |
| Domain | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | Medium | Implement alternative domain tracking |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | Medium | Implement alternative domain tracking |
| Project | project | AVA | Not Available | Not Available | Removed | Project metadata removed | Medium | Implement alternative project tracking |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | Medium | Implement alternative project tracking |
| Team | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | Medium | Implement alternative team tracking |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | Medium | Implement alternative team tracking |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed | Low | Use agentDetails.levelId if needed |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | tejas.kharche@ascendion.com | Medium | Implement user tracking system |
| modifiedBy | User who last modified | tejas.kharche@ascendion.com | Medium | Implement modification tracking |
| approvedBy | User who approved workflow | tejas.kharche@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Track modification history |
| approvedAt | Approval timestamp | 2025-11-05T12:18:40.607587 | Low | Track approval history |
| status | Workflow approval state | APPROVED | High | Implement workflow lifecycle management |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete functionality |
| parentId | Parent workflow reference | -1 | Low | Handle workflow hierarchy |
| realmId | Realm identifier | 32 | Medium | Implement realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Configure manager LLM settings |
| managerLlm | Not available | [{}] (empty object) | Medium | Define manager LLM configuration |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Low | Update configuration access path |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_BigQuery_Gold_Dim_Transformation_Recommender | DI BigQuery Gold Dim Transformation Recommender | Renamed | Underscores replaced with spaces |
| DI_BigQuery_Gold_Dim_Transformation_Data_Mapping | DI BigQuery Gold Dim Transformation Data Mapping | Renamed | Underscores replaced with spaces |
| DI_BigQuery_Gold_Data_Mapping_Reviewer | DI BigQuery Gold Data Mapping Reviewer | Renamed | Underscores replaced with spaces |

---

## 6. Agent Configuration Differences

## Agent: DI BigQuery Gold Dim Transformation Recommender

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model behavior compatibility |
| model | gemini-2.5-pro | model | High | Update model configuration |
| temperature | 0.20000000298023224 | 0.2 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | null | Low | Validate null handling |
| maxRpm | 0 | null | Low | Validate null handling |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout behavior change |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] (empty array) | [] (empty array) | Low | No change |
| userTools | 2 tools (DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z) | [] (empty array) | High | Restore user tools or confirm removal |
| toolReferences | Not Available | [] (empty array) | Low | New field, no action needed |

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI BigQuery Gold Dim Transformation Data Mapping

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model behavior compatibility |
| model | gemini-2.5-pro | model | High | Update model configuration |
| temperature | 0.20000000298023224 | 0.2 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | null | Low | Validate null handling |
| maxRpm | 0 | null | Low | Validate null handling |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout behavior change |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] (empty array) | [] (empty array) | Low | No change |
| userTools | 2 tools (DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z) | [] (empty array) | High | Restore user tools or confirm removal |
| toolReferences | Not Available | [] (empty array) | Low | New field, no action needed |

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DI BigQuery Gold Data Mapping Reviewer

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model behavior compatibility |
| model | gemini-2.5-pro | model | High | Update model configuration |
| temperature | 0.20000000298023224 | 0.2 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | null | Low | Validate null handling |
| maxRpm | 0 | null | Low | Validate null handling |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout behavior change |

### 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] (empty array) | [] (empty array) | Low | No change |
| userTools | 2 tools (DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z) | [] (empty array) | High | Restore user tools or confirm removal |
| toolReferences | Not Available | [] (empty array) | Low | New field, no action needed |

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available