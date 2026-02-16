# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Name (AAVA 1.0):** DI_Abinitio_MP_To_BigQuery
**Workflow Name (AAVA 2.0):** DI Abinitio MP To BigQuery

* **Workflow Comparison Score:** 85%
* **Total Agents Compared:** 1

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI AbInitio MP To BigQuery | 85% | Medium | role/goal/backstory removed, maxRpm/maxIter removed, maxExecutionTime reduced | Validate runtime behavior and confirm instruction field removal |

---

## 2. Workflow-Level Comparison

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 2490 | id | 8523 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_Abinitio_MP_To_BigQuery | name | DI Abinitio MP To BigQuery | Matched (Case Normalization) | Minor formatting differences in name | Low | No change required |
| Description | description | Converting MP to BigQuery | description | Converting MP to BigQuery | Matched | Description unchanged | Low | No change |
| Audit | createdAt | 2025-10-08T14:26:09.224+00:00 | createdAt | 2026-01-19T06:08:30.813120 | Modified | Creation timestamp updated | Low | Expected for new workflow version |
| Agents List | pipeLineAgents | [1 agent] | workflowAgents | [1 agent] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {topP: null, maxToken: null, managerLlm: [], temperature: null, enableAgenticMemory: false} | Renamed + Modified | Enhanced configuration structure | Medium | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Low | Verify memory settings in new structure |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Ensure org context is maintained elsewhere |
| Domain Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Ensure domain context is maintained elsewhere |
| Project Metadata | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Ensure project context is maintained elsewhere |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User audit trail | karthikeyan.iyappan@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | Modification audit | karthikeyan.iyappan@ascendion.com | Medium | Ensure modification tracking is implemented |
| modifiedAt | Modification timestamp | 2026-01-19T06:08:31.231877 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2026-01-19T06:08:31.232833 | Medium | Ensure workflow approval process is handled |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Standard deletion handling |
| parentId | Workflow versioning | 2356 | Medium | Ensure version tracking is implemented |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with null values | Medium | Configure workflow-level LLM settings |
| managerLlm | Not available | Empty array | Medium | Define manager LLM if needed |
| enableAgenticMemory | Root level: false | Nested in workflowConfigs: false | Low | Verify memory configuration location |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
- **AAVA 1.0 total agents:** 1
- **AAVA 2.0 total agents:** 1
- **Coverage:** Same agent count

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_AbInitio_MP_To_BigQuery | DI AbInitio MP To BigQuery | Matched (Case Normalization) | Minor formatting differences |

---

## 6. Agent Configuration Differences

## Agent: DI AbInitio MP To BigQuery

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.20000000298023224 | 0.2 | Low | Matched (Normalized) |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 32000 | 15000 | High | Validate token limit reduction |
| maxIter | 20 | Not Present | High | Add missing field or confirm removal |
| maxRpm | 50 | Not Present | High | Add missing field or confirm removal |
| maxExecutionTime | 180 | 90 | High | Validate execution time reduction |

---

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | FileWriterTool (ID: 4) | toolRef: [4] | Medium | Validate tool reference structure |
| userTools | [] | Not Available | Low | Confirm user tools handling |
| toolReferences | Not Available | [] | Low | New tool reference structure |

---

### 6.1.4 Knowledge Base Comparison

Not Available

---

### 6.1.5 Guardrails Comparison

Not Available