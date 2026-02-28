# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 83%**
**Total Agents Compared: 2**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| Fabric Gold Aggregated DE Pipeline | 78% | Medium | role/goal/backstory removed, model config matched, description matched | Validate agent instruction completeness |
| Fabric Pyspark Unit Test Case | 88% | Medium | role/goal/backstory removed, model config matched, description matched | Validate agent instruction completeness |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** Fabric Aggregated Data Engineer Gold Layer
**Workflow Name (AAVA 2.0):** Fabric Aggregated Data Engineer Gold Layer

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 828 | id | 2718 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new workflow ID |
| Naming | name | Fabric Aggregated Data Engineer Gold Layer | name | Fabric Aggregated Data Engineer Gold Layer | Matched | No change | Low | None |
| Description | description | Fabric Fact Data Engineer Gold Layer | description | Fabric Fact Data Engineer Gold Layer | Matched | No change | Low | None |
| Audit | createdAt | 2025-03-27T04:50:56.999+00:00 | createdAt | 2025-11-05T11:12:53.439187 | Matched | Field exists in both, values differ due to different creation times | Low | None |
| Agents List | pipeLineAgents | Array[2] | workflowAgents | Array[2] | Renamed + Matched (Normalized) | Field renamed but same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure enhanced | Medium | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Low | Verify memory settings in workflowConfigs |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm org metadata not needed |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm org ID not needed |
| Domain | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm domain metadata not needed |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm domain ID not needed |
| Project | project | AVA | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm project metadata not needed |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm project ID not needed |
| Team | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm team metadata not needed |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm team ID not needed |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm level ID not needed |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-11-30T11:55:00.892060 | Low | Automatic timestamp handling |
| approvedAt | Approval timestamp | 2025-11-05T11:12:54.481350 | Low | Automatic timestamp handling |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Implement soft delete logic |
| parentId | Parent workflow reference | -1 | Low | Handle workflow hierarchy |
| realmId | Realm identifier | 1 | Medium | Configure realm settings |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | callbacks: [] | managerLlm: [{}], enableAgenticMemory: false | Medium | Configure manager LLM settings |
| enableAgenticMemory | Top-level: false | Nested in workflowConfigs: false | Low | Update configuration structure |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 2
**AAVA 2.0 total agents:** 2
**Coverage:** Same agents maintained

### 5.2 Agent Name Mapping
| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| Fabric Gold Aggregated DE Pipeline | Fabric Gold Aggregated DE Pipeline | Matched | Same name |
| Fabric Pyspark Unit Test Case | Fabric Pyspark Unit Test Case | Matched | Same name |

---

## 6. Agent Configuration Differences

## Agent: Fabric Gold Aggregated DE Pipeline

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | None |
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | None |
| maxIter | 0 | null | Low | Handle null vs 0 difference |
| maxRpm | 0 | null | Low | Handle null vs 0 difference |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout change |

### 6.1.3 Tools Comparison
**Not Available**

### 6.1.4 Knowledge Base Comparison
**Not Available**

### 6.1.5 Guardrails Comparison
**Not Available**

---

## Agent: Fabric Pyspark Unit Test Case

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | None |
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | None |
| maxIter | 0 | null | Low | Handle null vs 0 difference |
| maxRpm | 0 | null | Low | Handle null vs 0 difference |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout change |

### 6.2.3 Tools Comparison
**Not Available**

### 6.2.4 Knowledge Base Comparison
**Not Available**

### 6.2.5 Guardrails Comparison
**Not Available**