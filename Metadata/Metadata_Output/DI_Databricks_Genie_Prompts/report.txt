# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 78%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI Databricks Dashboard Visuals Recommender | 82% | Medium | Agent ID changed, role/goal/backstory removed, maxIter/maxRpm/maxExecutionTime modified | Validate runtime behavior and confirm instruction field removal |
| DI Databricks GenieAlly | 78% | Medium | Agent ID changed, role/goal/backstory removed, maxIter/maxRpm/maxExecutionTime modified | Validate runtime behavior and confirm instruction field removal |
| DI Databricks Genie Reviewer | 74% | Medium | Agent ID changed, role/goal/backstory removed, maxIter/maxRpm/maxExecutionTime modified | Validate runtime behavior and confirm instruction field removal |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_Databricks_Genie_Prompts
**Workflow Name (AAVA 2.0):** DI Databricks Genie Prompts

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 6336 | id | 2154 | Renamed + Modified | Field renamed and ID value changed | Medium | Update ID references in dependent systems |
| Naming | name | DI_Databricks_Genie_Prompts | name | DI Databricks Genie Prompts | Matched (Case Normalization) | Underscore replaced with space | Low | No change |
| Description | description | This workflow ensures the generation of clear, actionable prompts for Genie that result in meaningful and insightful reports and also it will provide unit Test Cases and SQL Queries for prompt verification with DB Values. | description | This workflow ensures the generation of clear, actionable prompts for Genie that result in meaningful and insightful reports and also it will provide unit Test Cases and SQL Queries for prompt verification with DB Values. | Matched | Identical description | Low | No change |
| Audit | createdAt | 2025-08-25T15:46:57.243+00:00 | createdAt | 2025-11-05T10:49:08.329491 | Modified | Creation timestamp updated | Low | Update audit logs |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm, enableAgenticMemory} | Renamed + Modified | Enhanced configuration structure | Medium | Migrate configuration settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Update memory configuration handling |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Confirm removal is acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | High | Confirm removal is acceptable |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | High | Confirm removal is acceptable |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | High | Confirm removal is acceptable |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | High | Confirm removal is acceptable |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | High | Confirm removal is acceptable |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | High | Confirm removal is acceptable |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | High | Confirm removal is acceptable |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | High | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | elansuriyaa.p@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T10:49:09.404867 | Low | Standard audit field |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete logic is implemented |
| parentId | Parent workflow reference | -1 | Low | Standard hierarchy field |
| realmId | Realm/tenant identifier | 32 | Medium | Ensure multi-tenancy is handled |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm array | Medium | Align configuration structure |
| managerLlm | Direct object | Array of objects with ID | Medium | Update LLM configuration handling |
| enableAgenticMemory | Root level field | Nested in workflowConfigs | Medium | Update memory configuration access |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agent count with structural changes

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Databricks_Dashboard_Visuals_Recommender | DI Databricks Dashboard Visuals Recommender | Renamed | Underscore replaced with space |
| DI_Databricks_GenieAlly | DI Databricks GenieAlly | Renamed | Underscore replaced with space |
| DI_Databricks_Genie_Reviewer | DI Databricks Genie Reviewer | Renamed | Underscore replaced with space |

---

## 6. Agent Configuration Differences

## Agent: DI Databricks Dashboard Visuals Recommender

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | anthropic.claude-4-sonnet | model | High | Update model configuration |
| temperature | 0.10000000149011612 | 0.1 | Low | Normalized precision |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Available | Medium | Validate iteration limits |
| maxRpm | 50 | Not Available | Medium | Validate rate limits |
| maxExecutionTime | 400 | 90 | High | Validate timeout settings |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Available | Low | No change |
| userTools | [DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z] | Not Available | High | Migrate tool configurations |

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI Databricks GenieAlly

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | anthropic.claude-4-sonnet | model | High | Update model configuration |
| temperature | 0.10000000149011612 | 0.1 | Low | Normalized precision |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Available | Medium | Validate iteration limits |
| maxRpm | 50 | Not Available | Medium | Validate rate limits |
| maxExecutionTime | 600 | 90 | High | Validate timeout settings |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Available | Low | No change |
| userTools | [DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z] | Not Available | High | Migrate tool configurations |

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DI Databricks Genie Reviewer

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | anthropic.claude-4-sonnet | model | High | Update model configuration |
| temperature | 0.10000000149011612 | 0.1 | Low | Normalized precision |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Available | Medium | Validate iteration limits |
| maxRpm | 50 | Not Available | Medium | Validate rate limits |
| maxExecutionTime | 400 | 90 | High | Validate timeout settings |

### 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Available | Low | No change |
| userTools | [DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z] | Not Available | High | Migrate tool configurations |

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available