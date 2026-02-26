# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 73%**
**Total Agents Compared: 4**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| Fabric Silver Model Logical | 85% | Low | Description matched; model deployment renamed; LLM configs matched | Validate model deployment mapping |
| Fabric Silver Model Physical | 78% | Medium | Description matched; model deployment renamed; embedding config removed | Validate embedding removal impact |
| DI Mermaid Data Model View | 65% | Medium | Name normalized; description modified; model deployment changed | Validate model change impact |
| Fabric Silver Model Reviewer | 64% | Medium | Description matched; model deployment matched; embedding config removed | Validate embedding removal impact |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** Fabric Data Modeler Silver Layer
**Workflow Name (AAVA 2.0):** Fabric Data Modeler Silver Layer

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 376 | id | 2934 | Renamed + Modified | Field renamed and value changed | Medium | Update ID references in dependent systems |
| Naming | name | " Fabric Data Modeler Silver Layer" | name | " Fabric Data Modeler Silver Layer" | Matched (Normalized) | Values match after normalization | Low | No change |
| Description | description | "Data Modeler for Microsoft Fabric environment" | description | "Data Modeler for Microsoft Fabric environment" | Matched | Values are identical | Low | No change |
| Audit | createdAt | "2025-06-25T10:10:26.035+00:00" | createdAt | "2025-11-05T11:17:42.727961" | Matched | Field exists in both but values differ | Medium | Validate timestamp differences |
| Agents List | pipeLineAgents | Array of 4 agents | workflowAgents | Array of 4 agents | Renamed + Matched (Normalized) | Field renamed but agent count matches | Medium | Update agent reference paths |
| Workflow Config | callbacks | Empty array | workflowConfigs | Object with managerLlm and enableAgenticMemory | Renamed + Modified | Field renamed and structure changed | High | Implement new config structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Update memory config handling |
| Org Metadata | org | "Ascendion" | Not Available | Not Available | Removed | Organizational metadata removed | Medium | Confirm removal is acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organizational ID removed | Medium | Confirm removal is acceptable |
| Domain | domain | "Platform Engineering" | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal is acceptable |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm removal is acceptable |
| Project | project | "AVA" | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal is acceptable |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm removal is acceptable |
| Team | team | "Digital Ascender" | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm removal is acceptable |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm removal is acceptable |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | "karthikeyan.iyappan@ascendion.com" | Medium | Implement user tracking |
| modifiedBy | User who last modified workflow | "karthikeyan.iyappan@ascendion.com" | Medium | Implement modification tracking |
| approvedBy | User who approved workflow | "karthikeyan.iyappan@ascendion.com" | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | "2025-11-30T11:55:00.892060" | Medium | Implement modification tracking |
| approvedAt | Approval timestamp | "2025-11-05T11:17:43.902770" | Medium | Implement approval tracking |
| status | Workflow approval state | "APPROVED" | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete handling |
| parentId | Parent workflow reference | -1 | Low | Handle workflow hierarchy |
| realmId | Realm/tenant identifier | 1 | Medium | Implement multi-tenancy support |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align defaults and implement new structure |
| managerLlm | Not available | Empty object in workflowConfigs | Medium | Configure manager LLM settings |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update memory config access path |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 4
**AAVA 2.0 total agents:** 4
**Coverage:** Same agent count, names normalized

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| Fabric Silver Model Logical | Fabric Silver Model Logical | Matched (Normalized) | Trailing space normalized |
| Fabric Silver Model Physical | Fabric Silver Model Physical | Matched (Normalized) | Trailing space normalized |
| DI_Mermaid_Data_Model_View | DI Mermaid Data Model View | Renamed | Underscore to space conversion |
| Fabric Silver Model Reviewer | Fabric Silver Model Reviewer | Matched | Exact match |

---

## 6. Agent Configuration Differences

## Agent: Fabric Silver Model Logical

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
| modelDeploymentName | "Anthropic.claude-4-sonnet" | "gpt-4.1" | High | Validate model change impact |
| model | "anthropic.claude-4-sonnet" | "model" | High | Validate model change impact |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 8000 | "8000" | Low | Type change but value matches |
| maxIter | 0 | null | Medium | Validate null vs zero behavior |
| maxRpm | 0 | null | Medium | Validate null vs zero behavior |
| maxExecutionTime | 0 | 90 | Medium | Execution time limit added |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: Fabric Silver Model Physical

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
| modelDeploymentName | "Anthropic.claude-4-sonnet" | "gpt-4.1" | High | Validate model change impact |
| model | "anthropic.claude-4-sonnet" | "model" | High | Validate model change impact |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 8000 | "8000" | Low | Type change but value matches |
| maxIter | 0 | null | Medium | Validate null vs zero behavior |
| maxRpm | 0 | null | Medium | Validate null vs zero behavior |
| maxExecutionTime | 0 | 90 | Medium | Execution time limit added |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present with full config | Not Present | High | Validate embedding removal impact |

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: DI Mermaid Data Model View

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Medium | Description content modified |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | "gemini-2.5-pro" | "gpt-4.1" | High | Validate model change impact |
| model | "gemini-2.5-pro" | "model" | High | Validate model change impact |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 64000 | "4000" | High | Significant token limit reduction |
| maxIter | 0 | null | Medium | Validate null vs zero behavior |
| maxRpm | 0 | null | Medium | Validate null vs zero behavior |
| maxExecutionTime | 0 | 90 | Medium | Execution time limit added |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available

---

## Agent: Fabric Silver Model Reviewer

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
| modelDeploymentName | "gpt-4.1" | "gpt-4.1" | Low | No change |
| model | "gpt-4" | "model" | Medium | Model name changed |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 8000 | "8000" | Low | Type change but value matches |
| maxIter | 0 | null | Medium | Validate null vs zero behavior |
| maxRpm | 0 | null | Medium | Validate null vs zero behavior |
| maxExecutionTime | 0 | 90 | Medium | Execution time limit added |

### 6.4.3 Tools Comparison
Not Available

### 6.4.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present with full config | Not Present | High | Validate embedding removal impact |

### 6.4.5 Guardrails Comparison
Not Available