# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 84%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| SNOWFLAKE DOCUMENTATION | 88% | Medium | Model changed (gpt-4o to gpt-4.1), role/goal/backstory removed, expectedOutput format modified | Validate model behavior, confirm instruction field removal acceptable |
| SNOWFLAKE TO BIGQUERY ANALYZER | 84% | Medium | Model changed (claude-3.5-sonnet to gpt-4.1), role/goal/backstory removed, name normalized | Validate model behavior, confirm instruction field removal acceptable |
| SNOWFLAKE TO BIGQUERY PLAN | 80% | Medium | Model changed (gpt-4o to gpt-4.1), role/goal/backstory removed | Validate model behavior, confirm instruction field removal acceptable |

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** Snowflake_To_Bigquery_Doc_&_Analyze
**Workflow Name (AAVA 2.0):** Snowflake To Bigquery Doc & Analyze

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 1118 | id | 3879 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | Snowflake_To_Bigquery_Doc_&_Analyze | name | Snowflake To Bigquery Doc & Analyze | Matched (Normalized) | Minor formatting differences | Low | No change needed |
| Description | description | Snowflake_To_Bigquery_Doc_&_Analyze | description | Snowflake_To_Bigquery_Doc_&_Analyze | Matched | Exact match | Low | No change needed |
| Audit | createdAt | 2025-03-18T08:50:09.881+00:00 | createdAt | 2025-11-05T11:45:07.405538 | Matched | Field exists in both, different timestamps | Low | No change needed |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update references to new field name |
| Workflow Config | callbacks | [] | workflowConfigs | {"managerLlm":[{}],"enableAgenticMemory":false} | Renamed + Modified | Field renamed and structure changed | High | Migrate callback logic to workflowConfigs |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Confirm memory config location |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | Medium | Confirm org metadata removal acceptable |
| Domain Metadata | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm domain metadata removal acceptable |
| Project Metadata | project | AVA | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm project metadata removal acceptable |

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T11:45:08.457073 | Low | Standard audit field |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Standard deletion handling |
| parentId | Parent workflow reference | -1 | Low | Standard hierarchy field |
| realmId | Realm/tenant identifier | 1 | Medium | Ensure multi-tenancy is handled |

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | callbacks: [] | managerLlm: [{}], enableAgenticMemory: false | High | Migrate callback logic to new structure |
| Memory Management | enableAgenticMemory: false | workflowConfigs.enableAgenticMemory: false | Medium | Update memory config references |

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| SNOWFLAKE DOCUMENTATION | SNOWFLAKE DOCUMENTATION | Matched | Exact match |
| SNOWFLAKE_TO_BIGQUERY_ANALYZER | SNOWFLAKE TO BIGQUERY ANALYZER | Matched (Normalized) | Underscore to space conversion |
| SNOWFLAKE_TO_BIGQUERY_PLAN | SNOWFLAKE TO BIGQUERY PLAN | Matched (Normalized) | Underscore to space conversion |

## 6. Agent Configuration Differences

### Agent: SNOWFLAKE DOCUMENTATION

#### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Present | Low | No change |

#### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model behavior compatibility |
| model | gpt-4o | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Confirm field removal acceptable |
| maxRpm | 0 | Not Available | Medium | Confirm field removal acceptable |
| maxExecutionTime | 0 | 90 | Medium | Execution time limit added |

#### 6.1.3 Tools Comparison
Not Available

#### 6.1.4 Knowledge Base Comparison
Not Available

#### 6.1.5 Guardrails Comparison
Not Available

### Agent: SNOWFLAKE TO BIGQUERY ANALYZER

#### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | Medium | Add missing field or confirm removal |

#### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-3-5-sonnet | gpt-4.1 | High | Major model change - validate behavior |
| model | claude-3.5-sonnet | model | High | Model type change from Claude to GPT |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Confirm field removal acceptable |
| maxRpm | 0 | Not Available | Medium | Confirm field removal acceptable |
| maxExecutionTime | 0 | 90 | Medium | Execution time limit added |

#### 6.2.3 Tools Comparison
Not Available

#### 6.2.4 Knowledge Base Comparison
Not Available

#### 6.2.5 Guardrails Comparison
Not Available

### Agent: SNOWFLAKE TO BIGQUERY PLAN

#### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | Medium | Add missing field or confirm removal |

#### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model behavior compatibility |
| model | gpt-4o | model | High | Validate model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Confirm field removal acceptable |
| maxRpm | 0 | Not Available | Medium | Confirm field removal acceptable |
| maxExecutionTime | 0 | 90 | Medium | Execution time limit added |

#### 6.3.3 Tools Comparison
Not Available

#### 6.3.4 Knowledge Base Comparison
Not Available

#### 6.3.5 Guardrails Comparison
Not Available

**File successfully uploaded to:** Metadata/Metadata_Output/Snowflake_To_Bigquery_Doc_Analyze/Snowflake_To_Bigquery_Doc_Analyze_comparison.csv