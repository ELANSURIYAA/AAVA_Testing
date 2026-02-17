# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 72%
**Total Agents Compared:** 5

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI SQL Server To Snowflake Converter | 78% | Medium | role/goal/backstory removed, model config matched | Validate instruction field behavior |
| DI SQL Server To Snowflake Unit Test | 65% | Medium | role/goal/backstory removed, description masked | Add missing fields or confirm deprecation |
| DI SQL Server To Snowflake Conversion Tester | 78% | Medium | role/goal/backstory removed, model config matched | Validate instruction field behavior |
| DI SQL Server To Snowflake Reconciliation | 65% | Medium | role/goal/backstory removed, description masked | Add missing fields or confirm deprecation |
| DI SQL Server To Snowflake Reviewer | 72% | Medium | role/goal/backstory removed, model changed to Bedrock | Validate runtime behavior |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_SQL_Server_To_Snowflake_Conversion
**Workflow Name (AAVA 2.0):** DI SQL Server To Snowflake Conversion

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1042 | id | 4293 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new ID |
| Naming | name | DI_SQL_Server_To_Snowflake_Conversion | name | DI SQL Server To Snowflake Conversion | Matched (Normalized) | Spacing normalized | Low | No change |
| Description | description | Sqlserver to snowflake _Converter | description | Sqlserver to snowflake _Converter | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-06-17T07:45:23.888+00:00 | createdAt | 2025-11-05T11:57:56.140406 | Modified | Different creation timestamps | Low | No change |
| Agents List | pipeLineAgents | [5 agents] | workflowAgents | [5 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm, enableAgenticMemory} | Renamed + Modified | Enhanced configuration structure | Medium | Align configuration handling |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Update memory config access |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm removal acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm removal acceptable |
| Domain | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal acceptable |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm removal acceptable |
| Project | project | AVA | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal acceptable |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm removal acceptable |
| Team | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm removal acceptable |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm removal acceptable |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm removal acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User tracking | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is handled |
| modifiedBy | Modification tracking | elansuriyaa.p@ascendion.com | Medium | Implement modification tracking |
| approvedBy | Approval tracking | elansuriyaa.p@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Modification timestamp | 2025-12-03T15:03:31.224436 | Low | Track modification times |
| approvedAt | Approval timestamp | 2025-11-05T11:57:57.190609 | Low | Track approval times |
| status | Workflow state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete logic |
| parentId | Hierarchy tracking | -1 | Low | Handle workflow hierarchy |
| realmId | Realm association | 32 | Medium | Ensure realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align configuration structure |
| managerLlm | Direct field | Nested in workflowConfigs | Medium | Update configuration access patterns |
| enableAgenticMemory | Direct field | Nested in workflowConfigs | Medium | Update memory configuration handling |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5
**AAVA 2.0 total agents:** 5
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_SQL_Server_To_Snowflake_Converter | DI SQL Server To Snowflake Converter | Renamed | Underscore to space conversion |
| DI_SQL_Server_To_Snowflake_Unit_Test | DI SQL Server To Snowflake Unit Test | Renamed | Underscore to space conversion |
| DI_SQL_Server_To_Snowflake_Conversion_Tester | DI SQL Server To Snowflake Conversion Tester | Renamed | Underscore to space conversion |
| DI_SQL_Server_To_Snowflake_Reconciliation | DI SQL Server To Snowflake Reconciliation | Renamed | Underscore to space conversion |
| DI_SQL_Server_To_Snowflake_Reviewer | DI SQL Server To Snowflake Reviewer | Renamed | Underscore to space conversion |

---

## 6. Agent Configuration Differences

## Agent: DI SQL Server To Snowflake Converter

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | Medium | Validate new instruction field behavior |

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model reference |
| temperature | 0.30000001192092896 | 0.3 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | No change (normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | null | Low | No change |
| maxRpm | 0 | null | Low | No change |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout behavior |
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

## Agent: DI SQL Server To Snowflake Unit Test

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Medium | Validate masked content |
| expectedOutput | Present | Not Present | Medium | Validate new instruction field behavior |

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model reference |
| temperature | 0.30000001192092896 | 0.3 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | No change (normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | null | Low | No change |
| maxRpm | 0 | null | Low | No change |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout behavior |
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

## Agent: DI SQL Server To Snowflake Conversion Tester

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | Medium | Validate new instruction field behavior |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model reference |
| temperature | 0.30000001192092896 | 0.3 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | No change (normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | null | Low | No change |
| maxRpm | 0 | null | Low | No change |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout behavior |
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

## Agent: DI SQL Server To Snowflake Reconciliation

### 6.4.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Medium | Validate masked content |
| expectedOutput | Present | Not Present | Medium | Validate new instruction field behavior |

### 6.4.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model reference |
| temperature | 0.30000001192092896 | 0.3 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | No change (normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | null | Low | No change |
| maxRpm | 0 | null | Low | No change |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout behavior |
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

## Agent: DI SQL Server To Snowflake Reviewer

### 6.5.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | Medium | Validate new instruction field behavior |

### 6.5.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | anthropic.claude-3-7-sonnet | gpt-4.1 | High | Validate model change impact |
| model | claude-3.7sonnet | model | High | Validate model reference change |
| temperature | 0.30000001192092896 | 0.3 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | No change (normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | null | Low | No change |
| maxRpm | 0 | null | Low | No change |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout behavior |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.5.3 Tools Comparison
Not Available

### 6.5.4 Knowledge Base Comparison
Not Available

### 6.5.5 Guardrails Comparison
Not Available