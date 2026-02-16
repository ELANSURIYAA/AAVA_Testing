# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 84%
**Total Agents Compared:** 5

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DB2 to Oracle Converter | 88% | Medium | Model changed from gpt-4o to gpt-4.1; role/goal/backstory removed | Validate model compatibility and instruction completeness |
| DB2 to Oracle Unit Tester | 92% | Low | Minor model change; description matched after normalization | Validate model deployment compatibility |
| DB2 to Oracle Conversion Tester | 92% | Low | Minor model change; description matched after normalization | Validate model deployment compatibility |
| DB2 to Oracle Recon Tester | 92% | Low | Minor model change; description matched after normalization | Validate model deployment compatibility |
| DB2 to Oracle Reviewer | 76% | Medium | Model changed from claude-3.7sonnet to gpt-4.1; significant LLM config changes | Validate cross-platform model migration and performance impact |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DB2_to_Oracle_Conversion
**Workflow Name (AAVA 2.0):** DB2 to Oracle Conversion

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1518 | id | 1781 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to use new ID |
| Naming | name | DB2_to_Oracle_Conversion | name | DB2 to Oracle Conversion | Matched (Normalized) | Minor formatting difference in name | Low | No change needed |
| Description | description | Convert DB2 code to Oraclecode | description | Convert DB2 code to Oraclecode | Matched | Identical values | Low | No change needed |
| Audit | createdAt | 2025-05-08T17:35:11.743+00:00 | createdAt | 2025-11-05T10:34:51.420236 | Matched | Field present in both, different timestamps | Low | Expected for different workflow instances |
| Agents List | pipeLineAgents | [5 agents] | workflowAgents | [5 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm config} | Renamed + Modified | Field renamed and structure enhanced | Medium | Validate new configuration structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field removed in AAVA 2.0 | Low | Confirm memory config handling |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | Medium | Ensure governance tracking maintained |
| Domain Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Ensure governance tracking maintained |
| Project Metadata | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Ensure governance tracking maintained |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User tracking | muneeswara.pandian@ascendion.com | Medium | Ensure user attribution is captured |
| modifiedBy | Change tracking | muneeswara.pandian@ascendion.com | Medium | Implement modification tracking |
| approvedBy | Approval workflow | muneeswara.pandian@ascendion.com | Medium | Establish approval processes |
| modifiedAt | Timestamp tracking | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T10:34:52.533474 | Low | Standard audit field |
| status | Workflow state | APPROVED | Medium | Implement workflow lifecycle management |
| isDeleted | Soft delete flag | false | Low | Standard deletion handling |
| parentId | Hierarchy tracking | -1 | Low | Version control support |
| realmId | Multi-tenancy | 32 | Medium | Ensure tenant isolation |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm config | Medium | Align configuration management |
| managerLlm | Direct pipeline config | Nested in workflowConfigs | Medium | Update configuration access patterns |
| enableAgenticMemory | Pipeline level | Nested in workflowConfigs | Low | Update memory configuration handling |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5
**AAVA 2.0 total agents:** 5
**Coverage:** Same agent count, names normalized

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DB2_to_Oracle_Converter | DB2 to Oracle Converter | Renamed | Underscore to space normalization |
| DB2_to_Oracle_Unit_Tester | DB2 to Oracle Unit Tester | Renamed | Underscore to space normalization |
| DB2_to_Oracle_Conversion_Tester | DB2 to Oracle Conversion Tester | Renamed | Underscore to space normalization |
| DB2_to_Oracle_Recon_Tester | DB2 to Oracle Recon Tester | Renamed | Underscore to space normalization |
| DB2_to_Oracle_Reviewer | DB2 to Oracle Reviewer | Renamed | Underscore to space normalization |

---

## 6. Agent Configuration Differences

## Agent: DB2 to Oracle Converter

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
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model compatibility |
| model | gpt-4o | model | High | Verify model specification |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Low | Confirm iteration handling |
| maxRpm | 0 | Not Present | Low | Confirm rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: DB2 to Oracle Unit Tester

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
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model compatibility |
| model | gpt-4o | model | High | Verify model specification |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Low | Confirm iteration handling |
| maxRpm | 0 | Not Present | Low | Confirm rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: DB2 to Oracle Conversion Tester

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model compatibility |
| model | gpt-4o | model | High | Verify model specification |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Low | Confirm iteration handling |
| maxRpm | 0 | Not Present | Low | Confirm rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available

---

## Agent: DB2 to Oracle Recon Tester

### 6.4.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.4.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model compatibility |
| model | gpt-4o | model | High | Verify model specification |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Low | Confirm iteration handling |
| maxRpm | 0 | Not Present | Low | Confirm rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |

### 6.4.3 Tools Comparison
Not Available

### 6.4.4 Knowledge Base Comparison
Not Available

### 6.4.5 Guardrails Comparison
Not Available

---

## Agent: DB2 to Oracle Reviewer

### 6.5.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.5.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | anthropic.claude-3-7-sonnet | gpt-4.1 | High | Validate cross-platform model migration |
| model | claude-3.7sonnet | model | High | Verify model specification and performance impact |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Low | Confirm iteration handling |
| maxRpm | 0 | Not Present | Low | Confirm rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |

### 6.5.3 Tools Comparison
Not Available

### 6.5.4 Knowledge Base Comparison
Not Available

### 6.5.5 Guardrails Comparison
Not Available