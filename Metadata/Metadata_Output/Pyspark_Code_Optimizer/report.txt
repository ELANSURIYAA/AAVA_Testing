# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 76%
**Total Agents Compared:** 2

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| PySpark Code Analyzer | 72% | Medium | role/goal/backstory removed, description modified, model configs matched | Validate instruction field removal impact |
| PySpark Optimizer | 80% | Medium | role/goal/backstory removed, description matched, model configs matched | Validate instruction field removal impact |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** Pyspark_Code_Optimizer
**Workflow Name (AAVA 2.0):** PySpark Code Optimizer DI

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 6136 | id | 5678 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new workflow ID |
| Naming | name | Pyspark_Code_Optimizer | name | PySpark Code Optimizer DI | Matched (Normalized) | Name updated with proper casing and DI suffix | Low | Update documentation |
| Description | description | Analyze the provided PySpark code and generate a detailed report... | description | PySpark Code Output Optimization | Modified | Description significantly shortened | Medium | Validate new description covers requirements |
| Audit | createdAt | 2025-08-18T10:20:29.331+00:00 | createdAt | 2025-12-04T08:04:16.737439 | Matched | Timestamp format consistent | Low | No change |
| Agents List | pipeLineAgents | [2 agents] | workflowAgents | [2 agents] | Renamed + Matched (Normalized) | Field renamed, agent count preserved | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {topP: 0.95, maxToken: null, managerLlm: [], temperature: 0.1, enableAgenticMemory: false} | Renamed + Modified | Empty callbacks replaced with structured config | High | Configure workflow-level settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Verify memory settings in new structure |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm org tracking not needed |
| Domain Metadata | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm domain tracking not needed |
| Project Metadata | project | AVA | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm project tracking not needed |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User tracking | jahnavi.lingutla@ascendion.com | Medium | Ensure user attribution is captured |
| modifiedBy | Change tracking | jahnavi.lingutla@ascendion.com | Medium | Implement modification tracking |
| modifiedAt | Timestamp tracking | 2025-12-04T08:04:17.051023 | Medium | Ensure modification timestamps are captured |
| approvedAt | Approval workflow | 2025-12-04T08:04:17.074016 | High | Implement approval workflow process |
| status | Workflow state | APPROVED | High | Define workflow status lifecycle |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete functionality |
| parentId | Hierarchy tracking | -1 | Low | Define parent-child relationships if needed |
| realmId | Realm association | 79 | Medium | Map workflows to appropriate realms |
| tags | Categorization | [4] | Low | Implement tagging system |
| practiceArea | Practice grouping | 6 | Medium | Map workflows to practice areas |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|---------|-----------------|
| workflowConfigs | Not available | Present with topP, temperature, managerLlm | High | Configure workflow-level LLM settings |
| enableAgenticMemory | Workflow level | Moved to workflowConfigs | Medium | Verify memory configuration location |
| LLM Management | Agent-specific only | Workflow + Agent levels | High | Align LLM configuration hierarchy |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 2
**AAVA 2.0 total agents:** 2
**Coverage:** Same agent count, names updated

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| PySpark Code Analyzer | PySpark Code Analyzer DI | Renamed | Added DI suffix |
| PySpark Optimizer | PySpark Code Optimization DI | Renamed | Name updated with DI suffix |

---

## 6. Agent Configuration Differences

## Agent: PySpark Code Analyzer

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Present | Low | No change |

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.30000001192092896 | 0.0 | High | Validate temperature change impact |
| topP | 0.949999988079071 | 1.0 | Medium | Validate topP change impact |
| maxToken | 4000 | Not Available | Medium | Add missing field or confirm removal |
| maxIter | 0 | 10 | High | Validate iteration limit change |
| maxRpm | 0 | 60 | High | Validate rate limit change |
| maxExecutionTime | 0 | 300 | High | Validate timeout change |

### 6.1.3 Tools Comparison
**Not Available** - No tools configured in either version

### 6.1.4 Knowledge Base Comparison
**Not Available** - No knowledge base configured in either version

### 6.1.5 Guardrails Comparison

| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-----------------|----------------|----------------|------------------|-----------------|
| guardrailIds | Not Available | [] | Low | No guardrails configured |

---

## Agent: PySpark Optimizer

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Present | Low | No change |

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.30000001192092896 | 0.0 | High | Validate temperature change impact |
| topP | 0.949999988079071 | 1.0 | Medium | Validate topP change impact |
| maxToken | 4000 | Not Available | Medium | Add missing field or confirm removal |
| maxIter | 0 | 10 | High | Validate iteration limit change |
| maxRpm | 0 | 60 | High | Validate rate limit change |
| maxExecutionTime | 0 | 300 | High | Validate timeout change |

### 6.2.3 Tools Comparison
**Not Available** - No tools configured in either version

### 6.2.4 Knowledge Base Comparison
**Not Available** - No knowledge base configured in either version

### 6.2.5 Guardrails Comparison

| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-----------------|----------------|----------------|------------------|-----------------|
| guardrailIds | Not Available | [] | Low | No guardrails configured |