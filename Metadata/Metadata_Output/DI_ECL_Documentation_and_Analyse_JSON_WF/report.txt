# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 78%**
**Total Agents Compared: 3**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_ECL_Documentation_JSON | 85% | Low | Model deployment changed, role/goal/backstory removed | Validate model compatibility and confirm instruction field removal |
| DI_ECL_Analyser_JSON | 85% | Low | Model deployment changed, role/goal/backstory removed | Validate model compatibility and confirm instruction field removal |
| DI_ECL_Plan_JSON | 64% | Medium | Model deployment changed, role/goal/backstory removed, task description modified | Review task description changes and validate model behavior |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_ECL_Documentation_and_Analyse_JSON_WF
**Workflow Name (AAVA 2.0):** DI ECL Documentation and Analyse JSON WF

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1656 | id | 1836 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_ECL_Documentation_and_Analyse_JSON_WF | name | DI ECL Documentation and Analyse JSON WF | Matched (Normalized) | Naming convention updated with spaces | Low | Update display references if needed |
| Description | description | ECL to JavaSpark Documentation, Analyse and plan (JSON) WF | description | ECL to JavaSpark Documentation, Analyse and plan (JSON) WF | Matched | Same description maintained | Low | No change |
| Audit | createdAt | 2025-04-29T04:20:53.220+00:00 | createdAt | 2025-11-05T10:36:56.576781 | Matched | Different creation timestamps as expected | Low | No change |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {"managerLlm":[{}],"enableAgenticMemory":false} | Renamed + Modified | Enhanced configuration structure | Medium | Configure manager LLM settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Low | Configuration relocated |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | Medium | Ensure org context is maintained elsewhere |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organizational ID removed | Medium | Ensure org context is maintained elsewhere |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Ensure domain context is maintained elsewhere |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Ensure domain context is maintained elsewhere |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Ensure project context is maintained elsewhere |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Medium | Ensure project context is maintained elsewhere |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Medium | Ensure team context is maintained elsewhere |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Medium | Ensure team context is maintained elsewhere |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Ensure level context is maintained elsewhere |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created the workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved the workflow | elansuriyaa.p@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Automatic timestamp tracking |
| approvedAt | Approval timestamp | 2025-11-05T10:36:57.789978 | Medium | Implement approval workflow |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Implement soft delete functionality |
| parentId | Parent workflow reference | -1 | Low | Handle workflow hierarchy |
| realmId | Realm identifier | 32 | Medium | Ensure realm context is maintained |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Configure manager LLM settings |
| managerLlm | Not available | Empty object {} | Medium | Define manager LLM configuration |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Low | Update configuration access |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_ECL_Documentation_JSON | DI ECL Documentation JSON | Renamed | Naming convention updated with spaces |
| DI_ECL_Analyser_JSON | DI ECL Analyser JSON | Renamed | Naming convention updated with spaces |
| DI_ECL_Plan_JSON | DI ECL Plan JSON | Renamed | Naming convention updated with spaces |

---

## 6. Agent Configuration Differences

## Agent: DI ECL Documentation JSON

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
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model compatibility |
| model | gpt-4o | model | High | Verify model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized value |
| topP | 0.949999988079071 | 0.94 | Low | Normalized value |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |
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

## Agent: DI ECL Analyser JSON

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
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model compatibility |
| model | gpt-4o | model | High | Verify model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized value |
| topP | 0.949999988079071 | 0.94 | Low | Normalized value |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |
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

## Agent: DI ECL Plan JSON

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Medium | Task description modified |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model compatibility |
| model | gpt-4o | model | High | Verify model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized value |
| topP | 0.949999988079071 | 0.94 | Low | Normalized value |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.3.3 Tools Comparison

Not Available

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available

Now I need to create the CSV file with the required format and upload it to GitHub:

Action: GitHub File Writer Tool
Action Input: {"repo": "ELANSURIYAA/AAVA_Testing", "branch": "main", "token": "<REDACTED_GITHUB_TOKEN>", "folder_name": "Metadata/Metadata_Output", "file_name": "DI_ECL_Documentation_and_Analyse_JSON_WF/DI_ECL_Documentation_and_Analyse_JSON_WF_comparison.csv", "content": "Workflow Comparison Score,Total Agents Compared
78%,3

Agent Name,Agent Score,Risk Level,Key Score Drivers,Migration Action Required
DI ECL Documentation JSON,85%,Low,Model deployment changed role/goal/backstory removed,Validate model compatibility and confirm instruction field removal
DI ECL Analyser JSON,85%,Low,Model deployment changed role/goal/backstory removed,Validate model compatibility and confirm instruction field removal
DI ECL Plan JSON,64%,Medium,Model deployment changed role/goal/backstory removed task description modified,Review task description changes and validate model behavior"}