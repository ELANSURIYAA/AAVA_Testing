# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 78%  
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI DB2 AS400 Documentation | 75% | Medium | role/goal/backstory removed, description modified, LLM configs matched | Validate instruction field removal impact |
| DI DB2 AS400 to T SQL Analyzer | 82% | Medium | role/goal/backstory removed, description matched (normalized), model configs matched | Confirm agent behavior without role/goal/backstory |
| DI DB2 AS400 to T SQL Plan | 77% | Medium | role/goal/backstory removed, description matched (normalized), expectedOutput modified | Validate output format changes and instruction removal |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_DB2(AS400)_To_T-SQL_Doc&Analyze  
**Workflow Name (AAVA 2.0):** DI DB2(AS400) To T-SQL Doc&Analyze

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 8278 | id | 5532 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | DI_DB2(AS400)_To_T-SQL_Doc&Analyze | name | DI DB2(AS400) To T-SQL Doc&Analyze | Matched (Normalized) | Minor formatting differences | Low | No change required |
| Description | description | DB2(AS400)_DOCUMENTATION: Extracts and documents... | description | DB2(AS400) DOCUMENTATION: Extracts and documents... | Matched (Normalized) | Minor formatting differences | Low | No change required |
| Audit | createdAt | 2025-11-13T09:26:01.109+00:00 | createdAt | 2025-11-17T08:31:24.001469 | Matched | Field exists in both but values differ | Low | Timestamp difference expected |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {topP: 0.95, temperature: 0.1, ...} | Renamed + Modified | Field renamed and structure changed | High | Implement workflow configuration handling |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field removed in AAVA 2.0 | Medium | Confirm memory handling approach |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | Medium | Implement alternative org tracking |
| Domain Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Implement alternative domain tracking |
| Project Metadata | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Implement alternative project tracking |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | nishanth.janarthanan@ascendion.com | Medium | Implement user tracking |
| modifiedBy | User who last modified | nishanth.janarthanan@ascendion.com | Medium | Implement modification tracking |
| approvedBy | User who approved workflow | muneeswara.pandian@ascendion.com | High | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Implement modification tracking |
| approvedAt | Approval timestamp | 2025-11-28T08:14:07.263527 | High | Implement approval workflow |
| status | Workflow approval state | APPROVED | High | Implement workflow lifecycle |
| comments | Feedback structure | {whatWentGood, whatWentWrong, improvements} | Medium | Implement feedback system |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete handling |
| parentId | Workflow hierarchy | -1 | Low | Implement workflow relationships |
| realmId | Realm identifier | 79 | Medium | Implement realm-based access |
| tags | Workflow tags | [17,14,12,4] | Low | Implement tagging system |
| practiceArea | Practice area ID | 6 | Low | Implement practice area tracking |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with topP, temperature, maxToken, managerLlm, enableAgenticMemory | High | Implement workflow-level LLM configuration |
| callbacks | Empty array | Not available | Medium | Migrate callback handling to workflowConfigs |
| enableAgenticMemory | Workflow level: false | Workflow level: false (in workflowConfigs) | Low | Memory config moved to workflowConfigs |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3  
**AAVA 2.0 total agents:** 3  
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_DB2(AS400)_Documentation | DI DB2 AS400 Documentation | Renamed | Underscore to space conversion |
| DI_DB2(AS400)_to_T-SQL_Analyzer | DI DB2 AS400 to T SQL Analyzer | Renamed | Underscore to space conversion |
| DI_DB2(AS400)_to_T-SQL_Plan | DI DB2 AS400 to T SQL Plan | Renamed | Underscore to space conversion |

---

## 6. Agent Configuration Differences

## Agent: DI DB2 AS400 Documentation

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model reference change |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match (normalized) |
| topP | 0.949999988079071 | 0.95 | Low | Values match (normalized) |
| maxToken | 32000 | Not Available | Medium | Confirm token limit handling |
| maxIter | 0 | 10 | Medium | Iteration limit changed |
| maxRpm | 0 | 60 | Medium | Rate limit changed |
| maxExecutionTime | 0 | 300 | Medium | Execution timeout changed |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison

| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------------|----------------|----------------|------------------|-----------------|
| guardrailIds | Not Available | [] | Low | Empty guardrails maintained |

---

## Agent: DI DB2 AS400 to T SQL Analyzer

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model reference change |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match (normalized) |
| topP | 0.949999988079071 | 0.95 | Low | Values match (normalized) |
| maxToken | 32000 | Not Available | Medium | Confirm token limit handling |
| maxIter | 0 | 10 | Medium | Iteration limit changed |
| maxRpm | 0 | 60 | Medium | Rate limit changed |
| maxExecutionTime | 0 | 300 | Medium | Execution timeout changed |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison

| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------------|----------------|----------------|------------------|-----------------|
| guardrailIds | Not Available | [] | Low | Empty guardrails maintained |

---

## Agent: DI DB2 AS400 to T SQL Plan

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model reference change |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match (normalized) |
| topP | 0.949999988079071 | 0.95 | Low | Values match (normalized) |
| maxToken | 32000 | Not Available | Medium | Confirm token limit handling |
| maxIter | 0 | 10 | Medium | Iteration limit changed |
| maxRpm | 0 | 60 | Medium | Rate limit changed |
| maxExecutionTime | 0 | 300 | Medium | Execution timeout changed |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison

| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------------|----------------|----------------|------------------|-----------------|
| guardrailIds | Not Available | [] | Low | Empty guardrails maintained |