# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 76%
**Total Agents Compared:** 2

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI OptimizeTSQLScript | 72% | Medium | Model changed from claude-4-sonnet to gpt-4.1, role/goal/backstory removed, maxExecutionTime reduced | Validate model compatibility and runtime behavior |
| DI UnitTesting Tsql | 80% | Medium | Model changed from claude-4-5-sonnet to text-embedding-ada-002, role/goal/backstory removed, maxExecutionTime reduced | Validate model compatibility and runtime behavior |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_UnitTesting_Tsql
**Workflow Name (AAVA 2.0):** DI UnitTesting Tsql

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 7737 | id | 2480 | Renamed + Modified | Field renamed and value changed | High | Update references to new workflow ID |
| Naming | name | DI_UnitTesting_Tsql | name | DI UnitTesting Tsql | Matched (Case Normalization) | Minor formatting difference in name | Low | No change |
| Description | description | Develop a robust, automated framework for unit testing T-SQL scripts... | description | Develop a robust, automated framework for unit testing T-SQL scripts... | Matched (Normalized) | Same content after normalization | Low | No change |
| Audit | createdAt | 2025-10-27T05:54:39.203+00:00 | createdAt | 2025-11-05T11:01:13.778599 | Modified | Different creation timestamps | Medium | Validate audit trail |
| Agents List | pipeLineAgents | [Array of 2 agents] | workflowAgents | [Array of 2 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure changed | Medium | Align configuration structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Update memory configuration handling |
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
| createdBy | User who created workflow | dipali.nale@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | dipali.nale@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | dipali.nale@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T11:01:14.852278 | Medium | Ensure approval workflow is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete handling is implemented |
| parentId | Parent workflow reference | -1 | Low | Validate parent-child relationships |
| realmId | Security realm identifier | 32 | Medium | Ensure security realm handling is implemented |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|---------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align configuration structure |
| managerLlm | Not available | Empty object {} | Medium | Configure manager LLM settings |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update memory configuration access |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 2
**AAVA 2.0 total agents:** 2
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|--------|
| DI_OptimizeTSQLScript | DI OptimizeTSQLScript | Renamed | Underscore removed from name |
| DI_UnitTesting_Tsql | DI UnitTesting Tsql | Renamed | Underscores removed from name |

---

## 6. Agent Configuration Differences

## Agent: DI OptimizeTSQLScript

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | anthropic.claude-4-sonnet | model | High | Validate model compatibility |
| temperature | 0.30000001192092896 | 0.3 | Low | No change |
| topP | 0.949999988079071 | 0.94 | Low | No change |
| maxToken | 24000 | 24000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 300 | 90 | High | Validate timeout behavior |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | [DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z] | [] | High | Validate tool availability |

### 6.1.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present (tSQLStandardsKb collection) | Not Present | High | Validate knowledge base access |

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI UnitTesting Tsql

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
| modelDeploymentName | anthropic.claude-4_5-sonnet | text-embedding-ada-002 | High | Validate model compatibility |
| model | anthropic.claude-4-5-sonnet | model | High | Validate model compatibility |
| temperature | 0.30000001192092896 | 0.3 | Low | No change |
| topP | 0.949999988079071 | 0.94 | Low | No change |
| maxToken | 24000 | 24000 | Low | No change |
| maxIter | 10 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 600 | 90 | High | Validate timeout behavior |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | [DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z] | [] | High | Validate tool availability |

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available