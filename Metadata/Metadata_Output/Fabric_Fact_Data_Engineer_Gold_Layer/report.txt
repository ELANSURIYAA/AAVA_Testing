# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

# 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 87%
**Total Agents Compared:** 2

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| Fabric Gold Fact DE Pipeline | 89% | Low | Model deployment matched, description matched, temperature matched, topP matched, maxExecutionTime added | Validate new maxExecutionTime behavior |
| Fabric Pyspark Unit Test Case | 85% | Low | Model deployment matched, description matched, temperature matched, topP matched, maxExecutionTime added | Validate new maxExecutionTime behavior |

---

# 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** Fabric Fact Data Engineer Gold Layer
**Workflow Name (AAVA 2.0):** Fabric Fact Data Engineer Gold Layer

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 827 | id | 3301 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new ID |
| Naming | name | Fabric Fact Data Engineer Gold Layer | name | Fabric Fact Data Engineer Gold Layer | Matched | No change | Low | No change |
| Description | description | Fabric Fact Data Engineer Gold Layer | description | Fabric Fact Data Engineer Gold Layer | Matched | No change | Low | No change |
| Audit | createdAt | 2025-03-27T04:51:22.616+00:00 | createdAt | 2025-11-05T11:27:36.926407 | Modified | Creation timestamp changed | Low | Expected for new workflow version |
| Agents List | pipeLineAgents | Array of 2 agents | workflowAgents | Array of 2 agents | Renamed + Matched (Normalized) | Field renamed but content preserved | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | Object with managerLlm and enableAgenticMemory | Renamed + Modified | Structure and content changed | Medium | Validate new config structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Low | Check workflowConfigs.enableAgenticMemory |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm org tracking handled elsewhere |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm org tracking handled elsewhere |
| Domain | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm domain tracking handled elsewhere |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm domain tracking handled elsewhere |
| Project | project | AVA | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm project tracking handled elsewhere |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm project tracking handled elsewhere |
| Team | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm team tracking handled elsewhere |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm team tracking handled elsewhere |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm level tracking handled elsewhere |

---

# 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who modified workflow | default@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-11-30T11:55:00.892060 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T11:27:37.977705 | Medium | Ensure approval process is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Standard soft delete pattern |
| parentId | Parent workflow reference | -1 | Medium | Ensure workflow versioning is handled |
| realmId | Realm/tenant identifier | 1 | Medium | Ensure multi-tenancy is handled |

---

# 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align defaults and validate structure |
| managerLlm | Not available | Empty object in workflowConfigs | Medium | Validate manager LLM configuration |
| enableAgenticMemory | Top-level field (false) | Nested in workflowConfigs (false) | Low | Update field access path |

---

# 5. Agent Inventory Summary

## 5.1 Agent Count & Coverage

**AAVA 1.0 total agents:** 2
**AAVA 2.0 total agents:** 2
**Coverage:** Same agents maintained

## 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| Fabric Gold Fact DE Pipeline | Fabric Gold Fact DE Pipeline | Matched | No change |
| Fabric Pyspark Unit Test Case | Fabric Pyspark Unit Test Case | Matched | No change |

---

# 6. Agent Configuration Differences

## Agent: Fabric Gold Fact DE Pipeline

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility and performance |
| model | anthropic.claude-4-sonnet | model | High | Validate model compatibility and performance |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | null | Low | Null equivalent to 0 |
| maxRpm | 0 | null | Low | Null equivalent to 0 |
| maxExecutionTime | 0 | 90 | Medium | Validate new timeout behavior |

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
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | null | Low | Null equivalent to 0 |
| maxRpm | 0 | null | Low | Null equivalent to 0 |
| maxExecutionTime | 0 | 90 | Medium | Validate new timeout behavior |

---

## 6.2.3 Tools Comparison

Not Available

---

## 6.2.4 Knowledge Base Comparison

Not Available

---

## 6.2.5 Guardrails Comparison

Not Available