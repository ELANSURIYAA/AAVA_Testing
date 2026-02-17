# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 76%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_Data_Technical_Specification_SN | 72% | Medium | role/goal/backstory removed, maxIter/maxRpm/maxExecutionTime modified, temperature matched | Validate instruction completeness, confirm runtime parameter changes |
| DI_Delta_Model_Changes_SN | 80% | Medium | role/goal/backstory removed, maxIter/maxRpm/maxExecutionTime modified, core description preserved | Validate instruction completeness, confirm runtime parameter changes |
| DI_Functional_Test_Cases_SN | 76% | Medium | role/goal/backstory removed, maxIter/maxRpm/maxExecutionTime modified, expectedOutput masked in both | Validate instruction completeness, confirm runtime parameter changes |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_DataSpecs_Modelupdates_SN
**Workflow Name (AAVA 2.0):** DI DataSpecs Modelupdates SN

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1594 | id | 2147 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to use new ID |
| Naming | name | DI_DataSpecs_Modelupdates_SN | name | DI DataSpecs Modelupdates SN | Matched (Case Normalization) | Underscores replaced with spaces | Low | Update naming conventions |
| Description | description | Includes tech spec creation, functional testing with SQL scripts, and DDL-based model updates. | description | Includes tech spec creation, functional testing with SQL scripts, and DDL-based model updates. | Matched | Identical description | Low | No change |
| Audit | createdAt | 2025-08-25T06:28:32.344+00:00 | createdAt | 2025-11-05T10:48:51.806066 | Matched | Field preserved with different timestamp | Low | No change |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm, enableAgenticMemory} | Renamed + Modified | Structure completely changed | High | Migrate callback logic to workflowConfigs |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs.enableAgenticMemory | Medium | Update memory configuration access |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | Medium | Implement alternative org tracking |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organizational ID removed | Medium | Implement alternative org ID tracking |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Implement alternative domain tracking |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Implement alternative domain ID tracking |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Implement alternative project tracking |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Medium | Implement alternative project ID tracking |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Medium | Implement alternative team tracking |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Medium | Implement alternative team ID tracking |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Implement alternative level tracking |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | kiran.krishnakumar@ascendion.com | Medium | Implement user tracking for governance |
| modifiedBy | User who last modified workflow | kiran.krishnakumar@ascendion.com | Medium | Implement modification tracking |
| approvedBy | User who approved workflow | kiran.krishnakumar@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Track modification history |
| approvedAt | Approval timestamp | 2025-11-05T10:48:53.023443 | Low | Track approval history |
| status | Workflow approval state | APPROVED | High | Implement workflow lifecycle management |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete functionality |
| parentId | Parent workflow reference | -1 | Low | Implement workflow hierarchy if needed |
| realmId | Realm/tenant identifier | 32 | Medium | Implement multi-tenant support |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|---------|-----------------|
| managerLlm | Direct object with model configs | Nested under workflowConfigs.managerLlm array | High | Restructure manager LLM configuration access |
| enableAgenticMemory | Direct boolean field | Nested under workflowConfigs.enableAgenticMemory | Medium | Update memory configuration access pattern |
| callbacks | Empty array | Not available | Medium | Migrate callback functionality to workflowConfigs |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents with structural changes

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Data_Technical_Specification_SN | DI Data Technical Specification SN | Renamed | Underscores replaced with spaces |
| DI_Delta_Model_Changes_SN | DI Delta Model Changes SN | Renamed | Underscores replaced with spaces |
| DI_Functional_Test_Cases_SN | DI Functional Test Cases SN | Renamed | Underscores replaced with spaces |

---

## 6. Agent Configuration Differences

## Agent: DI_Data_Technical_Specification_SN

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Value slightly adjusted |
| maxToken | 12000 | 12000 | Low | No change |
| maxIter | 25 | null | High | Validate runtime behavior change |
| maxRpm | 0 | null | Medium | Confirm rate limiting removal |
| maxExecutionTime | 300 | 90 | High | Validate timeout reduction impact |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | [DI_Github_File_Writer_Z] | [] | High | Validate tool removal impact |

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI_Delta_Model_Changes_SN

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Value slightly adjusted |
| maxToken | 12000 | 12000 | Low | No change |
| maxIter | 0 | null | Medium | Confirm iteration limit removal |
| maxRpm | 0 | null | Medium | Confirm rate limiting removal |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout addition |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | [] | [] | Low | No change |

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DI_Functional_Test_Cases_SN

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Value slightly adjusted |
| maxToken | 12000 | 12000 | Low | No change |
| maxIter | 0 | null | Medium | Confirm iteration limit removal |
| maxRpm | 0 | null | Medium | Confirm rate limiting removal |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout addition |

### 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | [] | [] | Low | No change |

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available