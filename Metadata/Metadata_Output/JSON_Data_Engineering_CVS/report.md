# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 73%**
**Total Agents Compared: 2**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| JSON Data Pipeline CVS | 71% | Medium | model changed from gemini-2.5-pro to gpt-4.1; role/goal/backstory removed; maxToken reduced; allowDelegation changed | Validate model compatibility and runtime behavior |
| GCP PySpark Unit Tester | 75% | Medium | model changed from gemini-2.5-pro to gpt-4.1; role/goal/backstory removed; maxToken reduced; allowDelegation changed | Validate model compatibility and runtime behavior |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** JSON_Data_Engineering_CVS
**Workflow Name (AAVA 2.0):** JSON Data Engineering CVS

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 1209 | id | 3956 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to new workflow ID |
| Naming | name | JSON_Data_Engineering_CVS | name | JSON Data Engineering CVS | Matched (Normalized) | Minor spacing differences normalized | Low | No change |
| Description | description | This workflow will provide PySpark code | description | This workflow will provide PySpark code | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-03-25T12:19:59.091+00:00 | createdAt | 2025-11-05T11:47:26.597324 | Matched | Field present in both, values differ | Low | No change |
| Agents List | pipeLineAgents | [2 agents] | workflowAgents | [2 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {"managerLlm": [{}], "enableAgenticMemory": false} | Renamed + Modified | Field renamed and structure enhanced | Medium | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs structure | Medium | Update memory configuration handling |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm removal is acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm removal is acceptable |
| Domain | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal is acceptable |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm removal is acceptable |
| Project | project | AVA | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal is acceptable |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm removal is acceptable |
| Team | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm removal is acceptable |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm removal is acceptable |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T11:47:27.657151 | Medium | Ensure approval workflow is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete functionality is implemented |
| parentId | Parent workflow reference | -1 | Low | Understand workflow hierarchy |
| realmId | Realm identifier | 1 | Low | Understand realm-based organization |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Configure new workflow settings |
| managerLlm | Not available | Empty object {} | Medium | Configure manager LLM settings |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update memory configuration handling |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 2
**AAVA 2.0 total agents:** 2
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| JSON_Data_Pipeline_CVS | JSON Data Pipeline CVS | Renamed | Naming convention updated (underscores to spaces) |
| GCP_PySpark_Unit_Tester | GCP PySpark Unit Tester | Renamed | Naming convention updated (underscores to spaces) |

---

## 6. Agent Configuration Differences

## Agent: JSON Data Pipeline CVS

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility and performance |
| model | gemini-2.5-pro | model | High | Validate model compatibility and performance |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 64000 | 4000 | High | Validate token limit impact on output quality |
| maxIter | 0 | null | Low | Both indicate no iteration limit |
| maxRpm | 0 | null | Low | Both indicate no rate limit |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added, validate impact |
| allowDelegation | false | true | Medium | Delegation behavior changed |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: GCP PySpark Unit Tester

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility and performance |
| model | gemini-2.5-pro | model | High | Validate model compatibility and performance |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 64000 | 4000 | High | Validate token limit impact on output quality |
| maxIter | 0 | null | Low | Both indicate no iteration limit |
| maxRpm | 0 | null | Low | Both indicate no rate limit |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added, validate impact |
| allowDelegation | false | true | Medium | Delegation behavior changed |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available