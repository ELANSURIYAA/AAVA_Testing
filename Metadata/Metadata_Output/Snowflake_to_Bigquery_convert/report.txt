# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 82%**
**Total Agents Compared: 5**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| SNOWFLAKE DOCUMENTATION | 85% | Medium | Model deployment changed from gpt-4o to gpt-4.1; role/goal/backstory removed; maxToken changed from 4000 to string "4000" | Validate model compatibility and confirm instruction field removal |
| SNOWFLAKE TO BIGQUERY UNIT TESTER | 88% | Medium | Model deployment changed from gpt-4o to gpt-4.1; role/goal/backstory removed; maxToken changed from 4000 to string "4000" | Validate model compatibility and confirm instruction field removal |
| SNOWFLAKE TO BIGQUERY CONVERSION TESTER | 88% | Medium | Model deployment changed from gpt-4o to gpt-4.1; role/goal/backstory removed; maxToken changed from 4000 to string "4000" | Validate model compatibility and confirm instruction field removal |
| SNOWFLAKE TO BIGQUERY RECON TESTER | 75% | Medium | Agent name changed from SNOWFLAKE_TO_BIGQUERY_RECON_TESTER to SNOWFLAKE TO BIGQUERY RECON TESTER; model deployment changed; role/goal/backstory removed | Validate naming convention and model compatibility |
| SNOWFLAKE TO BIGQUERY REVIEWER | 74% | Medium | Agent name changed from SNOWFLAKE_TO_BIGQUERY_REVIEWER to SNOWFLAKE TO BIGQUERY REVIEWER; model deployment changed; role/goal/backstory removed; levelId changed from 4 to 152 | Validate naming convention and levelId impact |

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** Snowflake to Bigquery convert
**Workflow Name (AAVA 2.0):** Snowflake to Bigquery convert

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 1116 | id | 3234 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to use new ID |
| Naming | name | Snowflake to Bigquery convert | name | Snowflake to Bigquery convert | Matched | Workflow name unchanged | Low | No change |
| Description | description | Snowflake to Bigquery convert | description | Snowflake to Bigquery convert | Matched | Description unchanged | Low | No change |
| Audit | createdAt | 2025-04-01T06:21:24.617+00:00 | createdAt | 2025-11-05T11:25:16.559719 | Modified | Creation timestamp differs | Low | Expected for new workflow version |
| Agents List | pipeLineAgents | Array of 5 agents | workflowAgents | Array of 5 agents | Renamed + Matched (Normalized) | Field renamed but agent count preserved | Medium | Update field references |
| Workflow Config | callbacks | Empty array | workflowConfigs | Object with managerLlm and enableAgenticMemory | Renamed + Modified | Structure completely changed | High | Migrate configuration settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Verify memory config location |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Confirm removal is acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | High | Confirm removal is acceptable |
| Domain | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | High | Confirm removal is acceptable |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | High | Confirm removal is acceptable |
| Project | project | AVA | Not Available | Not Available | Removed | Project metadata removed | High | Confirm removal is acceptable |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | High | Confirm removal is acceptable |
| Team | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | High | Confirm removal is acceptable |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | High | Confirm removal is acceptable |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed from workflow level | Medium | Confirm removal is acceptable |

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-11-30T11:55:00.892060 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T11:25:17.622699 | Medium | Ensure approval process is implemented |
| status | Workflow approval state | APPROVED | High | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete handling |
| parentId | Parent workflow reference | -1 | Medium | Understand workflow hierarchy |
| realmId | Realm identifier | 1 | Medium | Understand multi-tenancy model |

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | High | Migrate to new config structure |
| managerLlm | Not available | Empty object array | Medium | Configure manager LLM settings |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update config access patterns |

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5
**AAVA 2.0 total agents:** 5
**Coverage:** Same agent count maintained

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| SNOWFLAKE DOCUMENTATION | SNOWFLAKE DOCUMENTATION | Matched | No change |
| SNOWFLAKE TO BIGQUERY UNIT TESTER | SNOWFLAKE TO BIGQUERY UNIT TESTER | Matched | No change |
| SNOWFLAKE TO BIGQUERY CONVERSION TESTER | SNOWFLAKE TO BIGQUERY CONVERSION TESTER | Matched | No change |
| SNOWFLAKE_TO_BIGQUERY_RECON_TESTER | SNOWFLAKE TO BIGQUERY RECON TESTER | Renamed | Underscore to space conversion |
| SNOWFLAKE_TO_BIGQUERY_REVIEWER | SNOWFLAKE TO BIGQUERY REVIEWER | Renamed | Underscore to space conversion |

## 6. Agent Configuration Differences

## Agent: SNOWFLAKE DOCUMENTATION

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model name mapping |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision difference acceptable |
| topP | 0.949999988079071 | 0.94 | Low | Precision difference acceptable |
| maxToken | 4000 | "4000" | Medium | Data type changed from int to string |
| maxIter | 0 | null | Medium | Default value representation changed |
| maxRpm | 0 | null | Medium | Default value representation changed |
| maxExecutionTime | 0 | 90 | High | Execution timeout significantly changed |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

## Agent: SNOWFLAKE TO BIGQUERY UNIT TESTER

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model name mapping |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision difference acceptable |
| topP | 0.949999988079071 | 0.94 | Low | Precision difference acceptable |
| maxToken | 4000 | "4000" | Medium | Data type changed from int to string |
| maxIter | 0 | null | Medium | Default value representation changed |
| maxRpm | 0 | null | Medium | Default value representation changed |
| maxExecutionTime | 0 | 90 | High | Execution timeout significantly changed |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

## Agent: SNOWFLAKE TO BIGQUERY CONVERSION TESTER

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model name mapping |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision difference acceptable |
| topP | 0.949999988079071 | 0.94 | Low | Precision difference acceptable |
| maxToken | 4000 | "4000" | Medium | Data type changed from int to string |
| maxIter | 0 | null | Medium | Default value representation changed |
| maxRpm | 0 | null | Medium | Default value representation changed |
| maxExecutionTime | 0 | 90 | High | Execution timeout significantly changed |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available

## Agent: SNOWFLAKE TO BIGQUERY RECON TESTER

### 6.4.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.4.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model name mapping |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision difference acceptable |
| topP | 0.949999988079071 | 0.94 | Low | Precision difference acceptable |
| maxToken | 4000 | "4000" | Medium | Data type changed from int to string |
| maxIter | 0 | null | Medium | Default value representation changed |
| maxRpm | 0 | null | Medium | Default value representation changed |
| maxExecutionTime | 0 | 90 | High | Execution timeout significantly changed |

### 6.4.3 Tools Comparison
Not Available

### 6.4.4 Knowledge Base Comparison
Not Available

### 6.4.5 Guardrails Comparison
Not Available

## Agent: SNOWFLAKE TO BIGQUERY REVIEWER

### 6.5.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.5.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Validate model name mapping |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision difference acceptable |
| topP | 0.949999988079071 | 0.94 | Low | Precision difference acceptable |
| maxToken | 4000 | "4000" | Medium | Data type changed from int to string |
| maxIter | 0 | null | Medium | Default value representation changed |
| maxRpm | 0 | null | Medium | Default value representation changed |
| maxExecutionTime | 0 | 90 | High | Execution timeout significantly changed |

### 6.5.3 Tools Comparison
Not Available

### 6.5.4 Knowledge Base Comparison
Not Available

### 6.5.5 Guardrails Comparison
Not Available

**CSV file successfully uploaded to:** Metadata/Metadata_Output/Snowflake_to_Bigquery_convert/Snowflake_to_Bigquery_convert_comparison.csv