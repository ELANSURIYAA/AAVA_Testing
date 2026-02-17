# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 76%
**Total Agents Compared:** 2

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| XML_Data_Pipeline_CVS | 72% | Medium | model changed (gemini-2.5-pro to gpt-4.1), role/goal/backstory removed, temperature modified, topP modified, maxToken modified | Validate model compatibility and instruction field removal impact |
| GCP_PySpark_Unit_Tester | 80% | Medium | model changed (gemini-2.5-pro to gpt-4.1), role/goal/backstory removed, temperature matched, topP matched | Validate model compatibility and instruction field removal impact |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** XML_Data_Engineering_CVS
**Workflow Name (AAVA 2.0):** XML Data Engineering CVS

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1210 | id | 3961 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID field |
| Naming | name | XML_Data_Engineering_CVS | name | XML Data Engineering CVS | Matched (Case Normalization) | Minor formatting difference | Low | No change needed |
| Description | description | This workflow will provide PySpark code | description | This workflow will provide PySpark code | Matched | Identical values | Low | No change needed |
| Audit | createdAt | 2025-03-25T15:41:37.962+00:00 | createdAt | 2025-11-05T11:47:35.181504 | Matched | Different timestamps (expected) | Low | No change needed |
| Agents List | pipeLineAgents | [2 agents] | workflowAgents | [2 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Enhanced configuration structure | Medium | Align configuration handling |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Update memory configuration access |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | High | Confirm removal is acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organizational ID removed | High | Confirm removal is acceptable |
| Domain | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | High | Confirm removal is acceptable |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | High | Confirm removal is acceptable |
| Project | project | AVA | Not Available | Not Available | Removed | Project metadata removed | High | Confirm removal is acceptable |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | High | Confirm removal is acceptable |
| Team | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | High | Confirm removal is acceptable |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | High | Confirm removal is acceptable |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed | High | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified | default@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Ensure approval workflow is handled |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Track modification history |
| approvedAt | Approval timestamp | 2025-11-05T11:47:36.232449 | Low | Track approval history |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete handling |
| parentId | Parent workflow reference | -1 | Low | Handle workflow hierarchy |
| realmId | Realm identifier | 1 | Medium | Ensure realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align configuration structure |
| managerLlm | Not available | Empty object [{}] | Medium | Configure manager LLM settings |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update memory config access pattern |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 2
**AAVA 2.0 total agents:** 2
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| XML_Data_Pipeline_CVS | XML Data Pipeline CVS | Renamed | Naming convention updated (underscore to space) |
| GCP_PySpark_Unit_Tester | GCP PySpark Unit Tester | Renamed | Naming convention updated (underscore to space) |

---

## 6. Agent Configuration Differences

## Agent: XML_Data_Pipeline_CVS

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
| model | gemini-2.5-pro | model | High | Update model configuration |
| temperature | 0.20000000298023224 | 0.3 | Medium | Validate temperature impact on outputs |
| topP | 1.0 | 0.94 | Medium | Validate topP impact on outputs |
| maxToken | 64000 | 4000 | High | Validate token limit impact on complex tasks |
| maxIter | 0 | null | Low | No functional change |
| maxRpm | 0 | null | Low | No functional change |
| maxExecutionTime | 0 | 90 | Medium | Validate execution time limits |
| allowDelegation | false | true | Medium | Validate delegation behavior change |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: GCP_PySpark_Unit_Tester

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
| model | gemini-2.5-pro | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change needed |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change needed |
| maxToken | 64000 | 4000 | High | Validate token limit impact on complex tasks |
| maxIter | 0 | null | Low | No functional change |
| maxRpm | 0 | null | Low | No functional change |
| maxExecutionTime | 0 | 90 | Medium | Validate execution time limits |
| allowDelegation | false | true | Medium | Validate delegation behavior change |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

**CSV file successfully uploaded to:** Metadata/Metadata_Output/XML_Data_Engineering_CVS/XML_Data_Engineering_CVS_comparison.csv