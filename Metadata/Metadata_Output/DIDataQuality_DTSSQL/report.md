# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 78%**
**Total Agents Compared: 2**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI-DQ Recommendation | 82% | Medium | role/goal/backstory removed, model changed to gpt-4.1, expectedOutput format modified | Validate instruction changes and model compatibility |
| DI-DQ Rule-to-DTS SQL | 74% | Medium | role/goal/backstory removed, model changed to gpt-4.1, name formatting updated | Validate instruction changes and model compatibility |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI-DataQuality_DTS-SQL
**Workflow Name (AAVA 2.0):** DI-DataQuality DTS-SQL

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1618 | id | 1819 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new ID |
| Naming | name | DI-DataQuality_DTS-SQL | name | DI-DataQuality DTS-SQL | Matched (Case Normalization) | Minor formatting difference | Low | No change needed |
| Description | description | This workflow analyzes sample data... | description | This workflow analyzes sample data... | Matched | Same description | Low | No change needed |
| Audit | createdAt | 2025-04-25T12:49:19.368+00:00 | createdAt | 2025-11-05T10:36:17.294864 | Matched | Different timestamp values | Low | Expected for new workflow |
| Agents List | pipeLineAgents | [2 agents] | workflowAgents | [2 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Enhanced configuration structure | Medium | Align configuration handling |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Update memory configuration access |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | High | Confirm removal acceptable |
| Domain Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | High | Confirm removal acceptable |
| Project Metadata | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | High | Confirm removal acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | gogulkanth.ashokan@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified | gogulkanth.ashokan@ascendion.com | Medium | Ensure modification tracking |
| approvedBy | User who approved workflow | gogulkanth.ashokan@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T10:36:18.512797 | Low | Standard audit field |
| status | Workflow approval state | APPROVED | High | Ensure workflow lifecycle handling |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete logic |
| parentId | Parent workflow reference | -1 | Medium | Handle workflow versioning |
| realmId | Realm identifier | 32 | Medium | Ensure realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align configuration structure |
| managerLlm | Not available | Empty object in workflowConfigs | Medium | Configure manager LLM if needed |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update memory access pattern |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 2
**AAVA 2.0 total agents:** 2
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI-DQ_Recommendation | DI-DQ Recommendation | Renamed | Underscore removed |
| DI-DQ_Rule-to-DTS_SQL | DI-DQ Rule-to-DTS SQL | Renamed | Underscores removed |

---

## 6. Agent Configuration Differences

## Agent: DI-DQ Recommendation

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
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | No change |
| maxRpm | 0 | null | Low | No change |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout change |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.1.3 Tools Comparison

**Not Available** - No tools configured in either version

### 6.1.4 Knowledge Base Comparison

**Not Available** - No knowledge base configured in either version

### 6.1.5 Guardrails Comparison

**Not Available** - No guardrails configured in either version

---

## Agent: DI-DQ Rule-to-DTS SQL

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
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | No change |
| maxRpm | 0 | null | Low | No change |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout change |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.2.3 Tools Comparison

**Not Available** - No tools configured in either version

### 6.2.4 Knowledge Base Comparison

**Not Available** - No knowledge base configured in either version

### 6.2.5 Guardrails Comparison

**Not Available** - No guardrails configured in either version