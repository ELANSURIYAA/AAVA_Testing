# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 76%
**Total Agents Compared:** 1

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI AbInitio XFR To PySpark | 76% | Medium | role removed, goal removed, backstory removed, model changed, temperature modified | Validate instruction completeness and runtime behavior |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_AbInitio_XFR_To_PySpark_EMR_Glue
**Workflow Name (AAVA 2.0):** DI AbInitio XFR To PySpark

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 8567 | id | 1857 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_AbInitio_XFR_To_PySpark_EMR_Glue | name | DI AbInitio XFR To PySpark | Matched (Normalized) | Name simplified, underscores removed | Low | Update display references |
| Description | description | This workflow is to convert Ab Initio .xfr transformation logic into reusable PySpark functions. | description | This workflow is to convert Ab Initio .xfr transformation logic into reusable PySpark functions. | Matched (Normalized) | Description matches after normalization | Low | No change |
| Audit | createdAt | 2025-11-18T10:05:50.284+00:00 | createdAt | 2025-11-05T10:37:45.872085 | Modified | Creation timestamp differs | Medium | Verify audit trail consistency |
| Agents List | pipeLineAgents | Array with 1 agent | workflowAgents | Array with 1 agent | Renamed + Matched (Normalized) | Field renamed but structure preserved | Low | Update code references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Enhanced configuration structure | Medium | Align configuration handling |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Low | Update configuration access |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Ensure governance tracking |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Ensure governance tracking |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Ensure governance tracking |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Ensure governance tracking |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Ensure governance tracking |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Medium | Ensure governance tracking |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Medium | Ensure governance tracking |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Medium | Ensure governance tracking |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Ensure governance tracking |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User audit trail | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | Modification audit trail | default@ascendion.com | Medium | Ensure user tracking is implemented |
| approvedBy | Approval audit trail | default@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure audit trail consistency |
| approvedAt | Approval timestamp | 2025-11-05T10:37:47.105450 | Medium | Ensure approval workflow is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure deletion handling is implemented |
| parentId | Workflow hierarchy | -1 | Low | Validate workflow relationships |
| realmId | Multi-tenancy support | 1 | Medium | Ensure tenant isolation is handled |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align configuration structure |
| managerLlm | Not available | Empty object array | Medium | Validate manager LLM configuration |
| enableAgenticMemory | Top-level field (false) | Nested in workflowConfigs (false) | Low | Update configuration access pattern |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 1
**AAVA 2.0 total agents:** 1
**Coverage:** Same agent count, name updated

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_AbInitio_XFR_To_PySpark_EMR_Glue | DI AbInitio XFR To PySpark | Renamed | Naming convention updated, underscores removed |

---

## 6. Agent Configuration Differences

## Agent: DI AbInitio XFR To PySpark

---

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility and performance |
| model | anthropic.claude-4-sonnet | model | High | Validate model compatibility and performance |
| temperature | 0.20000000298023224 | 0.3 | Medium | Validate output consistency |
| topP | 1.0 | 0.94 | Low | Minor parameter adjustment |
| maxToken | 64000 | 8000 | High | Validate token limit sufficiency |
| maxIter | 0 | null | Low | Default behavior unchanged |
| maxRpm | 0 | null | Low | Default behavior unchanged |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |
| allowDelegation | false | true | Medium | Validate delegation behavior |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

---

### 6.1.3 Tools Comparison

**Not Available** - No tools configured in either version.

---

### 6.1.4 Knowledge Base Comparison

**Not Available** - No knowledge base configuration in either version.

---

### 6.1.5 Guardrails Comparison

**Not Available** - No guardrails configuration in either version.