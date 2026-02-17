# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Name (AAVA 1.0):** DI_MarkLogic_to_MongoDB_Doc&Analyze
**Workflow Name (AAVA 2.0):** DI MarkLogic to MongoDB Doc&Analyze

* **Workflow Comparison Score:** 86%
* **Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| MarkLogic Documentation | 88% | Low | Model deployment changed from gpt-4o to gpt-4.1; role/goal/backstory removed; maxExecutionTime added | Validate model compatibility and confirm instruction field removal |
| MarkLogic to MongDB Analyzer | 85% | Low | Model deployment changed from gpt-4o to gpt-4.1; role/goal/backstory removed; maxExecutionTime added | Validate model compatibility and confirm instruction field removal |
| MarkLogic to MongDB Plan | 85% | Low | Model deployment changed from gpt-4o to gpt-4.1; role/goal/backstory removed; maxExecutionTime added | Validate model compatibility and confirm instruction field removal |

## 2. Workflow-Level Comparison

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 1050 | id | 2624 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | DI_MarkLogic_to_MongoDB_Doc&Analyze | name | DI MarkLogic to MongoDB Doc&Analyze | Matched (Normalized) | Minor spacing differences normalized | Low | No change |
| Description | description | Detailed Documentation, Analysis and Plan for MarkLogic to MongoDB | description | Detailed Documentation, Analysis and Plan for MarkLogic to MongoDB | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-05-12T06:04:35.764+00:00 | createdAt | 2025-11-05T11:09:05.570695 | Matched | Field exists in both versions | Medium | Validate timestamp differences |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {"managerLlm":[{}],"enableAgenticMemory":false} | Renamed + Modified | Field renamed and structure enhanced | Medium | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Low | Update configuration path |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm removal is acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm removal is acceptable |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal is acceptable |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm removal is acceptable |
| Project | project | Documenting | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal is acceptable |
| Project ID | projectId | 153 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm removal is acceptable |
| Team | team | DataEng | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm removal is acceptable |
| Team ID | teamId | 154 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm removal is acceptable |
| Level ID | levelId | 154 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm removal is acceptable |

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Ensure user tracking is implemented |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Track modification history |
| approvedAt | Approval timestamp | 2025-11-05T11:09:06.624277 | Low | Track approval history |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Implement soft delete logic |
| parentId | Parent workflow reference | -1 | Low | Handle workflow hierarchy |
| realmId | Realm identifier | 1 | Medium | Ensure realm-based access control |

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Configure new workflow settings |
| managerLlm | Not available | Empty object {} | Medium | Configure manager LLM if needed |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Low | Update configuration path |

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents with structural changes

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| MarkLogic_Documentation | MarkLogic Documentation | Renamed | Underscore removed, spacing normalized |
| MarkLogic_to_MongDB_Analyzer | MarkLogic to MongDB Analyzer | Renamed | Underscore removed, spacing normalized |
| MarkLogic_to_MongDB_Plan | MarkLogic to MongDB Plan | Renamed | Underscore removed, spacing normalized |

## 6. Agent Configuration Differences

## Agent: MarkLogic Documentation

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
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model compatibility |
| model | gpt-4o | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision difference normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision difference normalized |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | Default handling difference |
| maxRpm | 0 | null | Low | Default handling difference |
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

## Agent: MarkLogic to MongDB Analyzer

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
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model compatibility |
| model | gpt-4o | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision difference normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision difference normalized |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | Default handling difference |
| maxRpm | 0 | null | Low | Default handling difference |
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

## Agent: MarkLogic to MongDB Plan

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
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model compatibility |
| model | gpt-4o | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision difference normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision difference normalized |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | Default handling difference |
| maxRpm | 0 | null | Low | Default handling difference |
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