# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 78%**
**Total Agents Compared: 5**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| Hive to Delta Converter | 82% | Medium | modelDeploymentName changed, role/goal/backstory removed | Validate model compatibility and instruction completeness |
| Hive to Delta Unit Tester | 85% | Medium | modelDeploymentName changed, role/goal/backstory removed | Validate model compatibility and instruction completeness |
| Hive to Delta Conversion Tester | 85% | Medium | modelDeploymentName changed, role/goal/backstory removed | Validate model compatibility and instruction completeness |
| Hive to Delta Recon Tester | 85% | Medium | modelDeploymentName changed, role/goal/backstory removed | Validate model compatibility and instruction completeness |
| Hive to Delta Reviewer | 85% | Medium | modelDeploymentName changed, role/goal/backstory removed | Validate model compatibility and instruction completeness |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** Hive_to_Delta_Convert
**Workflow Name (AAVA 2.0):** Hive to Delta Convert

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1082 | id | 3861 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | Hive_to_Delta_Convert | name | Hive to Delta Convert | Matched (Normalized) | Minor formatting difference | Low | No change |
| Description | description | Hive_to_Delta_Convert | description | Hive_to_Delta_Convert | Matched | Identical values | Low | No change |
| Audit | createdAt | 2025-03-14T09:41:27.354+00:00 | createdAt | 2025-11-05T11:44:34.279490 | Matched | Field present in both, values differ due to different creation times | Low | No change |
| Agents List | pipeLineAgents | [5 agents] | workflowAgents | [5 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {"managerLlm": [{}], "enableAgenticMemory": false} | Renamed + Modified | Field renamed and structure changed | High | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Verify memory configuration |
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
| createdBy | User who created the workflow | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified the workflow | default@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved the workflow | default@ascendion.com | Medium | Ensure approval workflow is handled |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Automatic timestamp handling |
| approvedAt | Approval timestamp | 2025-11-05T11:44:35.332463 | Low | Automatic timestamp handling |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Ensure deletion handling is implemented |
| parentId | Parent workflow reference | -1 | Low | Handle workflow hierarchy if needed |
| realmId | Realm identifier | 1 | Medium | Ensure realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Configure manager LLM settings |
| callbacks | Empty array | Not available | Low | Verify callback handling migration |

---

## 5. Agent Inventory Summary

## 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5
**AAVA 2.0 total agents:** 5
**Coverage:** Same agents with naming updates

## 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| Hive to Delta Converter | Hive to Delta Converter | Matched | Identical names |
| Hive to Delta Unit Tester | Hive to Delta Unit Tester | Matched | Identical names |
| Hive to Delta Conversion Tester | Hive to Delta Conversion Tester | Matched | Identical names |
| Hive to Delta Recon Tester | Hive to Delta Recon Tester | Matched | Identical names |
| Hive to Delta Reviewer | Hive to Delta Reviewer | Matched | Identical names |

---

## 6. Agent Configuration Differences

## Agent: Hive to Delta Converter

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
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Execution time limit added |

### 6.1.3 Tools Comparison

**Not Available**

### 6.1.4 Knowledge Base Comparison

**Not Available**

### 6.1.5 Guardrails Comparison

**Not Available**

---

## Agent: Hive to Delta Unit Tester

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
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Execution time limit added |

### 6.2.3 Tools Comparison

**Not Available**

### 6.2.4 Knowledge Base Comparison

**Not Available**

### 6.2.5 Guardrails Comparison

**Not Available**

---

## Agent: Hive to Delta Conversion Tester

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
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Execution time limit added |

### 6.3.3 Tools Comparison

**Not Available**

### 6.3.4 Knowledge Base Comparison

**Not Available**

### 6.3.5 Guardrails Comparison

**Not Available**

---

## Agent: Hive to Delta Recon Tester

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
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Execution time limit added |

### 6.4.3 Tools Comparison

**Not Available**

### 6.4.4 Knowledge Base Comparison

**Not Available**

### 6.4.5 Guardrails Comparison

**Not Available**

---

## Agent: Hive to Delta Reviewer

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
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Execution time limit added |

### 6.5.3 Tools Comparison

**Not Available**

### 6.5.4 Knowledge Base Comparison

**Not Available**

### 6.5.5 Guardrails Comparison

**Not Available**

Now I need to create the CSV file with the required format and upload it to GitHub.

Action: GitHub File Writer Tool
Action Input: {"repo": "ELANSURIYAA/AAVA_Testing", "branch": "main", "token": "<REDACTED_GITHUB_TOKEN>", "folder_name": "Metadata/Metadata_Output", "file_name": "Hive_to_Delta_Convert/Hive_to_Delta_Convert_comparison.csv", "content": "Workflow Comparison Score,Total Agents Compared
78%,5

Agent Name,Agent Score,Risk Level,Key Score Drivers,Migration Action Required
Hive to Delta Converter,82%,Medium,modelDeploymentName changed; role/goal/backstory removed,Validate model compatibility and instruction completeness
Hive to Delta Unit Tester,85%,Medium,modelDeploymentName changed; role/goal/backstory removed,Validate model compatibility and instruction completeness
Hive to Delta Conversion Tester,85%,Medium,modelDeploymentName changed; role/goal/backstory removed,Validate model compatibility and instruction completeness
Hive to Delta Recon Tester,85%,Medium,modelDeploymentName changed; role/goal/backstory removed,Validate model compatibility and instruction completeness
Hive to Delta Reviewer,85%,Medium,modelDeploymentName changed; role/goal/backstory removed,Validate model compatibility and instruction completeness"}