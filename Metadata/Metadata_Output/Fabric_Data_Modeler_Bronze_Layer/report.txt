# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

# 1. Metadata Comparison Score Summary

* Workflow Comparison Score: 82.5%
* Total Agents Compared: 4

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| Fabric Bronze Model Logical | 85% | Medium | Model changed from Anthropic to GPT-4, role/goal/backstory removed | Validate LLM behavior consistency and confirm instruction field removal |
| Fabric Bronze Model Physical | 88% | Medium | Model changed from Anthropic to GPT-4, allowDelegation changed from true to true | Validate LLM behavior consistency |
| Fabric Bronze Model Data Mapping | 92% | Low | Model changed from GPT-4 to GPT-4, minimal config changes | Validate runtime behavior |
| DI Mermaid Data Model View | 65% | Medium | Agent name changed, model changed from Gemini to GPT-4, maxToken reduced | Validate model compatibility and performance impact |

---

# 2. Workflow-Level Comparison

Workflow Name (AAVA 1.0): Fabric Data Modeler Bronze Layer 
Workflow Name (AAVA 2.0): Fabric Data Modeler Bronze Layer 

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 375 | id | 3870 | Renamed + Modified | Pipeline ID renamed to id and value changed | Medium | Update references to new ID |
| Naming | name | Fabric Data Modeler Bronze Layer  | name | Fabric Data Modeler Bronze Layer  | Matched (Normalized) | Names match after normalization | Low | No change |
| Description | description | Data Modeler for Microsoft Fabric environment | description | Data Modeler for Microsoft Fabric environment | Matched | Descriptions are identical | Low | No change |
| Audit | createdAt | 2025-06-25T08:06:57.417+00:00 | createdAt | 2025-11-05T11:44:51.052414 | Modified | Creation timestamps differ | Low | Expected for different workflow instances |
| Agents List | pipeLineAgents | [4 agents] | workflowAgents | [4 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Renamed and structure changed | Medium | Validate new config structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Confirm new location |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Add missing governance fields |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | High | Add missing governance fields |
| Domain | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | High | Add missing governance fields |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | High | Add missing governance fields |
| Project | project | AVA | Not Available | Not Available | Removed | Project metadata removed | High | Add missing governance fields |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | High | Add missing governance fields |
| Team | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | High | Add missing governance fields |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | High | Add missing governance fields |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm removal is acceptable |

---

# 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | karthikeyan.iyappan@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified | karthikeyan.iyappan@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | karthikeyan.iyappan@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-11-30T11:55:00.892060 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T11:44:52.116412 | Medium | Ensure approval process is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Standard deletion handling |
| parentId | Parent workflow reference | -1 | Low | Workflow versioning support |
| realmId | Realm identifier | 1 | Medium | Multi-tenancy support |

---

# 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|---------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align defaults and validate structure |
| managerLlm | Not available | Empty object {} | Medium | Configure manager LLM settings |
| enableAgenticMemory | Top-level field (false) | Nested in workflowConfigs (false) | Medium | Update configuration access patterns |

---

# 5. Agent Inventory Summary

## 5.1 Agent Count & Coverage

AAVA 1.0 total agents: 4
AAVA 2.0 total agents: 4
Coverage: Same agent count, some renamed

## 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| Fabric Bronze Model Logical  | Fabric Bronze Model Logical  | Matched (Normalized) | Names match after normalization |
| Fabric Bronze Model Physical | Fabric Bronze Model Physical | Matched | Exact match |
| Fabric Bronze Model Data Mapping   | Fabric Bronze Model Data Mapping   | Matched (Normalized) | Names match after normalization |
| DI_Mermaid_Data_Model_View | DI Mermaid Data Model View | Renamed | Underscore naming convention changed |

---

# 6. Agent Configuration Differences

## Agent: Fabric Bronze Model Logical 

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model behavior consistency |
| model | anthropic.claude-4-sonnet | model | High | Validate model behavior consistency |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Confirm field removal |
| maxRpm | 0 | Not Present | Medium | Confirm field removal |
| maxExecutionTime | 0 | 90 | Medium | Execution time limit added |

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

## Agent: Fabric Bronze Model Physical

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model behavior consistency |
| model | anthropic.claude-4-sonnet | model | High | Validate model behavior consistency |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Confirm field removal |
| maxRpm | 0 | Not Present | Medium | Confirm field removal |
| maxExecutionTime | 0 | 90 | Medium | Execution time limit added |
| allowDelegation | true | true | Low | No change |

---

## 6.2.3 Tools Comparison

Not Available

---

## 6.2.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present (AzureOpenAI config) | Not Present | High | Restore knowledge base configuration |

---

## 6.2.5 Guardrails Comparison

Not Available

---

## Agent: Fabric Bronze Model Data Mapping  

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
| model | gpt-4 | model | Medium | Validate model reference consistency |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Confirm field removal |
| maxRpm | 0 | Not Present | Medium | Confirm field removal |
| maxExecutionTime | 0 | 90 | Medium | Execution time limit added |
| allowDelegation | true | true | Low | No change |

---

## 6.3.3 Tools Comparison

Not Available

---

## 6.3.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present (AzureOpenAI config) | Not Present | High | Restore knowledge base configuration |

---

## 6.3.5 Guardrails Comparison

Not Available

---

## Agent: DI Mermaid Data Model View

---

## 6.4.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

## 6.4.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model behavior consistency |
| model | gemini-2.5-pro | model | High | Validate model behavior consistency |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 64000 | 4000 | High | Token limit significantly reduced |
| maxIter | 0 | Not Present | Medium | Confirm field removal |
| maxRpm | 0 | Not Present | Medium | Confirm field removal |
| maxExecutionTime | 0 | 90 | Medium | Execution time limit added |
| allowDelegation | false | true | Medium | Delegation setting changed |

---

## 6.4.3 Tools Comparison

Not Available

---

## 6.4.4 Knowledge Base Comparison

Not Available

---

## 6.4.5 Guardrails Comparison

Not Available