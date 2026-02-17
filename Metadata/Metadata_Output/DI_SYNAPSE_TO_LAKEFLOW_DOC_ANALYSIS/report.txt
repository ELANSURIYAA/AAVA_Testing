# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 76%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI Synapse SQL Documentation | 68% | Medium | role/goal/backstory removed, description masked, model configs matched | Validate instruction field removal impact, unmask description field |
| DI Synapse To Lakeflow Analyzer | 84% | Medium | role/goal/backstory removed, description matched, model configs matched | Validate instruction field removal impact |
| DI Synapse To Lakeflow Plan | 84% | Medium | role/goal/backstory removed, description matched, model configs matched | Validate instruction field removal impact |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_SYNAPSE_TO_LAKEFLOW_DOC_&_ANALYSIS
**Workflow Name (AAVA 2.0):** DI SYNAPSE TO LAKEFLOW DOC & ANALYSIS

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 7923 | id | 2516 | Renamed + Modified | Field renamed and value changed | High | Update workflow ID references |
| Naming | name | DI_SYNAPSE_TO_LAKEFLOW_DOC_&_ANALYSIS | name | DI SYNAPSE TO LAKEFLOW DOC & ANALYSIS | Matched (Normalized) | Minor formatting differences | Low | No change |
| Description | description | Analyzing and Documenting the Synapse Code | description | Analyzing and Documenting the Synapse Code | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-11-12T06:40:01.699+00:00 | createdAt | 2025-11-05T11:02:32.067907 | Modified | Creation timestamp differs | Medium | Verify workflow versioning |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed but same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure changed | Medium | Align configuration structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Update memory configuration access |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Confirm metadata removal acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | High | Confirm metadata removal acceptable |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | High | Confirm metadata removal acceptable |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | High | Confirm metadata removal acceptable |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | High | Confirm metadata removal acceptable |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | High | Confirm metadata removal acceptable |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | High | Confirm metadata removal acceptable |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | High | Confirm metadata removal acceptable |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | High | Confirm metadata removal acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | jahnavi.lingutla@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | jahnavi.lingutla@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | jahnavi.lingutla@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T11:02:33.180421 | Medium | Ensure approval workflow is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete functionality is implemented |
| parentId | Parent workflow reference | -1 | Low | Validate workflow hierarchy handling |
| realmId | Realm/tenant identifier | 32 | Medium | Ensure multi-tenancy is handled |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | callbacks: [] | workflowConfigs: {managerLlm: [{}], enableAgenticMemory: false} | Medium | Align configuration structure and validate manager LLM settings |
| enableAgenticMemory | Direct field: false | Nested in workflowConfigs: false | Medium | Update memory configuration access pattern |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agent count

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Synapse_Documentation | DI Synapse SQL Documentation | Renamed | Naming convention updated |
| DI_Synapse_To_Lakeflow_Analyzer | DI Synapse To Lakeflow Analyzer | Renamed | Naming convention updated |
| DI_Synapse_To_Lakeflow_Plan | DI Synapse To Lakeflow Plan | Renamed | Naming convention updated |

---

## 6. Agent Configuration Differences

## Agent: DI Synapse SQL Documentation

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Medium | Validate new instruction field behavior |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.20000000298023224 | 0.2 | Low | No change |
| topP | 1.0 | 0.94 | Medium | Validate parameter change impact |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Available | Medium | Validate iteration limit removal |
| maxRpm | 0 | Not Available | Low | Validate rate limit removal |
| maxExecutionTime | 300 | 90 | Medium | Validate timeout reduction impact |

### 6.1.3 Tools Comparison

Not Available

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI Synapse To Lakeflow Analyzer

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.20000000298023224 | 0.2 | Low | No change |
| topP | 0.949999988079071 | 0.94 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 30 | Not Available | Medium | Validate iteration limit removal |
| maxRpm | 0 | Not Available | Low | Validate rate limit removal |
| maxExecutionTime | 300 | 90 | Medium | Validate timeout reduction impact |

### 6.2.3 Tools Comparison

Not Available

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DI Synapse To Lakeflow Plan

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.20000000298023224 | 0.2 | Low | No change |
| topP | 0.949999988079071 | 0.94 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 30 | Not Available | Medium | Validate iteration limit removal |
| maxRpm | 0 | Not Available | Low | Validate rate limit removal |
| maxExecutionTime | 300 | 90 | Medium | Validate timeout reduction impact |

### 6.3.3 Tools Comparison

Not Available

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available

---

**CSV file successfully uploaded to:** Metadata/Metadata_Output/DI_SYNAPSE_TO_LAKEFLOW_DOC_ANALYSIS/DI_SYNAPSE_TO_LAKEFLOW_DOC_ANALYSIS_comparison.csv