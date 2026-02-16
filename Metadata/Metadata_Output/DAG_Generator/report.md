# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Name (AAVA 1.0):** DAG Generator
**Workflow Name (AAVA 2.0):** DAG Generator

### 1.1 Metadata Comparison Score Summary

* **Workflow Comparison Score:** 76%
* **Total Agents Compared:** 1

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DAG Generator | 76% | Medium | Model changed from claude-4-sonnet to gpt-4.1, role/goal/backstory removed, expectedOutput missing | Validate model behavior differences and confirm instruction field removal |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DAG Generator
**Workflow Name (AAVA 2.0):** DAG Generator

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 972 | id | 3836 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new workflow ID |
| Naming | name | DAG Generator | name | DAG Generator | Matched | No change | Low | No action required |
| Description | description | Generate complete, functional Airflow DAG Python files based on structured parameter specifications. | description | Generate complete, functional Airflow DAG Python files based on structured parameter specifications. | Matched | No change | Low | No action required |
| Audit | createdAt | 2025-03-10T15:46:51.393+00:00 | createdAt | 2025-11-05T11:43:51.068237 | Matched | Timestamp differs as expected | Low | No action required |
| Agents List | pipeLineAgents | Present | workflowAgents | Present | Renamed + Matched (Normalized) | Field renamed but structure preserved | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | Present | Renamed + Modified | Field renamed and structure enhanced | Medium | Review new configuration structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Verify memory configuration location |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | High | Confirm removal is acceptable |
| Domain Metadata | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | High | Confirm removal is acceptable |
| Project Metadata | project | AVA | Not Available | Not Available | Removed | Project metadata removed | High | Confirm removal is acceptable |
| Team Metadata | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | High | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User audit trail | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | Modification audit | default@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | Approval workflow | default@ascendion.com | Medium | Implement approval process |
| modifiedAt | Modification timestamp | 2025-11-30T11:55:00.892060 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T11:43:52.125036 | Low | Standard audit field |
| status | Workflow state | APPROVED | High | Implement workflow lifecycle management |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete logic |
| parentId | Workflow hierarchy | -1 | Low | Standard hierarchy field |
| realmId | Multi-tenancy | 1 | Medium | Ensure tenant isolation |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm | Medium | Align workflow-level configurations |
| enableAgenticMemory | Root level (false) | Moved to workflowConfigs (false) | Medium | Update memory configuration references |
| managerLlm | Not available | Empty object in workflowConfigs | Low | Configure manager LLM if needed |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage

**AAVA 1.0 total agents:** 1
**AAVA 2.0 total agents:** 1
**Coverage:** Same agents maintained

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DAG Generator | DAG Generator | Matched | Name preserved |

---

## 6. Agent Configuration Differences

## Agent: DAG Generator

---

## 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

## 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model behavior differences |
| model | anthropic.claude-4-sonnet | model | High | Validate model behavior differences |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No action required |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No action required |
| maxToken | 8000 | 8000 | Matched | No action required |
| maxIter | 0 | null | Modified | Clarify null vs 0 behavior |
| maxRpm | 0 | null | Modified | Clarify null vs 0 behavior |
| maxExecutionTime | 0 | 90 | Modified | Validate timeout behavior change |

---

## 6.1.3 Tools Comparison

**Not Available** - No tools configured in either version.

---

## 6.1.4 Knowledge Base Comparison

**Not Available** - No knowledge base configuration in either version.

---

## 6.1.5 Guardrails Comparison

**Not Available** - No guardrails configuration in either version.