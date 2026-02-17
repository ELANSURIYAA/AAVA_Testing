# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 78%
**Total Agents Compared:** 1

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI SSIS ETL Asset Rationalizer | 78% | Medium | role/goal/backstory removed, model configs matched, description matched, maxIter/maxRpm modified | Validate removal of role/goal/backstory fields and confirm maxIter/maxRpm changes |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_SSIS_ETL_Asset_Rationalizer
**Workflow Name (AAVA 2.0):** DI SSIS ETL Asset Rationalizer

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 3403 | id | 1993 | Renamed + Modified | Field renamed and value changed | High | Update references to use new ID |
| Naming | name | DI_SSIS_ETL_Asset_Rationalizer | name | DI SSIS ETL Asset Rationalizer | Matched (Normalized) | Minor formatting difference in name | Low | No change needed |
| Description | description | DI_SSIS_ETL_Asset_Rationalizer | description | DI_SSIS_ETL_Asset_Rationalizer | Matched | Exact match | Low | No change needed |
| Audit | createdAt | 2025-06-24T09:18:25.466+00:00 | createdAt | 2025-11-05T10:43:03.716790 | Modified | Different creation timestamps | Medium | Validate workflow versioning |
| Agents List | pipeLineAgents | [1 agent] | workflowAgents | [1 agent] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {"managerLlm": [{}], "enableAgenticMemory": false} | Renamed + Modified | Field renamed and structure enhanced | Medium | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Validate memory configuration location |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm removal is acceptable |
| Domain Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal is acceptable |
| Project Metadata | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | elansuriyaa.p@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T10:43:04.915400 | Medium | Ensure approval workflow is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete functionality is implemented |
| parentId | Parent workflow reference | -1 | Low | Validate parent-child relationships |
| realmId | Realm identifier | 32 | Medium | Ensure realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | callbacks: [] | managerLlm: [{}], enableAgenticMemory: false | Medium | Configure manager LLM settings |
| enableAgenticMemory | Top-level field: false | Nested in workflowConfigs: false | Medium | Update configuration access patterns |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
- **AAVA 1.0 total agents:** 1
- **AAVA 2.0 total agents:** 1
- **Coverage:** Same agent count

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_SSIS_ETL_Asset_Rationalizer | DI SSIS ETL Asset Rationalizer | Matched (Normalized) | Minor formatting difference |

---

## 6. Agent Configuration Differences

### Agent: DI SSIS ETL Asset Rationalizer

#### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

#### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change needed |
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision difference acceptable |
| topP | 0.949999988079071 | 0.94 | Low | Precision difference acceptable |
| maxToken | 8000 | 8000 | Low | No change needed |
| maxIter | 10 | null | Medium | Validate removal of iteration limit |
| maxRpm | 0 | null | Medium | Validate removal of rate limit |
| maxExecutionTime | 300 | 90 | High | Validate reduced execution time |
| allowDelegation | true | true | Low | No change needed |
| allowCodeExecution | false | false | Low | No change needed |
| isSafeCodeExecution | true | true | Low | No change needed |

#### 6.1.3 Tools Comparison

**Not Available** - No tools configured in either version.

#### 6.1.4 Knowledge Base Comparison

**Not Available** - No knowledge base configuration in either version.

#### 6.1.5 Guardrails Comparison

**Not Available** - No guardrails configuration in either version.

---

**CSV file has been successfully uploaded to:** Metadata/Metadata_Output/DI_SSIS_ETL_Asset_Rationalizer/DI_SSIS_ETL_Asset_Rationalizer_comparison.csv

The comparison reveals a 78% compatibility score with medium migration risk. Key concerns include the removal of critical agent instruction fields (role, goal, backstory, expectedOutput) and modifications to runtime parameters (maxExecutionTime reduced from 300 to 90 seconds). The workflow structure has been enhanced with governance features but requires validation of the removed organizational metadata fields.