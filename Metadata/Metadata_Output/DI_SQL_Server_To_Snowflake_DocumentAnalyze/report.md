# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 78%**
**Total Agents Compared: 3**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI SQL Server To Snowflake Documentation | 85% | Medium | role/goal/backstory removed, description matched, LLM configs matched | Validate agent behavior without role/goal/backstory fields |
| DI SQL Server To Snowflake Analyzer | 85% | Medium | role/goal/backstory removed, description matched, LLM configs matched | Validate agent behavior without role/goal/backstory fields |
| DI SQL Server To Snowflake Plan | 85% | Medium | role/goal/backstory removed, description matched, LLM configs matched | Validate agent behavior without role/goal/backstory fields |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_SQL_Server_To_Snowflake_Document&Analyze
**Workflow Name (AAVA 2.0):** DI SQL Server To Snowflake Document&Analyze

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 1031 | id | 4294 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new ID |
| Naming | name | DI_SQL_Server_To_Snowflake_Document&Analyze | name | DI SQL Server To Snowflake Document&Analyze | Matched (Normalized) | Minor formatting differences | Low | None |
| Description | description | SQL Server to Snowflake Doc&Analyze | description | SQL Server to Snowflake Doc&Analyze | Matched | Exact match | Low | None |
| Audit | createdAt | 2025-06-17T07:51:24.199+00:00 | createdAt | 2025-11-05T11:57:56.634416 | Modified | Different creation timestamps | Low | None |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure changed | High | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Update memory configuration access |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | Medium | Confirm removal acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organizational ID removed | Medium | Confirm removal acceptable |
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
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking works |
| approvedBy | User who approved workflow | elansuriyaa.p@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure timestamp tracking works |
| approvedAt | Approval timestamp | 2025-11-05T11:57:57.691082 | Medium | Implement approval tracking |
| status | Workflow approval state | APPROVED | High | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete functionality |
| parentId | Parent workflow reference | -1 | Medium | Handle workflow hierarchy |
| realmId | Realm identifier | 32 | Medium | Ensure realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|---------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | High | Configure manager LLM settings |
| managerLlm | Not available | Empty object {} | Medium | Define manager LLM configuration |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update memory config access pattern |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_SQL_Server_To_Snowflake_Documentation | DI SQL Server To Snowflake Documentation | Renamed | Naming convention updated |
| DI_SQL_Server_To_Snowflake_Analyzer | DI SQL Server To Snowflake Analyzer | Renamed | Naming convention updated |
| DI_SQL_Server_To_Snowflake_Plan | DI SQL Server To Snowflake Plan | Renamed | Naming convention updated |

---

## 6. Agent Configuration Differences

## Agent: DI SQL Server To Snowflake Documentation

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | None |
| model | gpt-4 | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | None |
| topP | 0.949999988079071 | 0.94 | Low | None |
| maxToken | 8000 | 8000 | Low | None |
| maxIter | 0 | null | Medium | Validate null handling |
| maxRpm | 0 | null | Medium | Validate null handling |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout behavior |

### 6.1.3 Tools Comparison

Not Available

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI SQL Server To Snowflake Analyzer

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | None |
| model | gpt-4 | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | None |
| topP | 0.949999988079071 | 0.94 | Low | None |
| maxToken | 8000 | 8000 | Low | None |
| maxIter | 0 | null | Medium | Validate null handling |
| maxRpm | 0 | null | Medium | Validate null handling |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout behavior |

### 6.2.3 Tools Comparison

Not Available

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DI SQL Server To Snowflake Plan

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | None |
| model | gpt-4 | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | None |
| topP | 0.949999988079071 | 0.94 | Low | None |
| maxToken | 8000 | 8000 | Low | None |
| maxIter | 0 | null | Medium | Validate null handling |
| maxRpm | 0 | null | Medium | Validate null handling |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout behavior |

### 6.3.3 Tools Comparison

Not Available

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available