# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 76%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_ECL_Documentation_JSON vs DI ECL Documentation | 85% | Medium | Model changed (gpt-4o to gpt-4.1), role/goal/backstory removed, description modified | Validate model compatibility and confirm instruction field removal |
| DI_ECL_To_JavaSpringboot_Analyzer_Json vs DI ECL To JavaSpringboot Analyzer | 72% | Medium | Model changed, description significantly modified, name normalized | Review description changes and validate model behavior |
| DI_ECL_To_JavaSpringboot_Plan_JSON vs DI ECL To JavaSpringboot Plan | 71% | Medium | Model changed, description modified, name normalized | Validate model compatibility and review instruction changes |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_ECL_To_JavaSpringboot_Doc&Analyse_JSON_WF
**Workflow Name (AAVA 2.0):** DI ECL To JavaSpringboot Doc&Analyze

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 2586 | id | 2628 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_ECL_To_JavaSpringboot_Doc&Analyse_JSON_WF | name | DI ECL To JavaSpringboot Doc&Analyze | Matched (Normalized) | Name normalized (spacing, spelling) | Low | No action required |
| Description | description | HPCC ECL to the Java Spring boot json output workflow | description | ECL to Java Springboot Documentation, Analysis and plan | Modified | Description content changed | Medium | Review description alignment |
| Audit | createdAt | 2025-06-06T04:12:05.761+00:00 | createdAt | 2025-11-05T11:09:11.518806 | Matched | Field exists in both but different timestamps | Low | Expected for different workflow instances |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure enhanced | Medium | Migrate callback logic to new config structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Update memory config references |
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
| createdBy | User who created workflow | muneeswara.pandian@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified | muneeswara.pandian@ascendion.com | Medium | Implement modification tracking |
| approvedBy | User who approved workflow | muneeswara.pandian@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T11:09:12.573339 | Medium | Implement approval tracking |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Standard deletion handling |
| parentId | Parent workflow reference | -1 | Medium | Implement workflow hierarchy |
| realmId | Realm/tenant identifier | 32 | Medium | Implement multi-tenancy support |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align configuration structure |
| managerLlm | Not available | Empty object {} | Medium | Configure manager LLM settings |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update memory config access pattern |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agent count with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_ECL_Documentation_JSON | DI ECL Documentation | Renamed | Naming convention updated (removed _JSON suffix, normalized spacing) |
| DI_ECL_To_JavaSpringboot_Analyzer_Json | DI ECL To JavaSpringboot Analyzer | Renamed | Naming convention updated (removed _Json suffix, normalized spacing) |
| DI_ECL_To_JavaSpringboot_Plan_JSON | DI ECL To JavaSpringboot Plan | Renamed | Naming convention updated (removed _JSON suffix, normalized spacing) |

---

## 6. Agent Configuration Differences

## Agent: DI_ECL_Documentation_JSON vs DI ECL Documentation

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
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility and performance |
| model | gpt-4o | model | High | Validate model compatibility |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Validate runtime behavior |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
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

## Agent: DI_ECL_To_JavaSpringboot_Analyzer_Json vs DI ECL To JavaSpringboot Analyzer

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Medium | Validate new instruction field behavior |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility and performance |
| model | gpt-4o | model | High | Validate model compatibility |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Validate runtime behavior |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
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

## Agent: DI_ECL_To_JavaSpringboot_Plan_JSON vs DI ECL To JavaSpringboot Plan

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Medium | Validate new instruction field behavior |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility and performance |
| model | gpt-4o | model | High | Validate model compatibility |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Validate runtime behavior |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
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