# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 74%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI BigQuery Gold Dim DE Pipeline | 68% | Medium | Model changed from gemini-2.5-pro to gpt-4.1, role/goal/backstory removed, tools removed | Validate model compatibility and confirm instruction field removal |
| DI BigQuery Unit Test Case | 82% | Medium | Model changed from gemini-2.5-pro to gpt-4.1, role/goal/backstory removed, tools removed | Validate model compatibility and confirm instruction field removal |
| DI BigQuery DE Pipeline Reviewer | 72% | Medium | Model changed from gemini-2.5-pro to gpt-4.1, role/goal/backstory removed, tools removed | Validate model compatibility and confirm instruction field removal |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_BigQuery_Dim_Data_Engineer_Gold_Layer
**Workflow Name (AAVA 2.0):** DI BigQuery Dim Data Engineer Gold Layer

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|---------------|----------------|---------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 8000 | id | 2538 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_BigQuery_Dim_Data_Engineer_Gold_Layer | name | DI BigQuery Dim Data Engineer Gold Layer | Matched (Normalized) | Naming convention updated (underscores to spaces) | Low | No change required |
| Description | description | BigQuery Gold dimension layer pipeline | description | BigQuery Gold dimension layer pipeline | Matched | No change | Low | No change required |
| Audit | createdAt | 2025-11-03T18:05:22.462+00:00 | createdAt | 2025-11-05T11:03:21.765712 | Modified | Different creation timestamps | Low | Expected for different workflow instances |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure enhanced | Medium | Validate new configuration structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Confirm memory config handling |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm org metadata not required |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm org ID not required |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm domain metadata not required |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm domain ID not required |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm project metadata not required |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm project ID not required |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm team metadata not required |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm team ID not required |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm level ID not required |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | karthikeyan.iyappan@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | karthikeyan.iyappan@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | karthikeyan.iyappan@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T11:03:22.845721 | Low | Standard audit field |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Standard soft delete implementation |
| parentId | Parent workflow reference | -1 | Low | Workflow hierarchy support |
| realmId | Realm identifier | 1 | Low | Multi-tenancy support |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|---------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align with new configuration structure |
| managerLlm | Not available | Empty object {} | Medium | Validate manager LLM configuration |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update configuration access patterns |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agent count, all agents mapped

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_BigQuery_Gold_Dim_DE_Pipeline | DI BigQuery Gold Dim DE Pipeline | Renamed | Naming convention updated (underscores to spaces) |
| DI_BigQuery_Unit_Test_Case | DI BigQuery Unit Test Case | Renamed | Naming convention updated (underscores to spaces) |
| DI_BigQuery_DE_Pipeline_Reviewer | DI BigQuery DE Pipeline Reviewer | Renamed | Naming convention updated (underscores to spaces) |

---

## 6. Agent Configuration Differences

## Agent: DI BigQuery Gold Dim DE Pipeline

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility and performance |
| model | gemini-2.5-pro | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision difference |
| topP | 0.949999988079071 | 0.94 | Low | Normalized precision difference |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Confirm iteration limit handling |
| maxRpm | 0 | Not Present | Medium | Confirm rate limit handling |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |
| allowDelegation | true | false | Medium | Delegation capability changed |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Present | Medium | Confirm tools not required |
| userTools | [DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z] | [] | High | Validate tool removal impact |

### 6.1.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present (AzureOpenAI configuration) | Not Present | High | Validate knowledge base removal impact |

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI BigQuery Unit Test Case

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility and performance |
| model | gemini-2.5-pro | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision difference |
| topP | 0.949999988079071 | 0.94 | Low | Normalized precision difference |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Confirm iteration limit handling |
| maxRpm | 0 | Not Present | Medium | Confirm rate limit handling |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |
| allowDelegation | false | false | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Present | Medium | Confirm tools not required |
| userTools | [] | [] | Low | No change |

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DI BigQuery DE Pipeline Reviewer

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility and performance |
| model | gemini-2.5-pro | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision difference |
| topP | 0.949999988079071 | 0.94 | Low | Normalized precision difference |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Confirm iteration limit handling |
| maxRpm | 0 | Not Present | Medium | Confirm rate limit handling |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |
| allowDelegation | false | false | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Present | Medium | Confirm tools not required |
| userTools | [] | [] | Low | No change |

### 6.3.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present (AzureOpenAI configuration) | Not Present | High | Validate knowledge base removal impact |

### 6.3.5 Guardrails Comparison

Not Available