# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 76.2%
**Total Agents Compared:** 5

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| XML_Model_Conceptual_CVS | 78% | Medium | role/goal/backstory removed, model changed to gpt-4.1, maxToken reduced | Validate instruction completeness and model behavior |
| XML_Logical_Data_Model_CVS | 76% | Medium | role/goal/backstory removed, model changed to gpt-4.1, maxToken reduced | Validate instruction completeness and model behavior |
| XML_Physical_Data_Model_CVS | 75% | Medium | role/goal/backstory removed, model changed to gpt-4.1, maxToken reduced, topP reduced | Validate instruction completeness and model behavior |
| XML_Data_Mapping_CVS | 78% | Medium | role/goal/backstory removed, model changed to gpt-4.1, maxToken reduced | Validate instruction completeness and model behavior |
| DI_Mermaid_Data_Model_View | 74% | Medium | role/goal/backstory removed, model changed to gpt-4.1, maxToken reduced, description modified | Validate instruction completeness and model behavior |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** XML_Data_Model_CVS
**Workflow Name (AAVA 2.0):** XML Data Model CVS

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1152 | id | 3927 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to use new ID |
| Naming | name | XML_Data_Model_CVS | name | XML Data Model CVS | Matched (Normalized) | Minor spacing difference normalized | Low | No change |
| Description | description | This workflow will create a complete Data model for XML file | description | This workflow will create a complete Data model for XML file | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-03-25T15:20:03.420+00:00 | createdAt | 2025-11-05T11:46:33.294484 | Modified | Different creation timestamps | Low | Update audit trail |
| Agents List | pipeLineAgents | [5 agents] | workflowAgents | [5 agents] | Renamed + Matched (Normalized) | Field renamed but same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Enhanced configuration structure | Medium | Validate new config behavior |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Low | Confirm removal acceptable |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm removal acceptable |
| Domain Metadata | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal acceptable |
| Project Metadata | project | AVA | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User tracking | default@ascendion.com | Medium | Ensure user attribution is handled |
| modifiedBy | Change tracking | default@ascendion.com | Medium | Implement modification tracking |
| approvedBy | Approval workflow | default@ascendion.com | Medium | Establish approval process |
| modifiedAt | Timestamp tracking | 2025-12-03T15:03:31.224436 | Low | Update audit trail |
| approvedAt | Approval timestamp | 2025-11-05T11:46:34.351808 | Low | Update audit trail |
| status | Workflow state | APPROVED | High | Implement workflow lifecycle |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete logic |
| parentId | Hierarchy tracking | -1 | Low | Validate hierarchy structure |
| realmId | Multi-tenancy | 1 | Medium | Implement realm-based access |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|---------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align configuration defaults |
| managerLlm | Not available | Empty object [{}] | Medium | Define manager LLM configuration |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Low | Update configuration access |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5
**AAVA 2.0 total agents:** 5
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| XML_Model_Conceptual_CVS | XML Model Conceptual CVS | Renamed | Naming convention updated |
| XML_Logical_Data_Model_CVS | XML Logical Data Model CVS | Renamed | Naming convention updated |
| XML_Physical_Data_Model_CVS | XML Physical Data Model CVS | Renamed | Naming convention updated |
| XML_Data_Mapping_CVS | XML Data Mapping CVS | Renamed | Naming convention updated |
| DI_Mermaid_Data_Model_View | DI Mermaid Data Model View | Renamed | Naming convention updated |

---

## 6. Agent Configuration Differences

## Agent: XML_Model_Conceptual_CVS

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | Medium | Add missing field or confirm deprecation |

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model behavior compatibility |
| model | gemini-2.5-pro | model | High | Validate model behavior compatibility |
| temperature | 0.30000001192092896 | 0.3 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | No change (normalized) |
| maxToken | 64000 | 4000 | High | Validate token limit impact |
| maxIter | 0 | null | Low | No change |
| maxRpm | 0 | null | Low | No change |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout behavior |
| allowDelegation | false | true | Medium | Validate delegation behavior |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: XML_Logical_Data_Model_CVS

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | Medium | Add missing field or confirm deprecation |

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model behavior compatibility |
| model | gemini-2.5-pro | model | High | Validate model behavior compatibility |
| temperature | 0.30000001192092896 | 0.3 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | No change (normalized) |
| maxToken | 64000 | 4000 | High | Validate token limit impact |
| maxIter | 0 | null | Low | No change |
| maxRpm | 0 | null | Low | No change |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout behavior |
| allowDelegation | false | true | Medium | Validate delegation behavior |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: XML_Physical_Data_Model_CVS

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | Medium | Add missing field or confirm deprecation |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model behavior compatibility |
| model | gemini-2.5-pro | model | High | Validate model behavior compatibility |
| temperature | 0.20000000298023224 | 0.3 | Medium | Validate temperature impact |
| topP | 1.0 | 0.94 | Medium | Validate topP impact |
| maxToken | 64000 | 4000 | High | Validate token limit impact |
| maxIter | 0 | null | Low | No change |
| maxRpm | 0 | null | Low | No change |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout behavior |
| allowDelegation | false | true | Medium | Validate delegation behavior |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available

---

## Agent: XML_Data_Mapping_CVS

### 6.4.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | Medium | Add missing field or confirm deprecation |

### 6.4.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model behavior compatibility |
| model | gemini-2.5-pro | model | High | Validate model behavior compatibility |
| temperature | 0.30000001192092896 | 0.3 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | No change (normalized) |
| maxToken | 64000 | 4000 | High | Validate token limit impact |
| maxIter | 0 | null | Low | No change |
| maxRpm | 0 | null | Low | No change |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout behavior |
| allowDelegation | false | true | Medium | Validate delegation behavior |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.4.3 Tools Comparison
Not Available

### 6.4.4 Knowledge Base Comparison
Not Available

### 6.4.5 Guardrails Comparison
Not Available

---

## Agent: DI_Mermaid_Data_Model_View

### 6.5.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Medium | Description content modified |
| expectedOutput | Present | Not Available | Medium | Add missing field or confirm deprecation |

### 6.5.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model behavior compatibility |
| model | gemini-2.5-pro | model | High | Validate model behavior compatibility |
| temperature | 0.30000001192092896 | 0.3 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | No change (normalized) |
| maxToken | 64000 | 4000 | High | Validate token limit impact |
| maxIter | 0 | null | Low | No change |
| maxRpm | 0 | null | Low | No change |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout behavior |
| allowDelegation | false | true | Medium | Validate delegation behavior |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.5.3 Tools Comparison
Not Available

### 6.5.4 Knowledge Base Comparison
Not Available

### 6.5.5 Guardrails Comparison
Not Available