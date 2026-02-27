# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 52%
**Total Agents Compared:** 5

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_DB2(AS400)_to_T-SQL_Conversion_Tester | 85% | Medium | role/goal/backstory removed; description matched; LLM configs matched | Validate instruction field removal impact |
| DI DB2 AS400 to T SQL Converter | 60% | Medium | New agent in 2.0; no direct mapping from 1.0 | Validate new agent functionality |
| DI DB2 AS400 to T SQL Unit Tester | 60% | Medium | New agent in 2.0; no direct mapping from 1.0 | Validate new agent functionality |
| DI DB2 AS400 to T SQL Recon Tester | 60% | Medium | New agent in 2.0; no direct mapping from 1.0 | Validate new agent functionality |
| DI DB2 AS400 to T SQL Reviewer | 60% | Medium | New agent in 2.0; no direct mapping from 1.0 | Validate new agent functionality |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_DB2(AS400)_to_T-SQL_Conversion_Tester
**Workflow Name (AAVA 2.0):** DI DB2(AS400) To T-SQL Conversion

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 8403 | id | 5533 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | DI_DB2(AS400)_to_T-SQL_Conversion_Tester | name | DI DB2(AS400) To T-SQL Conversion | Matched (Normalized) | Name simplified, normalized match | Low | No change |
| Description | description | This work flow is for the Conversion Tester | description | Convert DB2(AS400) to T-SQL code | Modified | Description content changed | Medium | Validate description accuracy |
| Audit | createdAt | 2025-11-14T07:08:23.697+00:00 | createdAt | 2025-11-17T08:46:13.066025 | Matched | Field exists in both, values differ by timestamp | Low | No change |
| Agents List | pipeLineAgents | 1 agent | workflowAgents | 5 agents | Renamed + Modified | Field renamed, agent count increased | High | Validate expanded workflow |
| Workflow Config | callbacks | [] | workflowConfigs | Present with LLM configs | Renamed + Modified | Structure and content changed | Medium | Configure workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field removed in 2.0 | Low | Confirm removal acceptable |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Handle org context loss |
| Domain Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Handle domain context loss |
| Project Metadata | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Handle project context loss |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User tracking | nishanth.janarthanan@ascendion.com | Medium | Ensure user context is captured |
| modifiedBy | Change tracking | nishanth.janarthanan@ascendion.com | Medium | Implement change tracking |
| approvedBy | Approval workflow | muneeswara.pandian@ascendion.com | Medium | Set up approval process |
| modifiedAt | Timestamp tracking | 2025-12-03T15:03:31.224436 | Low | Automatic timestamp handling |
| approvedAt | Approval timestamp | 2025-11-28T08:13:51.332063 | Low | Automatic approval tracking |
| status | Workflow state | APPROVED | High | Implement workflow lifecycle |
| comments | Feedback tracking | Empty object with structured fields | Medium | Enable feedback collection |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete logic |
| parentId | Hierarchy tracking | -1 | Medium | Handle workflow relationships |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with LLM settings | Medium | Configure workflow-level LLM settings |
| managerLlm | Not available | Empty array | Low | Define manager LLM if needed |
| enableAgenticMemory | false | false (in workflowConfigs) | Low | Maintain memory setting |
| realmId | Not available | 79 | Medium | Handle realm context |
| tags | Not available | [12,8,1,4] | Medium | Implement tagging system |
| practiceArea | Not available | 6 | Medium | Handle practice area classification |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 1
**AAVA 2.0 total agents:** 5
**Coverage:** Expanded - workflow significantly enhanced with additional agents

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_DB2(AS400)_to_T-SQL_Conversion_Tester | DI DB2 AS400 to T SQL Conversion Tester | Renamed | Naming convention updated, closest match |
| Not Available | DI DB2 AS400 to T SQL Converter | New | New agent in 2.0 |
| Not Available | DI DB2 AS400 to T SQL Unit Tester | New | New agent in 2.0 |
| Not Available | DI DB2 AS400 to T SQL Recon Tester | New | New agent in 2.0 |
| Not Available | DI DB2 AS400 to T SQL Reviewer | New | New agent in 2.0 |

---

## 6. Agent Configuration Differences

## Agent: DI_DB2(AS400)_to_T-SQL_Conversion_Tester → DI DB2 AS400 to T SQL Conversion Tester

---

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | Medium | Add missing field or confirm deprecation |

---

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model reference change |
| temperature | 0.30000001192092896 | 0.3 | Low | No change (normalized) |
| topP | 0.949999988079071 | 0.95 | Low | No change (normalized) |
| maxToken | 32000 | Not Available | Medium | Add missing field or confirm removal |
| maxIter | 0 | 10 | Medium | Validate iteration limit change |
| maxRpm | 0 | 60 | Medium | Validate rate limit change |
| maxExecutionTime | 0 | 300 | Medium | Validate timeout change |

---

### 6.1.3 Tools Comparison

**Not Available** - No tools configured in either version.

---

### 6.1.4 Knowledge Base Comparison

**Not Available** - No knowledge base configured in either version.

---

### 6.1.5 Guardrails Comparison

| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-----------------|----------------|----------------|------------------|-----------------|
| guardrailIds | Not Available | [] | Low | Empty guardrails maintained |

---

## Agent: DI DB2 AS400 to T SQL Converter

---

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Not Available | Not Available | Low | No change |
| goal | Not Available | Not Available | Low | No change |
| backstory | Not Available | Not Available | Low | No change |
| description | Not Available | Present | Medium | Validate new instruction field behavior |
| expectedOutput | Not Available | Not Available | Low | No change |

---

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Not Available | gpt-4.1 | Medium | Validate new LLM configuration |
| model | Not Available | model | Medium | Validate new model reference |
| temperature | Not Available | 0.3 | Medium | Validate new temperature setting |
| topP | Not Available | 0.95 | Medium | Validate new topP setting |
| maxIter | Not Available | 10 | Medium | Validate new iteration limit |
| maxRpm | Not Available | 60 | Medium | Validate new rate limit |
| maxExecutionTime | Not Available | 300 | Medium | Validate new timeout setting |

---

### 6.2.3 Tools Comparison

**Not Available** - No tools configured in either version.

---

### 6.2.4 Knowledge Base Comparison

**Not Available** - No knowledge base configured in either version.

---

### 6.2.5 Guardrails Comparison

| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-----------------|----------------|----------------|------------------|-----------------|
| guardrailIds | Not Available | [] | Low | Empty guardrails configured |

---

## Agent: DI DB2 AS400 to T SQL Unit Tester

---

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Not Available | Not Available | Low | No change |
| goal | Not Available | Not Available | Low | No change |
| backstory | Not Available | Not Available | Low | No change |
| description | Not Available | Present | Medium | Validate new instruction field behavior |
| expectedOutput | Not Available | Not Available | Low | No change |

---

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Not Available | gpt-4.1 | Medium | Validate new LLM configuration |
| model | Not Available | model | Medium | Validate new model reference |
| temperature | Not Available | 0.3 | Medium | Validate new temperature setting |
| topP | Not Available | 0.95 | Medium | Validate new topP setting |
| maxIter | Not Available | 10 | Medium | Validate new iteration limit |
| maxRpm | Not Available | 60 | Medium | Validate new rate limit |
| maxExecutionTime | Not Available | 300 | Medium | Validate new timeout setting |

---

### 6.3.3 Tools Comparison

**Not Available** - No tools configured in either version.

---

### 6.3.4 Knowledge Base Comparison

**Not Available** - No knowledge base configured in either version.

---

### 6.3.5 Guardrails Comparison

| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-----------------|----------------|----------------|------------------|-----------------|
| guardrailIds | Not Available | [] | Low | Empty guardrails configured |

---

## Agent: DI DB2 AS400 to T SQL Recon Tester

---

### 6.4.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Not Available | Not Available | Low | No change |
| goal | Not Available | Not Available | Low | No change |
| backstory | Not Available | Not Available | Low | No change |
| description | Not Available | Present | Medium | Validate new instruction field behavior |
| expectedOutput | Not Available | Not Available | Low | No change |

---

### 6.4.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Not Available | gpt-4.1 | Medium | Validate new LLM configuration |
| model | Not Available | model | Medium | Validate new model reference |
| temperature | Not Available | 0.3 | Medium | Validate new temperature setting |
| topP | Not Available | 0.95 | Medium | Validate new topP setting |
| maxIter | Not Available | 10 | Medium | Validate new iteration limit |
| maxRpm | Not Available | 60 | Medium | Validate new rate limit |
| maxExecutionTime | Not Available | 300 | Medium | Validate new timeout setting |

---

### 6.4.3 Tools Comparison

**Not Available** - No tools configured in either version.

---

### 6.4.4 Knowledge Base Comparison

**Not Available** - No knowledge base configured in either version.

---

### 6.4.5 Guardrails Comparison

| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-----------------|----------------|----------------|------------------|-----------------|
| guardrailIds | Not Available | [] | Low | Empty guardrails configured |

---

## Agent: DI DB2 AS400 to T SQL Reviewer

---

### 6.5.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Not Available | Not Available | Low | No change |
| goal | Not Available | Not Available | Low | No change |
| backstory | Not Available | Not Available | Low | No change |
| description | Not Available | Present | Medium | Validate new instruction field behavior |
| expectedOutput | Not Available | Not Available | Low | No change |

---

### 6.5.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Not Available | gpt-4.1 | Medium | Validate new LLM configuration |
| model | Not Available | model | Medium | Validate new model reference |
| temperature | Not Available | 0.3 | Medium | Validate new temperature setting |
| topP | Not Available | 0.95 | Medium | Validate new topP setting |
| maxIter | Not Available | 10 | Medium | Validate new iteration limit |
| maxRpm | Not Available | 60 | Medium | Validate new rate limit |
| maxExecutionTime | Not Available | 300 | Medium | Validate new timeout setting |

---

### 6.5.3 Tools Comparison

**Not Available** - No tools configured in either version.

---

### 6.5.4 Knowledge Base Comparison

**Not Available** - No knowledge base configured in either version.

---

### 6.5.5 Guardrails Comparison

| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-----------------|----------------|----------------|------------------|-----------------|
| guardrailIds | Not Available | [] | Low | Empty guardrails configured |