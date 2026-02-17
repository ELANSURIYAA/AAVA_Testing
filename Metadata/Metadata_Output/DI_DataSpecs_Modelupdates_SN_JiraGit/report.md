# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

# 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 78%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI Data Technical Specification SN Jira Git | 75% | Medium | role/goal/backstory removed, model config changed, tools removed | Validate agent behavior without role/goal/backstory fields |
| DI Delta Model Changes SN Jira Git | 82% | Medium | role/goal/backstory removed, model config changed, description modified | Validate model performance and description changes |
| DI Functional Test Cases SN Jira Git | 77% | Medium | role/goal/backstory removed, model deployment changed, maxIter reduced | Validate new model deployment and iteration limits |

---

# 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_DataSpecs_Modelupdates_SN_Jira&Git
**Workflow Name (AAVA 2.0):** DI DataSpecs Modelupdates SN Jira&Git

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 9403 | id | 5646 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | DI_DataSpecs_Modelupdates_SN_Jira&Git | name | DI DataSpecs Modelupdates SN Jira&Git | Matched (Normalized) | Minor formatting differences | Low | No change required |
| Description | description | DI_DataSpecs_Modelupdates_SN_Jira&Git | description | DI_DataSpecs_Modelupdates_SN_Jira&Git | Matched | Exact match | Low | No change required |
| Audit | createdAt | 2025-12-01T04:55:22.058+00:00 | createdAt | 2025-12-01T11:29:26.405371 | Matched | Different timestamps as expected | Low | No change required |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update references to new field name |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure changed | High | Configure new workflow config structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Verify memory config location |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Confirm org metadata removal acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | High | Confirm org ID removal acceptable |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | High | Confirm domain removal acceptable |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | High | Confirm domain ID removal acceptable |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | High | Confirm project removal acceptable |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | High | Confirm project ID removal acceptable |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | High | Confirm team removal acceptable |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | High | Confirm team ID removal acceptable |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | High | Confirm level ID removal acceptable |

---

# 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | elansuriyaa.p@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification timestamps are tracked |
| approvedAt | Approval timestamp | 2025-12-01T11:29:28.065355 | Medium | Ensure approval timestamps are tracked |
| status | Workflow approval state | APPROVED | High | Ensure workflow lifecycle management |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete functionality |
| parentId | Parent workflow reference | -1 | Medium | Ensure workflow hierarchy support |

---

# 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | callbacks: [] | managerLlm: [{}], enableAgenticMemory: false | High | Configure new workflow management structure |
| managerLlm | Not Available | [{}] | High | Configure manager LLM settings |
| enableAgenticMemory | Top-level field: false | Nested in workflowConfigs: false | Medium | Update memory config access pattern |

---

# 5. Agent Inventory Summary

## 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agent count with naming updates

## 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Data_Technical_Specification_SN_Jira&Git | DI Data Technical Specification SN Jira Git | Renamed | Naming convention updated (underscores to spaces) |
| DI_Delta_Model_Changes_SN_Jira&git | DI Delta Model Changes SN Jira Git | Renamed | Naming convention updated (underscores to spaces) |
| DI_Functional_Test_Cases_SN_Jira&Git | DI Functional Test Cases SN Jira Git | Renamed | Naming convention updated (underscores to spaces) |

---

# 6. Agent Configuration Differences

## Agent: DI Data Technical Specification SN Jira Git

---

## 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Present | Low | No change |

---

## 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-4-sonnet | anthropic.claude-4-sonnet | Low | Validate model deployment name format |
| model | anthropic.claude-4-sonnet | model | High | Validate model name change |
| temperature | 0.30000001192092896 | 0.5 | Medium | Validate temperature change impact |
| topP | 0.949999988079071 | 0.9 | Low | Minor topP adjustment |
| maxToken | 12000 | 8000 | Medium | Validate token limit reduction |
| maxIter | 20 | 10 | Medium | Validate iteration limit reduction |
| maxRpm | 0 | 20 | Medium | Rate limiting added |
| maxExecutionTime | 400 | 150 | High | Validate execution time reduction |

---

## 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| DI_Github_File_Writer_Z | Present | Not Available | High | Confirm tool removal or add to toolReferences |
| DI_GitHub_File_Reader_Z | Present | Not Available | High | Confirm tool removal or add to toolReferences |
| DI_JiraStoryReaderTool | Present | Not Available | High | Confirm tool removal or add to toolReferences |
| toolReferences | Not Available | [] | Medium | Validate new tool reference system |

---

## 6.1.4 Knowledge Base Comparison

Not Available

---

## 6.1.5 Guardrails Comparison

| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-----------------|----------------|----------------|------------------|-----------------|
| guardrailIds | Not Available | [] | Medium | Validate new guardrail system |

---

## Agent: DI Delta Model Changes SN Jira Git

---

## 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Present | Low | No change |

---

## 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-4-sonnet | anthropic.claude-4-sonnet | Low | Validate model deployment name format |
| model | anthropic.claude-4-sonnet | model | High | Validate model name change |
| temperature | 0.30000001192092896 | 0.5 | Medium | Validate temperature change impact |
| topP | 0.949999988079071 | 0.9 | Low | Minor topP adjustment |
| maxToken | 16000 | Not Available | High | Token limit configuration removed |
| maxIter | 20 | 10 | Medium | Validate iteration limit reduction |
| maxRpm | 0 | 20 | Medium | Rate limiting added |
| maxExecutionTime | 400 | 150 | High | Validate execution time reduction |

---

## 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| DI_Github_File_Writer_Z | Present | Not Available | High | Confirm tool removal or add to toolReferences |
| DI_GitHub_File_Reader_Z | Present | Not Available | High | Confirm tool removal or add to toolReferences |
| toolReferences | Not Available | [] | Medium | Validate new tool reference system |

---

## 6.2.4 Knowledge Base Comparison

Not Available

---

## 6.2.5 Guardrails Comparison

| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-----------------|----------------|----------------|------------------|-----------------|
| guardrailIds | Not Available | [] | Medium | Validate new guardrail system |

---

## Agent: DI Functional Test Cases SN Jira Git

---

## 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Present | Low | No change |

---

## 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model deployment change |
| model | anthropic.claude-4-sonnet | model | High | Validate model name change |
| temperature | 0.30000001192092896 | 0.5 | Medium | Validate temperature change impact |
| topP | 0.949999988079071 | 0.9 | Low | Minor topP adjustment |
| maxToken | 12000 | 10000 | Medium | Validate token limit reduction |
| maxIter | 10 | 10 | Low | No change |
| maxRpm | 0 | 20 | Medium | Rate limiting added |
| maxExecutionTime | 400 | 150 | High | Validate execution time reduction |

---

## 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| DI_Github_File_Writer_Z | Present | Not Available | High | Confirm tool removal or add to toolReferences |
| DI_GitHub_File_Reader_Z | Present | Not Available | High | Confirm tool removal or add to toolReferences |
| DI_JiraStoryReaderTool | Present | Not Available | High | Confirm tool removal or add to toolReferences |
| toolReferences | Not Available | [] | Medium | Validate new tool reference system |

---

## 6.3.4 Knowledge Base Comparison

Not Available

---

## 6.3.5 Guardrails Comparison

| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-----------------|----------------|----------------|------------------|-----------------|
| guardrailIds | Not Available | [] | Medium | Validate new guardrail system |