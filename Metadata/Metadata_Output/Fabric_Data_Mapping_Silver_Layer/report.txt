# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 76.7%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| Fabric Silver DQ Recommender | 73.3% | Moderate | role/goal/backstory removed, model configs matched, description matched | Validate removal of role/goal/backstory fields is acceptable |
| Fabric Silver DQ Data Mapping | 80.0% | Good | role/goal/backstory removed, model configs matched, description matched | Validate removal of role/goal/backstory fields is acceptable |
| Fabric Silver Data Mapping Reviewer | 76.7% | Good | role/goal/backstory removed, model configs matched, description matched | Validate removal of role/goal/backstory fields is acceptable |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** Fabric Data Mapping Silver Layer
**Workflow Name (AAVA 2.0):** Fabric Data Mapping Silver Layer

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 819 | id | 3853 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | Fabric Data Mapping Silver Layer | name | Fabric Data Mapping Silver Layer | Matched | No change | Low | No change |
| Description | description | This agent will give the data mapping silver layer output | description | This agent will give the data mapping silver layer output | Matched | No change | Low | No change |
| Audit | createdAt | 2025-02-28T07:49:37.577+00:00 | createdAt | 2025-11-05T11:44:21.686130 | Modified | Timestamp value changed | Low | No change |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure changed | Medium | Validate new config structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Low | Update config references |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Ensure org context is maintained |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | High | Ensure org context is maintained |
| Domain | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | High | Ensure domain context is maintained |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | High | Ensure domain context is maintained |
| Project | project | AVA | Not Available | Not Available | Removed | Project metadata removed | High | Ensure project context is maintained |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | High | Ensure project context is maintained |
| Team | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | High | Ensure team context is maintained |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | High | Ensure team context is maintained |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed | Medium | Validate level context handling |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Ensure proper user attribution |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Implement modification tracking |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-11-30T11:55:00.892060 | Low | Track modification history |
| approvedAt | Approval timestamp | 2025-11-05T11:44:22.739367 | Low | Track approval history |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete logic |
| parentId | Parent workflow reference | -1 | Low | Handle workflow hierarchy |
| realmId | Realm/tenant identifier | 1 | Medium | Ensure proper tenant isolation |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align defaults and validate structure |
| managerLlm | Not available | Empty object {} | Medium | Configure manager LLM settings |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Low | Update config path references |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents maintained

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| Fabric Silver DQ Recommender | Fabric Silver DQ Recommender | Matched | Same name |
| Fabric Silver DQ Data Mapping | Fabric Silver DQ Data Mapping | Matched | Same name |
| Fabric Silver Data Mapping Reviewer | Fabric Silver Data Mapping Reviewer | Matched | Same name |

---

## 6. Agent Configuration Differences

## Agent: Fabric Silver DQ Recommender

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Not Present | Not Present | Low | No change |

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Validate removal is acceptable |
| maxRpm | 0 | Not Present | Medium | Validate removal is acceptable |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout change |

### 6.1.3 Tools Comparison

Not Available

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: Fabric Silver DQ Data Mapping

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | Medium | Add missing field or confirm deprecation |

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Validate removal is acceptable |
| maxRpm | 0 | Not Present | Medium | Validate removal is acceptable |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout change |

### 6.2.3 Tools Comparison

Not Available

### 6.2.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present (AzureOpenAI config) | Not Present | High | Restore embedding configuration or confirm removal |

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: Fabric Silver Data Mapping Reviewer

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | Medium | Add missing field or confirm deprecation |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Validate removal is acceptable |
| maxRpm | 0 | Not Present | Medium | Validate removal is acceptable |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout change |

### 6.3.3 Tools Comparison

Not Available

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available