# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 86%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| Matillion to Informatica Documentation | 85% | Medium | role/goal/backstory removed, model changed, maxToken modified | Validate instruction field removal and model compatibility |
| Matillion to Informatica Analyser | 87% | Medium | role/goal/backstory removed, model changed, maxToken modified | Validate instruction field removal and model compatibility |
| Matillion to Informatica Plan | 86% | Medium | role/goal/backstory removed, model changed, maxToken modified | Validate instruction field removal and model compatibility |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** Matillion to Informatica Doc&Ana
**Workflow Name (AAVA 2.0):** Matillion to Informatica Doc&Ana

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1088 | id | 3510 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | Matillion to Informatica Doc&Ana | name | Matillion to Informatica Doc&Ana | Matched | No change | Low | No change |
| Description | description | Matillion to Informatica | description | Matillion to Informatica | Matched | No change | Low | No change |
| Audit | createdAt | 2025-03-14T13:19:21.081+00:00 | createdAt | 2025-11-05T11:33:59.514744 | Modified | Creation timestamp differs | Low | Expected for different workflow instances |
| Agents List | pipeLineAgents | Array[3] | workflowAgents | Array[3] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure enhanced | Medium | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Low | No change needed |
| Org/Domain/Project | org/orgId/domain/domainId/project/projectId/team/teamId/levelId | Multiple values | Not Available | Not Available | Removed | Organizational metadata removed | Medium | Ensure governance tracking elsewhere |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User tracking | default@ascendion.com | Medium | Ensure user attribution is handled |
| modifiedBy | Change tracking | default@ascendion.com | Medium | Implement change tracking |
| approvedBy | Approval workflow | default@ascendion.com | Medium | Set up approval processes |
| modifiedAt | Modification timestamp | 2025-11-30T11:55:00.892060 | Low | Automatic timestamp handling |
| approvedAt | Approval timestamp | 2025-11-05T11:34:00.573700 | Low | Automatic timestamp handling |
| status | Workflow state | APPROVED | High | Implement workflow lifecycle management |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete logic |
| parentId | Hierarchy tracking | -1 | Low | Handle workflow relationships |
| realmId | Multi-tenancy | 1 | Medium | Ensure proper tenant isolation |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|---------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Configure workflow-level LLM settings |
| managerLlm | Not available | Empty object [{}] | Medium | Define manager LLM configuration |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Low | Update configuration access patterns |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents maintained

### 5.2 Agent Name Mapping
| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|--------|
| Matillion to Informatica Documentation | Matillion to Informatica Documentation | Matched | No change |
| Matillion to Informatica Analyser | Matillion to Informatica Analyser | Matched | No change |
| Matillion to Informatica Plan | Matillion to Informatica Plan | Matched | No change |

---

## 6. Agent Configuration Differences

## Agent: Matillion to Informatica Documentation

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
| model | gpt-4o | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change |
| maxToken | 4000 | 4000 | Matched (Normalized) | No change |
| maxIter | 0 | null | Modified | Validate iteration limits |
| maxRpm | 0 | null | Modified | Validate rate limits |
| maxExecutionTime | 0 | 90 | Modified | Update execution timeout |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: Matillion to Informatica Analyser

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
| model | gpt-4o | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change |
| maxToken | 4000 | 4000 | Matched (Normalized) | No change |
| maxIter | 0 | null | Modified | Validate iteration limits |
| maxRpm | 0 | null | Modified | Validate rate limits |
| maxExecutionTime | 0 | 90 | Modified | Update execution timeout |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: Matillion to Informatica Plan

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
| model | gpt-4o | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change |
| maxToken | 4000 | 4000 | Matched (Normalized) | No change |
| maxIter | 0 | null | Modified | Validate iteration limits |
| maxRpm | 0 | null | Modified | Validate rate limits |
| maxExecutionTime | 0 | 90 | Modified | Update execution timeout |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available