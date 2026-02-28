# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Name (AAVA 1.0):** DI_PySpark_Consolidate_Design_Pattern
**Workflow Name (AAVA 2.0):** DI PySpark Consolidate Design Pattern

### Workflow Comparison Score: 78%
### Total Agents Compared: 1

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_PySpark_Consolidate_Design_Pattern | 78% | Medium | role/goal/backstory removed, model changed, maxIter/maxRpm nullified, maxExecutionTime reduced | Validate instruction completeness and runtime behavior |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_PySpark_Consolidate_Design_Pattern
**Workflow Name (AAVA 2.0):** DI PySpark Consolidate Design Pattern

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 6091 | id | 2110 | Renamed + Modified | Field renamed and value changed | High | Update references to new workflow ID |
| Naming | name | DI_PySpark_Consolidate_Design_Pattern | name | DI PySpark Consolidate Design Pattern | Matched (Normalized) | Minor spacing differences normalized | Low | No change |
| Description | description | PySpark Design pattern consolidate | description | PySpark Design pattern consolidate | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-08-14T03:26:13.457+00:00 | createdAt | 2025-11-05T10:47:30.435973 | Modified | Different creation timestamps | Medium | Verify workflow versioning |
| Agents List | pipeLineAgents | [1 agent] | workflowAgents | [1 agent] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure changed | Medium | Align configuration handling |
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

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | elansuriyaa.p@ascendion.com | Medium | Ensure approval workflow is handled |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T10:47:31.497670 | Medium | Ensure approval workflow is handled |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure deletion handling is implemented |
| parentId | Parent workflow reference | -1 | Low | Understand workflow hierarchy |
| realmId | Realm identifier | 32 | Medium | Ensure realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | callbacks: [] | workflowConfigs: {managerLlm: [{}], enableAgenticMemory: false} | Medium | Align configuration structure |
| managerLlm | Not available | Present (empty object) | Medium | Configure manager LLM settings |
| enableAgenticMemory | Direct field: false | Nested in workflowConfigs: false | Low | Update configuration path |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 1
**AAVA 2.0 total agents:** 1
**Coverage:** Same agent count

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_PySpark_Consolidate_Design_Pattern | DI PySpark Consolidate Design Pattern | Matched (Normalized) | Minor spacing differences normalized |

---

## 6. Agent Configuration Differences

## Agent: DI_PySpark_Consolidate_Design_Pattern

---

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model configuration change |
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | null | High | Validate removal of iteration limit |
| maxRpm | 20 | null | High | Validate removal of rate limit |
| maxExecutionTime | 180 | 90 | High | Validate reduced execution timeout |

---

### 6.1.3 Tools Comparison

**Not Available** - No tools configured in either version.

---

### 6.1.4 Knowledge Base Comparison

**Not Available** - No knowledge base configured in either version.

---

### 6.1.5 Guardrails Comparison

**Not Available** - No guardrails configured in either version.

Now I need to generate the CSV file with the required format and upload it to GitHub:

Action: GitHub File Writer Tool
Action Input: {"repo": "ELANSURIYAA/AAVA_Testing", "branch": "main", "token": "<REDACTED_GITHUB_TOKEN>", "folder_name": "Metadata/Metadata_Output", "file_name": "DI_PySpark_Consolidate_Design_Pattern/DI_PySpark_Consolidate_Design_Pattern_comparison.csv", "content": "Workflow Comparison Score,Total Agents Compared
78%,1

Agent Name,Agent Score,Risk Level,Key Score Drivers,Migration Action Required
DI_PySpark_Consolidate_Design_Pattern,78%,Medium,\"role/goal/backstory removed, model changed, maxIter/maxRpm nullified, maxExecutionTime reduced\",Validate instruction completeness and runtime behavior"}