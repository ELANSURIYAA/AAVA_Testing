# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 73%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI ALTERYX DOCUMENTATION | 85% | Low | Name normalized, description matched, model configs matched | Validate maxIter and maxRpm removal |
| ALTERYX TO PYTHON ANALYZER | 72% | Medium | Name matched, description simplified, maxIter/maxRpm/maxExecutionTime removed | Validate runtime behavior changes |
| ALTERYX TO PYTHON PLAN | 62% | Medium | Name matched, description matched, model deployment changed | Validate model deployment change impact |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** ALTERYX_to_Python_Doc&Analyze
**Workflow Name (AAVA 2.0):** ALTERYX to Python Doc&Analyze

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1407 | id | 4103 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | ALTERYX_to_Python_Doc&Analyze | name | ALTERYX to Python Doc&Analyze | Matched (Normalized) | Minor formatting differences | Low | No change required |
| Description | description | Analyzing and Documenting the ALTERYX Code | description | Analyzing and Documenting the ALTERYX Code | Matched | Exact match | Low | No change required |
| Audit | createdAt | 2025-04-01T11:30:18.310+00:00 | createdAt | 2025-11-05T11:51:56.971683 | Matched | Field present in both, values differ by timestamp | Low | No change required |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure changed | High | Migrate callback logic to workflowConfigs |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Confirm memory config handling |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Confirm org context handling |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | High | Confirm org context handling |
| Domain | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | High | Confirm domain context handling |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | High | Confirm domain context handling |
| Project | project | AVA | Not Available | Not Available | Removed | Project metadata removed | High | Confirm project context handling |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | High | Confirm project context handling |
| Team | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | High | Confirm team context handling |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | High | Confirm team context handling |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed | High | Confirm level context handling |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T11:51:58.049564 | Medium | Ensure approval workflow is implemented |
| status | Workflow approval state | APPROVED | High | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete logic is implemented |
| parentId | Parent workflow reference | -1 | Low | Understand workflow hierarchy |
| realmId | Realm identifier | 1 | Medium | Ensure realm context is handled |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | High | Align workflow configuration structure |
| managerLlm | Not available | Empty object in workflowConfigs | Medium | Configure manager LLM settings |
| enableAgenticMemory | Top-level field (false) | Nested in workflowConfigs (false) | Medium | Update memory config access pattern |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agent count with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_ALTERYX_DOCUMENTATION | DI ALTERYX DOCUMENTATION | Renamed | Underscore to space conversion |
| ALTERYX_TO_PYTHON_ANALYZER | ALTERYX TO PYTHON ANALYZER | Renamed | Underscore to space conversion |
| ALTERYX_TO_PYTHON_PLAN | ALTERYX TO PYTHON PLAN | Renamed | Underscore to space conversion |

---

## 6. Agent Configuration Differences

## Agent: DI ALTERYX DOCUMENTATION

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change required |
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 8000 | 8000 | Low | No change required |
| maxIter | 20 | Not Available | Medium | Validate iteration limit removal |
| maxRpm | 0 | Not Available | Medium | Validate rate limit removal |
| maxExecutionTime | 300 | 90 | Medium | Validate execution time reduction |

### 6.1.3 Tools Comparison

**Not Available** - No tools configured in either version

### 6.1.4 Knowledge Base Comparison

**Not Available** - No knowledge base configured in either version

### 6.1.5 Guardrails Comparison

**Not Available** - No guardrails configured in either version

---

## Agent: ALTERYX TO PYTHON ANALYZER

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
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate model deployment change |
| model | gpt-4o | model | Medium | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 4000 | 4000 | Low | No change required |
| maxIter | 0 | Not Available | Medium | Validate iteration limit removal |
| maxRpm | 0 | Not Available | Medium | Validate rate limit removal |
| maxExecutionTime | 0 | 90 | Medium | Validate execution time change |

### 6.2.3 Tools Comparison

**Not Available** - No tools configured in either version

### 6.2.4 Knowledge Base Comparison

**Not Available** - No knowledge base configured in either version

### 6.2.5 Guardrails Comparison

**Not Available** - No guardrails configured in either version

---

## Agent: ALTERYX TO PYTHON PLAN

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
| modelDeploymentName | anthropic.claude-3-7-sonnet | gpt-4.1 | High | Validate model deployment change |
| model | claude-3.7sonnet | model | High | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 8000 | 8000 | Low | No change required |
| maxIter | 0 | Not Available | Medium | Validate iteration limit removal |
| maxRpm | 0 | Not Available | Medium | Validate rate limit removal |
| maxExecutionTime | 0 | 90 | Medium | Validate execution time change |

### 6.3.3 Tools Comparison

**Not Available** - No tools configured in either version

### 6.3.4 Knowledge Base Comparison

**Not Available** - No knowledge base configured in either version

### 6.3.5 Guardrails Comparison

**Not Available** - No guardrails configured in either version