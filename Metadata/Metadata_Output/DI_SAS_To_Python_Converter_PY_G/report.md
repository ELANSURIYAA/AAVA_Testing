# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

# 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 78%
**Total Agents Compared:** 2

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI SAS To Python Converter PY G | 72% | Medium | Model changed from gemini to gpt-4.1, role/goal/backstory removed, topP modified | Validate model compatibility and instruction field removal |
| DI SAS To Python Reviewer | 84% | Medium | Model deployment name matched, description preserved, maxExecutionTime added | Validate new execution timeout behavior |

---

# 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_SAS_To_Python_Converter_PY_G
**Workflow Name (AAVA 2.0):** DI SAS To Python Converter PY G

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 2102 | id | 2599 | Renamed + Modified | Workflow ID changed from 2102 to 2599 | High | Update references to new workflow ID |
| Naming | name | DI_SAS_To_Python_Converter_PY_G | name | DI SAS To Python Converter PY G | Matched (Case Normalization) | Underscores replaced with spaces | Low | Update naming conventions |
| Description | description | SAS to python Convertion | description | SAS to python Convertion | Matched | No change in description | Low | No change |
| Audit | createdAt | 2025-05-21T10:34:56.079+00:00 | createdAt | 2025-11-05T11:07:28.193371 | Modified | Creation timestamp updated | Medium | Verify audit trail continuity |
| Agents List | pipeLineAgents | 2 agents | workflowAgents | 2 agents | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | Present | Renamed + Modified | Empty callbacks replaced with structured configs | Medium | Align workflow configuration |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Memory config moved to workflowConfigs | Medium | Verify memory handling |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm removal acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm removal acceptable |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal acceptable |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm removal acceptable |
| Project | project | Conversions | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal acceptable |
| Project ID | projectId | 149 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm removal acceptable |
| Team | team | DataEngineer | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm removal acceptable |
| Team ID | teamId | 150 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm removal acceptable |
| Level ID | levelId | 150 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm removal acceptable |

---

# 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Ensure user attribution is handled |
| modifiedBy | User who last modified | default@ascendion.com | Medium | Ensure modification tracking |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Ensure approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure audit trail continuity |
| approvedAt | Approval timestamp | 2025-11-05T11:07:29.255640 | Medium | Ensure approval tracking |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure deletion handling |
| parentId | Parent workflow reference | -1 | Low | Validate workflow hierarchy |
| realmId | Realm identifier | 1 | Low | Validate realm assignment |

---

# 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|---------|-----------------|
| workflowConfigs | Not available | Present with managerLlm array | Medium | Align configuration structure |
| managerLlm | Single object at pipeline level | Array within workflowConfigs | Medium | Update configuration access patterns |
| enableAgenticMemory | Pipeline level boolean | Within workflowConfigs | Medium | Update memory configuration access |

---

# 5. Agent Inventory Summary

## 5.1 Agent Count & Coverage

**AAVA 1.0 total agents:** 2
**AAVA 2.0 total agents:** 2
**Coverage:** Same agent count, renamed agents

## 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_SAS_To_Python_Converter_PY_G | DI SAS To Python Converter PY G | Renamed | Underscores replaced with spaces |
| DI_SAS_To_Python_Reviewer | DI SAS To Python Reviewer | Renamed | Underscores replaced with spaces |

---

# 6. Agent Configuration Differences

## Agent: DI SAS To Python Converter PY G

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
| modelDeploymentName | gemini-2.0-flash-001 | gpt-4.1 | High | Validate model compatibility |
| model | gemini-2.0-flash-001 | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | No functional change |
| topP | 0.949999988079071 | 0.94 | Low | Minor precision difference |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 25 | Not Present | Medium | Validate iteration limit handling |
| maxRpm | 0 | Not Present | Low | Rate limiting not configured |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout behavior |

---

## 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | FileWriterTool (ID: 4) | toolRef: [4] | Medium | Validate tool reference structure |
| userTools | [] | Not Present | Low | No user tools configured |

---

## 6.1.4 Knowledge Base Comparison

Not Available

---

## 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI SAS To Python Reviewer

---

## 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

## 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | No functional change |
| topP | 0.949999988079071 | 0.94 | Low | Minor precision difference |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Present | Medium | Validate iteration limit handling |
| maxRpm | 0 | Not Present | Low | Rate limiting not configured |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout behavior |

---

## 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No tools configured |
| userTools | [] | Not Present | Low | No user tools configured |

---

## 6.2.4 Knowledge Base Comparison

Not Available

---

## 6.2.5 Guardrails Comparison

Not Available