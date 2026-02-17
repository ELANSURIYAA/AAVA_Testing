# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

# 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 87%
**Total Agents Compared:** 5

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| SqlServer to DBT Converter | 89% | Medium | Model changed (gpt-4o to gpt-4.1); role/goal/backstory removed; description matched | Validate model compatibility and confirm instruction field removal |
| SqlServer to DBT Unit Test | 89% | Medium | Model changed (gpt-4o to gpt-4.1); role/goal/backstory removed; description matched | Validate model compatibility and confirm instruction field removal |
| SqlServer to DBT Conversion Tester | 89% | Medium | Model changed (gpt-4o to gpt-4.1); role/goal/backstory removed; description matched | Validate model compatibility and confirm instruction field removal |
| SqlServer to DBT Reconciliation | 89% | Medium | Model changed (gpt-4o to gpt-4.1); role/goal/backstory removed; description matched | Validate model compatibility and confirm instruction field removal |
| SQL Server to DBT Reviewer | 84% | Medium | Model changed (gpt-4o to gpt-4.1); role/goal/backstory removed; description matched; maxExecutionTime added | Validate model compatibility and confirm instruction field removal |

---

# 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** Sql Server to DBT Converter
**Workflow Name (AAVA 2.0):** Sql Server to DBT Converter

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1068 | id | 3812 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to use new ID |
| Naming | name | Sql Server to DBT Converter | name | Sql Server to DBT Converter | Matched | No change | Low | None |
| Description | description | Sql Server to DBT Converter | description | Sql Server to DBT Converter | Matched | No change | Low | None |
| Audit | createdAt | 2025-08-18T05:37:08.440+00:00 | createdAt | 2025-11-05T11:43:09.196660 | Matched (Normalized) | Timestamp updated for new workflow | Low | None |
| Agents List | pipeLineAgents | Array of 5 agents | workflowAgents | Array of 5 agents | Renamed + Matched (Normalized) | Field renamed but agent count preserved | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | Object with managerLlm | Renamed + Modified | Enhanced configuration structure | High | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Verify memory configuration |
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

# 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | sharmilee.d@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified | sharmilee.d@ascendion.com | Medium | Ensure modification tracking works |
| approvedBy | User who approved workflow | sharmilee.d@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-11-30T11:55:00.892060 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T11:43:10.301867 | Low | Standard audit field |
| status | Workflow approval state | APPROVED | High | Ensure workflow lifecycle management |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete handling |
| parentId | Parent workflow reference | -1 | Medium | Handle workflow versioning |
| realmId | Realm/tenant identifier | 32 | High | Ensure multi-tenancy support |

---

# 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm | High | Configure manager LLM settings |
| enableAgenticMemory | Top-level field (false) | Nested in workflowConfigs (false) | Medium | Update configuration access path |
| callbacks | Empty array | Not available | Medium | Verify callback handling not needed |

---

# 5. Agent Inventory Summary

## 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5
**AAVA 2.0 total agents:** 5
**Coverage:** Same agent count with naming updates

## 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| SqlServer_to_DBT_Converter | SqlServer to DBT Converter | Renamed | Underscore to space conversion |
| SqlServer_to_DBT_Unit_Test | SqlServer to DBT Unit Test | Renamed | Underscore to space conversion |
| SqlServer_to_DBT_Conversion_Tester | SqlServer to DBT Conversion Tester | Renamed | Underscore to space conversion |
| SqlServer_to_DBT_Reconciliation | SqlServer to DBT Reconciliation | Renamed | Underscore to space conversion |
| SQL Server to DBT Reviewer | SQL Server to DBT Reviewer | Matched | No change |

---

# 6. Agent Configuration Differences

## Agent: SqlServer to DBT Converter

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
| model | gpt-4o | model | High | Validate model compatibility |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change |
| maxToken | 4000 | 4000 | Matched (Normalized) | No change |
| maxIter | 0 | null | Modified | Verify null handling |
| maxRpm | 0 | null | Modified | Verify null handling |
| maxExecutionTime | 0 | 90 | Modified | Validate timeout settings |

### 6.1.3 Tools Comparison

Not Available

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: SqlServer to DBT Unit Test

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
| model | gpt-4o | model | High | Validate model compatibility |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change |
| maxToken | 4000 | 4000 | Matched (Normalized) | No change |
| maxIter | 0 | null | Modified | Verify null handling |
| maxRpm | 0 | null | Modified | Verify null handling |
| maxExecutionTime | 0 | 90 | Modified | Validate timeout settings |

### 6.2.3 Tools Comparison

Not Available

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: SqlServer to DBT Conversion Tester

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
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model compatibility |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change |
| maxToken | 4000 | 4000 | Matched (Normalized) | No change |
| maxIter | 0 | null | Modified | Verify null handling |
| maxRpm | 0 | null | Modified | Verify null handling |
| maxExecutionTime | 0 | 90 | Modified | Validate timeout settings |

### 6.3.3 Tools Comparison

Not Available

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available

---

## Agent: SqlServer to DBT Reconciliation

### 6.4.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.4.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model compatibility |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change |
| maxToken | 4000 | 4000 | Matched (Normalized) | No change |
| maxIter | 0 | null | Modified | Verify null handling |
| maxRpm | 0 | null | Modified | Verify null handling |
| maxExecutionTime | 0 | 90 | Modified | Validate timeout settings |

### 6.4.3 Tools Comparison

Not Available

### 6.4.4 Knowledge Base Comparison

Not Available

### 6.4.5 Guardrails Comparison

Not Available

---

## Agent: SQL Server to DBT Reviewer

### 6.5.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.5.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model compatibility |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change |
| maxToken | 4000 | 4000 | Matched (Normalized) | No change |
| maxIter | 0 | null | Modified | Verify null handling |
| maxRpm | 0 | null | Modified | Verify null handling |
| maxExecutionTime | 0 | 90 | Modified | Validate timeout settings |

### 6.5.3 Tools Comparison

Not Available

### 6.5.4 Knowledge Base Comparison

Not Available

### 6.5.5 Guardrails Comparison

Not Available