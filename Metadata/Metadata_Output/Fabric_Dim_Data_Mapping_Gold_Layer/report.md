# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

# 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 84%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| Fabric Gold Dim Transformation Recommender | 88% | Medium | role/goal/backstory removed, LLM configs matched, description matched | Validate instruction field removal impact |
| Fabric Gold Dim Transformation Data Mapping | 88% | Medium | role/goal/backstory removed, LLM configs matched, description matched | Validate instruction field removal impact |
| Fabric Gold Data Mapping Reviewer | 88% | Medium | role/goal/backstory removed, LLM configs matched, description matched | Validate instruction field removal impact |

---

# 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** Fabric Dim Data Mapping Gold Layer
**Workflow Name (AAVA 2.0):** Fabric Dim Data Mapping Gold Layer

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 805 | id | 3718 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | Fabric Dim Data Mapping Gold Layer | name | Fabric Dim Data Mapping Gold Layer | Matched | No change | Low | None |
| Description | description | This workflow is for recommending and creating the gold dimension data mapping | description | This workflow is for recommending and creating the gold dimension data mapping | Matched | No change | Low | None |
| Audit | createdAt | 2025-02-28T07:52:38.208+00:00 | createdAt | 2025-11-05T11:40:20.153499 | Matched | Timestamp format preserved | Low | None |
| Agents List | pipeLineAgents | Array of 3 agents | workflowAgents | Array of 3 agents | Renamed + Matched (Normalized) | Field renamed but content preserved | Low | Update field references |
| Workflow Config | callbacks | Empty array | workflowConfigs | Object with managerLlm and enableAgenticMemory | Renamed + Modified | Structure and content changed | Medium | Align configuration format |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Verify memory configuration location |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | High | Confirm removal is acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organizational ID removed | High | Confirm removal is acceptable |
| Domain | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | High | Confirm removal is acceptable |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | High | Confirm removal is acceptable |
| Project | project | AVA | Not Available | Not Available | Removed | Project metadata removed | High | Confirm removal is acceptable |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | High | Confirm removal is acceptable |
| Team | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | High | Confirm removal is acceptable |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | High | Confirm removal is acceptable |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed | High | Confirm removal is acceptable |

---

# 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-11-30T11:55:00.892060 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T11:40:21.199444 | Medium | Ensure approval workflow is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete functionality is implemented |
| parentId | Parent workflow reference | -1 | Low | Validate workflow hierarchy handling |
| realmId | Realm identifier | 1 | Medium | Ensure realm-based access control |

---

# 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align configuration structure |
| managerLlm | Not available | Empty object array | Medium | Configure manager LLM settings |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update configuration access path |

---

# 5. Agent Inventory Summary

## 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents maintained

## 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| Fabric Gold Dim Transformation Recommender | Fabric Gold Dim Transformation Recommender | Matched | Name preserved exactly |
| Fabric Gold Dim Transformation Data Mapping | Fabric Gold Dim Transformation Data Mapping | Matched | Name preserved exactly |
| Fabric Gold Data Mapping Reviewer | Fabric Gold Data Mapping Reviewer | Matched | Name preserved exactly |

---

# 6. Agent Configuration Differences

## Agent: Fabric Gold Dim Transformation Recommender

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
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | null | Low | Matched (Normalized) |
| maxRpm | 0 | null | Low | Matched (Normalized) |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout changed |

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

## Agent: Fabric Gold Dim Transformation Data Mapping

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
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | null | Low | Matched (Normalized) |
| maxRpm | 0 | null | Low | Matched (Normalized) |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout changed |

---

## 6.2.3 Tools Comparison

Not Available

---

## 6.2.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present (AzureOpenAI config) | Not Present | High | Validate knowledge base configuration removal |

---

## 6.2.5 Guardrails Comparison

Not Available

---

## Agent: Fabric Gold Data Mapping Reviewer

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | null | Low | Matched (Normalized) |
| maxRpm | 0 | null | Low | Matched (Normalized) |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout changed |

---

## 6.3.3 Tools Comparison

Not Available

---

## 6.3.4 Knowledge Base Comparison

Not Available

---

## 6.3.5 Guardrails Comparison

Not Available