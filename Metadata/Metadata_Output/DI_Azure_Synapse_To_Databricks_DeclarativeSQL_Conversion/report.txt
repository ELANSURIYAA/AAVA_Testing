# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 74%**
**Total Agents Compared: 5**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Converter | 68% | Medium | Model changed from Claude to GPT-4; maxIter/maxRpm/maxExecutionTime removed; role/goal/backstory removed | Validate model behavior and runtime configs |
| DI_Azure_Synapse_To_Databricks_DeclarativeSQL_UnitTest | 76% | Medium | Model configs matched; maxIter/maxRpm/maxExecutionTime removed; role/goal/backstory removed | Validate runtime behavior without execution limits |
| DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Conversion_Tester | 80% | Medium | Model configs matched; maxIter/maxRpm/maxExecutionTime removed; role/goal/backstory removed | Validate runtime behavior without execution limits |
| DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Recon_Tester | 76% | Medium | Model configs matched; maxIter/maxRpm/maxExecutionTime removed; role/goal/backstory removed | Validate runtime behavior without execution limits |
| DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Reviewer | 72% | Medium | Model changed from Claude to GPT-4; maxIter/maxRpm/maxExecutionTime removed; role/goal/backstory removed | Validate model behavior and runtime configs |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Conversion
**Workflow Name (AAVA 2.0):** DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Conversion

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 7575 | id | 5708 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Conversion | name | DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Conversion | Matched | No change | Low | None |
| Description | description | The Workflow is to Convert Azure Synapse Stored Procedure code to Databricks declarative SQL | description | The Workflow is to Convert Azure Synapse Stored Procedure code to Databricks declarative SQL | Matched (Normalized) | Values match after normalization | Low | None |
| Audit | createdAt | 2025-11-14T04:53:11.716+00:00 | createdAt | 2025-12-05T13:32:56.753763 | Modified | Creation timestamp differs | Low | Accept new timestamp |
| Agents List | pipeLineAgents | [5 agents] | workflowAgents | [5 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure changed | Medium | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Low | Check workflowConfigs.enableAgenticMemory |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Ensure org tracking via other means |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Ensure org tracking via other means |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Ensure domain tracking via other means |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Ensure domain tracking via other means |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Ensure project tracking via other means |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Medium | Ensure project tracking via other means |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Medium | Ensure team tracking via other means |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Medium | Ensure team tracking via other means |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Ensure level tracking via other means |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | elansuriyaa.p@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-05T13:48:27.677683 | Low | Track modification history |
| approvedAt | Approval timestamp | 2025-12-05T13:32:58.134866 | Medium | Ensure approval process is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete functionality |
| parentId | Parent workflow reference | -1 | Low | Handle workflow hierarchy if needed |
| realmId | Realm identifier | 1 | Medium | Ensure realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Configure manager LLM settings |
| managerLlm | Not available | Empty object {} | Medium | Define manager LLM configuration |
| enableAgenticMemory | Top-level field (false) | Nested in workflowConfigs (false) | Low | Update configuration access path |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5
**AAVA 2.0 total agents:** 5
**Coverage:** Same agents with structural changes

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Converter | DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Converter | Matched | Same name |
| DI_Azure_Synapse_To_Databricks_DeclarativeSQL_UnitTest | DI_Azure_Synapse_To_Databricks_DeclarativeSQL_UnitTest | Matched | Same name |
| DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Conversion_Tester | DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Conversion_Tester | Matched | Same name |
| DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Recon_Tester | DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Recon_Tester | Matched | Same name |
| DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Reviewer | DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Reviewer | Matched | Same name |

---

## 6. Agent Configuration Differences

## Agent: DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Converter

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model behavior change |
| model | anthropic.claude-4-sonnet | model | High | Validate model behavior change |
| temperature | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 20000 | 20000 | Low | No change |
| maxIter | 50 | Not Present | Medium | Validate runtime behavior without limit |
| maxRpm | 100 | Not Present | Medium | Validate runtime behavior without limit |
| maxExecutionTime | 1800 | Not Present | Medium | Validate runtime behavior without limit |

### 6.1.3 Tools Comparison

Not Available

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI_Azure_Synapse_To_Databricks_DeclarativeSQL_UnitTest

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
| model | gpt-4 | model | Medium | Validate model reference change |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Present | Medium | Validate runtime behavior without limit |
| maxRpm | 0 | Not Present | Medium | Validate runtime behavior without limit |
| maxExecutionTime | 1500 | Not Present | Medium | Validate runtime behavior without limit |

### 6.2.3 Tools Comparison

Not Available

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Conversion_Tester

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model reference change |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 3 | Not Present | Medium | Validate runtime behavior without limit |
| maxRpm | 300 | Not Present | Medium | Validate runtime behavior without limit |
| maxExecutionTime | 400 | Not Present | Medium | Validate runtime behavior without limit |

### 6.3.3 Tools Comparison

Not Available

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available

---

## Agent: DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Recon_Tester

### 6.4.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.4.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model reference change |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Present | Medium | Validate runtime behavior without limit |
| maxRpm | 0 | Not Present | Medium | Validate runtime behavior without limit |
| maxExecutionTime | 1500 | Not Present | Medium | Validate runtime behavior without limit |

### 6.4.3 Tools Comparison

Not Available

### 6.4.4 Knowledge Base Comparison

Not Available

### 6.4.5 Guardrails Comparison

Not Available

---

## Agent: DI_Azure_Synapse_To_Databricks_DeclarativeSQL_Reviewer

### 6.5.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.5.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model behavior change |
| model | anthropic.claude-4-sonnet | model | High | Validate model behavior change |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Present | Medium | Validate runtime behavior without limit |
| maxRpm | 0 | Not Present | Medium | Validate runtime behavior without limit |
| maxExecutionTime | 1500 | Not Present | Medium | Validate runtime behavior without limit |

### 6.5.3 Tools Comparison

Not Available

### 6.5.4 Knowledge Base Comparison

Not Available

### 6.5.5 Guardrails Comparison

Not Available