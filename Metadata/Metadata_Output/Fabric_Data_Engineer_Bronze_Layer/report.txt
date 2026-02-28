# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 86%
**Total Agents Compared:** 2

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| Fabric Bronze DE Pipeline | 84% | Medium | role/goal/backstory removed, expectedOutput modified, tools removed | Validate instruction field removal and tool migration |
| Fabric Pyspark Unit Test Case | 88% | Medium | role/goal/backstory removed, maxExecutionTime modified | Confirm instruction field deprecation |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** Fabric Data Engineer Bronze Layer
**Workflow Name (AAVA 2.0):** Fabric Data Engineer Bronze Layer

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 608 | id | 3015 | Renamed + Modified | Field renamed and ID value changed | Medium | Update ID references in dependent systems |
| Naming | name | " Fabric Data Engineer Bronze Layer" | name | " Fabric Data Engineer Bronze Layer" | Matched (Normalized) | Names match after normalization | Low | No change |
| Description | description | "DE Pipeline for Bronze Layer" | description | "DE Pipeline for Bronze Layer" | Matched | Values identical | Low | No change |
| Audit | createdAt | "2025-03-27T04:27:55.410+00:00" | createdAt | "2025-11-05T11:19:31.473692" | Matched | Field present in both, values differ by timestamp | Low | No change |
| Agents List | pipeLineAgents | [2 agents] | workflowAgents | [2 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update agent list references |
| Workflow Config | callbacks | [] | workflowConfigs | {"managerLlm": [{}], "enableAgenticMemory": false} | Renamed + Modified | Field renamed and structure changed | Medium | Align workflow configuration handling |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Update memory configuration access |
| Org Metadata | org | "Ascendion" | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm org metadata deprecation |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm org ID deprecation |
| Domain | domain | "Platform Engineering" | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm domain metadata deprecation |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm domain ID deprecation |
| Project | project | "AVA" | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm project metadata deprecation |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm project ID deprecation |
| Team | team | "Digital Ascender" | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm team metadata deprecation |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm team ID deprecation |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed from workflow level | Medium | Confirm level ID deprecation |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | "default@ascendion.com" | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | "default@ascendion.com" | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | "default@ascendion.com" | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | "2025-11-30T11:55:00.892060" | Medium | Ensure modification timestamp tracking |
| approvedAt | Approval timestamp | "2025-11-05T11:19:32.644495" | Medium | Ensure approval timestamp tracking |
| status | Workflow approval state | "APPROVED" | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete functionality |
| parentId | Parent workflow reference | -1 | Low | Validate parent-child workflow relationships |
| realmId | Realm identifier | 1 | Low | Validate realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align workflow configuration structure |
| managerLlm | Not available | Empty object {} in workflowConfigs | Medium | Validate manager LLM configuration |
| enableAgenticMemory | Top-level field (false) | Nested in workflowConfigs (false) | Medium | Update memory configuration access path |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 2
**AAVA 2.0 total agents:** 2
**Coverage:** Same agents maintained

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| Fabric Bronze DE Pipeline | Fabric Bronze DE Pipeline | Matched | Names identical |
| Fabric Pyspark Unit Test Case | Fabric Pyspark Unit Test Case | Matched | Names identical |

---

## 6. Agent Configuration Differences

## Agent: Fabric Bronze DE Pipeline

---

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | "gpt-4.1" | "gpt-4.1" | Low | No change |
| model | "gpt-4" | "model" | Medium | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 8000 | "8000" | Low | Type change from number to string |
| maxIter | 0 | null | Medium | Validate null vs zero behavior |
| maxRpm | 0 | null | Medium | Validate null vs zero behavior |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout changed from 0 to 90 |

---

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| userTools | 2 tools present (DI_Github_File_Writer_Z, DI_GitHub_To_Fabric_Notebook_Tool) | Not Available | High | Migrate tools to new structure or confirm removal |
| tools | Empty array | Not Available | Low | Confirm empty tools removal |
| toolReferences | Not Available | Empty array | Low | Validate new tool reference structure |

---

### 6.1.4 Knowledge Base Comparison

Not Available

---

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: Fabric Pyspark Unit Test Case

---

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | "gpt-4.1" | "gpt-4.1" | Low | No change |
| model | "gpt-4" | "model" | Medium | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 8000 | "8000" | Low | Type change from number to string |
| maxIter | 0 | null | Medium | Validate null vs zero behavior |
| maxRpm | 0 | null | Medium | Validate null vs zero behavior |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout changed from 0 to 90 |

---

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| userTools | Empty array | Not Available | Low | Confirm empty tools removal |
| tools | Empty array | Not Available | Low | Confirm empty tools removal |
| toolReferences | Not Available | Empty array | Low | Validate new tool reference structure |

---

### 6.2.4 Knowledge Base Comparison

Not Available

---

### 6.2.5 Guardrails Comparison

Not Available