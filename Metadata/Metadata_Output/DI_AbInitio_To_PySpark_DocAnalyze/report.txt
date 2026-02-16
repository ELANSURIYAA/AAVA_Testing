# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 78%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI AbInitio Documentation | 85% | Low | Model changed from claude-4-sonnet to gpt-4.1, role/goal/backstory removed, description significantly modified | Validate model behavior change and confirm instruction field removal |
| DI AbInitio To PySpark Analyzer | 92% | Low | Description matched, LLM configs matched, tools matched | None - minimal changes detected |
| DI AbInitio To PySpark Plan | 71% | Medium | Description matched, but agent ID changed from 3776 to 3647, maxExecutionTime reduced from 300 to 90 | Validate runtime timeout reduction impact |

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_AbInitio_To_PySpark_Doc&Analyze
**Workflow Name (AAVA 2.0):** DI AbInitio To PySpark Doc&Analyze

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 2729 | id | 1897 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_AbInitio_To_PySpark_Doc&Analyze | name | DI AbInitio To PySpark Doc&Analyze | Matched (Normalized) | Minor formatting differences in naming | Low | No action required |
| Description | description | Analyzing and Documenting the Abinitio Code | description | Analyzing and Documenting the Abinitio Code | Matched | Exact match | Low | No action required |
| Audit | createdAt | 2025-06-08T15:10:48.608+00:00 | createdAt | 2025-11-05T10:39:20.563992 | Modified | Creation timestamp differs | Low | Expected for different workflow instances |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed but same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure enhanced | Medium | Align configuration handling |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Low | Update configuration access pattern |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm removal is acceptable |
| Domain Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal is acceptable |
| Project Metadata | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal is acceptable |

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User tracking | default@ascendion.com | Medium | Ensure user tracking is handled |
| modifiedBy | Modification tracking | default@ascendion.com | Medium | Ensure modification tracking is handled |
| approvedBy | Approval tracking | default@ascendion.com | Medium | Ensure approval workflow is handled |
| modifiedAt | Modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T10:39:21.771493 | Low | Standard audit field |
| status | Workflow state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure deletion handling is implemented |
| parentId | Hierarchy tracking | -1 | Low | Standard hierarchy field |
| realmId | Realm association | 1 | Medium | Ensure realm-based access control |

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align configuration structure |
| managerLlm | Not available | Empty object {} | Medium | Validate manager LLM configuration |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Low | Update configuration access pattern |

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agent count with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_AbInitio_Documentation | DI AbInitio Documentation | Renamed | Underscore to space conversion |
| DI_AbInitio_To_PySpark_Analyzer | DI AbInitio To PySpark Analyzer | Renamed | Underscore to space conversion |
| DI_AbInitio_To_PySpark_Plan | DI AbInitio To PySpark Plan | Renamed | Underscore to space conversion |

## 6. Agent Configuration Differences

### Agent: DI AbInitio Documentation

#### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

#### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model behavior change |
| model | anthropic.claude-4-sonnet | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.2 | Medium | Validate temperature change impact |
| topP | 0.949999988079071 | 1.0 | Low | Minor topP adjustment |
| maxToken | 64000 | 8000 | High | Validate token limit reduction |
| maxIter | 0 | Not Available | Medium | Confirm iteration handling |
| maxRpm | 0 | Not Available | Low | Rate limiting configuration |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |

#### 6.1.3 Tools Comparison
Not Available

#### 6.1.4 Knowledge Base Comparison
Not Available

#### 6.1.5 Guardrails Comparison
Not Available

### Agent: DI AbInitio To PySpark Analyzer

#### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

#### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model reference |
| temperature | 0.20000000298023224 | 0.2 | Matched (Normalized) | No change |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Available | Medium | Confirm iteration handling |
| maxRpm | 0 | Not Available | Low | Rate limiting configuration |
| maxExecutionTime | 300 | 90 | High | Validate timeout reduction impact |

#### 6.2.3 Tools Comparison
Not Available

#### 6.2.4 Knowledge Base Comparison
Not Available

#### 6.2.5 Guardrails Comparison
Not Available

### Agent: DI AbInitio To PySpark Plan

#### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

#### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model reference |
| temperature | 0.20000000298023224 | 0.2 | Matched (Normalized) | No change |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Available | Medium | Confirm iteration handling |
| maxRpm | 0 | Not Available | Low | Rate limiting configuration |
| maxExecutionTime | 300 | 90 | High | Validate timeout reduction impact |

#### 6.3.3 Tools Comparison
Not Available

#### 6.3.4 Knowledge Base Comparison
Not Available

#### 6.3.5 Guardrails Comparison
Not Available

---

**Report Status:** Successfully uploaded comparison CSV to GitHub repository at Metadata/Metadata_Output/DI_AbInitio_To_PySpark_DocAnalyze/DI_AbInitio_To_PySpark_DocAnalyze_comparison.csv