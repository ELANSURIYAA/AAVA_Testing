# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 78%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI Data Technical Specification BQY | 75% | Medium | modelDeploymentName changed from gemini-2.5-pro to gpt-4.1, role/goal/backstory removed, maxExecutionTime added | Validate model compatibility and confirm instruction field removal |
| DI Model Changes BQY | 82% | Medium | modelDeploymentName changed from gemini-2.5-pro to gpt-4.1, role/goal/backstory removed, maxExecutionTime added | Validate model compatibility and confirm instruction field removal |
| DI Functional Test Cases BQY | 77% | Medium | modelDeploymentName changed from gemini-2.5-pro to gpt-4.1, role/goal/backstory removed, maxExecutionTime added | Validate model compatibility and confirm instruction field removal |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_DataSpecs_Modelupdates_BQY
**Workflow Name (AAVA 2.0):** DI DataSpecs Modelupdates BQY

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 7921 | id | 2519 | Renamed + Modified | Field renamed and value changed | High | Update references to new workflow ID |
| Naming | name | DI_DataSpecs_Modelupdates_BQY | name | DI DataSpecs Modelupdates BQY | Matched (Normalized) | Minor formatting differences | Low | No change |
| Description | description | Includes tech spec creation, functional testing with SQL scripts, and DDL-based model updates. | description | Includes tech spec creation, functional testing with SQL scripts, and DDL-based model updates. | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-10-31T17:40:00.303+00:00 | createdAt | 2025-11-05T11:02:39.229010 | Matched | Different timestamps as expected | Low | No change |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm, enableAgenticMemory} | Renamed + Modified | Enhanced configuration structure | Medium | Migrate to new config format |
| Memory Config | enableAgenticMemory | false | workflowConfigs.enableAgenticMemory | false | Renamed + Matched (Normalized) | Moved to workflowConfigs | Low | Update field path |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm removal acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm removal acceptable |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal acceptable |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm removal acceptable |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal acceptable |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm removal acceptable |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm removal acceptable |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm removal acceptable |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm removal acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | karthikeyan.iyappan@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | karthikeyan.iyappan@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | karthikeyan.iyappan@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Automatic timestamp handling |
| approvedAt | Approval timestamp | 2025-11-05T11:02:40.295133 | Low | Automatic timestamp handling |
| status | Workflow approval state | APPROVED | High | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete functionality |
| parentId | Parent workflow reference | -1 | Medium | Understand workflow hierarchy |
| realmId | Realm identifier | 1 | Medium | Understand realm-based isolation |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| managerLlm | Direct object | Nested in workflowConfigs | Medium | Update configuration access patterns |
| workflowConfigs | Not available | Present with structured config | Medium | Align with new config structure |
| enableAgenticMemory | Direct field | Nested in workflowConfigs | Low | Update field access path |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agent count maintained

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Data_Technical_Specification_BQY | DI Data Technical Specification BQY | Renamed | Underscore to space conversion |
| DI_Model_Changes_BQY | DI Model Changes BQY | Renamed | Underscore to space conversion |
| DI_Functional_Test_Cases_BQY | DI Functional Test Cases BQY | Renamed | Underscore to space conversion |

---

## 6. Agent Configuration Differences

## Agent: DI Data Technical Specification BQY

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility |
| model | gemini-2.5-pro | model | High | Validate model configuration |
| temperature | 0.20000000298023224 | 0.2 | Low | Normalized precision |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Confirm field removal |
| maxRpm | 0 | Not Available | Medium | Confirm field removal |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: DI Model Changes BQY

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility |
| model | gemini-2.5-pro | model | High | Validate model configuration |
| temperature | 0.20000000298023224 | 0.2 | Low | Normalized precision |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Confirm field removal |
| maxRpm | 0 | Not Available | Medium | Confirm field removal |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: DI Functional Test Cases BQY

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility |
| model | gemini-2.5-pro | model | High | Validate model configuration |
| temperature | 0.20000000298023224 | 0.2 | Low | Normalized precision |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Confirm field removal |
| maxRpm | 0 | Not Available | Medium | Confirm field removal |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available

The CSV file has been successfully uploaded to GitHub at: Metadata/Metadata_Output/DI_DataSpecs_Modelupdates_BQY/DI_DataSpecs_Modelupdates_BQY_comparison.csv