# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 78%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_Synapse_Documentation | 85% | Medium | role/goal/backstory removed, model configs matched, description matched | Validate instruction field removal impact |
| DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Analyzer | 82% | Medium | role/goal/backstory removed, topP modified, model configs mostly matched | Validate instruction field removal and topP change |
| DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Plan | 67% | Medium | role/goal/backstory removed, model changed from Anthropic to gpt-4.1, topP modified | Validate model change impact and instruction field removal |

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Doc&Analyze
**Workflow Name (AAVA 2.0):** DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Doc&Analyze

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 7429 | id | 5707 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to use new ID |
| Naming | name | DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Doc&Analyze | name | DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Doc&Analyze | Matched | Workflow name identical | Low | No change |
| Description | description | Document , Analyse and provide the plan for the Synapse Code | description | Document , Analyse and provide the plan for the Synapse Code | Matched | Description identical | Low | No change |
| Audit | createdAt | 2025-11-14T04:51:44.350+00:00 | createdAt | 2025-12-05T13:32:56.547199 | Modified | Creation timestamp differs | Medium | Validate audit trail |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed but agent count matches | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Structure and content changed | High | Align configuration handling |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Confirm removal is acceptable |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | High | Confirm removal is acceptable |
| Domain Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | High | Confirm removal is acceptable |
| Project Metadata | project | Documenting | Not Available | Not Available | Removed | Project metadata removed | High | Confirm removal is acceptable |

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is handled |
| modifiedBy | User who last modified workflow | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking is handled |
| approvedBy | User who approved workflow | elansuriyaa.p@ascendion.com | Medium | Ensure approval workflow is handled |
| modifiedAt | Last modification timestamp | 2025-12-05T13:48:27.677683 | Medium | Ensure modification tracking is handled |
| approvedAt | Approval timestamp | 2025-12-05T13:32:58.134866 | Medium | Ensure approval workflow is handled |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure deletion handling is implemented |
| parentId | Parent workflow reference | -1 | Low | Validate parent-child relationships |
| realmId | Realm identifier | 1 | Low | Validate realm-based access control |

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|---------|-----------------|
| workflowConfigs | callbacks: [] | workflowConfigs: {managerLlm: [{}], enableAgenticMemory: false} | High | Align configuration structure |
| managerLlm | Not available | Present (empty object) | Medium | Validate manager LLM configuration |
| enableAgenticMemory | Top-level field: false | Nested in workflowConfigs: false | Medium | Update configuration access patterns |

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agent count, all agents preserved

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Synapse_Documentation | DI_Synapse_Documentation | Matched | Agent name identical |
| DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Analyzer | DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Analyzer | Matched | Agent name identical |
| DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Plan | DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Plan | Matched | Agent name identical |

## 6. Agent Configuration Differences

## Agent: DI_Synapse_Documentation

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.20000000298023224 | 0.2 | Low | Matched (Normalized) |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Available | Medium | Confirm removal is acceptable |
| maxRpm | 0 | Not Available | Medium | Confirm removal is acceptable |
| maxExecutionTime | 300 | Not Available | Medium | Confirm removal is acceptable |

### 6.1.3 Tools Comparison

Not Available

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

## Agent: DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Analyzer

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
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Available | Medium | Confirm removal is acceptable |
| maxRpm | 0 | Not Available | Medium | Confirm removal is acceptable |
| maxExecutionTime | 300 | Not Available | Medium | Confirm removal is acceptable |

### 6.2.3 Tools Comparison

Not Available

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

## Agent: DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Plan

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model deployment change |
| model | anthropic.claude-4-sonnet | model | High | Validate model change from Anthropic to GPT |
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Available | Medium | Confirm removal is acceptable |
| maxRpm | 0 | Not Available | Medium | Confirm removal is acceptable |
| maxExecutionTime | 300 | Not Available | Medium | Confirm removal is acceptable |

### 6.3.3 Tools Comparison

Not Available

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available

**CSV file successfully uploaded to:** Metadata/Metadata_Output/DI_Azure_Synapse_To_Databricks_DeclarativeSQL_DocAnalyze/DI_Azure_Synapse_To_Databricks_DeclarativeSQL_DocAnalyze_comparison.csv

The comparison reveals a 78% compatibility score with medium risk level across all agents. Key migration concerns include the removal of instruction fields (role, goal, backstory, expectedOutput) and model changes for the third agent. The workflow structure has been significantly modernized with new governance fields while removing organizational metadata.