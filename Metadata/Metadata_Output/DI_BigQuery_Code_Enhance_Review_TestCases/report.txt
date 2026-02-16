# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 76%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI BigQuery Code Update | 78% | Medium | Model changed from gemini-2.5-pro to gpt-4.1; role/goal/backstory removed; maxExecutionTime added | Validate model compatibility and instruction completeness |
| DI BigQuery UnitTest Generation | 82% | Medium | Model changed from gemini-2.5-pro to gpt-4.1; tools removed; maxExecutionTime added | Validate model compatibility and tool migration |
| DI BigQuery Code Review | 68% | Medium | Model changed from gemini-2.5-pro to gpt-4.1; role/goal/backstory removed; maxExecutionTime added | Validate model compatibility and instruction completeness |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_BigQuery_Code_Enhance_Review_TestCases
**Workflow Name (AAVA 2.0):** DI BigQuery Code Enhance Review TestCases

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 7799 | id | 2512 | Renamed + Modified | Field renamed and value changed | High | Update references to new workflow ID |
| Naming | name | DI_BigQuery_Code_Enhance_Review_TestCases | name | DI BigQuery Code Enhance Review TestCases | Matched (Normalized) | Minor formatting differences | Low | No change |
| Description | description | Code enhancement, code review and unit test case preparation | description | Code enhancement, code review and unit test case preparation | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-10-31T16:34:18.273+00:00 | createdAt | 2025-11-05T11:02:23.366317 | Modified | Different creation timestamp | Medium | Update audit trail |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed but agent count preserved | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm, enableAgenticMemory} | Renamed + Modified | Field renamed and structure enhanced | High | Migrate configuration structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Update configuration access |
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
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | karthikeyan.iyappan@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | karthikeyan.iyappan@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | karthikeyan.iyappan@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T11:02:24.444042 | Medium | Ensure approval workflow is implemented |
| status | Workflow approval state | APPROVED | High | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete functionality is implemented |
| parentId | Parent workflow reference | -1 | Low | Validate workflow hierarchy handling |
| realmId | Realm identifier | 1 | Medium | Ensure realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| managerLlm | Direct field | Nested in workflowConfigs | High | Update configuration access patterns |
| enableAgenticMemory | Direct field | Nested in workflowConfigs | Medium | Update configuration access patterns |
| callbacks | Empty array | Not available | Medium | Confirm callback removal is acceptable |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agent count maintained

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_BigQuery_Code_Update | DI BigQuery Code Update | Renamed | Naming convention updated (underscore to space) |
| DI_BigQuery_UnitTest_Generation | DI BigQuery UnitTest Generation | Renamed | Naming convention updated (underscore to space) |
| DI_BigQuery_Code_Review | DI BigQuery Code Review | Renamed | Naming convention updated (underscore to space) |

---

## 6. Agent Configuration Differences

## Agent: DI BigQuery Code Update

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility |
| model | gemini-2.5-pro | model | High | Validate model compatibility |
| temperature | 0.10000000149011612 | 0.1 | Low | No change (normalized) |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Validate iteration handling |
| maxRpm | 0 | Not Available | Medium | Validate rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout handling |

### 6.1.3 Tools Comparison

Not Available

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI BigQuery UnitTest Generation

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility |
| model | gemini-2.5-pro | model | High | Validate model compatibility |
| temperature | 0.20000000298023224 | 0.2 | Low | No change (normalized) |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Validate iteration handling |
| maxRpm | 0 | Not Available | Medium | Validate rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout handling |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| DI_Github_File_Writer_Z | Present | Not Available | High | Migrate tool configuration |
| DI_GitHub_File_Reader_Z | Present | Not Available | High | Migrate tool configuration |

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DI BigQuery Code Review

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility |
| model | gemini-2.5-pro | model | High | Validate model compatibility |
| temperature | 0.20000000298023224 | 0.2 | Low | No change (normalized) |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Validate iteration handling |
| maxRpm | 0 | Not Available | Medium | Validate rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout handling |

### 6.3.3 Tools Comparison

Not Available

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available