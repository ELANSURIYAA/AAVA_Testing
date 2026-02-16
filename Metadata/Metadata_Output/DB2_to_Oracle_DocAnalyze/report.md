# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

# 1. Metadata Comparison Score Summary

**Workflow Comparison Score**: 78%
**Total Agents Compared**: 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DB2 DOCUMENTATION | 85% | Low | Description matched, model changed from gpt-4o to gpt-4.1, role/goal/backstory removed | Validate model compatibility and confirm instruction field removal |
| DB2 to Oracle Analyzer | 82% | Low | Description matched, model changed from gpt-4o to gpt-4.1, role/goal/backstory removed | Validate model compatibility and confirm instruction field removal |
| DB2 to Oracle Plan | 67% | Medium | Description matched, model changed from claude-3.7sonnet to gpt-4.1, role/goal/backstory removed | Validate significant model change impact and confirm instruction field removal |

---

# 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0)**: DB2_to_Oracle_Doc&Analyze
**Workflow Name (AAVA 2.0)**: DB2 to Oracle Doc&Analyze

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 1517 | id | 2662 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to use new ID |
| Naming | name | DB2_to_Oracle_Doc&Analyze | name | DB2 to Oracle Doc&Analyze | Matched (Normalized) | Minor formatting difference in name | Low | No change needed |
| Description | description | Analyzing and Documenting the DB2 Code | description | Analyzing and Documenting the DB2 Code | Matched | Exact match | Low | No change needed |
| Audit | createdAt | 2025-11-11T10:54:31.865+00:00 | createdAt | 2025-11-05T11:11:31.632320 | Modified | Creation timestamp differs | Low | Update audit trail |
| Agents List | pipeLineAgents | Present | workflowAgents | Present | Renamed + Matched (Normalized) | Field renamed but content structure preserved | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | Present | Renamed + Modified | Field renamed and structure enhanced | Medium | Migrate to new config structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Verify memory config handling |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | High | Implement governance tracking |
| Domain Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | High | Implement governance tracking |
| Project Metadata | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | High | Implement governance tracking |

---

# 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User audit tracking | saiprakash.r@ascendion.com | Medium | Implement user tracking |
| modifiedBy | Modification audit | saiprakash.r@ascendion.com | Medium | Implement user tracking |
| approvedBy | Approval workflow | saiprakash.r@ascendion.com | Medium | Implement approval process |
| modifiedAt | Modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T11:11:32.687409 | Medium | Implement approval workflow |
| status | Workflow state | APPROVED | High | Implement lifecycle management |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete handling |
| parentId | Hierarchy tracking | -1 | Low | Standard hierarchy field |
| realmId | Multi-tenancy | 32 | Medium | Implement realm-based access |

---

# 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm | Medium | Implement new config structure |
| enableAgenticMemory | Top-level field | Nested in workflowConfigs | Medium | Update config access patterns |
| managerLlm | Not available | Present but empty | Low | Validate manager LLM configuration |

---

# 5. Agent Inventory Summary

## 5.1 Agent Count & Coverage
**AAVA 1.0 total agents**: 3
**AAVA 2.0 total agents**: 3
**Coverage**: Same agents with structural changes

## 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DB2_DOCUMENTATION | DB2 DOCUMENTATION | Matched (Normalized) | Underscore removed from name |
| DB2_to_Oracle_Analyzer | DB2 to Oracle Analyzer | Matched (Normalized) | Underscores replaced with spaces |
| DB2_to_Oracle_Plan | DB2 to Oracle Plan | Matched (Normalized) | Underscores replaced with spaces |

---

# 6. Agent Configuration Differences

## Agent: DB2 DOCUMENTATION

---

## 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

---

## 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model compatibility |
| model | gpt-4o | model | High | Verify model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision |
| topP | 0.949999988079071 | 0.94 | Low | Normalized precision |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Verify iteration handling |
| maxRpm | 0 | Not Available | Medium | Verify rate limiting |
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

## Agent: DB2 to Oracle Analyzer

---

## 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

---

## 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model compatibility |
| model | gpt-4o | model | High | Verify model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision |
| topP | 0.949999988079071 | 0.94 | Low | Normalized precision |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Verify iteration handling |
| maxRpm | 0 | Not Available | Medium | Verify rate limiting |
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

## Agent: DB2 to Oracle Plan

---

## 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

---

## 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | anthropic.claude-3-7-sonnet | gpt-4.1 | High | Validate significant model change |
| model | claude-3.7sonnet | model | High | Verify model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision |
| topP | 0.949999988079071 | 0.94 | Low | Normalized precision |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Verify iteration handling |
| maxRpm | 0 | Not Available | Medium | Verify rate limiting |
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