# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 85%
**Total Agents Compared:** 2

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI SASCode Audit | 88% | Medium | Model deployment changed from gpt-4o to gpt-4.1; role/goal/backstory removed | Validate model compatibility and instruction completeness |
| DI SASCode Audit Review | 82% | Medium | Model deployment changed from gpt-4o to gpt-4.1; role/goal/backstory removed | Validate model compatibility and instruction completeness |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_SASCode_Auditor
**Workflow Name (AAVA 2.0):** DI SASCode Auditor

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 2264 | id | 1902 | Renamed + Modified | Field renamed and value changed | High | Update references to new workflow ID |
| Naming | name | DI_SASCode_Auditor | name | DI SASCode Auditor | Matched (Case Normalization) | Minor spacing difference | Low | No change |
| Description | description | Analyze SAS code to verify compliance with SAS-Oracle interaction best practices, ensuring efficient queries that use the Oracle platform strengths and reduce SAS server workload. | description | Analyze SAS code to verify compliance with SAS-Oracle interaction best practices, ensuring efficient queries that use the Oracle platform strengths and reduce SAS server workload. | Matched | Same description | Low | No change |
| Audit | createdAt | 2025-06-05T08:10:05.915+00:00 | createdAt | 2025-11-05T10:39:32.485295 | Matched | Field present in both, different timestamps | Low | No change |
| Agents List | pipeLineAgents | [2 agents] | workflowAgents | [2 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {"managerLlm": [{}], "enableAgenticMemory": false} | Renamed + Modified | Field renamed and structure enhanced | Medium | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Verify memory settings in new structure |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm org context handling |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm org context handling |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm domain context handling |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm domain context handling |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm project context handling |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm project context handling |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm team context handling |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm team context handling |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm level context handling |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T10:39:33.681598 | Medium | Ensure approval workflow is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure deletion handling is implemented |
| parentId | Parent workflow reference | -1 | Medium | Ensure workflow hierarchy is handled |
| realmId | Realm identifier | 1 | Medium | Ensure realm context is handled |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Configure manager LLM settings |
| managerLlm | Not available | Empty object [{}] | Medium | Define manager LLM configuration |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update memory configuration access |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 2
**AAVA 2.0 total agents:** 2
**Coverage:** Same agents maintained

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_SASCode_Audit | DI SASCode Audit | Renamed | Underscore replaced with space |
| DI_SASCode_Audit_Review | DI SASCode Audit Review | Renamed | Underscores replaced with spaces |

---

## 6. Agent Configuration Differences

## Agent: DI SASCode Audit

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
| temperature | 0.30000001192092896 | 0.3 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | No change (normalized) |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 20 | Not Present | Medium | Validate iteration limits |
| maxRpm | 0 | Not Present | Medium | Validate rate limits |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout settings |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | [] | Not Present | Medium | Confirm user tools handling |

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI SASCode Audit Review

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
| temperature | 0.30000001192092896 | 0.3 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | No change (normalized) |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 20 | Not Present | Medium | Validate iteration limits |
| maxRpm | 0 | Not Present | Medium | Validate rate limits |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout settings |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | [] | Not Present | Medium | Confirm user tools handling |

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available