# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

# 1. Metadata Comparison Score Summary

* Workflow Comparison Score: 78%
* Total Agents Compared: 2

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
| ---------- | ----------- | ---------- | ----------------------------------- | ------------------------- |
| DI_SSIS_SrcTgt_SP_Extractor | 76% | Medium | role/goal/backstory removed, maxExecutionTime reduced, maxIter removed | Validate agent instruction completeness and runtime behavior |
| DI_SSIS_SQLEDW_Mapping | 80% | Medium | role/goal/backstory removed, maxExecutionTime reduced, maxIter removed | Validate agent instruction completeness and runtime behavior |

---

# 2. Workflow-Level Comparison

Workflow Name (AAVA 1.0): DI_SSIS_SQLServerEDWAnalyzer
Workflow Name (AAVA 2.0): DI SSIS SQLServerEDWAnalyzer

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact (Low/Medium/High) | Action Required |
| -------- | -------------- | -------------- | -------------- | -------------- | ----------- | --------------------- | ---------------------------------- | --------------- |
| Identifier | pipelineId | 3311 | id | 1970 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to use new ID |
| Naming | name | DI_SSIS_SQLServerEDWAnalyzer | name | DI SSIS SQLServerEDWAnalyzer | Matched (Case Normalization) | Minor spacing differences in name | Low | No change |
| Description | description | Determine the database objects that are not used in the SSIS and as well mostl widely and least used objects . Provide recommendation to Architect the SQL Server EDW on Microsoft Fabric | description | Determine the database objects that are not used in the SSIS and as well mostl widely and least used objects . Provide recommendation to Architect the SQL Server EDW on Microsoft Fabric | Matched | Description unchanged | Low | No change |
| Audit | createdAt | 2025-06-22T18:34:03.292+00:00 | createdAt | 2025-11-05T10:42:09.576530 | Matched | Field exists in both but different timestamps | Low | No change |
| Agents List | pipeLineAgents | Array of 2 agents | workflowAgents | Array of 2 agents | Renamed + Matched (Normalized) | Field renamed but same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | Object with managerLlm and enableAgenticMemory | Renamed + Modified | Field renamed and structure changed | High | Align configuration structure |
| Memory Config | enableAgenticMemory | false | workflowConfigs.enableAgenticMemory | false | Renamed + Matched (Normalized) | Field moved to nested structure | Medium | Update configuration path |
| Org/Domain/Project Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm removal is acceptable |
| Org/Domain/Project Metadata | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm removal is acceptable |
| Org/Domain/Project Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal is acceptable |
| Org/Domain/Project Metadata | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm removal is acceptable |
| Org/Domain/Project Metadata | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal is acceptable |
| Org/Domain/Project Metadata | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm removal is acceptable |
| Org/Domain/Project Metadata | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm removal is acceptable |
| Org/Domain/Project Metadata | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm removal is acceptable |
| Org/Domain/Project Metadata | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm removal is acceptable |

---

# 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
| --------- | ----------------------- | ---------------------- | ---------------- | ------------------------------------ |
| createdBy | User who created workflow | muneeswara.pandian@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | muneeswara.pandian@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | muneeswara.pandian@ascendion.com | Medium | Ensure approval workflow is handled |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Automatic timestamp handling |
| approvedAt | Approval timestamp | 2025-11-05T10:42:10.788965 | Low | Automatic timestamp handling |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure deletion handling is implemented |
| parentId | Parent workflow reference | -1 | Low | Handle workflow hierarchy |
| realmId | Realm/tenant identifier | 32 | Medium | Ensure multi-tenancy is handled |

---

# 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
| --------------- | ------------- | -------- | ------ | --------------- |
| workflowConfigs | callbacks: [] | managerLlm: [{}], enableAgenticMemory: false | High | Align configuration structure and validate manager LLM settings |
| enableAgenticMemory | Top-level field: false | Nested in workflowConfigs: false | Medium | Update configuration access path |

---

# 5. Agent Inventory Summary

## 5.1 Agent Count & Coverage

AAVA 1.0 total agents: 2
AAVA 2.0 total agents: 2
Coverage: Same agents with naming updates

---

## 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
| ------------------------------ | --------------------------------- | ---------- | ------------------------- |
| DI_SSIS_SrcTgt_SP_Extractor | DI SSIS SrcTgt SP Extractor | Renamed | Naming convention updated (underscores to spaces) |
| DI_SSIS_SQLEDW_Mapping | DI SSIS SQLEDW Mapping | Renamed | Naming convention updated (underscores to spaces) |

---

# 6. Agent Configuration Differences

## Agent: DI_SSIS_SrcTgt_SP_Extractor

---

## 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
| ----- | ----------------- | ----------------- | ---------------- | --------------- |
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

## 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
| ----- | -------------- | -------------- | ---------------- | --------------- |
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | No change (normalized) |
| maxToken | 15000 | 15000 | Low | No change |
| maxIter | 20 | Not Present | Medium | Validate iteration limit removal |
| maxRpm | 0 | Not Present | Low | Validate rate limit removal |
| maxExecutionTime | 300 | 90 | High | Validate execution time reduction |

---

## 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
| ---------------------- | -------------- | -------------- | ---------------- | --------------- |
| tools | [{"toolId": 4, "toolName": "FileWriterTool", "parameters": []}] | toolRef: [4], toolReferences: [] | Medium | Validate tool reference structure change |
| userTools | [] | Not Available | Low | Confirm user tools removal |

---

## 6.1.4 Knowledge Base Comparison

Not Available

---

## 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI_SSIS_SQLEDW_Mapping

---

## 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
| ----- | ----------------- | ----------------- | ---------------- | --------------- |
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

## 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
| ----- | -------------- | -------------- | ---------------- | --------------- |
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | No change (normalized) |
| maxToken | 15000 | 15000 | Low | No change |
| maxIter | 25 | Not Present | Medium | Validate iteration limit removal |
| maxRpm | 0 | Not Present | Low | Validate rate limit removal |
| maxExecutionTime | 300 | 90 | High | Validate execution time reduction |

---

## 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
| ---------------------- | -------------- | -------------- | ---------------- | --------------- |
| tools | [] | toolRef: [], toolReferences: [] | Low | No change (both empty) |
| userTools | [] | Not Available | Low | Confirm user tools removal |

---

## 6.2.4 Knowledge Base Comparison

Not Available

---

## 6.2.5 Guardrails Comparison

Not Available