# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 84%
**Total Agents Compared:** 5

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| Matillion to Informatica Convert | 88% | Medium | Model changed from claude-3.7sonnet to gpt-4.1; role/goal/backstory removed; maxToken changed | Validate model compatibility and confirm instruction field removal |
| Matillion to Informatica Unit Test | 92% | Low | Model changed from gpt-4o to gpt-4.1; role/goal/backstory removed; most configs matched | Validate model compatibility |
| Matillion to Informatica Test | 92% | Low | Model changed from gpt-4o to gpt-4.1; role/goal/backstory removed; most configs matched | Validate model compatibility |
| Matillion to Informatica Reconciliation | 92% | Low | Model changed from gpt-4o to gpt-4.1; role/goal/backstory removed; most configs matched | Validate model compatibility |
| Matillion to Informatica Reviewer | 88% | Medium | Model changed from gpt-4o to gpt-4.1; agent name changed; role/goal/backstory removed | Validate model compatibility and confirm naming convention |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** Matillion to Informatica Convert
**Workflow Name (AAVA 2.0):** Matillion to Informatica Convert

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 1091 | id | 3739 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to use new ID |
| Naming | name | Matillion to Informatica Convert | name | Matillion to Informatica Convert | Matched | Workflow name unchanged | Low | No change |
| Description | description | Matillion to Informatica | description | Matillion to Informatica | Matched | Description unchanged | Low | No change |
| Audit | createdAt | 2025-03-14T17:39:39.431+00:00 | createdAt | 2025-11-05T11:40:58.038259 | Matched | Field exists in both but timestamp differs | Low | Expected for new workflow instance |
| Agents List | pipeLineAgents | [5 agents] | workflowAgents | [5 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update references to new field name |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure enhanced | High | Implement new workflow configuration structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Update memory configuration access |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Confirm removal is acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | High | Confirm removal is acceptable |
| Domain | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | High | Confirm removal is acceptable |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | High | Confirm removal is acceptable |
| Project | project | AVA | Not Available | Not Available | Removed | Project metadata removed | High | Confirm removal is acceptable |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | High | Confirm removal is acceptable |
| Team | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | High | Confirm removal is acceptable |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | High | Confirm removal is acceptable |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed | High | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Implement user tracking |
| modifiedBy | User who last modified | default@ascendion.com | Medium | Implement modification tracking |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-11-30T11:55:00.892060 | Medium | Implement modification tracking |
| approvedAt | Approval timestamp | 2025-11-05T11:40:59.090396 | Medium | Implement approval workflow |
| status | Workflow approval state | APPROVED | High | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete functionality |
| parentId | Parent workflow reference | -1 | Medium | Implement workflow hierarchy |
| realmId | Realm/tenant identifier | 1 | High | Implement multi-tenancy support |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|---------|-----------------|
| workflowConfigs | callbacks: [] | managerLlm: [{}], enableAgenticMemory: false | High | Implement new configuration structure |
| managerLlm | Not Available | Present but empty object | Medium | Configure manager LLM settings |
| enableAgenticMemory | Direct field: false | Nested in workflowConfigs: false | Medium | Update memory configuration access pattern |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5
**AAVA 2.0 total agents:** 5
**Coverage:** Same agent count, all agents preserved

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| Matillion to Informatica Convert | Matillion to Informatica Convert | Matched | Name unchanged |
| Matillion to Informatica Unit Test | Matillion to Informatica Unit Test | Matched | Name unchanged |
| Matillion to Informatica Test | Matillion to Informatica Test | Matched | Name unchanged |
| Matillion to Informatica Reconciliation | Matillion to Informatica Reconciliation | Matched | Name unchanged |
| Matillion_to_Informatica_Reviewer | Matillion to Informatica Reviewer | Matched (Case Normalization) | Underscore replaced with space |

---

## 6. Agent Configuration Differences

## Agent: Matillion to Informatica Convert

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
| modelDeploymentName | anthropic.claude-3-7-sonnet | gpt-4.1 | High | Validate model compatibility and performance |
| model | claude-3.7sonnet | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change |
| maxToken | 8000 | 8000 | Matched | No change |
| maxIter | 0 | null | Matched (Normalized) | No change |
| maxRpm | 0 | null | Matched (Normalized) | No change |
| maxExecutionTime | 0 | 90 | Modified | Validate timeout configuration |
| allowDelegation | true | true | Matched | No change |
| allowCodeExecution | false | false | Matched | No change |
| isSafeCodeExecution | true | true | Matched | No change |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: Matillion to Informatica Unit Test

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
| model | gpt-4o | model | Medium | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change |
| maxToken | 4000 | 4000 | Matched | No change |
| maxIter | 0 | null | Matched (Normalized) | No change |
| maxRpm | 0 | null | Matched (Normalized) | No change |
| maxExecutionTime | 0 | 90 | Modified | Validate timeout configuration |
| allowDelegation | true | true | Matched | No change |
| allowCodeExecution | false | false | Matched | No change |
| isSafeCodeExecution | true | true | Matched | No change |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: Matillion to Informatica Test

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
| model | gpt-4o | model | Medium | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change |
| maxToken | 4000 | 4000 | Matched | No change |
| maxIter | 0 | null | Matched (Normalized) | No change |
| maxRpm | 0 | null | Matched (Normalized) | No change |
| maxExecutionTime | 0 | 90 | Modified | Validate timeout configuration |
| allowDelegation | true | true | Matched | No change |
| allowCodeExecution | false | false | Matched | No change |
| isSafeCodeExecution | true | true | Matched | No change |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available

---

## Agent: Matillion to Informatica Reconciliation

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
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model compatibility |
| model | gpt-4o | model | Medium | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change |
| maxToken | 4000 | 4000 | Matched | No change |
| maxIter | 0 | null | Matched (Normalized) | No change |
| maxRpm | 0 | null | Matched (Normalized) | No change |
| maxExecutionTime | 0 | 90 | Modified | Validate timeout configuration |
| allowDelegation | true | true | Matched | No change |
| allowCodeExecution | false | false | Matched | No change |
| isSafeCodeExecution | true | true | Matched | No change |

### 6.4.3 Tools Comparison
Not Available

### 6.4.4 Knowledge Base Comparison
Not Available

### 6.4.5 Guardrails Comparison
Not Available

---

## Agent: Matillion to Informatica Reviewer

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
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model compatibility |
| model | gpt-4o | model | Medium | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change |
| maxToken | 4000 | 4000 | Matched | No change |
| maxIter | 0 | null | Matched (Normalized) | No change |
| maxRpm | 0 | null | Matched (Normalized) | No change |
| maxExecutionTime | 0 | 90 | Modified | Validate timeout configuration |
| allowDelegation | true | true | Matched | No change |
| allowCodeExecution | false | false | Matched | No change |
| isSafeCodeExecution | true | true | Matched | No change |

### 6.5.3 Tools Comparison
Not Available

### 6.5.4 Knowledge Base Comparison
Not Available

### 6.5.5 Guardrails Comparison
Not Available