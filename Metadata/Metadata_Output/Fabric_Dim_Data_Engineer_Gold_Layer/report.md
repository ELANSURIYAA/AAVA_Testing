# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

# 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 76%**
**Total Agents Compared: 2**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| Fabric Gold DIM DE Pipeline | 72% | Medium | role/goal/backstory removed, model configs matched, description matched | Validate removal of instruction fields is acceptable |
| Fabric Pyspark Unit Test Case | 80% | Medium | role/goal/backstory removed, model configs matched, description matched | Validate removal of instruction fields is acceptable |

---

# 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** Fabric Dim Data Engineer Gold Layer
**Workflow Name (AAVA 2.0):** Fabric Dim Data Engineer Gold Layer

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 610 | id | 3276 | Renamed + Modified | Field renamed and value changed | High | Update references to new workflow ID |
| Naming | name | Fabric Dim Data Engineer Gold Layer | name | Fabric Dim Data Engineer Gold Layer | Matched | No change | Low | No change |
| Description | description | This agent will give the Pyspark code for Gold Dimension table | description | This agent will give the Pyspark code for Gold Dimension table | Matched | No change | Low | No change |
| Audit | createdAt | 2025-03-27T04:50:42.071+00:00 | createdAt | 2025-11-05T11:26:39.699667 | Modified | Creation timestamp updated | Medium | Verify audit trail continuity |
| Agents List | pipeLineAgents | Array[2] | workflowAgents | Array[2] | Renamed + Matched (Normalized) | Field renamed but agent count preserved | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | Object with managerLlm | Renamed + Modified | Enhanced configuration structure | Medium | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Verify memory configuration location |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Implement alternative org tracking |
| Domain Metadata | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | High | Implement alternative domain tracking |
| Project Metadata | project | AVA | Not Available | Not Available | Removed | Project metadata removed | High | Implement alternative project tracking |

---

# 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User audit trail | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | Modification audit | default@ascendion.com | Medium | Ensure modification tracking works |
| approvedBy | Approval workflow | default@ascendion.com | Medium | Implement approval process |
| modifiedAt | Modification timestamp | 2025-11-30T11:55:00.892060 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T11:26:40.754621 | Medium | Ensure approval workflow active |
| status | Workflow state | APPROVED | High | Implement workflow lifecycle management |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete handling |
| parentId | Workflow hierarchy | -1 | Low | Standard hierarchy field |
| realmId | Multi-tenancy | 1 | Medium | Ensure realm isolation works |

---

# 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm | High | Configure manager LLM settings |
| enableAgenticMemory | Top-level field | Nested in workflowConfigs | Medium | Update memory configuration access |
| callbacks | Empty array | Not available | Medium | Verify callback handling migration |

---

# 5. Agent Inventory Summary

## 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 2
**AAVA 2.0 total agents:** 2
**Coverage:** Same agents maintained

## 5.2 Agent Name Mapping
| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| Fabric Gold DIM DE Pipeline | Fabric Gold DIM DE Pipeline | Matched | No change |
| Fabric Pyspark Unit Test Case | Fabric Pyspark Unit Test Case | Matched | No change |

---

# 6. Agent Configuration Differences

## Agent: Fabric Gold DIM DE Pipeline

---

## 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

## 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Verify model name mapping |
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | null | Low | Matched (Normalized) |
| maxRpm | 0 | null | Low | Matched (Normalized) |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout updated |

---

## 6.1.3 Tools Comparison

**Not Available**

---

## 6.1.4 Knowledge Base Comparison

**Not Available**

---

## 6.1.5 Guardrails Comparison

**Not Available**

---

## Agent: Fabric Pyspark Unit Test Case

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Verify model name mapping |
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | null | Low | Matched (Normalized) |
| maxRpm | 0 | null | Low | Matched (Normalized) |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout updated |

---

## 6.2.3 Tools Comparison

**Not Available**

---

## 6.2.4 Knowledge Base Comparison

**Not Available**

---

## 6.2.5 Guardrails Comparison

**Not Available**