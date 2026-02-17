# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 85%**
**Total Agents Compared: 2**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI BigQuery Model Conceptual | 82% | Medium | Model changed from gemini-2.5-pro to gpt-4.1, role/goal/backstory removed, expectedOutput renamed | Validate model behavior and confirm instruction field removal |
| DI BigQuery Model Data Contraints | 88% | Medium | Model changed from gemini-2.5-pro to gpt-4.1, role/goal/backstory removed | Validate model behavior and confirm instruction field removal |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_BigQuery_Model_Conceptual_and_Constraints
**Workflow Name (AAVA 2.0):** DI BigQuery Model Conceptual and Constraints

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 7945 | id | 2517 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_BigQuery_Model_Conceptual_and_Constraints | name | DI BigQuery Model Conceptual and Constraints | Matched (Normalized) | Minor formatting differences in name | Low | No change |
| Description | description | This agent is for giving model conceptual and data constraints
 | description | This agent is for giving model conceptual and data constraints
 | Matched | Identical values | Low | No change |
| Audit | createdAt | 2025-10-31T04:31:50.476+00:00 | createdAt | 2025-11-05T11:02:35.669103 | Modified | Different creation timestamps | Low | Expected for different workflow instances |
| Agents List | pipeLineAgents | [Array of 2 agents] | workflowAgents | [Array of 2 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure enhanced | Medium | Align workflow configuration handling |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Low | Field relocated, no functional impact |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm org metadata handling approach |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm org metadata handling approach |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm domain metadata handling approach |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm domain metadata handling approach |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm project metadata handling approach |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm project metadata handling approach |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm team metadata handling approach |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm team metadata handling approach |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm level metadata handling approach |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | balamurugan.r@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | balamurugan.r@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | balamurugan.r@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T11:02:36.731550 | Low | Standard audit field |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Standard deletion handling |
| parentId | Parent workflow reference | -1 | Low | Workflow hierarchy support |
| realmId | Realm identifier | 32 | Medium | Ensure realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align workflow configuration structure |
| managerLlm | Not available | Empty object in workflowConfigs | Medium | Configure manager LLM settings if needed |
| enableAgenticMemory | Top-level field (false) | Moved to workflowConfigs (false) | Low | Update configuration access path |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 2
**AAVA 2.0 total agents:** 2
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_BigQuery_Model_Conceptual | DI BigQuery Model Conceptual | Renamed | Underscore to space conversion |
| DI_BigQuery_Model_Data_Contraints | DI BigQuery Model Data Contraints | Renamed | Underscore to space conversion |

---

## 6. Agent Configuration Differences

## Agent: DI BigQuery Model Conceptual

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Present | Low | No change |

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model behavior compatibility |
| model | gemini-2.5-pro | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | null | Low | Both indicate no limit |
| maxRpm | 0 | null | Low | Both indicate no limit |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | 2 tools (DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z) | [] | High | Validate tool migration to toolReferences |
| toolReferences | Not Available | [] | Medium | Confirm tool configuration approach |

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI BigQuery Model Data Contraints

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Present | Low | No change |

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model behavior compatibility |
| model | gemini-2.5-pro | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | null | Low | Both indicate no limit |
| maxRpm | 0 | null | Low | Both indicate no limit |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | 2 tools (DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z) | [] | High | Validate tool migration to toolReferences |
| toolReferences | Not Available | [] | Medium | Confirm tool configuration approach |

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available