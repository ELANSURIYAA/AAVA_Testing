# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 84%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_Synapse_Documentation | 92% | Low | role/goal/backstory removed, description matched, LLM configs matched | Validate instruction field removal impact |
| DI_Azure_Synapse_To_PySpark_Analyzer | 84% | Medium | role/goal/backstory removed, temperature modified, topP modified | Review LLM parameter changes and instruction removal |
| DI_Azure_Synapse_To_PySpark_Plan | 76% | Medium | role/goal/backstory removed, maxIter removed, maxRpm removed | Validate runtime parameter removal and instruction changes |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_Azure_Synapse_To_PySpark_Doc&Analyze
**Workflow Name (AAVA 2.0):** DI_Azure_Synapse_To_PySpark_Doc&Analyze

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 8190 | id | 5710 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_Azure_Synapse_To_PySpark_Doc&Analyze | name | DI_Azure_Synapse_To_PySpark_Doc&Analyze | Matched | No change | Low | No change |
| Description | description | Synapse to pyspark Documentation, Analysis and plan workflow | description | Synapse to pyspark Documentation, Analysis and plan workflow | Matched | No change | Low | No change |
| Audit | createdAt | 2025-11-10T06:23:50.122+00:00 | createdAt | 2025-12-05T13:33:03.952575 | Matched | Timestamp updated for new version | Low | No change |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, agent count preserved | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {"managerLlm": [{}], "enableAgenticMemory": false} | Renamed + Modified | Field renamed and structure enhanced | Medium | Review new configuration options |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Low | Update configuration access |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | High | Ensure governance tracking maintained |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organizational ID removed | High | Ensure governance tracking maintained |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | High | Ensure governance tracking maintained |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | High | Ensure governance tracking maintained |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | High | Ensure governance tracking maintained |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | High | Ensure governance tracking maintained |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | High | Ensure governance tracking maintained |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | High | Ensure governance tracking maintained |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Review access control implications |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User tracking | elansuriyaa.p@ascendion.com | Medium | Ensure user attribution is maintained |
| modifiedBy | Change tracking | elansuriyaa.p@ascendion.com | Medium | Implement change audit trail |
| approvedBy | Approval workflow | elansuriyaa.p@ascendion.com | High | Establish approval process |
| modifiedAt | Modification timestamp | 2025-12-05T13:48:27.677683 | Medium | Track change history |
| approvedAt | Approval timestamp | 2025-12-05T13:33:05.686746 | High | Track approval workflow |
| status | Workflow state | APPROVED | High | Implement workflow lifecycle management |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete functionality |
| parentId | Hierarchy tracking | -1 | Low | Support workflow versioning |
| realmId | Multi-tenancy | 1 | Medium | Ensure proper tenant isolation |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align configuration defaults |
| managerLlm | Not available | Empty object {} | Medium | Configure manager LLM settings |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Low | Update configuration access pattern |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents maintained

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Synapse_Documentation | DI_Synapse_Documentation | Matched | Name preserved |
| DI_Azure_Synapse_To_PySpark_Analyzer | DI_Azure_Synapse_To_PySpark_Analyzer | Matched | Name preserved |
| DI_Azure_Synapse_To_PySpark_Plan | DI_Azure_Synapse_To_PySpark_Plan | Matched | Name preserved |

---

## 6. Agent Configuration Differences

## Agent: DI_Synapse_Documentation

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model reference change |
| temperature | 0.20000000298023224 | 0.2 | Low | Matched (Normalized) |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Present | Medium | Validate runtime parameter removal |
| maxRpm | 0 | Not Present | Medium | Validate runtime parameter removal |
| maxExecutionTime | 300 | Not Present | Medium | Validate runtime parameter removal |

### 6.1.3 Tools Comparison

Not Available

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI_Azure_Synapse_To_PySpark_Analyzer

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model reference change |
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Present | Medium | Validate runtime parameter removal |
| maxRpm | 0 | Not Present | Medium | Validate runtime parameter removal |
| maxExecutionTime | 300 | Not Present | Medium | Validate runtime parameter removal |

### 6.2.3 Tools Comparison

Not Available

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DI_Azure_Synapse_To_PySpark_Plan

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model reference change |
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 3 | Not Present | Medium | Validate runtime parameter removal |
| maxRpm | 300 | Not Present | Medium | Validate runtime parameter removal |
| maxExecutionTime | 300 | Not Present | Medium | Validate runtime parameter removal |

### 6.3.3 Tools Comparison

Not Available

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available