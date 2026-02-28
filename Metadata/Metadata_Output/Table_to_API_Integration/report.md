# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

# 1. Metadata Comparison Score Summary

* Workflow Comparison Score: 85%
* Total Agents Compared: 1

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
| ---------- | ----------- | ---------- | ----------------------------------- | ------------------------- |
| Table to API Integration | 85% | Medium | role/goal/backstory removed, model changed from gpt-4o to model, maxExecutionTime changed from 0 to 90 | Validate new model behavior and confirm instruction field removal is acceptable |

---

# 2. Workflow-Level Comparison

Workflow Name (AAVA 1.0): Table to API Integration

Workflow Name (AAVA 2.0): Table to API Integration

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact (Low/Medium/High) | Action Required |
| -------- | -------------- | -------------- | -------------- | -------------- | ----------- | --------------------- | ---------------------------------- | --------------- |
| Identifier | pipelineId | 1055 | id | 3873 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | Table to API Integration | name | Table to API Integration | Matched | No change | Low | None |
| Description | description | This workflow is to automates data migration between PostgreSQL databases with different schemas, ensuring accurate transformation while maintaining data integrity. | description | This workflow is to automates data migration between PostgreSQL databases with different schemas, ensuring accurate transformation while maintaining data integrity. | Matched | No change | Low | None |
| Audit | createdAt | 2025-03-13T13:48:51.153+00:00 | createdAt | 2025-11-05T11:44:56.310887 | Matched | Timestamp format consistent | Low | None |
| Agents List | pipeLineAgents | Present | workflowAgents | Present | Renamed + Matched (Normalized) | Field renamed but structure preserved | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | Present | Renamed + Modified | Field renamed and structure enhanced | Medium | Review new workflow configuration structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Ensure memory settings are configured in workflowConfigs |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Confirm removal is acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | High | Confirm removal is acceptable |
| Domain | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | High | Confirm removal is acceptable |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | High | Confirm removal is acceptable |
| Project | project | AVA | Not Available | Not Available | Removed | Project metadata removed | High | Confirm removal is acceptable |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | High | Confirm removal is acceptable |
| Team | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | High | Confirm removal is acceptable |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | High | Confirm removal is acceptable |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed | High | Confirm removal is acceptable |

---

# 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
| --------- | ----------------------- | ---------------------- | ---------------- | ------------------------------------ |
| createdBy | User who created workflow | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-11-30T11:55:00.892060 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T11:44:57.362094 | Medium | Ensure approval workflow is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete functionality is implemented |
| parentId | Parent workflow reference | -1 | Medium | Ensure workflow hierarchy is handled |
| realmId | Realm identifier | 1 | Medium | Ensure realm-based access control |

---

# 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
| --------------- | ------------- | -------- | ------ | --------------- |
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align defaults and ensure proper configuration |
| managerLlm | Not available | Empty object in workflowConfigs | Medium | Configure manager LLM settings if needed |
| enableAgenticMemory | Top-level field (false) | Nested in workflowConfigs (false) | Medium | Update configuration access patterns |

---

# 5. Agent Inventory Summary

## 5.1 Agent Count & Coverage

AAVA 1.0 total agents: 1

AAVA 2.0 total agents: 1

Coverage: Same agent count, same agent maintained

---

## 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
| ------------------------------ | --------------------------------- | ---------- | ------------------------- |
| Table to API Integration | Table to API Integration | Matched | Same name maintained |

---

# 6. Agent Configuration Differences

## Agent: Table to API Integration

---

## 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
| ----- | ----------------- | ----------------- | ---------------- | --------------- |
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

## 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
| ----- | -------------- | -------------- | ---------------- | --------------- |
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate new model deployment behavior |
| model | gpt-4o | model | High | Validate model change impact on performance |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change |
| maxToken | 4000 | 4000 | Matched | No change |
| maxIter | 0 | Not Available | Medium | Confirm iteration limit removal is acceptable |
| maxRpm | 0 | Not Available | Medium | Confirm rate limit removal is acceptable |
| maxExecutionTime | 0 | 90 | Modified | Validate new execution timeout behavior |
| allowDelegation | true | true | Matched | No change |
| allowCodeExecution | false | false | Matched | No change |
| isSafeCodeExecution | true | true | Matched | No change |

---

## 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
| ---------------------- | -------------- | -------------- | ---------------- | --------------- |
| tools | [] | [] | Matched | No change |
| userTools | [] | Not Available | Medium | Confirm userTools removal is acceptable |

---

## 6.1.4 Knowledge Base Comparison

Not Available

---

## 6.1.5 Guardrails Comparison

Not Available