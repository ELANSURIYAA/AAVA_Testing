# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

# 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 78%  
**Total Agents Compared:** 2

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_SQLEDW-SSIS-SSRS_RedundancyAnalyzer | 76% | Medium | role/goal/backstory removed, maxExecutionTime reduced, maxIter removed | Validate agent instruction completeness and runtime behavior |
| DI_FabricArchitecture_Recommendation | 80% | Medium | role/goal/backstory removed, maxExecutionTime reduced, maxIter removed | Validate agent instruction completeness and runtime behavior |

---

# 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_SQLEDW_FabricRecommendation  
**Workflow Name (AAVA 2.0):** DI SQLEDW FabricRecommendation

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 3321 | id | 1972 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_SQLEDW_FabricRecommendation | name | DI SQLEDW FabricRecommendation | Matched (Normalized) | Minor spacing differences normalized | Low | No change |
| Description | description | Analyze SQL EDW with SSIS, SSRS and Recommend Microsoft Fabric Architecture | description | Analyze SQL EDW with SSIS, SSRS and Recommend Microsoft Fabric Architecture | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-06-22T19:00:01.875+00:00 | createdAt | 2025-11-05T10:42:13.705999 | Modified | Different creation timestamps | Low | Expected for different workflow instances |
| Agents List | pipeLineAgents | [Array of 2 agents] | workflowAgents | [Array of 2 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure enhanced | Medium | Validate new config structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Confirm memory config location |
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
| createdBy | User who created workflow | muneeswara.pandian@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | muneeswara.pandian@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | muneeswara.pandian@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T10:42:14.774923 | Low | Standard audit field |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Standard soft delete implementation |
| parentId | Parent workflow reference | -1 | Low | Workflow hierarchy support |
| realmId | Realm/tenant identifier | 32 | Medium | Ensure multi-tenancy is handled |

---

# 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align defaults and validate structure |
| managerLlm | Not available | Empty object in workflowConfigs | Medium | Configure manager LLM settings |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update configuration access patterns |

---

# 5. Agent Inventory Summary

## 5.1 Agent Count & Coverage

**AAVA 1.0 total agents:** 2  
**AAVA 2.0 total agents:** 2  
**Coverage:** Same agent count with naming updates

## 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_SQLEDW-SSIS-SSRS_RedundancyAnalyzer | DI SQLEDW-SSIS-SSRS RedundancyAnalyzer | Renamed | Underscore to space conversion |
| DI_FabricArchitecture_Recommendation | DI FabricArchitecture Recommendation | Renamed | Underscore to space conversion |

---

# 6. Agent Configuration Differences

## Agent: DI_SQLEDW-SSIS-SSRS_RedundancyAnalyzer

---

## 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

## 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 15000 | 15000 | Low | No change |
| maxIter | 25 | Not Present | Medium | Validate removal or set default |
| maxRpm | 0 | Not Present | Medium | Validate removal or set default |
| maxExecutionTime | 300 | 90 | High | Significant timeout reduction |

## 6.1.3 Tools Comparison

**Not Available**

## 6.1.4 Knowledge Base Comparison

**Not Available**

## 6.1.5 Guardrails Comparison

**Not Available**

---

## Agent: DI_FabricArchitecture_Recommendation

---

## 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

## 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 20000 | 20000 | Low | No change |
| maxIter | 25 | Not Present | Medium | Validate removal or set default |
| maxRpm | 0 | Not Present | Medium | Validate removal or set default |
| maxExecutionTime | 300 | 90 | High | Significant timeout reduction |

## 6.2.3 Tools Comparison

**Not Available**

## 6.2.4 Knowledge Base Comparison

**Not Available**

## 6.2.5 Guardrails Comparison

**Not Available**