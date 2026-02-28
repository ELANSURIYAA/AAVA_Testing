# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

# 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 86%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| T-SQL Server Documentation | 92% | Low | model deployment changed, minor field restructuring | Validate model compatibility |
| T-SQL Server to PySpark Analyzer | 88% | Medium | agent name normalized, model deployment changed | Validate model compatibility and name consistency |
| T-SQL Server to PySpark Plan | 78% | Medium | model deployment changed, field restructuring | Validate model compatibility and runtime configuration |

---

# 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** SQL Server(T-SQL) to PySpark Doc&Analysis
**Workflow Name (AAVA 2.0):** SQL Server(T-SQL) to PySpark Doc&Analysis

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1157 | id | 3923 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to new workflow ID |
| Naming | name | SQL Server(T-SQL) to PySpark Doc&Analysis | name | SQL Server(T-SQL) to PySpark Doc&Analysis | Matched | Workflow name unchanged | Low | No change |
| Description | description | To migrate or integrate SQL Server T-SQL-based processes into PySpark for distributed data processing, enabling scalability and faster computation for large datasets. This workflow streamlines the transition and ensures accurate data handling and analysis. | description | To migrate or integrate SQL Server T-SQL-based processes into PySpark for distributed data processing, enabling scalability and faster computation for large datasets. This workflow streamlines the transition and ensures accurate data handling and analysis. | Matched | Description unchanged | Low | No change |
| Audit | createdAt | 2025-03-21T09:09:18.784+00:00 | createdAt | 2025-11-05T11:46:26.988645 | Matched | Field name same, value updated for new workflow | Low | No change |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed but agent count preserved | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {"managerLlm": [{}], "enableAgenticMemory": false} | Renamed + Modified | Field renamed and structure enhanced | High | Implement new workflow configuration structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Verify memory configuration in new structure |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Confirm removal of organizational context is acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | High | Confirm removal of organizational context is acceptable |
| Domain | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | High | Confirm removal of domain context is acceptable |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | High | Confirm removal of domain context is acceptable |
| Project | project | AVA | Not Available | Not Available | Removed | Project metadata removed | High | Confirm removal of project context is acceptable |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | High | Confirm removal of project context is acceptable |
| Team | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | High | Confirm removal of team context is acceptable |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | High | Confirm removal of team context is acceptable |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed | High | Confirm removal of level context is acceptable |

---

# 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-11-30T11:55:00.892060 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T11:46:28.036915 | Medium | Ensure approval workflow is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete functionality is implemented |
| parentId | Parent workflow reference | -1 | Medium | Ensure workflow hierarchy is handled |
| realmId | Realm/tenant identifier | 1 | Medium | Ensure multi-tenancy is handled |

---

# 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align defaults and implement new configuration structure |
| managerLlm | Not available | Empty object {} | Medium | Define manager LLM configuration if needed |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update configuration access patterns |

---

# 5. Agent Inventory Summary

## 5.1 Agent Count & Coverage

**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agent count maintained

## 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| T-SQL Server Documentation | T-SQL Server Documentation | Matched | Name unchanged |
| T-SQL Server_to_PySpark_Analyzer | T-SQL Server to PySpark Analyzer | Matched (Normalized) | Underscore replaced with space |
| T-SQL Server_to_PySpark_Plan | T-SQL Server to PySpark Plan | Matched (Normalized) | Underscore replaced with space |

---

# 6. Agent Configuration Differences

## Agent: T-SQL Server Documentation

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
| modelDeploymentName | anthropic.claude-3-7-sonnet | gpt-4.1 | High | Validate model compatibility and performance |
| model | claude-3.7sonnet | model | High | Validate model compatibility and performance |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Verify iteration configuration |
| maxRpm | 0 | Not Present | Medium | Verify rate limit configuration |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout configuration changed |

---

## 6.1.3 Tools Comparison

**Not Available** - No tools configured in either version

---

## 6.1.4 Knowledge Base Comparison

**Not Available** - No knowledge base configured in either version

---

## 6.1.5 Guardrails Comparison

**Not Available** - No guardrails configured in either version

---

## Agent: T-SQL Server to PySpark Analyzer

---

## 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

## 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | anthropic.claude-3-7-sonnet | gpt-4.1 | High | Validate model compatibility and performance |
| model | claude-3.7sonnet | model | High | Validate model compatibility and performance |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Verify iteration configuration |
| maxRpm | 0 | Not Present | Medium | Verify rate limit configuration |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout configuration changed |

---

## 6.2.3 Tools Comparison

**Not Available** - No tools configured in either version

---

## 6.2.4 Knowledge Base Comparison

**Not Available** - No knowledge base configured in either version

---

## 6.2.5 Guardrails Comparison

**Not Available** - No guardrails configured in either version

---

## Agent: T-SQL Server to PySpark Plan

---

## 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

## 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | anthropic.claude-3-7-sonnet | gpt-4.1 | High | Validate model compatibility and performance |
| model | claude-3.7sonnet | model | High | Validate model compatibility and performance |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Verify iteration configuration |
| maxRpm | 0 | Not Present | Medium | Verify rate limit configuration |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout configuration changed |

---

## 6.3.3 Tools Comparison

**Not Available** - No tools configured in either version

---

## 6.3.4 Knowledge Base Comparison

**Not Available** - No knowledge base configured in either version

---

## 6.3.5 Guardrails Comparison

**Not Available** - No guardrails configured in either version