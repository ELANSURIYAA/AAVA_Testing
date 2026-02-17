# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 74%
**Total Agents Compared:** 5

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| JSON Model Conceptual CVS | 72% | Medium | role/goal/backstory removed, model changed, description matched | Validate agent behavior without role/goal/backstory fields |
| JSON Logical Data Model CVS | 76% | Medium | role/goal/backstory removed, model changed, description matched | Validate agent behavior without role/goal/backstory fields |
| JSON Physical Data Model CVS | 74% | Medium | role/goal/backstory removed, model changed, description matched | Validate agent behavior without role/goal/backstory fields |
| JSON Data Mapping CVS | 72% | Medium | role/goal/backstory removed, model changed, description matched | Validate agent behavior without role/goal/backstory fields |
| DI Mermaid Data Model View | 76% | Medium | role/goal/backstory removed, model changed, description matched | Validate agent behavior without role/goal/backstory fields |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** JSON_Data_Model_CVS
**Workflow Name (AAVA 2.0):** JSON Data Model CVS

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1155 | id | 3925 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | JSON_Data_Model_CVS | name | JSON Data Model CVS | Matched (Case Normalization) | Minor formatting difference | Low | No change required |
| Description | description | This workflow will create a complete Data model for JSON file | description | This workflow will create a complete Data model for JSON file | Matched | Identical values | Low | No change required |
| Audit | createdAt | 2025-03-25T14:19:12.475+00:00 | createdAt | 2025-11-05T11:46:30.744294 | Matched | Field present in both | Medium | Validate timestamp differences |
| Agents List | pipeLineAgents | [5 agents] | workflowAgents | [5 agents] | Renamed + Matched (Normalized) | Field renamed but content preserved | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {"managerLlm": [{}], "enableAgenticMemory": false} | Renamed + Modified | Field renamed and structure changed | High | Migrate callback logic to workflowConfigs |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Confirm memory settings in workflowConfigs |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm org context handling |
| Domain Metadata | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm domain context handling |
| Project Metadata | project | AVA | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm project context handling |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T11:46:31.791135 | Medium | Ensure approval workflow is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete logic is implemented |
| parentId | Parent workflow reference | -1 | Low | Confirm workflow hierarchy handling |
| realmId | Realm/tenant identifier | 1 | Medium | Ensure multi-tenancy is handled |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align configuration structure |
| managerLlm | Not available | Empty object {} | Medium | Configure manager LLM settings |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update memory configuration access |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5
**AAVA 2.0 total agents:** 5
**Coverage:** Same agent count with naming convention updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| JSON_Model_Conceptual_CVS | JSON Model Conceptual CVS | Renamed | Underscore to space conversion |
| JSON_Logical_Data_Model_CVS | JSON Logical Data Model CVS | Renamed | Underscore to space conversion |
| JSON_Physical_Data_Model_CVS | JSON Physical Data Model CVS | Renamed | Underscore to space conversion |
| JSON_Data_Mapping_CVS | JSON Data Mapping CVS | Renamed | Underscore to space conversion |
| DI_Mermaid_Data_Model_View | DI Mermaid Data Model View | Renamed | Underscore to space conversion |

---

## 6. Agent Configuration Differences

## Agent: JSON Model Conceptual CVS

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility |
| model | gemini-2.5-pro | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 64000 | 4000 | High | Validate token limit impact |
| maxIter | 0 | null | Medium | Confirm iteration handling |
| maxRpm | 0 | null | Medium | Confirm rate limit handling |
| maxExecutionTime | 0 | 90 | Medium | Validate execution time settings |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: JSON Logical Data Model CVS

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility |
| model | gemini-2.5-pro | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 64000 | 4000 | High | Validate token limit impact |
| maxIter | 0 | null | Medium | Confirm iteration handling |
| maxRpm | 0 | null | Medium | Confirm rate limit handling |
| maxExecutionTime | 0 | 90 | Medium | Validate execution time settings |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: JSON Physical Data Model CVS

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility |
| model | gemini-2.5-pro | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 64000 | 4000 | High | Validate token limit impact |
| maxIter | 0 | null | Medium | Confirm iteration handling |
| maxRpm | 0 | null | Medium | Confirm rate limit handling |
| maxExecutionTime | 0 | 90 | Medium | Validate execution time settings |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available

---

## Agent: JSON Data Mapping CVS

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility |
| model | gemini-2.5-pro | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 64000 | 4000 | High | Validate token limit impact |
| maxIter | 0 | null | Medium | Confirm iteration handling |
| maxRpm | 0 | null | Medium | Confirm rate limit handling |
| maxExecutionTime | 0 | 90 | Medium | Validate execution time settings |

### 6.4.3 Tools Comparison
Not Available

### 6.4.4 Knowledge Base Comparison
Not Available

### 6.4.5 Guardrails Comparison
Not Available

---

## Agent: DI Mermaid Data Model View

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility |
| model | gemini-2.5-pro | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 64000 | 4000 | High | Validate token limit impact |
| maxIter | 0 | null | Medium | Confirm iteration handling |
| maxRpm | 0 | null | Medium | Confirm rate limit handling |
| maxExecutionTime | 0 | 90 | Medium | Validate execution time settings |

### 6.5.3 Tools Comparison
Not Available

### 6.5.4 Knowledge Base Comparison
Not Available

### 6.5.5 Guardrails Comparison
Not Available