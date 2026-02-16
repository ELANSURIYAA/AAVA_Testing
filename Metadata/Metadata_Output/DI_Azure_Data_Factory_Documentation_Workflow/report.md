# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 85%
**Total Agents Compared:** 1

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI Azure Data Factory Documentation | 85% | Medium | role/goal/backstory removed, maxExecutionTime reduced, model configs matched | Validate instruction completeness and runtime behavior |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_Azure_Data_Factory_Documentation_Workflow
**Workflow Name (AAVA 2.0):** DI Azure Data Factory Documentation Workflow

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 6101 | id | 2113 | Renamed + Modified | Field renamed and value changed | High | Update references to new workflow ID |
| Naming | name | DI_Azure_Data_Factory_Documentation_Workflow | name | DI Azure Data Factory Documentation Workflow | Matched (Normalized) | Name normalized with spaces | Low | No action required |
| Description | description | Create a detailed and structured Technical Specification document... | description | Create a detailed and structured Technical Specification document... | Matched | Description identical | Low | No action required |
| Audit | createdAt | 2025-08-20T13:29:42.931+00:00 | createdAt | 2025-11-05T10:47:36.860992 | Matched | Field present in both versions | Medium | Validate timestamp differences |
| Agents List | pipeLineAgents | Array with 1 agent | workflowAgents | Array with 1 agent | Renamed + Matched (Normalized) | Field renamed, content preserved | Medium | Update agent array references |
| Workflow Config | callbacks | Empty array | workflowConfigs | Object with managerLlm and enableAgenticMemory | Renamed + Modified | Structure and content changed | High | Migrate callback logic to workflowConfigs |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs.enableAgenticMemory | Medium | Update memory configuration references |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm removal is acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm removal is acceptable |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal is acceptable |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm removal is acceptable |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal is acceptable |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm removal is acceptable |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm removal is acceptable |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm removal is acceptable |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | abhinav.mishra@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | abhinav.mishra@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | abhinav.mishra@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T10:47:37.944108 | Medium | Ensure approval workflow is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete functionality is implemented |
| parentId | Parent workflow reference | -1 | Low | Validate parent-child relationships |
| realmId | Realm identifier | 32 | Medium | Ensure realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | callbacks (empty array) | workflowConfigs object with managerLlm and enableAgenticMemory | High | Migrate callback logic to new structure |
| managerLlm | Not available | Empty object in workflowConfigs.managerLlm | Medium | Configure manager LLM settings |
| enableAgenticMemory | Root level boolean (false) | Nested in workflowConfigs.enableAgenticMemory (false) | Medium | Update memory configuration references |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 1
**AAVA 2.0 total agents:** 1
**Coverage:** Same agent count, name normalized

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Azure_Data_Factory_Documentation | DI Azure Data Factory Documentation | Renamed | Naming convention updated with spaces |

---

## 6. Agent Configuration Differences

## Agent: DI Azure Data Factory Documentation

---

## 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

## 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model configuration change |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 4500 | 4500 | Low | No change |
| maxIter | 25 | Not Available | Medium | Add missing field or confirm removal |
| maxRpm | 0 | Not Available | Medium | Add missing field or confirm removal |
| maxExecutionTime | 300 | 90 | High | Validate timeout reduction impact |

---

## 6.1.3 Tools Comparison

Not Available

---

## 6.1.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present with full configuration | Not Available | High | Migrate knowledge base configuration |
| chroma_end_point | http://chromadb.da.svc.cluster.local | Not Available | High | Migrate embedding endpoint configuration |
| index_collection | dI_Azure_Data_Factory_Documentation_kb | Not Available | High | Migrate collection configuration |
| embedding_model | text-embedding-ada-002 | Not Available | High | Migrate embedding model configuration |

---

## 6.1.5 Guardrails Comparison

Not Available