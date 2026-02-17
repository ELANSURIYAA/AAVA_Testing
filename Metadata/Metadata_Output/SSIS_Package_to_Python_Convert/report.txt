# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

# 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 76%**
**Total Agents Compared: 5**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| SSIS Package to Python Converter | 82% | Medium | Model changed (claude-3.7sonnet to gpt-4.1), role/goal/backstory removed, expectedOutput format changed | Validate model behavior and confirm instruction removal |
| SSIS Package to Python Unit Tester | 88% | Medium | Model changed (gpt-4o to gpt-4.1), role/goal/backstory removed | Validate model behavior and confirm instruction removal |
| SSIS Package to Python Conversion Tester | 88% | Medium | Model changed (gpt-4o to gpt-4.1), role/goal/backstory removed | Validate model behavior and confirm instruction removal |
| SSIS Package  to Python Recon Tester | 88% | Medium | Model changed (gpt-4o to gpt-4.1), role/goal/backstory removed | Validate model behavior and confirm instruction removal |
| SSIS Package to Python Reviewer | 88% | Medium | Model changed (gpt-4o to gpt-4.1), role/goal/backstory removed | Validate model behavior and confirm instruction removal |

---

# 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** SSIS_Package_to_Python_Convert
**Workflow Name (AAVA 2.0):** SSIS Package to Python Convert

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 1448 | id | 4026 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to new workflow ID |
| Naming | name | SSIS_Package_to_Python_Convert | name | SSIS Package to Python Convert | Matched (Normalized) | Name normalized with spaces | Low | No change |
| Description | description | converter for ssis to python
 | description | converter for ssis to python
 | Matched | Description unchanged | Low | No change |
| Audit | createdAt | 2025-04-03T13:16:56.895+00:00 | createdAt | 2025-11-05T11:49:37.644676 | Modified | Creation timestamp differs | Low | Expected for different workflow instances |
| Agents List | pipeLineAgents | [5 agents] | workflowAgents | [5 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Enhanced configuration structure | Medium | Validate new configuration format |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Low | Configuration relocated |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | Medium | Confirm removal is acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organizational ID removed | Medium | Confirm removal is acceptable |
| Domain | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal is acceptable |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm removal is acceptable |
| Project | project | AVA | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal is acceptable |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm removal is acceptable |
| Team | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm removal is acceptable |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm removal is acceptable |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm removal is acceptable |

---

# 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Ensure approval workflow is handled |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T11:49:38.694136 | Low | Standard audit field |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Standard deletion handling |
| parentId | Parent workflow reference | -1 | Low | Workflow hierarchy support |
| realmId | Realm/tenant identifier | 1 | Medium | Ensure multi-tenancy is handled |

---

# 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align defaults and validate configuration |
| managerLlm | Not available | Empty object {} | Medium | Validate manager LLM configuration |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Low | Update configuration access pattern |

---

# 5. Agent Inventory Summary

## 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5
**AAVA 2.0 total agents:** 5
**Coverage:** Same agent count, all agents preserved

## 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| SSIS_Package_to_Python_Converter | SSIS Package to Python Converter | Renamed | Naming convention updated with spaces |
| SSIS_Package_to_Python_Unit_Tester | SSIS Package to Python Unit Tester | Renamed | Naming convention updated with spaces |
| SSIS_Package_to_Python_Conversion_Tester | SSIS Package to Python Conversion Tester | Renamed | Naming convention updated with spaces |
| SSIS_Package _to_Python_Recon_Tester | SSIS Package  to Python Recon Tester | Renamed | Naming convention updated with spaces |
| SSIS_Package_to_Python_Reviewer | SSIS Package to Python Reviewer | Renamed | Naming convention updated with spaces |

---

# 6. Agent Configuration Differences

## Agent: SSIS Package to Python Converter

---

## 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Present | Low | No change |

---

## 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | anthropic.claude-3-7-sonnet | gpt-4.1 | High | Validate model behavior change |
| model | claude-3.7sonnet | model | High | Validate model behavior change |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision |
| topP | 0.949999988079071 | 0.94 | Low | Normalized precision |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | null | Low | Normalized representation |
| maxRpm | 0 | null | Low | Normalized representation |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

---

## 6.1.3 Tools Comparison

Not Available

---

## 6.1.4 Knowledge Base Comparison

Not Available

---

## 6.1.5 Guardrails Comparison

Not Available

---

## Agent: SSIS Package to Python Unit Tester

---

## 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | Medium | Add missing field or confirm deprecation |

---

## 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model behavior change |
| model | gpt-4o | model | Medium | Validate model behavior change |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision |
| topP | 0.949999988079071 | 0.94 | Low | Normalized precision |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | Normalized representation |
| maxRpm | 0 | null | Low | Normalized representation |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

---

## 6.2.3 Tools Comparison

Not Available

---

## 6.2.4 Knowledge Base Comparison

Not Available

---

## 6.2.5 Guardrails Comparison

Not Available

---

## Agent: SSIS Package to Python Conversion Tester

---

## 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | Medium | Add missing field or confirm deprecation |

---

## 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model behavior change |
| model | gpt-4o | model | Medium | Validate model behavior change |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision |
| topP | 0.949999988079071 | 0.94 | Low | Normalized precision |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | Normalized representation |
| maxRpm | 0 | null | Low | Normalized representation |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

---

## 6.3.3 Tools Comparison

Not Available

---

## 6.3.4 Knowledge Base Comparison

Not Available

---

## 6.3.5 Guardrails Comparison

Not Available

---

## Agent: SSIS Package  to Python Recon Tester

---

## 6.4.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | Medium | Add missing field or confirm deprecation |

---

## 6.4.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model behavior change |
| model | gpt-4o | model | Medium | Validate model behavior change |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision |
| topP | 0.949999988079071 | 0.94 | Low | Normalized precision |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | Normalized representation |
| maxRpm | 0 | null | Low | Normalized representation |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

---

## 6.4.3 Tools Comparison

Not Available

---

## 6.4.4 Knowledge Base Comparison

Not Available

---

## 6.4.5 Guardrails Comparison

Not Available

---

## Agent: SSIS Package to Python Reviewer

---

## 6.5.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | Medium | Add missing field or confirm deprecation |

---

## 6.5.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model behavior change |
| model | gpt-4o | model | Medium | Validate model behavior change |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision |
| topP | 0.949999988079071 | 0.94 | Low | Normalized precision |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Low | Normalized representation |
| maxRpm | 0 | null | Low | Normalized representation |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout added |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

---

## 6.5.3 Tools Comparison

Not Available

---

## 6.5.4 Knowledge Base Comparison

Not Available

---

## 6.5.5 Guardrails Comparison

Not Available