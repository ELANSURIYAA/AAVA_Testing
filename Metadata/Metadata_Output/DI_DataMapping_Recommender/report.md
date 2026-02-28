# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

# 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 78%
**Total Agents Compared:** 1

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI DataMapping Recommender | 78% | Medium | role/goal/backstory removed, maxExecutionTime reduced, maxIter/maxRpm changed to null | Validate instruction completeness and runtime behavior |

---

# 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_DataMapping_Recommender
**Workflow Name (AAVA 2.0):** DI DataMapping Recommender

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 5907 | id | 2096 | Renamed + Modified | Field renamed and ID value changed | Medium | Update ID references in dependent systems |
| Naming | name | DI_DataMapping_Recommender | name | DI DataMapping Recommender | Matched (Case Normalization) | Minor spacing difference in name | Low | No change |
| Description | description | Map the data elements between two files | description | Map the data elements between two files | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-08-08T12:42:08.579+00:00 | createdAt | 2025-11-05T10:46:57.363721 | Matched | Field exists in both versions but with different timestamps | Low | No change |
| Agents List | pipeLineAgents | [Array with 1 agent] | workflowAgents | [Array with 1 agent] | Renamed + Matched (Normalized) | Field renamed but content structure preserved | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {"managerLlm":[{}],"enableAgenticMemory":false} | Renamed + Modified | Field renamed and structure enhanced | Medium | Validate new config structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Update memory configuration access |
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
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T10:46:58.557195 | Medium | Ensure approval workflow is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete functionality is implemented |
| parentId | Parent workflow reference | -1 | Low | Validate parent-child relationships |
| realmId | Realm identifier | 32 | Medium | Ensure realm-based access control |

---

# 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align configuration structure |
| managerLlm | Not available | Empty object in workflowConfigs | Medium | Configure manager LLM settings |
| enableAgenticMemory | Top-level field (false) | Nested in workflowConfigs (false) | Medium | Update memory configuration access |

---

# 5. Agent Inventory Summary

## 5.1 Agent Count & Coverage

**AAVA 1.0 total agents:** 1
**AAVA 2.0 total agents:** 1
**Coverage:** Same agent count, agent renamed

## 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_DataMapping_Recommender | DI DataMapping Recommender | Matched (Case Normalization) | Minor spacing difference |

---

# 6. Agent Configuration Differences

## Agent: DI DataMapping Recommender

---

## 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

## 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | null | Medium | Validate null value behavior |
| maxRpm | 0 | null | Medium | Validate null value behavior |
| maxExecutionTime | 300 | 90 | High | Execution time significantly reduced |

---

## 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [{"toolId":4,"toolName":"FileWriterTool","parameters":[]}] | toolReferences: [] | High | Tool configuration lost in migration |
| userTools | [] | toolReferences: [] | Low | Both empty |
| toolRef | Not Available | [4] | Medium | New tool reference format |

---

## 6.1.4 Knowledge Base Comparison

Not Available

---

## 6.1.5 Guardrails Comparison

Not Available