# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 82%
**Total Agents Compared:** 2

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI SSRS SrcTgt SP Extractor | 84% | Medium | role/goal/backstory removed, description matched, LLM configs matched | Validate instruction field removal impact |
| DI SSRS SQLEDW Mapping | 80% | Medium | role/goal/backstory removed, description matched, LLM configs matched | Validate instruction field removal impact |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_SSRS_SQLServerEDWAnalyzer
**Workflow Name (AAVA 2.0):** DI SSRS SQLServerEDWAnalyzer

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 3319 | id | 1971 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_SSRS_SQLServerEDWAnalyzer | name | DI SSRS SQLServerEDWAnalyzer | Matched (Normalized) | Minor spacing differences | Low | No change |
| Description | description | Analyze SSRS RDL files to extract and document all referenced database objects | description | Analyze SSRS RDL files to extract and document all referenced database objects | Matched | Identical values | Low | No change |
| Audit | createdAt | 2025-06-22T18:34:35.800+00:00 | createdAt | 2025-11-05T10:42:12.097614 | Matched | Field exists in both but different timestamps | Low | No change |
| Agents List | pipeLineAgents | [2 agents] | workflowAgents | [2 agents] | Renamed + Matched (Normalized) | Field renamed but same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {"managerLlm": [{}], "enableAgenticMemory": false} | Renamed + Modified | Field renamed and structure changed | Medium | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Low | Verify memory settings in new structure |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm org tracking not needed |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm org tracking not needed |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm domain tracking not needed |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm domain tracking not needed |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm project tracking not needed |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm project tracking not needed |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm team tracking not needed |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm team tracking not needed |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm level tracking not needed |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | muneeswara.pandian@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | muneeswara.pandian@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | muneeswara.pandian@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T10:42:13.288597 | Medium | Ensure approval process is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Standard deletion tracking |
| parentId | Parent workflow reference | -1 | Low | Workflow hierarchy tracking |
| realmId | Realm/tenant identifier | 32 | Medium | Ensure multi-tenancy is handled |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Configure workflow-level settings |
| managerLlm | Not available | Empty object {} | Medium | Define manager LLM configuration |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Low | Update configuration structure |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 2
**AAVA 2.0 total agents:** 2
**Coverage:** Same agent count

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_SSRS_SrcTgt_SP_Extractor | DI SSRS SrcTgt SP Extractor | Renamed | Underscore to space conversion |
| DI_SSRS_SQLEDW_Mapping | DI SSRS SQLEDW Mapping | Renamed | Underscore to space conversion |

---

## 6. Agent Configuration Differences

## Agent: DI SSRS SrcTgt SP Extractor

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
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision difference only |
| topP | 0.949999988079071 | 0.94 | Low | Precision difference only |
| maxToken | 15000 | 15000 | Low | No change |
| maxIter | 20 | Not Available | Medium | Validate iteration limit removal |
| maxRpm | 0 | Not Available | Low | Rate limiting not configured |
| maxExecutionTime | 120 | 90 | Medium | Execution time reduced |

### 6.1.3 Tools Comparison

Not Available

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI SSRS SQLEDW Mapping

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
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision difference only |
| topP | 0.949999988079071 | 0.94 | Low | Precision difference only |
| maxToken | 15000 | 15000 | Low | No change |
| maxIter | 20 | Not Available | Medium | Validate iteration limit removal |
| maxRpm | 0 | Not Available | Low | Rate limiting not configured |
| maxExecutionTime | 120 | 90 | Medium | Execution time reduced |

### 6.2.3 Tools Comparison

Not Available

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available