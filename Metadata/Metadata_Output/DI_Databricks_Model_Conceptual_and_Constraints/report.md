# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 74%
**Total Agents Compared:** 2

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI Databricks Model Conceptual | 72% | Medium | model changed from claude-4-sonnet to gpt-4.1, role/goal/backstory removed, maxRpm/maxIter removed | Validate runtime behavior and confirm instruction field removal |
| DI Databricks Model Data Constraints | 76% | Medium | model changed from claude-4-sonnet to gpt-4.1, role/goal/backstory removed, maxRpm/maxIter removed | Validate runtime behavior and confirm instruction field removal |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_Databricks_Model_Conceptual_and_Constraints
**Workflow Name (AAVA 2.0):** DI Databricks Model Conceptual and Constraints

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 6254 | id | 2155 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | DI_Databricks_Model_Conceptual_and_Constraints | name | DI Databricks Model Conceptual and Constraints | Matched (Normalized) | Underscore formatting normalized to spaces | Low | No change |
| Description | description | This agent is for giving model conceptual and data constraints
 | description | This agent is for giving model conceptual and data constraints
 | Matched | Same content | Low | No change |
| Audit | createdAt | 2025-08-22T04:19:59.669+00:00 | createdAt | 2025-11-05T10:49:09.747505 | Modified | Different creation timestamps | Medium | Validate audit trail |
| Agents List | pipeLineAgents | [array of 2 agents] | workflowAgents | [array of 2 agents] | Renamed + Matched (Normalized) | Field renamed but content preserved | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {"managerLlm": [{}], "enableAgenticMemory": false} | Renamed + Modified | Field renamed and structure enhanced | Medium | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs structure | Medium | Verify memory configuration |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Confirm org tracking not needed |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | High | Confirm org tracking not needed |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | High | Confirm domain tracking not needed |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | High | Confirm domain tracking not needed |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | High | Confirm project tracking not needed |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | High | Confirm project tracking not needed |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | High | Confirm team tracking not needed |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | High | Confirm team tracking not needed |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | High | Confirm level tracking not needed |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | elansuriyaa.p@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T10:49:10.947359 | Medium | Ensure approval workflow is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure deletion tracking is implemented |
| parentId | Parent workflow reference | -1 | Low | Understand workflow hierarchy |
| realmId | Realm identifier | 32 | Medium | Ensure realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | callbacks: [] | managerLlm: [{}], enableAgenticMemory: false | Medium | Configure manager LLM settings |
| enableAgenticMemory | Top-level field: false | Nested in workflowConfigs: false | Medium | Update configuration structure |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 2
**AAVA 2.0 total agents:** 2
**Coverage:** Same agents maintained

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Databricks_Model_Conceptual | DI Databricks Model Conceptual | Renamed | Underscore formatting normalized to spaces |
| DI_Databricks_Model_Data_Constraints | DI Databricks Model Data Constraints | Renamed | Underscore formatting normalized to spaces |

---

## 6. Agent Configuration Differences

## Agent: DI Databricks Model Conceptual

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility and performance |
| model | anthropic.claude-4-sonnet | model | High | Validate model compatibility and performance |
| temperature | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Present | Medium | Add missing field or confirm removal |
| maxRpm | 50 | Not Present | Medium | Add missing field or confirm removal |
| maxExecutionTime | 300 | 90 | Medium | Validate timeout reduction impact |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Present | Low | Confirm empty tools list |
| userTools | DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z | Not Present | High | Restore required tools or confirm removal |
| toolReferences | Not Present | [] | Low | New field with empty array |

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI Databricks Model Data Constraints

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility and performance |
| model | anthropic.claude-4-sonnet | model | High | Validate model compatibility and performance |
| temperature | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Present | Medium | Add missing field or confirm removal |
| maxRpm | 50 | Not Present | Medium | Add missing field or confirm removal |
| maxExecutionTime | 300 | 90 | Medium | Validate timeout reduction impact |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Present | Low | Confirm empty tools list |
| userTools | DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z | Not Present | High | Restore required tools or confirm removal |
| toolReferences | Not Present | [] | Low | New field with empty array |

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available