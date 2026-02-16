# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 78%**
**Total Agents Compared: 2**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DQ Recommender | 82% | Medium | role/goal/backstory removed, model changed from gpt-4o to gpt-4.1, maxExecutionTime added | Validate new model behavior and confirm instruction field removal |
| DQ Generate GEScripts | 74% | Medium | role/goal/backstory removed, model changed from gpt-4o to gpt-4.1, maxExecutionTime added | Validate new model behavior and confirm instruction field removal |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DataQuality_GE_Script_Recommender
**Workflow Name (AAVA 2.0):** DataQuality GE Script Recommender

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 564 | id | 3633 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to new workflow ID |
| Naming | name | DataQuality_GE_Script_Recommender | name | DataQuality GE Script Recommender | Matched (Normalized) | Minor formatting differences in name | Low | No change |
| Description | description | This workflow automates... | description | This workflow automates... | Matched | Same description content | Low | No change |
| Audit | createdAt | 2025-03-31T11:46:59.050+00:00 | createdAt | 2025-11-05T11:37:44.209214 | Modified | Different creation timestamps | Low | Expected for different workflow instances |
| Agents List | pipeLineAgents | [2 agents] | workflowAgents | [2 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [...], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure enhanced | Medium | Align configuration handling |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs structure | Low | Update configuration access |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm org context handling |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm org context handling |
| Domain | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm domain context handling |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm domain context handling |
| Project | project | AVA | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm project context handling |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm project context handling |
| Team | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm team context handling |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm team context handling |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed from workflow level | Low | Moved to agent level |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T11:37:45.270014 | Low | Standard audit field |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Standard deletion handling |
| parentId | Parent workflow reference | -1 | Low | Workflow versioning support |
| realmId | Realm/tenant identifier | 1 | Medium | Ensure multi-tenancy is handled |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| managerLlm | Direct object at pipeline level | Nested in workflowConfigs array | Medium | Update configuration access patterns |
| enableAgenticMemory | Direct boolean field | Nested in workflowConfigs | Low | Update configuration access |
| callbacks | Empty array | Not present | Low | Confirm callback handling |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 2
**AAVA 2.0 total agents:** 2
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DQ_Recommender | DQ Recommender | Renamed | Underscore removed from name |
| DQ_Generate_GEScripts | DQ Generate GEScripts | Renamed | Underscores removed from name |

---

## 6. Agent Configuration Differences

## Agent: DQ Recommender

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
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility and performance |
| model | gpt-4o | model | High | Validate model name mapping |
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | Null vs zero handling |
| maxRpm | 0 | null | Low | Null vs zero handling |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout behavior change |

### 6.1.3 Tools Comparison

**Not Available** - No tools configured in either version

### 6.1.4 Knowledge Base Comparison

**Not Available** - No knowledge base configured in either version

### 6.1.5 Guardrails Comparison

**Not Available** - No guardrails configured in either version

---

## Agent: DQ Generate GEScripts

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
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility and performance |
| model | gpt-4o | model | High | Validate model name mapping |
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | Null vs zero handling |
| maxRpm | 0 | null | Low | Null vs zero handling |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout behavior change |

### 6.2.3 Tools Comparison

**Not Available** - No tools configured in either version

### 6.2.4 Knowledge Base Comparison

**Not Available** - No knowledge base configured in either version

### 6.2.5 Guardrails Comparison

**Not Available** - No guardrails configured in either version