# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 76%**
**Total Agents Compared: 2**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI-DQ Rule-to-Snowflake SP | 74% | Medium | Model changed (gpt-4o → gpt-4.1), role/goal/backstory removed, expectedOutput missing | Validate model compatibility and add missing instruction fields |
| DI-DQ Rule-to-Informatica Mapping | 78% | Medium | Model changed (gpt-4o → gpt-4.1), role/goal/backstory removed, expectedOutput missing | Validate model compatibility and add missing instruction fields |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI-DataQuality_SF-INFA
**Workflow Name (AAVA 2.0):** DI-DataQuality SF-INFA

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1619 | id | 1820 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new ID |
| Naming | name | DI-DataQuality_SF-INFA | name | DI-DataQuality SF-INFA | Matched (Normalized) | Minor formatting difference | Low | No change needed |
| Description | description | This workflow takes DQ recommendations... | description | This workflow takes DQ recommendations... | Matched | Same description | Low | No change |
| Audit | createdAt | 2025-04-25T13:34:30.985+00:00 | createdAt | 2025-11-05T10:36:19.750522 | Modified | Creation timestamp updated | Low | Expected for new version |
| Agents List | pipeLineAgents | [2 agents] | workflowAgents | [2 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Enhanced configuration structure | Medium | Align configuration handling |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Low | Update configuration access |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm removal acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm removal acceptable |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal acceptable |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm removal acceptable |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal acceptable |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm removal acceptable |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm removal acceptable |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm removal acceptable |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm removal acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | gogulkanth.ashokan@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified | gogulkanth.ashokan@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | gogulkanth.ashokan@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T10:36:21.014214 | Medium | Implement approval tracking |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Standard deletion handling |
| parentId | Parent workflow reference | -1 | Low | Hierarchy tracking |
| realmId | Realm/tenant identifier | 32 | Medium | Ensure multi-tenancy support |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align configuration structure |
| managerLlm | Not available | Empty object {} | Low | Define manager LLM configuration |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Low | Update configuration access path |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 2
**AAVA 2.0 total agents:** 2
**Coverage:** Same agents maintained

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI-DQ_Rule-to-Snowflake_SP | DI-DQ Rule-to-Snowflake SP | Renamed | Underscore to hyphen conversion |
| DI-DQ_Rule-to-Informatica_Mapping | DI-DQ Rule-to-Informatica Mapping | Renamed | Underscore to hyphen conversion |

---

## 6. Agent Configuration Differences

## Agent: DI-DQ Rule-to-Snowflake SP

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
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | Null vs zero handling |
| maxRpm | 0 | null | Low | Null vs zero handling |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.1.3 Tools Comparison

**Not Available** - No tools configured in either version

### 6.1.4 Knowledge Base Comparison

**Not Available** - No knowledge base configuration in either version

### 6.1.5 Guardrails Comparison

**Not Available** - No guardrails configuration in either version

---

## Agent: DI-DQ Rule-to-Informatica Mapping

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
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | Null vs zero handling |
| maxRpm | 0 | null | Low | Null vs zero handling |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.2.3 Tools Comparison

**Not Available** - No tools configured in either version

### 6.2.4 Knowledge Base Comparison

**Not Available** - No knowledge base configuration in either version

### 6.2.5 Guardrails Comparison

**Not Available** - No guardrails configuration in either version

Now I need to create the CSV file with the required format:

Action: GitHub File Writer Tool
Action Input: {"repo": "ELANSURIYAA/AAVA_Testing", "branch": "main", "token": "<REDACTED_GITHUB_TOKEN>", "folder_name": "Metadata/Metadata_Output", "file_name": "DIDataQuality_SFINFA/DIDataQuality_SFINFA_comparison.csv", "content": "Workflow Comparison Score,Total Agents Compared
76%,2

Agent Name,Agent Score,Risk Level,Key Score Drivers,Migration Action Required
DI-DQ Rule-to-Snowflake SP,74%,Medium,Model changed (gpt-4o → gpt-4.1); role/goal/backstory removed; expectedOutput missing,Validate model compatibility and add missing instruction fields
DI-DQ Rule-to-Informatica Mapping,78%,Medium,Model changed (gpt-4o → gpt-4.1); role/goal/backstory removed; expectedOutput missing,Validate model compatibility and add missing instruction fields"}