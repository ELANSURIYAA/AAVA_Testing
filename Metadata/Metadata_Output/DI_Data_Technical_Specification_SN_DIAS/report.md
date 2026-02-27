# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 72%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_Workbench_Input_Validator_Async | 45% | High Risk | role/goal/backstory removed; model changed from gpt-4o to not available | Validate agent behavior and add missing instruction fields |
| DI_Data_Technical_Specification_SN_DIAS | 85% | Medium Risk | role/goal/backstory removed; model deployment changed; tools removed | Confirm instruction field removal and validate tool dependencies |
| DI_Workbench_Workflow_CallBack_Agent_Async | 0% | High Risk | Agent completely removed from AAVA 2.0 | Determine if agent functionality is handled elsewhere |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_Data_Technical_Specification_SN_DIAS
**Workflow Name (AAVA 2.0):** DI Data Technical Specification

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 9333 | id | 9065 | Renamed + Modified | Field renamed and value changed | High | Update references to new workflow ID |
| Naming | name | DI_Data_Technical_Specification_SN_DIAS | name | DI Data Technical Specification | Matched (Normalized) | Name simplified and normalized | Low | No change |
| Description | description | DI_Data_Technical_Specification_SN_DIAS | description | Data mapping agent designed to analyze Jira stories, Confluence documentation, and data models to produce accurate source-to-target mappings, technical implementation guidelines, and model update recommendations. | Modified | Description significantly enhanced | Medium | Validate new description aligns with workflow purpose |
| Audit | createdAt | 2025-11-28T12:18:12.455+00:00 | createdAt | 2026-02-02T07:41:29.324570 | Modified | Creation timestamp changed | Low | Update audit records |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [1 agent] | Renamed + Modified | Field renamed and agent count reduced | High | Validate agent consolidation |
| Workflow Config | callbacks | [] | workflowConfigs | {topP: null, maxToken: null, managerLlm: [], temperature: null, enableAgenticMemory: false} | Renamed + Modified | Enhanced configuration structure | Medium | Configure workflow-level settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Low | No change needed |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | Medium | Ensure governance tracking |
| Domain Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Ensure governance tracking |
| Project Metadata | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Ensure governance tracking |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | karthikeyan.iyappan@ascendion.com | Medium | Ensure user attribution is captured |
| modifiedBy | User who last modified workflow | karthikeyan.iyappan@ascendion.com | Medium | Implement modification tracking |
| modifiedAt | Last modification timestamp | 2026-02-02T07:41:29.760818 | Medium | Implement change tracking |
| approvedAt | Workflow approval timestamp | 2026-02-02T07:41:29.751904 | High | Implement approval workflow |
| status | Workflow approval state | APPROVED | High | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete functionality |
| parentId | Parent workflow reference | -1 | Low | Validate workflow hierarchy |
| realmId | Realm/tenant identifier | 79 | Medium | Ensure multi-tenancy support |
| tags | Workflow categorization | [2, 12] | Low | Implement tagging system |
| practiceArea | Practice area classification | 6 | Low | Validate practice area mapping |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|---------|-----------------|
| workflowConfigs | Not available | Present with null values | Medium | Configure workflow-level LLM settings |
| managerLlm | Not available | Empty array | Medium | Determine if manager LLM is needed |
| enableAgenticMemory | Workflow level: false | Moved to workflowConfigs: false | Low | Validate memory configuration |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 1
**Coverage:** 2 agents removed, 1 agent consolidated

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Workbench_Input_Validator_Async | Not Available | Removed | Input validation agent removed |
| DI_Data_Technical_Specification_SN_DIAS | DI Data Technical Specification | Renamed | Core agent renamed and consolidated |
| DI_Workbench_Workflow_CallBack_Agent_Async | Not Available | Removed | Callback agent removed |

---

## 6. Agent Configuration Differences

## Agent: DI_Workbench_Input_Validator_Async

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Not Present | High | Add missing field or confirm deprecation |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | Not Available | High | Configure model deployment |
| model | gpt-4o | Not Available | High | Configure model |
| temperature | 0.1 | Not Available | High | Configure temperature |
| topP | 0.0 | Not Available | High | Configure topP |
| maxToken | 1500 | Not Available | High | Configure maxToken |
| maxIter | 1 | Not Available | High | Configure maxIter |
| maxRpm | 0 | Not Available | High | Configure maxRpm |
| maxExecutionTime | 30 | Not Available | High | Configure maxExecutionTime |

### 6.1.3 Tools Comparison

Not Available

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI_Data_Technical_Specification_SN_DIAS

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Present | Low | No change |

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model change impact |
| model | anthropic.claude-4-sonnet | model | High | Validate model change impact |
| temperature | 0.3 | 0.1 | Medium | Validate temperature change |
| topP | 0.95 | 1.0 | Low | Validate topP change |
| maxToken | 12000 | Not Available | Medium | Configure maxToken |
| maxIter | 20 | 2000 | High | Validate iteration limit increase |
| maxRpm | 0 | 20 | Medium | Validate rate limit change |
| maxExecutionTime | 400 | 175 | Medium | Validate execution time reduction |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| DI_GitHubFileReaderTool_DIAscendion_repo | Present | Not Available | High | Restore tool or confirm removal |
| DI_GitHubFileWriterTool_DIAscendion_Repo | Present | Not Available | High | Restore tool or confirm removal |
| DI_JiraStoryReaderTool_DIAscendion_Repo | Present | Not Available | High | Restore tool or confirm removal |

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DI_Workbench_Workflow_CallBack_Agent_Async

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Not Present | High | Add missing field or confirm deprecation |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | Not Available | High | Configure model deployment |
| model | gpt-4 | Not Available | High | Configure model |
| temperature | 0.1 | Not Available | High | Configure temperature |
| topP | 0.0 | Not Available | High | Configure topP |
| maxToken | 5000 | Not Available | High | Configure maxToken |
| maxIter | 10 | Not Available | High | Configure maxIter |
| maxRpm | 0 | Not Available | High | Configure maxRpm |
| maxExecutionTime | 300 | Not Available | High | Configure maxExecutionTime |

### 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| Workbench_Dynamic_API_Caller_Z | Present | Not Available | High | Restore tool or confirm removal |

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available