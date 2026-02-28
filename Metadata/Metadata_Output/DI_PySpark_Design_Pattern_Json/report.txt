# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

# 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 68%
**Total Agents Compared:** 1

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_PySpark_Design_Pattern_Json -> DI PySpark Consolidate Design Pattern | 68% | Medium | role/goal/backstory removed, description modified, model configs matched, tools matched | Validate instruction field removal impact, confirm new description alignment |

---

# 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_PySpark_Design_Pattern_Json
**Workflow Name (AAVA 2.0):** DI PySpark Consolidate Design Pattern

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 10871 | id | 2110 | Renamed + Modified | Field renamed and value changed | High | Update references to use new ID |
| Naming | name | DI_PySpark_Design_Pattern_Json | name | DI PySpark Consolidate Design Pattern | Modified | Workflow name changed | Medium | Update documentation and references |
| Description | description | DI_PySpark_Design_Pattern_Json | description | PySpark Design pattern consolidate | Modified | Description updated | Low | Review new description for accuracy |
| Audit | createdAt | 2025-12-16T14:10:05.445+00:00 | createdAt | 2025-11-05T10:47:30.435973 | Modified | Creation timestamp differs | Low | Expected for different workflow instances |
| Agents List | pipeLineAgents | [1 agent] | workflowAgents | [1 agent] | Renamed + Matched (Normalized) | Field renamed but same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {"managerLlm": [{}], "enableAgenticMemory": false} | Renamed + Modified | Field renamed and structure changed | Medium | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Verify memory settings in new structure |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm org metadata handling |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm org ID handling |
| Domain | domain | AAVA Domain | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm domain metadata handling |
| Domain ID | domainId | 697 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm domain ID handling |
| Project | project | AAVA Learning | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm project metadata handling |
| Project ID | projectId | 1735 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm project ID handling |
| Team | team | Data Crew | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm team metadata handling |
| Team ID | teamId | 1736 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm team ID handling |
| Level ID | levelId | 1736 | Not Available | Not Available | Removed | Level ID removed from workflow level | Medium | Verify level ID in agent details |

---

# 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | elansuriyaa.p@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Track modification history |
| approvedAt | Approval timestamp | 2025-11-05T10:47:31.497670 | Low | Track approval history |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete logic |
| parentId | Parent workflow reference | -1 | Low | Handle workflow hierarchy |
| realmId | Realm identifier | 32 | Medium | Ensure realm-based access control |

---

# 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Configure manager LLM settings |
| managerLlm | Not available | Empty object {} | Medium | Define manager LLM configuration |
| enableAgenticMemory | Top-level field (false) | Nested in workflowConfigs (false) | Medium | Update memory configuration access |

---

# 5. Agent Inventory Summary

## 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 1
**AAVA 2.0 total agents:** 1
**Coverage:** Same agent count, different agent

## 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_PySpark_Design_Pattern_Json | DI PySpark Consolidate Design Pattern | Modified | Different agent with different purpose |

---

# 6. Agent Configuration Differences

## Agent: DI_PySpark_Design_Pattern_Json -> DI PySpark Consolidate Design Pattern

---

## 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Medium | Validate new instruction field behavior |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

## 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model configuration change |
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Present | Medium | Add missing field or confirm deprecation |
| maxRpm | 20 | Not Present | Medium | Add missing field or confirm deprecation |
| maxExecutionTime | 180 | 90 | High | Validate timeout reduction impact |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

---

## 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No differences found |
| userTools | [] | Not Available | Medium | Confirm userTools removal |

---

## 6.1.4 Knowledge Base Comparison

Not Available

---

## 6.1.5 Guardrails Comparison

Not Available