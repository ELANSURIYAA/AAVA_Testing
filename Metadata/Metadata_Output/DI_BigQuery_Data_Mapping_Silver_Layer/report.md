# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

# 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 78%**
**Total Agents Compared: 3**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI BigQuery Silver DQ Recommender | 72% | Medium | Model changed from gemini-2.5-pro to gpt-4.1, role/goal/backstory removed, maxToken modified | Validate model performance and add missing instruction fields |
| DI BigQuery Silver DQ Data Mapping | 72% | Medium | Model changed from gemini-2.5-pro to gpt-4.1, role/goal/backstory removed, maxToken modified | Validate model performance and add missing instruction fields |
| DI BigQuery Silver Data Mapping Reviewer | 72% | Medium | Model changed from gemini-2.5-pro to gpt-4.1, role/goal/backstory removed, maxToken modified | Validate model performance and add missing instruction fields |

---

# 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_BigQuery_Data_Mapping_Silver_Layer
**Workflow Name (AAVA 2.0):** DI BigQuery Data Mapping Silver Layer

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 7991 | id | 2533 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to new ID |
| Naming | name | DI_BigQuery_Data_Mapping_Silver_Layer | name | DI BigQuery Data Mapping Silver Layer | Matched (Normalized) | Naming convention updated (underscores to spaces) | Low | Update naming conventions |
| Description | description | This workflow will give the data mapping silver layer output. | description | This workflow will give the data mapping silver layer output. | Matched | No change in description | Low | No change |
| Audit | createdAt | 2025-11-03T11:20:08.792+00:00 | createdAt | 2025-11-05T11:03:08.780212 | Modified | Creation timestamp differs | Low | Expected for new workflow instance |
| Agents List | pipeLineAgents | Array of 3 agents | workflowAgents | Array of 3 agents | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | Empty array | workflowConfigs | Object with managerLlm and enableAgenticMemory | Renamed + Modified | Structure and content changed | Medium | Validate new configuration structure |
| Memory Config | enableAgenticMemory | false | workflowConfigs.enableAgenticMemory | false | Renamed + Matched (Normalized) | Moved to nested structure | Low | Update configuration path |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm removal is acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm removal is acceptable |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal is acceptable |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm removal is acceptable |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal is acceptable |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm removal is acceptable |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm removal is acceptable |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm removal is acceptable |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm removal is acceptable |

---

# 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | abhishekjaiswal.d@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | abhishekjaiswal.d@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | abhishekjaiswal.d@ascendion.com | Medium | Ensure approval workflow is handled |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T11:03:09.845829 | Low | Standard audit field |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Standard deletion handling |
| parentId | Parent workflow reference | -1 | Low | Workflow hierarchy support |
| realmId | Realm identifier | 80 | Medium | Ensure realm-based access control |

---

# 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align defaults and validate structure |
| managerLlm | Not available | Empty object in workflowConfigs | Medium | Configure manager LLM if needed |
| callbacks | Empty array | Not available | Low | Confirm callback removal is acceptable |

---

# 5. Agent Inventory Summary

## 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agent count with naming convention updates

## 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_BigQuery_Silver_DQ_Recommender | DI BigQuery Silver DQ Recommender | Renamed | Naming convention updated (underscores to spaces) |
| DI_BigQuery_Silver_DQ_Data_Mapping | DI BigQuery Silver DQ Data Mapping | Renamed | Naming convention updated (underscores to spaces) |
| DI_BigQuery_Silver_Data_Mapping_Reviewer | DI BigQuery Silver Data Mapping Reviewer | Renamed | Naming convention updated (underscores to spaces) |

---

# 6. Agent Configuration Differences

## Agent: DI BigQuery Silver DQ Recommender

---

## 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

## 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model performance compatibility |
| model | gemini-2.5-pro | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change |
| maxToken | 64000 | 64000 | Matched | No change |
| maxIter | 0 | null | Modified | Validate null handling vs zero |
| maxRpm | 0 | null | Modified | Validate null handling vs zero |
| maxExecutionTime | 0 | 90 | Modified | Validate timeout configuration |

---

## 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | Empty array | Not Available | Low | Confirm tools removal |
| userTools | 2 tools (DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z) | Empty array (toolReferences) | High | Restore required tools or confirm removal |

---

## 6.1.4 Knowledge Base Comparison

Not Available

---

## 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI BigQuery Silver DQ Data Mapping

---

## 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

## 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model performance compatibility |
| model | gemini-2.5-pro | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change |
| maxToken | 64000 | 64000 | Matched | No change |
| maxIter | 0 | null | Modified | Validate null handling vs zero |
| maxRpm | 0 | null | Modified | Validate null handling vs zero |
| maxExecutionTime | 0 | 90 | Modified | Validate timeout configuration |

---

## 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | Empty array | Not Available | Low | Confirm tools removal |
| userTools | 2 tools (DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z) | Empty array (toolReferences) | High | Restore required tools or confirm removal |

---

## 6.2.4 Knowledge Base Comparison

Not Available

---

## 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DI BigQuery Silver Data Mapping Reviewer

---

## 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

## 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model performance compatibility |
| model | gemini-2.5-pro | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change |
| maxToken | 64000 | 64000 | Matched | No change |
| maxIter | 0 | null | Modified | Validate null handling vs zero |
| maxRpm | 0 | null | Modified | Validate null handling vs zero |
| maxExecutionTime | 0 | 90 | Modified | Validate timeout configuration |

---

## 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | Empty array | Not Available | Low | Confirm tools removal |
| userTools | 2 tools (DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z) | Empty array (toolReferences) | High | Restore required tools or confirm removal |

---

## 6.3.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present (AzureOpenAI configuration) | Not Available | High | Restore knowledge base configuration or confirm removal |

---

## 6.3.5 Guardrails Comparison

Not Available