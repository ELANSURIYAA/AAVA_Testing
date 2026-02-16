# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 78%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_AbInitio_Document_To_PySpark_Code_Generator | 75% | Medium | role/goal/backstory removed, model configs matched, description masked | Validate instruction field removal impact |
| DI_AbInitio_To_PySpark_Unit_Tester | 82% | Medium | role/goal/backstory removed, temperature changed, maxIter increased | Validate performance impact of config changes |
| DI_AbInitio_Document_To_PySpark_Reviewer | 77% | Medium | role/goal/backstory removed, temperature changed, maxIter increased | Validate instruction field removal and config changes |

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_AbInitio_Document_To_PySpark
**Workflow Name (AAVA 2.0):** DI AbInitio Document To PySpark

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 13116 | id | 9098 | Renamed + Modified | Field renamed and value changed | High | Update ID references in dependent systems |
| Naming | name | DI_AbInitio_Document_To_PySpark | name | DI AbInitio Document To PySpark | Matched (Case Normalization) | Minor formatting differences | Low | No change |
| Description | description | Generate the PySpark code using the AbInitio Document | description | Generate the Pyspark script from abinitio document | Matched (Normalized) | Minor wording differences | Low | No change |
| Audit | createdAt | 2026-01-29T10:30:44.366+00:00 | createdAt | 2026-02-02T11:00:14.324357 | Modified | Different timestamps | Medium | Verify audit trail continuity |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update agent references |
| Workflow Config | callbacks | [] | workflowConfigs | {topP: 0.95, temperature: 0.1, ...} | Renamed + Modified | Field renamed and enhanced config | High | Configure workflow-level settings |
| Memory Config | enableAgenticMemory | false | enableAgenticMemory (in workflowConfigs) | true | Modified | Memory setting changed | Medium | Validate memory behavior |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Ensure governance continuity |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | High | Update organizational references |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | High | Maintain domain classification |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | High | Update domain references |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | High | Maintain project tracking |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | High | Update project references |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | High | Maintain team assignment |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | High | Update team references |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Verify access level handling |

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User tracking | karthikeyan.iyappan@ascendion.com | Medium | Ensure user attribution is maintained |
| modifiedBy | Change tracking | karthikeyan.iyappan@ascendion.com | Medium | Implement modification tracking |
| modifiedAt | Timestamp tracking | 2026-02-02T11:00:14.784624 | Medium | Sync with audit systems |
| approvedAt | Approval workflow | 2026-02-02T11:00:14.771957 | High | Implement approval process |
| status | Workflow state | APPROVED | High | Define status lifecycle |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete logic |
| parentId | Hierarchy tracking | 9097 | Medium | Maintain workflow relationships |
| realmId | Realm assignment | 79 | Medium | Configure realm access |
| tags | Categorization | [2, 12] | Low | Implement tagging system |
| practiceArea | Business classification | 6 | Medium | Maintain practice area mapping |

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with topP: 0.95, temperature: 0.1, managerLlm configs | High | Configure workflow-level LLM settings |
| managerLlm | Not available | Detailed LLM configuration with maxIteration: 2018, maxExecutionTime: 727 | High | Implement manager LLM behavior |
| enableAgenticMemory | false (workflow level) | true (in workflowConfigs) | Medium | Validate memory functionality |

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agent count with naming convention updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_AbInitio_Document_To_PySpark_Code_Generator | DI AbInitio Document To PySpark | Renamed | Naming convention updated, underscores removed |
| DI_AbInitio_To_PySpark_Unit_Tester | DI AbInitio Document To PySpark Unit Tester | Renamed | Naming convention updated, underscores removed |
| DI_AbInitio_Document_To_PySpark_Reviewer | DI AbInitio Document To PySpark Reviewer | Renamed | Naming convention updated, underscores removed |

## 6. Agent Configuration Differences

### Agent: DI AbInitio Document To PySpark

#### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Medium | Validate masked content |
| expectedOutput | Present | Present | Low | No change |

#### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model reference |
| temperature | 0.10000000149011612 | 0.5 | High | Validate temperature impact on outputs |
| topP | 1.0 | 0.95 | Medium | Validate topP impact |
| maxToken | 32000 | Not Available | Medium | Verify token limit handling |
| maxIter | 0 | 330 | High | Validate iteration behavior |
| maxRpm | 0 | 20 | Medium | Configure rate limiting |
| maxExecutionTime | 0 | 410 | Medium | Configure timeout handling |

#### 6.1.3 Tools Comparison
Not Available

#### 6.1.4 Knowledge Base Comparison
Not Available

#### 6.1.5 Guardrails Comparison

| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-----------------|----------------|----------------|------------------|-----------------|
| guardrailIds | Not Available | [] | Low | No guardrails configured |

### Agent: DI AbInitio Document To PySpark Unit Tester

#### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Present | Low | No change |

#### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model reference |
| temperature | 0.10000000149011612 | 0.5 | High | Validate temperature impact |
| topP | 1.0 | 0.9 | Medium | Validate topP impact |
| maxToken | 32000 | Not Available | Medium | Verify token limit handling |
| maxIter | 0 | 4000 | High | Validate iteration behavior |
| maxRpm | 0 | 20 | Medium | Configure rate limiting |
| maxExecutionTime | 0 | 455 | Medium | Configure timeout handling |

#### 6.2.3 Tools Comparison
Not Available

#### 6.2.4 Knowledge Base Comparison
Not Available

#### 6.2.5 Guardrails Comparison

| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-----------------|----------------|----------------|------------------|-----------------|
| guardrailIds | Not Available | [] | Low | No guardrails configured |

### Agent: DI AbInitio Document To PySpark Reviewer

#### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Medium | Validate masked content |
| expectedOutput | Present | Present | Low | No change |

#### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model reference |
| temperature | 0.10000000149011612 | 0.6 | High | Validate temperature impact |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 32000 | Not Available | Medium | Verify token limit handling |
| maxIter | 0 | 8000 | High | Validate iteration behavior |
| maxRpm | 0 | 20 | Medium | Configure rate limiting |
| maxExecutionTime | 0 | 300 | Medium | Configure timeout handling |

#### 6.3.3 Tools Comparison
Not Available

#### 6.3.4 Knowledge Base Comparison
Not Available

#### 6.3.5 Guardrails Comparison

| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-----------------|----------------|----------------|------------------|-----------------|
| guardrailIds | Not Available | [] | Low | No guardrails configured |