# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 67%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| Fabric Gold Fact Transformation Recommender | 67% | Medium | role/goal/backstory removed; LLM config restructured; model field modified | Validate agent behavior without role/goal/backstory fields |
| Fabric Gold Fact Transformation Data Mapping | 67% | Medium | role/goal/backstory removed; LLM config restructured; embedding config removed | Validate agent behavior and restore embedding configuration |
| Fabric Gold Data Mapping Reviewer | 67% | Medium | role/goal/backstory removed; LLM config restructured; expectedOutput format changed | Validate agent behavior without role/goal/backstory fields |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** Fabric Fact Data Mapping Gold Layer
**Workflow Name (AAVA 2.0):** Fabric Fact Data Mapping Gold Layer

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 808 | id | 3752 | Renamed + Modified | Field renamed and value changed | High | Update all references to use new ID |
| Naming | name | Fabric Fact Data Mapping Gold Layer | name | Fabric Fact Data Mapping Gold Layer | Matched | No change | Low | None |
| Description | description | This workflow is for recommending and creating the gold Fact data mapping | description | This workflow is for recommending and creating the gold Fact data mapping | Matched | No change | Low | None |
| Audit | createdAt | 2025-02-28T07:24:18.779+00:00 | createdAt | 2025-11-05T11:41:20.781786 | Modified | Creation timestamp changed | Medium | Verify audit trail continuity |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure changed | High | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Verify memory settings in new location |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | High | Restore organizational context |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organizational ID removed | High | Restore organizational context |
| Domain | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | High | Restore domain context |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | High | Restore domain context |
| Project | project | AVA | Not Available | Not Available | Removed | Project metadata removed | High | Restore project context |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | High | Restore project context |
| Team | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | High | Restore team context |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | High | Restore team context |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed | Medium | Verify hierarchy settings |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Set appropriate user attribution |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Set appropriate user attribution |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Set appropriate approval workflow |
| modifiedAt | Last modification timestamp | 2025-11-30T11:55:00.892060 | Low | Automatic timestamp handling |
| approvedAt | Approval timestamp | 2025-11-05T11:41:21.835145 | Medium | Implement approval process |
| status | Workflow approval state | APPROVED | High | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete logic |
| parentId | Parent workflow reference | -1 | Low | Handle workflow hierarchy |
| realmId | Realm identifier | 1 | Medium | Configure realm settings |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | High | Configure new workflow settings |
| managerLlm | Not available | Empty object {} | Medium | Configure manager LLM settings |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update memory configuration access |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents maintained

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| Fabric Gold Fact Transformation Recommender | Fabric Gold Fact Transformation Recommender | Matched | Same name |
| Fabric Gold Fact Transformation Data Mapping | Fabric Gold Fact Transformation Data Mapping | Matched | Same name |
| Fabric Gold Data Mapping Reviewer | Fabric Gold Data Mapping Reviewer | Matched | Same name with trailing space |

---

## 6. Agent Configuration Differences

## Agent: Fabric Gold Fact Transformation Recommender

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
| model | gpt-4 | model | High | Validate model configuration change |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Verify iteration settings |
| maxRpm | 0 | Not Present | Medium | Verify rate limiting settings |
| maxExecutionTime | 0 | 90 | High | Execution timeout changed |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: Fabric Gold Fact Transformation Data Mapping

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
| model | gpt-4 | model | High | Validate model configuration change |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Verify iteration settings |
| maxRpm | 0 | Not Present | Medium | Verify rate limiting settings |
| maxExecutionTime | 0 | 90 | High | Execution timeout changed |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present (AzureOpenAI config) | Not Present | High | Restore embedding configuration |

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: Fabric Gold Data Mapping Reviewer

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
| model | gpt-4 | model | High | Validate model configuration change |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Verify iteration settings |
| maxRpm | 0 | Not Present | Medium | Verify rate limiting settings |
| maxExecutionTime | 0 | 90 | High | Execution timeout changed |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available