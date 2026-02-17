# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 61%
**Total Agents Compared:** 1

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI INFA XML DQ | 61% | Medium | role/goal/backstory removed, model changed from gpt-4 to model, agentId changed | Validate agent instruction completeness and model compatibility |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_INFA_XML_DQ
**Workflow Name (AAVA 2.0):** DI INFA XML DQ

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1668 | id | 2590 | Renamed + Modified | Field renamed and value changed from 1668 to 2590 | High | Update all references to use new workflow ID |
| Naming | name | DI_INFA_XML_DQ | name | DI INFA XML DQ | Matched (Normalized) | Minor spacing differences normalized | Low | No change |
| Description | description | This workflow requires an XML file to be provided as an input so that it generates the appropriate Data Quality rules and the SQLs | description | This workflow requires an XML file to be provided as an input so that it generates the appropriate Data Quality rules and the SQLs | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-04-30T07:44:59.992+00:00 | createdAt | 2025-11-05T11:07:11.662030 | Matched | Field present in both, values differ due to different creation times | Low | No change |
| Agents List | pipeLineAgents | Present | workflowAgents | Present | Renamed + Matched (Normalized) | Field renamed but structure preserved | Medium | Update code references |
| Workflow Config | callbacks | [] | workflowConfigs | Present | Renamed + Modified | Field renamed and structure enhanced | Medium | Align configuration handling |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Update memory configuration access |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | Medium | Confirm removal is acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organizational ID removed | Medium | Confirm removal is acceptable |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal is acceptable |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm removal is acceptable |
| Project | project | Conversions | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal is acceptable |
| Project ID | projectId | 149 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm removal is acceptable |
| Team | team | DataEngineer | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm removal is acceptable |
| Team ID | teamId | 150 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm removal is acceptable |
| Level ID | levelId | 150 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | Track workflow creator | mohamed.shahidomar@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | Track workflow modifier | mohamed.shahidomar@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | Track workflow approver | mohamed.shahidomar@ascendion.com | Medium | Ensure approval workflow is handled |
| modifiedAt | Track modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Track approval timestamp | 2025-11-05T11:07:12.725510 | Medium | Ensure approval workflow is handled |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure deletion handling is implemented |
| parentId | Workflow hierarchy | -1 | Low | Validate hierarchy handling |
| realmId | Realm identifier | 32 | Medium | Ensure realm context is handled |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align configuration structure |
| managerLlm | Not available | Present (empty object) | Medium | Validate manager LLM configuration |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update memory configuration access |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 1
**AAVA 2.0 total agents:** 1
**Coverage:** Same agent count, different agent IDs

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_INFA_XML_DQ | DI INFA XML DQ | Renamed | Naming convention updated with spaces |

---

## 6. Agent Configuration Differences

## Agent: DI INFA XML DQ

---

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

---

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model compatibility and behavior |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Validate iteration handling |
| maxRpm | 0 | Not Available | Medium | Validate rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout changed from 0 to 90 seconds |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

---

### 6.1.3 Tools Comparison

Not Available

---

### 6.1.4 Knowledge Base Comparison

Not Available

---

### 6.1.5 Guardrails Comparison

Not Available