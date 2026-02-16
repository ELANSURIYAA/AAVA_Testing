# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

# 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 85.3%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DB2 DOCUMENTATION | 88.2% | Medium | role/goal/backstory removed; model changed; maxIter/maxRpm/maxExecutionTime modified | Validate instruction completeness and runtime behavior |
| DB2 ANALYZER | 87.1% | Medium | role/goal/backstory removed; model changed; maxIter/maxRpm/maxExecutionTime modified | Validate instruction completeness and runtime behavior |
| DB2_To_Synapse_Plan | 80.6% | Medium | role/goal/backstory removed; model changed; maxIter/maxRpm/maxExecutionTime modified; name normalized | Validate instruction completeness and runtime behavior |

---

# 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DB2_To_Synapse_Doc_&_Analyze
**Workflow Name (AAVA 2.0):** DB2 To Synapse Doc & Analyze

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 1080 | id | 3805 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to new workflow ID |
| Naming | name | DB2_To_Synapse_Doc_&_Analyze | name | DB2 To Synapse Doc & Analyze | Matched (Normalized) | Minor formatting differences normalized | Low | No change |
| Description | description | DB2_To_Synapse_Doc_&_Analyze | description | DB2_To_Synapse_Doc_&_Analyze | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-03-14T09:22:32.304+00:00 | createdAt | 2025-11-05T11:42:57.286304 | Matched | Field exists in both but different timestamps | Low | No change |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed but same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {"managerLlm":[{}],"enableAgenticMemory":false} | Renamed + Modified | Field renamed and structure changed | Medium | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Verify memory configuration location |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Confirm org metadata handling |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | High | Confirm org ID handling |
| Domain | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | High | Confirm domain metadata handling |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | High | Confirm domain ID handling |
| Project | project | AVA | Not Available | Not Available | Removed | Project metadata removed | High | Confirm project metadata handling |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | High | Confirm project ID handling |
| Team | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | High | Confirm team metadata handling |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | High | Confirm team ID handling |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed | High | Confirm level ID handling |

---

# 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T11:42:58.338871 | Medium | Ensure approval tracking is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete functionality is implemented |
| parentId | Parent workflow reference | -1 | Low | Understand workflow hierarchy |
| realmId | Realm identifier | 1 | Medium | Ensure realm-based access control |

---

# 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Configure workflow-level LLM settings |
| managerLlm | Not available | Empty object {} | Medium | Define manager LLM configuration |
| enableAgenticMemory | Top-level field (false) | Nested in workflowConfigs (false) | Medium | Update memory configuration location |

---

# 5. Agent Inventory Summary

## 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents with naming updates

## 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DB2 DOCUMENTATION | DB2 DOCUMENTATION | Matched | Exact match |
| DB2 ANALYZER | DB2 ANALYZER | Matched | Exact match |
| DB2_To_Synapse_Plan | DB2 To Synapse Plan | Renamed | Naming convention updated |

---

# 6. Agent Configuration Differences

## Agent: DB2 DOCUMENTATION

---

## 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Not Present | Not Present | Low | No change |

---

## 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | anthropic.claude-3-7-sonnet | gpt-4.1 | High | Validate model compatibility and behavior |
| model | claude-3.7sonnet | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Medium | Validate runtime behavior with null values |
| maxRpm | 0 | null | Medium | Validate runtime behavior with null values |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout behavior change |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

---

## 6.1.3 Tools Comparison

Not Available

---

## 6.1.4 Knowledge Base Comparison

Not Available

---

## 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DB2 ANALYZER

---

## 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

## 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | anthropic.claude-3-7-sonnet | gpt-4.1 | High | Validate model compatibility and behavior |
| model | claude-3.7sonnet | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Medium | Validate runtime behavior with null values |
| maxRpm | 0 | null | Medium | Validate runtime behavior with null values |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout behavior change |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

---

## 6.2.3 Tools Comparison

Not Available

---

## 6.2.4 Knowledge Base Comparison

Not Available

---

## 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DB2_To_Synapse_Plan / DB2 To Synapse Plan

---

## 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

## 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model version compatibility |
| model | gpt-4o | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 5 | null | Medium | Validate runtime behavior with null values |
| maxRpm | 0 | null | Medium | Validate runtime behavior with null values |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout behavior change |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

---

## 6.3.3 Tools Comparison

Not Available

---

## 6.3.4 Knowledge Base Comparison

Not Available

---

## 6.3.5 Guardrails Comparison

Not Available