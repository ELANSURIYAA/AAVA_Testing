# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 78%**
**Total Agents Compared: 5**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI Oracle to Snowflake Converter | 82% | Medium | Model deployment changed, role/goal/backstory removed | Validate model compatibility and instruction completeness |
| DI Oracle to Snowflake Unit Tester | 82% | Medium | Model deployment changed, role/goal/backstory removed | Validate model compatibility and instruction completeness |
| DI Oracle to Snowflake Conversion Tester | 82% | Medium | Model deployment changed, role/goal/backstory removed | Validate model compatibility and instruction completeness |
| DI Oracle to Snowflake Recon Tester | 82% | Medium | Model deployment changed, role/goal/backstory removed | Validate model compatibility and instruction completeness |
| DI Oracle to Snowflake Reviewer | 82% | Medium | Model deployment changed, role/goal/backstory removed | Validate model compatibility and instruction completeness |

---

## Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_Oracle_to_Snowflake_Conversion
**Workflow Name (AAVA 2.0):** DI Oracle to Snowflake Conversion

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1035 | id | 3745 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | DI_Oracle_to_Snowflake_Conversion | name | DI Oracle to Snowflake Conversion | Matched (Case Normalization) | Minor formatting differences | Low | No change needed |
| Description | description | Convert Oracle code to Snowflake code | description | Convert Oracle code to Snowflake code | Matched | Identical values | Low | No change |
| Audit | createdAt | 2025-04-29T10:10:48.727+00:00 | createdAt | 2025-11-05T11:41:09.593546 | Modified | Different creation timestamps | Low | Expected for different workflow instances |
| Agents List | pipeLineAgents | [5 agents] | workflowAgents | [5 agents] | Renamed + Matched (Normalized) | Field renamed but same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure changed | High | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Verify memory configuration location |
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
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | elansuriyaa.p@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T11:41:10.644204 | Low | Standard audit field |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Standard deletion handling |
| parentId | Parent workflow reference | -1 | Medium | Understand workflow hierarchy |
| realmId | Realm/tenant identifier | 32 | Medium | Ensure multi-tenancy support |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align defaults and understand new structure |
| managerLlm | Not available | Empty object {} | Medium | Configure manager LLM settings if needed |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update configuration access patterns |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5
**AAVA 2.0 total agents:** 5
**Coverage:** Same agent count with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Oracle_to_Snowflake_Converter | DI Oracle to Snowflake Converter | Renamed | Underscore to space conversion |
| DI_Oracle_to_Snowflake_Unit_Tester | DI Oracle to Snowflake Unit Tester | Renamed | Underscore to space conversion |
| DI_Oracle_to_Snowflake_Conversion_Tester | DI Oracle to Snowflake Conversion Tester | Renamed | Underscore to space conversion |
| DI_Oracle_to_Snowflake_Recon_Tester | DI Oracle to Snowflake Recon Tester | Renamed | Underscore to space conversion |
| DI_Oracle_to_Snowflake_Reviewer | DI Oracle to Snowflake Reviewer | Renamed | Underscore to space conversion |

---

## 6. Agent Configuration Differences

## Agent: DI Oracle to Snowflake Converter

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
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision difference |
| topP | 0.949999988079071 | 0.94 | Low | Normalized precision difference |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | Null vs zero handling |
| maxRpm | 0 | null | Low | Null vs zero handling |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout increased |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: DI Oracle to Snowflake Unit Tester

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
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision difference |
| topP | 0.949999988079071 | 0.94 | Low | Normalized precision difference |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | Null vs zero handling |
| maxRpm | 0 | null | Low | Null vs zero handling |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout increased |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: DI Oracle to Snowflake Conversion Tester

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
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision difference |
| topP | 0.949999988079071 | 0.94 | Low | Normalized precision difference |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | Null vs zero handling |
| maxRpm | 0 | null | Low | Null vs zero handling |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout increased |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available

---

## Agent: DI Oracle to Snowflake Recon Tester

### 6.4.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.4.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision difference |
| topP | 0.949999988079071 | 0.94 | Low | Normalized precision difference |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | Null vs zero handling |
| maxRpm | 0 | null | Low | Null vs zero handling |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout increased |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.4.3 Tools Comparison
Not Available

### 6.4.4 Knowledge Base Comparison
Not Available

### 6.4.5 Guardrails Comparison
Not Available

---

## Agent: DI Oracle to Snowflake Reviewer

### 6.5.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.5.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision difference |
| topP | 0.949999988079071 | 0.94 | Low | Normalized precision difference |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | Null vs zero handling |
| maxRpm | 0 | null | Low | Null vs zero handling |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout increased |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.5.3 Tools Comparison
Not Available

### 6.5.4 Knowledge Base Comparison
Not Available

### 6.5.5 Guardrails Comparison
Not Available

Now I need to create the CSV file with the required format and upload it to GitHub.

Action: GitHub File Writer Tool
Action Input: {"repo": "ELANSURIYAA/AAVA_Testing", "branch": "main", "token": "<REDACTED_GITHUB_TOKEN>", "folder_name": "Metadata/Metadata_Output", "file_name": "DI_Oracle_to_Snowflake_Conversion/DI_Oracle_to_Snowflake_Conversion_comparison.csv", "content": "Workflow Comparison Score,Total Agents Compared
78%,5

Agent Name,Agent Score,Risk Level,Key Score Drivers,Migration Action Required
DI Oracle to Snowflake Converter,82%,Medium,Model deployment changed role/goal/backstory removed,Validate model compatibility and instruction completeness
DI Oracle to Snowflake Unit Tester,82%,Medium,Model deployment changed role/goal/backstory removed,Validate model compatibility and instruction completeness
DI Oracle to Snowflake Conversion Tester,82%,Medium,Model deployment changed role/goal/backstory removed,Validate model compatibility and instruction completeness
DI Oracle to Snowflake Recon Tester,82%,Medium,Model deployment changed role/goal/backstory removed,Validate model compatibility and instruction completeness
DI Oracle to Snowflake Reviewer,82%,Medium,Model deployment changed role/goal/backstory removed,Validate model compatibility and instruction completeness"}