# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 84%
**Total Agents Compared:** 5

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| MarkLogic to MongDB Converter | 88% | Medium | Model deployment changed from gpt-4o to gpt-4.1; role/goal/backstory removed | Validate new model performance and confirm instruction removal acceptable |
| MarkLogic to MongDB Unit Testing | 88% | Medium | Model deployment changed from gpt-4o to gpt-4.1; role/goal/backstory removed | Validate new model performance and confirm instruction removal acceptable |
| MarkLogic to MongDB Conversion Tester | 88% | Medium | Model deployment changed from gpt-4o to gpt-4.1; role/goal/backstory removed | Validate new model performance and confirm instruction removal acceptable |
| MarkLogic to MongDB Recon Tester | 88% | Medium | Model deployment changed from gpt-4o to gpt-4.1; role/goal/backstory removed | Validate new model performance and confirm instruction removal acceptable |
| MarkLogic to MongDB Reviewer | 88% | Medium | Model deployment changed from gpt-4o to gpt-4.1; role/goal/backstory removed | Validate new model performance and confirm instruction removal acceptable |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_MarkLogic_to_MongoDB_Conversion
**Workflow Name (AAVA 2.0):** DI MarkLogic to MongoDB Conversion

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1073 | id | 2595 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | DI_MarkLogic_to_MongoDB_Conversion | name | DI MarkLogic to MongoDB Conversion | Matched (Normalized) | Minor formatting difference in underscores | Low | No change |
| Description | description | Convert MarkLogic database structures, queries, and data models into an equivalent MongoDB representation while maintaining data integrity and performance. | description | Convert MarkLogic database structures, queries, and data models into an equivalent MongoDB representation while maintaining data integrity and performance. | Matched | Identical description | Low | No change |
| Audit | createdAt | 2025-05-12T06:03:30.361+00:00 | createdAt | 2025-11-05T11:07:19.340724 | Matched | Different timestamp values | Low | No change |
| Agents List | pipeLineAgents | Present (5 agents) | workflowAgents | Present (5 agents) | Renamed + Matched (Normalized) | Field renamed but same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | Present with managerLlm config | Renamed + Modified | Enhanced configuration structure | Medium | Align configuration handling |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Confirm removal is acceptable |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Add missing organizational context |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | High | Add missing organizational context |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | High | Add missing domain context |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | High | Add missing domain context |
| Project | project | Conversions | Not Available | Not Available | Removed | Project metadata removed | High | Add missing project context |
| Project ID | projectId | 149 | Not Available | Not Available | Removed | Project ID removed | High | Add missing project context |
| Team | team | DataEngineer | Not Available | Not Available | Removed | Team metadata removed | High | Add missing team context |
| Team ID | teamId | 150 | Not Available | Not Available | Removed | Team ID removed | High | Add missing team context |
| Level ID | levelId | 150 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T11:07:20.412583 | Medium | Ensure approval workflow is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure deletion handling is implemented |
| parentId | Parent workflow reference | -1 | Low | Validate parent-child relationships |
| realmId | Realm identifier | 1 | Medium | Ensure realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm array | Medium | Align configuration structure |
| managerLlm | Direct object | Array with id field | Medium | Update configuration parsing |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update configuration access |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5
**AAVA 2.0 total agents:** 5
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| MarkLogic_to_MongDB_Converter | MarkLogic to MongDB Converter | Renamed | Underscore to space conversion |
| MarkLogic_to_MongDB_Unit_Testing | MarkLogic to MongDB Unit Testing | Renamed | Underscore to space conversion |
| MarkLogic_to_MongDB_Conversion_Tester | MarkLogic to MongDB Conversion Tester | Renamed | Underscore to space conversion |
| MarkLogic_to_MongDB_Recon_Tester | MarkLogic to MongDB Recon Tester | Renamed | Underscore to space conversion |
| MarkLogic_to_MongDB_Reviewer | MarkLogic to MongDB Reviewer | Renamed | Underscore to space conversion |

---

## 6. Agent Configuration Differences

## Agent: MarkLogic to MongDB Converter

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | Medium | Add missing field or confirm deprecation |

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate new model performance |
| model | gpt-4o | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Minor precision difference |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |

### 6.1.3 Tools Comparison

Not Available

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: MarkLogic to MongDB Unit Testing

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | Medium | Add missing field or confirm deprecation |

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate new model performance |
| model | gpt-4o | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Minor precision difference |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |

### 6.2.3 Tools Comparison

Not Available

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: MarkLogic to MongDB Conversion Tester

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | Medium | Add missing field or confirm deprecation |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate new model performance |
| model | gpt-4o | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Minor precision difference |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |

### 6.3.3 Tools Comparison

Not Available

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available

---

## Agent: MarkLogic to MongDB Recon Tester

### 6.4.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | Medium | Add missing field or confirm deprecation |

### 6.4.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate new model performance |
| model | gpt-4o | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Minor precision difference |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |

### 6.4.3 Tools Comparison

Not Available

### 6.4.4 Knowledge Base Comparison

Not Available

### 6.4.5 Guardrails Comparison

Not Available

---

## Agent: MarkLogic to MongDB Reviewer

### 6.5.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | Medium | Add missing field or confirm deprecation |

### 6.5.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate new model performance |
| model | gpt-4o | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Minor precision difference |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |

### 6.5.3 Tools Comparison

Not Available

### 6.5.4 Knowledge Base Comparison

Not Available

### 6.5.5 Guardrails Comparison

Not Available