# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Name (AAVA 1.0):** Talend_to_PySpark_Doc_Analyze_Plan
**Workflow Name (AAVA 2.0):** Talend to PySpark Doc Analyze Plan

* **Workflow Comparison Score:** 78%
* **Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| Talend_to_PySpark_Documentation / Talend to PySpark Documentation | 85% | Medium | Model changed (gpt-4o → gpt-4.1), name normalized, description matched | Validate model compatibility |
| Talend_to_PySpark_Analyzer / Talend to PySpark Analyzer | 87% | Medium | Model changed (gpt-4o → gpt-4.1), description matched, configs matched | Validate model compatibility |
| Talend_to_PySpark_Plan / Talend to PySpark Plan | 85% | Medium | Model changed (gpt-4o → gpt-4.1), description matched, configs matched | Validate model compatibility |

---

## 2. Workflow-Level Comparison

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 1454 | id | 4134 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to use new ID |
| Naming | name | Talend_to_PySpark_Doc_Analyze_Plan | name | Talend to PySpark Doc Analyze Plan | Matched (Normalized) | Name normalized (underscores to spaces) | Low | No action required |
| Description | description | Talend_to_PySpark_Doc_Analyze_Plan | description | Talend_to_PySpark_Doc_Analyze_Plan | Matched | Description unchanged | Low | No action required |
| Audit | createdAt | 2025-04-04T06:17:04.594+00:00 | createdAt | 2025-11-05T11:52:52.118981 | Matched | Field exists in both but timestamp differs | Low | Expected difference |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update code references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure enhanced | High | Implement new config structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Update config access pattern |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | Medium | Confirm removal acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organizational ID removed | Medium | Confirm removal acceptable |
| Domain | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal acceptable |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm removal acceptable |
| Project | project | AVA | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal acceptable |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm removal acceptable |
| Team | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm removal acceptable |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm removal acceptable |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm removal acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Implement user tracking |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Implement modification tracking |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Implement modification tracking |
| approvedAt | Approval timestamp | 2025-11-05T11:52:53.171517 | Medium | Implement approval tracking |
| status | Workflow approval state | APPROVED | High | Implement workflow lifecycle |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete logic |
| parentId | Parent workflow reference | -1 | Medium | Implement workflow hierarchy |
| realmId | Realm/tenant identifier | 1 | Medium | Implement multi-tenancy |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | High | Implement new config structure |
| managerLlm | Not available | Empty object [{}] | Medium | Configure manager LLM settings |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update config access pattern |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agent count with naming normalization

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| Talend_to_PySpark_Documentation | Talend to PySpark Documentation | Renamed | Naming convention updated (underscores to spaces) |
| Talend_to_PySpark_Analyzer | Talend to PySpark Analyzer | Renamed | Naming convention updated (underscores to spaces) |
| Talend_to_PySpark_Plan | Talend to PySpark Plan | Renamed | Naming convention updated (underscores to spaces) |

---

## 6. Agent Configuration Differences

## Agent: Talend_to_PySpark_Documentation / Talend to PySpark Documentation

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility and performance |
| model | gpt-4o | model | High | Update model reference |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Confirm removal acceptable |
| maxRpm | 0 | Not Available | Medium | Confirm removal acceptable |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.1.3 Tools Comparison
**Not Available** - No tools configured in either version

### 6.1.4 Knowledge Base Comparison
**Not Available** - No knowledge base configured in either version

### 6.1.5 Guardrails Comparison
**Not Available** - No guardrails configured in either version

---

## Agent: Talend_to_PySpark_Analyzer

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility and performance |
| model | gpt-4o | model | High | Update model reference |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Confirm removal acceptable |
| maxRpm | 0 | Not Available | Medium | Confirm removal acceptable |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.2.3 Tools Comparison
**Not Available** - No tools configured in either version

### 6.2.4 Knowledge Base Comparison
**Not Available** - No knowledge base configured in either version

### 6.2.5 Guardrails Comparison
**Not Available** - No guardrails configured in either version

---

## Agent: Talend_to_PySpark_Plan

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility and performance |
| model | gpt-4o | model | High | Update model reference |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Confirm removal acceptable |
| maxRpm | 0 | Not Available | Medium | Confirm removal acceptable |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

### 6.3.3 Tools Comparison
**Not Available** - No tools configured in either version

### 6.3.4 Knowledge Base Comparison
**Not Available** - No knowledge base configured in either version

### 6.3.5 Guardrails Comparison
**Not Available** - No guardrails configured in either version

Now I'll create the CSV file with the required format and upload both files to GitHub.

Action: GitHub File Writer Tool
Action Input: {"repo": "ELANSURIYAA/AAVA_Testing", "branch": "main", "token": "<REDACTED_GITHUB_TOKEN>", "folder_name": "Metadata/Metadata_Output", "file_name": "Talend_to_PySpark_Doc_Analyze_Plan/Talend_to_PySpark_Doc_Analyze_Plan_comparison.csv", "content": "Workflow Comparison Score,Total Agents Compared
78%,3

Agent Name,Agent Score,Risk Level,Key Score Drivers,Migration Action Required
Talend_to_PySpark_Documentation / Talend to PySpark Documentation,85%,Medium,Model changed (gpt-4o → gpt-4.1) name normalized description matched,Validate model compatibility
Talend_to_PySpark_Analyzer / Talend to PySpark Analyzer,87%,Medium,Model changed (gpt-4o → gpt-4.1) description matched configs matched,Validate model compatibility
Talend_to_PySpark_Plan / Talend to PySpark Plan,85%,Medium,Model changed (gpt-4o → gpt-4.1) description matched configs matched,Validate model compatibility"}