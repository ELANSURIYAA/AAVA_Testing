# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 78%**
**Total Agents Compared: 3**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| Snowflake to PySpark Documentation | 85% | Low | Model changed, role/goal/backstory removed, description matched | Validate new model behavior, confirm instruction field removal |
| Snowflake to PySpark Analysis | 85% | Low | Model changed, role/goal/backstory removed, description matched | Validate new model behavior, confirm instruction field removal |
| Snowflake to PySpark Plan | 85% | Low | Model changed, role/goal/backstory removed, description matched | Validate new model behavior, confirm instruction field removal |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** Snowflake_to_PySpark_Doc&Analyse
**Workflow Name (AAVA 2.0):** Snowflake to PySpark Doc&Analyse

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1027 | id | 3405 | Renamed + Modified | Pipeline ID changed from 1027 to 3405 | Medium | Update references to new workflow ID |
| Naming | name | Snowflake_to_PySpark_Doc&Analyse | name | Snowflake to PySpark Doc&Analyse | Matched (Normalized) | Name normalized (underscores to spaces) | Low | No change |
| Description | description | Detailed Documentation, Analysis and Plan for Snowflake to PySpark | description | Detailed Documentation, Analysis and Plan for Snowflake to PySpark | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-03-12T09:47:02.494+00:00 | createdAt | 2025-11-05T11:30:47.715379 | Matched | Different timestamps (expected for different instances) | Low | No change |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {"managerLlm": [{}], "enableAgenticMemory": false} | Renamed + Modified | Enhanced configuration structure | Medium | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Low | Use workflowConfigs.enableAgenticMemory |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Handle org context externally |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Handle org ID externally |
| Domain | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | Medium | Handle domain context externally |
| Domain ID | domainId | 2 | Not Available | Not Available | Removed | Domain ID removed | Medium | Handle domain ID externally |
| Project | project | AVA | Not Available | Not Available | Removed | Project metadata removed | Medium | Handle project context externally |
| Project ID | projectId | 3 | Not Available | Not Available | Removed | Project ID removed | Medium | Handle project ID externally |
| Team | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | Medium | Handle team context externally |
| Team ID | teamId | 4 | Not Available | Not Available | Removed | Team ID removed | Medium | Handle team ID externally |
| Level ID | levelId | 4 | Not Available | Not Available | Removed | Level ID removed | Medium | Handle level context externally |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Set appropriate user attribution |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Track modification history |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Automatic timestamp tracking |
| approvedAt | Approval timestamp | 2025-11-05T11:30:48.760636 | Medium | Track approval lifecycle |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Implement soft delete logic |
| parentId | Parent workflow reference | -1 | Low | Handle workflow hierarchy |
| realmId | Realm/tenant identifier | 1 | Medium | Configure multi-tenant support |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Configure workflow-level LLM settings |
| managerLlm | Not available | Empty object {} | Medium | Define manager LLM configuration |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Low | Update configuration path |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents with naming normalization

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| Snowflake_to_PySpark_Documentation | Snowflake to PySpark Documentation | Renamed | Naming convention updated (underscores to spaces) |
| Snowflake_to_PySpark_Analysis | Snowflake to PySpark Analysis | Renamed | Naming convention updated (underscores to spaces) |
| Snowflake_to_PySpark_Plan | Snowflake to PySpark Plan | Renamed | Naming convention updated (underscores to spaces) |

---

## 6. Agent Configuration Differences

## Agent: Snowflake to PySpark Documentation

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
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate new model compatibility |
| model | gpt-4o | model | High | Verify model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision |
| topP | 0.949999988079071 | 0.94 | Low | Normalized precision |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Confirm iteration handling |
| maxRpm | 0 | Not Present | Medium | Confirm rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: Snowflake to PySpark Analysis

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
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate new model compatibility |
| model | gpt-4o | model | High | Verify model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision |
| topP | 0.949999988079071 | 0.94 | Low | Normalized precision |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Confirm iteration handling |
| maxRpm | 0 | Not Present | Medium | Confirm rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: Snowflake to PySpark Plan

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
| modelDeploymentName | gpt-4o | gpt-4.1 | Medium | Validate new model compatibility |
| model | gpt-4o | model | High | Verify model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision |
| topP | 0.949999988079071 | 0.94 | Low | Normalized precision |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Confirm iteration handling |
| maxRpm | 0 | Not Present | Medium | Confirm rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Validate timeout configuration |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available

Now I'll create the CSV file with the required format:

Action: GitHub File Writer Tool
Action Input: {"repo": "ELANSURIYAA/AAVA_Testing", "branch": "main", "token": "<REDACTED_GITHUB_TOKEN>", "folder_name": "Metadata/Metadata_Output", "file_name": "Snowflake_to_PySpark_DocAnalyse/Snowflake_to_PySpark_DocAnalyse_comparison.csv", "content": "Workflow Comparison Score,Total Agents Compared
78%,3

Agent Name,Agent Score,Risk Level,Key Score Drivers,Migration Action Required
Snowflake to PySpark Documentation,85%,Low,Model changed gpt-4o to gpt-4.1; role/goal/backstory removed; description matched,Validate new model behavior and confirm instruction field removal
Snowflake to PySpark Analysis,85%,Low,Model changed gpt-4o to gpt-4.1; role/goal/backstory removed; description matched,Validate new model behavior and confirm instruction field removal
Snowflake to PySpark Plan,85%,Low,Model changed gpt-4o to gpt-4.1; role/goal/backstory removed; description matched,Validate new model behavior and confirm instruction field removal"}