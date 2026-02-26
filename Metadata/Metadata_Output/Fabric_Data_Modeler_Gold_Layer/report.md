# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 87.5%**
**Total Agents Compared: 4**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| Fabric Gold Model Logical | 92.3% | Low | Model configs matched, description matched, LLM settings preserved | None |
| Fabric Gold Model Physical | 89.2% | Medium | Model configs matched, description matched, embedding configs removed | Validate embedding functionality |
| DI Mermaid Data Model View | 84.6% | Medium | Name normalized, description matched, task input reference changed | Update task input references |
| Fabric Gold Model Reviewer | 84.6% | Medium | Description matched, model configs matched, embedding configs removed | Validate embedding functionality |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** Fabric Data Modeler Gold Layer
**Workflow Name (AAVA 2.0):** Fabric Data Modeler Gold Layer

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 377 | id | 3438 | Renamed + Modified | Field renamed and value changed | Medium | Update ID references |
| Naming | name | " Fabric Data Modeler Gold Layer" | name | " Fabric Data Modeler Gold Layer" | Matched (Normalized) | Names match after normalization | Low | No change |
| Description | description | "Data Modeler for Microsoft Fabric environment" | description | "Data Modeler for Microsoft Fabric environment" | Matched | Descriptions identical | Low | No change |
| Audit | createdAt | "2025-06-25T10:38:15.861+00:00" | createdAt | "2025-11-05T11:31:46.938638" | Modified | Creation timestamps differ | Low | Expected for different workflows |
| Agents List | pipeLineAgents | Array[4] | workflowAgents | Array[4] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | Object with managerLlm | Renamed + Modified | Structure and content changed | High | Implement new config structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Update memory configuration |
| Org Metadata | org | "Ascendion" | Not Available | Not Available | Removed | Organizational metadata removed | Medium | Confirm removal acceptable |
| Domain Metadata | domain | "Platform Engineering" | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal acceptable |
| Project Metadata | project | "AVA" | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User audit trail | "karthikeyan.iyappan@ascendion.com" | Medium | Implement user tracking |
| modifiedBy | Modification tracking | "karthikeyan.iyappan@ascendion.com" | Medium | Implement modification tracking |
| approvedBy | Approval workflow | "karthikeyan.iyappan@ascendion.com" | Medium | Implement approval process |
| status | Workflow state | "APPROVED" | High | Ensure workflow lifecycle handling |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete logic |
| parentId | Workflow hierarchy | -1 | Low | Handle workflow relationships |
| realmId | Multi-tenancy | 1 | Medium | Implement realm-based access |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm | High | Implement new config structure |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update memory config access |
| managerLlm | Not available | Empty array in workflowConfigs | Medium | Validate manager LLM functionality |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents: 4**
**AAVA 2.0 total agents: 4**
**Coverage: Same agents with naming updates**

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| Fabric Gold Model Logical | Fabric Gold Model Logical | Matched (Normalized) | Trailing space normalized |
| Fabric Gold Model Physical | Fabric Gold Model Physical | Matched (Normalized) | Trailing space normalized |
| DI_Mermaid_Data_Model_View | DI Mermaid Data Model View | Renamed | Underscore to space conversion |
| Fabric Gold Model Reviewer | Fabric Gold Model Reviewer | Matched | Exact match |

---

## 6. Agent Configuration Differences

## Agent: Fabric Gold Model Logical

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
| modelDeploymentName | "Anthropic.claude-4-sonnet" | "gpt-4.1" | High | Validate model compatibility |
| model | "anthropic.claude-4-sonnet" | "model" | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 8000 | "8000" | Low | Type change but value preserved |
| maxIter | 0 | null | Low | Default handling change |
| maxRpm | 0 | null | Low | Default handling change |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout increased |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: Fabric Gold Model Physical

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
| modelDeploymentName | "Anthropic.claude-4-sonnet" | "gpt-4.1" | High | Validate model compatibility |
| model | "anthropic.claude-4-sonnet" | "model" | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 8000 | "8000" | Low | Type change but value preserved |
| maxIter | 0 | null | Low | Default handling change |
| maxRpm | 0 | null | Low | Default handling change |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout increased |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present (AzureOpenAI config) | Not Present | High | Validate embedding functionality removal |

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
| description | Present | Present | Medium | Task input reference changed |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | "gemini-2.5-pro" | "gpt-4.1" | High | Validate model compatibility |
| model | "gemini-2.5-pro" | "model" | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 64000 | "4000" | High | Token limit significantly reduced |
| maxIter | 0 | null | Low | Default handling change |
| maxRpm | 0 | null | Low | Default handling change |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout increased |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available

---

## Agent: Fabric Gold Model Reviewer

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
| maxToken | 8000 | "8000" | Low | Type change but value preserved |
| maxIter | 0 | null | Low | Default handling change |
| maxRpm | 0 | null | Low | Default handling change |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout increased |

### 6.4.3 Tools Comparison
Not Available

### 6.4.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present (AzureOpenAI config) | Not Present | High | Validate embedding functionality removal |

### 6.4.5 Guardrails Comparison
Not Available