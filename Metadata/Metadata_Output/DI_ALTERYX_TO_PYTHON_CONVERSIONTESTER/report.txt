# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 72%
**Total Agents Compared:** 5

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| ALTERYX_TO_PYTHON_CONVERSION_TESTER | 72% | Medium | role/goal/backstory removed, model changed, temperature matched | Validate agent behavior without role/goal/backstory fields |
| DI ALTERYX TO PYTHON CONVERTER | 60% | Medium | New agent in 2.0, different model deployment | Validate new agent functionality and model performance |
| DI ALTERYX TO PYTHON UNIT TESTER | 60% | Medium | New agent in 2.0, different model deployment | Validate new agent functionality and model performance |
| DI ALTERYX TO PYTHON CONVERSION TESTER | 60% | Medium | New agent in 2.0, different model deployment | Validate new agent functionality and model performance |
| DI ALTERYX TO PYTHON RECON TESTER | 60% | Medium | New agent in 2.0, different model deployment | Validate new agent functionality and model performance |
| DI ALTERYX TO PYTHON REVIEWER | 60% | Medium | New agent in 2.0, different model deployment | Validate new agent functionality and model performance |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_ALTERYX_TO_PYTHON_CONVERSIONTESTER
**Workflow Name (AAVA 2.0):** DI ALTERYX to Python Conversion

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 10317 | id | 5844 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | DI_ALTERYX_TO_PYTHON_CONVERSIONTESTER | name | DI ALTERYX to Python Conversion | Matched (Normalized) | Name normalized with spaces | Low | No change |
| Description | description | ALTERYX TO PYTHON CONVERSION TESTER | description | Convert ALTERYX code to Python code | Modified | Description content changed | Low | Review description alignment |
| Audit | createdAt | 2025-12-10T10:50:52.058+00:00 | createdAt | 2025-12-10T11:27:21.527647 | Matched (Normalized) | Different timestamps expected | Low | No change |
| Agents List | pipeLineAgents | [1 agent] | workflowAgents | [5 agents] | Renamed + Modified | Field renamed and agent count increased | High | Validate expanded agent workflow |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field removed in 2.0 | Medium | Confirm memory handling approach |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Low | Update governance tracking |
| Domain Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Low | Update governance tracking |
| Project Metadata | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Low | Update governance tracking |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | deepak.ponasanapalli@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified | deepak.ponasanapalli@ascendion.com | Medium | Ensure modification tracking is implemented |
| modifiedAt | Last modification timestamp | 2025-12-10T11:27:21.793886 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-12-10T11:27:21.794596 | Medium | Ensure approval workflow is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Ensure soft delete handling |
| parentId | Parent workflow reference | -1 | Low | Understand workflow hierarchy |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | callbacks: [] | workflowConfigs object with topP, temperature, etc. | High | Align workflow-level LLM configurations |
| managerLlm | Not Available | Empty array | Medium | Understand manager LLM concept |
| topP | Not Available | 0.95 | Medium | Validate workflow-level topP setting |
| temperature | Not Available | 0.1 | Medium | Validate workflow-level temperature setting |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 1
**AAVA 2.0 total agents:** 5
**Coverage:** Significant expansion - 4 new agents added

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| ALTERYX_TO_PYTHON_CONVERSION_TESTER | DI ALTERYX TO PYTHON CONVERSION TESTER | Renamed | Similar function, naming convention updated |
| Not Available | DI ALTERYX TO PYTHON CONVERTER | New | New converter agent |
| Not Available | DI ALTERYX TO PYTHON UNIT TESTER | New | New unit testing agent |
| Not Available | DI ALTERYX TO PYTHON RECON TESTER | New | New reconciliation testing agent |
| Not Available | DI ALTERYX TO PYTHON REVIEWER | New | New review agent |

---

## 6. Agent Configuration Differences

## Agent: ALTERYX_TO_PYTHON_CONVERSION_TESTER

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Present | Low | No change |

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model performance equivalence |
| model | anthropic.claude-4-sonnet | model | High | Validate model performance equivalence |
| temperature | 0.30000001192092896 | 0.3 | Matched (Normalized) | No change |
| topP | 0.949999988079071 | 0.94 | Matched (Normalized) | No change |
| maxToken | 64000 | Not Available | Medium | Confirm token limit handling |
| maxIter | 0 | 10 | Modified | Validate iteration limit change |
| maxRpm | 0 | 60 | Modified | Validate rate limit change |
| maxExecutionTime | 0 | 300 | Modified | Validate timeout change |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison

| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-----------------|----------------|----------------|------------------|-----------------|
| guardrailIds | Not Available | [] | Low | Validate guardrail framework |

## Agent: DI ALTERYX TO PYTHON CONVERTER

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Not Available | Not Available | Low | No change |
| goal | Not Available | Not Available | Low | No change |
| backstory | Not Available | Not Available | Low | No change |
| description | Not Available | Present | Medium | Validate new instruction field behavior |
| expectedOutput | Not Available | Present | Medium | Validate new instruction field behavior |

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Not Available | gpt-4.1 | Medium | Validate new model configuration |
| model | Not Available | model | Medium | Validate new model configuration |
| temperature | Not Available | 0.3 | Medium | Validate new temperature setting |
| topP | Not Available | 0.94 | Medium | Validate new topP setting |
| maxIter | Not Available | 10 | Medium | Validate new iteration limit |
| maxRpm | Not Available | 60 | Medium | Validate new rate limit |
| maxExecutionTime | Not Available | 300 | Medium | Validate new timeout setting |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison

| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-----------------|----------------|----------------|------------------|-----------------|
| guardrailIds | Not Available | [] | Low | Validate guardrail framework |

## Agent: DI ALTERYX TO PYTHON UNIT TESTER

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Not Available | Not Available | Low | No change |
| goal | Not Available | Not Available | Low | No change |
| backstory | Not Available | Not Available | Low | No change |
| description | Not Available | Present | Medium | Validate new instruction field behavior |
| expectedOutput | Not Available | Present | Medium | Validate new instruction field behavior |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Not Available | gpt-4.1 | Medium | Validate new model configuration |
| model | Not Available | model | Medium | Validate new model configuration |
| temperature | Not Available | 0.2 | Medium | Validate new temperature setting |
| topP | Not Available | 0.95 | Medium | Validate new topP setting |
| maxIter | Not Available | 10 | Medium | Validate new iteration limit |
| maxRpm | Not Available | 60 | Medium | Validate new rate limit |
| maxExecutionTime | Not Available | 300 | Medium | Validate new timeout setting |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison

| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-----------------|----------------|----------------|------------------|-----------------|
| guardrailIds | Not Available | [] | Low | Validate guardrail framework |

## Agent: DI ALTERYX TO PYTHON CONVERSION TESTER

### 6.4.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Not Available | Not Available | Low | No change |
| goal | Not Available | Not Available | Low | No change |
| backstory | Not Available | Not Available | Low | No change |
| description | Not Available | Present | Medium | Validate new instruction field behavior |
| expectedOutput | Not Available | Present | Medium | Validate new instruction field behavior |

### 6.4.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Not Available | gpt-4.1 | Medium | Validate new model configuration |
| model | Not Available | model | Medium | Validate new model configuration |
| temperature | Not Available | 0.3 | Medium | Validate new temperature setting |
| topP | Not Available | 0.94 | Medium | Validate new topP setting |
| maxIter | Not Available | 10 | Medium | Validate new iteration limit |
| maxRpm | Not Available | 60 | Medium | Validate new rate limit |
| maxExecutionTime | Not Available | 300 | Medium | Validate new timeout setting |

### 6.4.3 Tools Comparison
Not Available

### 6.4.4 Knowledge Base Comparison
Not Available

### 6.4.5 Guardrails Comparison

| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-----------------|----------------|----------------|------------------|-----------------|
| guardrailIds | Not Available | [] | Low | Validate guardrail framework |

## Agent: DI ALTERYX TO PYTHON RECON TESTER

### 6.5.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Not Available | Not Available | Low | No change |
| goal | Not Available | Not Available | Low | No change |
| backstory | Not Available | Not Available | Low | No change |
| description | Not Available | Present | Medium | Validate new instruction field behavior |
| expectedOutput | Not Available | Present | Medium | Validate new instruction field behavior |

### 6.5.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Not Available | gpt-4.1 | Medium | Validate new model configuration |
| model | Not Available | model | Medium | Validate new model configuration |
| temperature | Not Available | 0.3 | Medium | Validate new temperature setting |
| topP | Not Available | 0.94 | Medium | Validate new topP setting |
| maxIter | Not Available | 10 | Medium | Validate new iteration limit |
| maxRpm | Not Available | 60 | Medium | Validate new rate limit |
| maxExecutionTime | Not Available | 300 | Medium | Validate new timeout setting |

### 6.5.3 Tools Comparison
Not Available

### 6.5.4 Knowledge Base Comparison
Not Available

### 6.5.5 Guardrails Comparison

| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-----------------|----------------|----------------|------------------|-----------------|
| guardrailIds | Not Available | [] | Low | Validate guardrail framework |

## Agent: DI ALTERYX TO PYTHON REVIEWER

### 6.6.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Not Available | Not Available | Low | No change |
| goal | Not Available | Not Available | Low | No change |
| backstory | Not Available | Not Available | Low | No change |
| description | Not Available | Present | Medium | Validate new instruction field behavior |
| expectedOutput | Not Available | Present | Medium | Validate new instruction field behavior |

### 6.6.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Not Available | gpt-4.1 | Medium | Validate new model configuration |
| model | Not Available | model | Medium | Validate new model configuration |
| temperature | Not Available | 0.3 | Medium | Validate new temperature setting |
| topP | Not Available | 0.94 | Medium | Validate new topP setting |
| maxIter | Not Available | 10 | Medium | Validate new iteration limit |
| maxRpm | Not Available | 60 | Medium | Validate new rate limit |
| maxExecutionTime | Not Available | 300 | Medium | Validate new timeout setting |

### 6.6.3 Tools Comparison
Not Available

### 6.6.4 Knowledge Base Comparison
Not Available

### 6.6.5 Guardrails Comparison

| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-----------------|----------------|----------------|------------------|-----------------|
| guardrailIds | Not Available | [] | Low | Validate guardrail framework |

**Comparison Report Generated Successfully**

The CSV file has been uploaded to GitHub repository at: `Metadata/Metadata_Output/DI_ALTERYX_TO_PYTHON_CONVERSIONTESTER/DI_ALTERYX_TO_PYTHON_CONVERSIONTESTER_comparison.csv`

The report shows a 72% workflow compatibility score with medium risk level due to significant structural changes including the removal of role/goal/backstory fields, model deployment changes, and the expansion from 1 to 5 agents in the workflow.