# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 78%
**Total Agents Compared:** 5

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_Synapse_To_Lakeflow_Conversion | 85% | Medium | Model configs matched, role/goal/backstory removed, LLM structure changed | Validate instruction field removal impact |
| DI_Synapse_To_Lakeflow_Unit_Test | 82% | Medium | Model configs matched, role/goal/backstory removed, description modified | Validate instruction field removal impact |
| DI_Synapse_To_Lakeflow_Conversion_Tester | 80% | Medium | Model configs matched, role/goal/backstory removed, description modified | Validate instruction field removal impact |
| DI_Synapse_To_Lakeflow_Recon_Tester | 75% | Medium | Model configs matched, role/goal/backstory removed, task description masked | Validate instruction field removal and masking impact |
| DI_Synapse_To_Lakeflow_Reviewer | 72% | Medium | Model changed from claude to gpt-4, role/goal/backstory removed, LLM config restructured | Validate model change and instruction field removal impact |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_Synapse_To_Lakeflow_Conversion
**Workflow Name (AAVA 2.0):** DI_Synapse_To_Lakeflow_Conversion

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 8051 | id | 5711 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_Synapse_To_Lakeflow_Conversion | name | DI_Synapse_To_Lakeflow_Conversion | Matched | Workflow name unchanged | Low | No change |
| Description | description | Convert synapse code to databricks lakeflow declarative sql code | description | Convert synapse code to databricks lakeflow declarative sql code | Matched | Description unchanged | Low | No change |
| Audit | createdAt | 2025-11-05T07:27:28.630+00:00 | createdAt | 2025-12-05T13:33:04.139897 | Modified | Creation timestamp updated | Low | Expected for new workflow version |
| Agents List | pipeLineAgents | [5 agents] | workflowAgents | [5 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update agent references |
| Workflow Config | callbacks | [] | workflowConfigs | {"managerLlm": [{}], "enableAgenticMemory": false} | Renamed + Modified | Field renamed and structure enhanced | High | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs structure | Medium | Verify memory config location |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | High | Confirm org metadata deprecation |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organizational ID removed | High | Confirm org ID deprecation |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | High | Confirm domain metadata deprecation |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | High | Confirm domain ID deprecation |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | High | Confirm project metadata deprecation |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | High | Confirm project ID deprecation |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | High | Confirm team metadata deprecation |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | High | Confirm team ID deprecation |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | High | Confirm level ID deprecation |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | jahnavi.lingutla@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | jahnavi.lingutla@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | jahnavi.lingutla@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-05T13:48:27.677683 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-12-05T13:33:05.677123 | Medium | Ensure approval process is configured |
| status | Workflow approval state | APPROVED | High | Ensure workflow lifecycle management |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete functionality |
| parentId | Parent workflow reference | -1 | Medium | Understand workflow hierarchy |
| realmId | Realm/tenant identifier | 1 | High | Ensure multi-tenancy support |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | High | Configure manager LLM settings |
| managerLlm | Not available | Empty object {} | Medium | Define manager LLM configuration |
| enableAgenticMemory | Top-level field (false) | Nested in workflowConfigs (false) | Medium | Update memory config references |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5
**AAVA 2.0 total agents:** 5
**Coverage:** Same agent count, all agents preserved

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Synapse_To_Lakeflow_Conversion | DI_Synapse_To_Lakeflow_Conversion | Matched | Name unchanged |
| DI_Synapse_To_Lakeflow_Unit_Test | DI_Synapse_To_Lakeflow_Unit_Test | Matched | Name unchanged |
| DI_Synapse_To_Lakeflow_Conversion_Tester | DI_Synapse_To_Lakeflow_Conversion_Tester | Matched | Name unchanged |
| DI_Synapse_To_Lakeflow_Recon_Tester | DI_Synapse_To_Lakeflow_Recon_Tester | Matched | Name unchanged |
| DI_Synapse_To_Lakeflow_Reviewer | DI_Synapse_To_Lakeflow_Reviewer | Matched | Name unchanged |

---

## 6. Agent Configuration Differences

## Agent: DI_Synapse_To_Lakeflow_Conversion

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
| model | gpt-4 | model | Medium | Validate generic model reference |
| temperature | 0.20000000298023224 | 0.2 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 30 | null | Medium | Validate null iteration limit |
| maxRpm | 0 | null | Low | Null RPM acceptable |
| maxExecutionTime | 300 | null | Medium | Validate null execution time |
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

## Agent: DI_Synapse_To_Lakeflow_Unit_Test

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
| model | gpt-4 | model | Medium | Validate generic model reference |
| temperature | 0.20000000298023224 | 0.2 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 30 | null | Medium | Validate null iteration limit |
| maxRpm | 0 | null | Low | Null RPM acceptable |
| maxExecutionTime | 300 | null | Medium | Validate null execution time |
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

## Agent: DI_Synapse_To_Lakeflow_Conversion_Tester

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
| model | gpt-4 | model | Medium | Validate generic model reference |
| temperature | 0.20000000298023224 | 0.2 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 30 | null | Medium | Validate null iteration limit |
| maxRpm | 0 | null | Low | Null RPM acceptable |
| maxExecutionTime | 300 | null | Medium | Validate null execution time |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available

---

## Agent: DI_Synapse_To_Lakeflow_Recon_Tester

### 6.4.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | High | Task description is masked in AAVA 2.0 |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.4.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate generic model reference |
| temperature | 0.20000000298023224 | 0.2 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 30 | null | Medium | Validate null iteration limit |
| maxRpm | 0 | null | Low | Null RPM acceptable |
| maxExecutionTime | 300 | null | Medium | Validate null execution time |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.4.3 Tools Comparison
Not Available

### 6.4.4 Knowledge Base Comparison
Not Available

### 6.4.5 Guardrails Comparison
Not Available

---

## Agent: DI_Synapse_To_Lakeflow_Reviewer

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
| modelDeploymentName | Anthropic.claude-3-5-sonnet | gpt-4.1 | High | Validate model change from Claude to GPT-4 |
| model | claude-3.5-sonnet | model | High | Significant model change requires validation |
| temperature | 0.20000000298023224 | 0.2 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 30 | null | Medium | Validate null iteration limit |
| maxRpm | 0 | null | Low | Null RPM acceptable |
| maxExecutionTime | 300 | null | Medium | Validate null execution time |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.5.3 Tools Comparison
Not Available

### 6.5.4 Knowledge Base Comparison
Not Available

### 6.5.5 Guardrails Comparison
Not Available