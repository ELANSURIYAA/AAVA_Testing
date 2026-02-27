# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 68%
**Total Agents Compared:** 1

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI AbInitio DML To PySpark | 68% | Medium | Model changed from claude-4-sonnet to generic model, temperature modified from 0.2 to 0.3, maxToken reduced from 64000 to 8000, workflow name normalized | Validate model performance impact, confirm token limit sufficiency, test temperature behavior |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_AbInitio_DML_To_PySpark_EMR_Glue
**Workflow Name (AAVA 2.0):** DI AbInitio DML To PySpark

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 8578 | id | 1858 | Renamed + Modified | Field renamed and ID value changed | High | Update references to new workflow ID |
| Naming | name | DI_AbInitio_DML_To_PySpark_EMR_Glue | name | DI AbInitio DML To PySpark | Matched (Normalized) | Name normalized with spacing and removed suffix | Medium | Validate naming convention alignment |
| Description | description | This workflow is to convert Ab Initio .dml record definitions into PySpark StructType schemas. | description | This workflow is to convert Ab Initio .dml record definitions into PySpark StructType schemas. | Matched (Normalized) | Description matches after normalization | Low | No change |
| Audit | createdAt | 2025-11-18T11:09:02.788+00:00 | createdAt | 2025-11-05T10:37:50.149714 | Matched | Field present in both versions | Low | No change |
| Agents List | pipeLineAgents | [1 agent] | workflowAgents | [1 agent] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update agent references |
| Workflow Config | callbacks | [] | workflowConfigs | {"managerLlm": [{}], "enableAgenticMemory": false} | Renamed + Modified | Field renamed and structure enhanced | Medium | Align configuration handling |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs structure | Medium | Confirm memory config location |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm org metadata deprecation |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm org ID deprecation |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm domain metadata deprecation |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm domain ID deprecation |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm project metadata deprecation |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm project ID deprecation |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm team metadata deprecation |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm team ID deprecation |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm level ID deprecation |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Ensure approval workflow is handled |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T10:37:51.273822 | Medium | Ensure approval workflow is handled |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete handling is implemented |
| parentId | Parent workflow reference | -1 | Low | Understand workflow hierarchy |
| realmId | Realm identifier | 1 | Low | Understand realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | callbacks: [] | managerLlm: [{}], enableAgenticMemory: false | Medium | Align configuration structure |
| managerLlm | Not available | Present (empty object) | Medium | Understand manager LLM configuration |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 1
**AAVA 2.0 total agents:** 1
**Coverage:** Same agent count, agent renamed

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_AbInitio_DML_To_PySpark_EMR_Glue | DI AbInitio DML To PySpark | Renamed | Naming convention updated, EMR_Glue suffix removed |

---

## 6. Agent Configuration Differences

## Agent: DI AbInitio DML To PySpark

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model performance equivalence |
| model | anthropic.claude-4-sonnet | model | High | Confirm model specification accuracy |
| temperature | 0.20000000298023224 | 0.3 | Medium | Test temperature behavior impact |
| topP | 1.0 | 0.94 | Medium | Validate topP parameter impact |
| maxToken | 64000 | 8000 | High | Confirm token limit sufficiency for use case |
| maxIter | 0 | null | Low | Confirm iteration limit handling |
| maxRpm | 0 | null | Low | Confirm rate limit handling |
| maxExecutionTime | 0 | 90 | Medium | Validate execution timeout configuration |
| allowDelegation | false | true | Medium | Confirm delegation behavior change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

---

### 6.1.3 Tools Comparison

**Not Available** - No tools configured in either version

---

### 6.1.4 Knowledge Base Comparison

**Not Available** - No knowledge base configuration in either version

---

### 6.1.5 Guardrails Comparison

**Not Available** - No guardrails configuration in either version