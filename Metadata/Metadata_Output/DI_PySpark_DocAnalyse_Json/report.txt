# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 75%**
**Total Agents Compared: 5**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_PySpark_Documentation_Json | 85% | Low | Model configs matched, description matched, temperature matched | Validate expectedOutput format changes |
| DI_PySpark_Analyser_Json | 80% | Low | Model configs matched, description matched, temperature matched | Validate expectedOutput format changes |
| DI_PySpark_Plan_Json | 75% | Medium | Model configs matched, maxExecutionTime reduced, maxRpm changed | Validate runtime behavior and performance impact |
| DI_PySpark_Design_Pattern_Json | 60% | Medium | New agent in AAVA 2.0, no direct mapping from AAVA 1.0 | Validate new agent functionality and integration |
| DI_PySpark_ETL_Asset_Rationaliser | 60% | Medium | New agent in AAVA 2.0, no direct mapping from AAVA 1.0 | Validate new agent functionality and integration |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_PySpark_Doc&Analyse_Json
**Workflow Name (AAVA 2.0):** DI PySpark Doc&Analyse Json

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 6090 | id | 2109 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_PySpark_Doc&Analyse_Json | name | DI PySpark Doc&Analyse Json | Matched (Normalized) | Minor formatting differences | Low | No change required |
| Description | description | PySpark Asset Riontionaliser Workflow | description | PySpark Asset Riontionaliser Workflow | Matched | Exact match | Low | No change required |
| Audit | createdAt | 2025-12-16T14:06:11.085+00:00 | createdAt | 2025-11-05T10:47:27.655231 | Modified | Different creation timestamps | Low | Accept new timestamp |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [5 agents] | Renamed + Modified | Field renamed and agent count increased | High | Validate new agents and dependencies |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure changed | Medium | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Low | Update configuration references |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Ensure governance tracking |
| Domain Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Ensure governance tracking |
| Project Metadata | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Ensure governance tracking |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | elansuriyaa.p@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Accept new timestamp tracking |
| approvedAt | Approval timestamp | 2025-11-05T10:47:28.852727 | Low | Accept approval tracking |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Ensure deletion handling is implemented |
| parentId | Parent workflow reference | -1 | Low | Validate workflow hierarchy |
| realmId | Realm identifier | 32 | Medium | Ensure realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align defaults and configure manager LLM |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Low | Update configuration access pattern |
| callbacks | Empty array | Not available | Low | Remove callback references |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 5
**Coverage:** Added agents (2 new agents introduced)

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_PySpark_Documentation_Json | DI PySpark Documentation Json | Renamed | Naming convention updated (spaces instead of underscores) |
| DI_PySpark_Analyser_Json | DI PySpark Analyser Json | Renamed | Naming convention updated (spaces instead of underscores) |
| DI_PySpark_Plan_Json | DI PySpark Plan Json | Renamed | Naming convention updated (spaces instead of underscores) |
| Not Available | DI PySpark Design Pattern Json | New | New agent added in AAVA 2.0 |
| Not Available | DI PySpark ETL Asset Rationaliser | New | New agent added in AAVA 2.0 |

---

## 6. Agent Configuration Differences

## Agent: DI_PySpark_Documentation_Json

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
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 15 | Not Present | Medium | Validate iteration control removal |
| maxRpm | 0 | Not Present | Low | Validate rate limit removal |
| maxExecutionTime | 300 | 90 | High | Validate execution time reduction impact |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: DI_PySpark_Analyser_Json

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
| maxIter | 15 | Not Present | Medium | Validate iteration control removal |
| maxRpm | 0 | Not Present | Low | Validate rate limit removal |
| maxExecutionTime | 300 | 90 | High | Validate execution time reduction impact |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: DI_PySpark_Plan_Json

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
| maxIter | 20 | Not Present | Medium | Validate iteration control removal |
| maxRpm | 20 | Not Present | Medium | Validate rate limit removal |
| maxExecutionTime | 180 | 90 | High | Validate execution time reduction impact |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available

---

## Agent: DI_PySpark_Design_Pattern_Json

### 6.4.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Not Present | Not Present | Low | No change |
| goal | Not Present | Not Present | Low | No change |
| backstory | Not Present | Not Present | Low | No change |
| description | Not Present | Present | Medium | Validate new instruction field behavior |
| expectedOutput | Not Present | Not Present | Low | No change |

### 6.4.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Not Available | gpt-4.1 | Medium | Validate new model configuration |
| model | Not Available | model | Medium | Validate new model configuration |
| temperature | Not Available | 0.3 | Medium | Validate new temperature setting |
| topP | Not Available | 0.94 | Medium | Validate new topP setting |
| maxToken | Not Available | 8000 | Medium | Validate new token limit |
| maxIter | Not Available | Not Present | Low | No change |
| maxRpm | Not Available | Not Present | Low | No change |
| maxExecutionTime | Not Available | 90 | Medium | Validate new execution time limit |

### 6.4.3 Tools Comparison
Not Available

### 6.4.4 Knowledge Base Comparison
Not Available

### 6.4.5 Guardrails Comparison
Not Available

---

## Agent: DI_PySpark_ETL_Asset_Rationaliser

### 6.5.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Not Present | Not Present | Low | No change |
| goal | Not Present | Not Present | Low | No change |
| backstory | Not Present | Not Present | Low | No change |
| description | Not Present | Present | Medium | Validate new instruction field behavior |
| expectedOutput | Not Present | Not Present | Low | No change |

### 6.5.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Not Available | gpt-4.1 | Medium | Validate new model configuration |
| model | Not Available | model | Medium | Validate new model configuration |
| temperature | Not Available | 0.1 | Medium | Validate new temperature setting |
| topP | Not Available | 1.0 | Medium | Validate new topP setting |
| maxToken | Not Available | 8000 | Medium | Validate new token limit |
| maxIter | Not Available | Not Present | Low | No change |
| maxRpm | Not Available | Not Present | Low | No change |
| maxExecutionTime | Not Available | 90 | Medium | Validate new execution time limit |

### 6.5.3 Tools Comparison
Not Available

### 6.5.4 Knowledge Base Comparison
Not Available

### 6.5.5 Guardrails Comparison
Not Available