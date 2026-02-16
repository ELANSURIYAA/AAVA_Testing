# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 84%
**Total Agents Compared:** 5

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DB2 TO SYNAPSE CONVERTER | 88% | Medium | Model changed from claude-3.7sonnet to gpt-4.1; role/goal/backstory removed; maxExecutionTime added | Validate model compatibility and confirm instruction field removal |
| DB2 to SYNAPSE Unit Testing | 92% | Low | Minor model changes and execution time limits added | Minimal validation required |
| DB2 To SYNAPSE Conversion Tester | 90% | Low | Model standardization and execution time configuration | Standard migration validation |
| DB2 To SYNAPSE Reconciliation | 89% | Medium | Model changes and execution time standardization | Validate runtime behavior |
| DB2 TO SYNAPSE REVIEWER | 91% | Low | Model changes with consistent execution parameters | Standard validation |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DB2_To_Synapse_Convert
**Workflow Name (AAVA 2.0):** DB2 To Synapse Convert

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1079 | id | 3785 | Renamed + Modified | Field renamed and ID value changed | Medium | Update ID references in dependent systems |
| Naming | name | DB2_To_Synapse_Convert | name | DB2 To Synapse Convert | Matched (Normalized) | Minor formatting difference in spacing | Low | No change required |
| Description | description | DB2_To_Synapse_Convert | description | DB2_To_Synapse_Convert | Matched | Exact match | Low | No change required |
| Audit | createdAt | 2025-03-14T09:20:49.367+00:00 | createdAt | 2025-11-05T11:42:19.096591 | Matched | Field preserved, different timestamp | Low | No change required |
| Agents List | pipeLineAgents | Array[5] | workflowAgents | Array[5] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | Object with managerLlm | Renamed + Modified | Structure and content changed | High | Validate new configuration structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Confirm memory configuration handling |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | Medium | Confirm metadata removal is acceptable |
| Domain Metadata | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm metadata removal is acceptable |
| Project Metadata | project | AVA | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm metadata removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User tracking | default@ascendion.com | Medium | Implement user tracking system |
| modifiedBy | Change tracking | default@ascendion.com | Medium | Implement change tracking |
| approvedBy | Approval workflow | default@ascendion.com | Medium | Implement approval process |
| modifiedAt | Timestamp tracking | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T11:42:20.149991 | Low | Standard audit field |
| status | Workflow state | APPROVED | High | Implement workflow lifecycle management |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete handling |
| parentId | Hierarchy tracking | -1 | Low | Standard hierarchy field |
| realmId | Multi-tenancy | 1 | Medium | Implement realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm array | High | Implement new configuration structure |
| managerLlm | Direct object | Array of objects with ID references | High | Update LLM configuration handling |
| enableAgenticMemory | Top-level field | Nested in workflowConfigs | Medium | Update memory configuration access |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5
**AAVA 2.0 total agents:** 5
**Coverage:** Same agent count with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DB2_TO_SYNAPSE_CONVERTER | DB2 TO SYNAPSE CONVERTER | Matched (Case Normalization) | Underscore to space conversion |
| DB2_to_SYNAPSE_Unit_Testing | DB2 to SYNAPSE Unit Testing | Matched (Case Normalization) | Underscore to space conversion |
| DB2_To_SYNAPSE_Conversion_Tester | DB2 To SYNAPSE Conversion Tester | Matched (Case Normalization) | Underscore to space conversion |
| DB2_To_SYNAPSE_Reconciliation | DB2 To SYNAPSE Reconciliation | Matched (Case Normalization) | Underscore to space conversion |
| DB2_TO_SYNAPSE_REVIEWER | DB2 TO SYNAPSE REVIEWER | Matched | Exact match |

---

## 6. Agent Configuration Differences

## Agent: DB2 TO SYNAPSE CONVERTER

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
| modelDeploymentName | anthropic.claude-3-7-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | claude-3.7sonnet | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalization |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Confirm iteration handling |
| maxRpm | 0 | Not Present | Medium | Confirm rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate execution time limits |

### 6.1.3 Tools Comparison

Not Available

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DB2 to SYNAPSE Unit Testing

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
| model | gpt-4o | model | Medium | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalization |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 5 | Not Present | Medium | Confirm iteration handling |
| maxRpm | 0 | Not Present | Medium | Confirm rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate execution time limits |

### 6.2.3 Tools Comparison

Not Available

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DB2 To SYNAPSE Conversion Tester

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
| model | gpt-4o | model | Medium | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalization |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Confirm iteration handling |
| maxRpm | 0 | Not Present | Medium | Confirm rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate execution time limits |

### 6.3.3 Tools Comparison

Not Available

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available

---

## Agent: DB2 To SYNAPSE Reconciliation

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
| model | gpt-4o | model | Medium | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalization |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Confirm iteration handling |
| maxRpm | 0 | Not Present | Medium | Confirm rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate execution time limits |

### 6.4.3 Tools Comparison

Not Available

### 6.4.4 Knowledge Base Comparison

Not Available

### 6.4.5 Guardrails Comparison

Not Available

---

## Agent: DB2 TO SYNAPSE REVIEWER

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
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model compatibility |
| model | gpt-4o | model | Medium | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalization |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 5 | Not Present | Medium | Confirm iteration handling |
| maxRpm | 0 | Not Present | Medium | Confirm rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate execution time limits |

### 6.5.3 Tools Comparison

Not Available

### 6.5.4 Knowledge Base Comparison

Not Available

### 6.5.5 Guardrails Comparison

Not Available