# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 78%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_Hive_Documentation | 82% | Medium | role/goal/backstory removed, model changed | Validate instruction completeness and model behavior |
| DI_Hive_to_PySpark_Analyze | 81% | Medium | role/goal/backstory removed, model changed | Validate instruction completeness and model behavior |
| DI_Hive_to_PySpark_Plan | 71% | Medium | role/goal/backstory removed, model changed, maxIter/maxRpm removed | Validate instruction completeness, model behavior, and runtime limits |

---

**Workflow Name (AAVA 1.0):** DI_Hive_to_PySpark_Doc&Analyze
**Workflow Name (AAVA 2.0):** DI Hive to PySpark Doc&Analyze

## 2. Workflow-Level Comparison

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1354 | id | 1924 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | DI_Hive_to_PySpark_Doc&Analyze | name | DI Hive to PySpark Doc&Analyze | Matched (Case Normalization) | Minor spacing difference | Low | No change needed |
| Description | description | Hive code to PySpark Documentation , Analyze and Plan | description | Hive code to PySpark Documentation , Analyze and Plan | Matched | Values identical | Low | No change needed |
| Audit | createdAt | 2025-08-13T10:41:02.316+00:00 | createdAt | 2025-11-05T10:40:20.633636 | Modified | Different creation timestamps | Low | Expected for different instances |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed but same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure changed | High | Implement new config structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Update config location |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm removal acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm removal acceptable |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal acceptable |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm removal acceptable |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal acceptable |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm removal acceptable |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm removal acceptable |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm removal acceptable |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm removal acceptable |

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User tracking | default@ascendion.com | Medium | Implement user tracking |
| modifiedBy | Change tracking | default@ascendion.com | Medium | Implement change tracking |
| approvedBy | Approval tracking | default@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T10:40:21.844510 | Low | Standard audit field |
| status | Workflow state | APPROVED | High | Implement workflow lifecycle |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete logic |
| parentId | Hierarchy tracking | -1 | Low | Standard hierarchy field |
| realmId | Multi-tenancy | 1 | Medium | Implement realm-based access |

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|---------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | High | Implement new config structure |
| managerLlm | Not available | Empty object array | Medium | Define manager LLM configuration |
| enableAgenticMemory | Top-level field | Nested in workflowConfigs | Medium | Update config location |

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Hive_Documentation | DI Hive Documentation | Matched (Case Normalization) | Underscore to space |
| DI_Hive_to_PySpark_Analyze | DI Hive to PySpark Analyze | Matched (Case Normalization) | Underscore to space |
| DI_Hive_to_PySpark_Plan | DI Hive to PySpark Plan | Matched (Case Normalization) | Underscore to space |

## 6. Agent Configuration Differences

## Agent: DI_Hive_Documentation

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | anthropic.claude-4-sonnet | model | High | Validate model compatibility |
| temperature | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 25 | Not Present | Medium | Validate removal acceptable |
| maxRpm | 50 | Not Present | Medium | Validate removal acceptable |
| maxExecutionTime | 300 | 90 | Medium | Validate timeout reduction |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | 2 tools present | Not Present | High | Validate tool removal |

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI_Hive_to_PySpark_Analyze

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | anthropic.claude-4-sonnet | model | High | Validate model compatibility |
| temperature | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 20 | Not Present | Medium | Validate removal acceptable |
| maxRpm | 50 | Not Present | Medium | Validate removal acceptable |
| maxExecutionTime | 300 | 90 | Medium | Validate timeout reduction |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | 2 tools present | Not Present | High | Validate tool removal |

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DI_Hive_to_PySpark_Plan

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | anthropic.claude-4-sonnet | model | High | Validate model compatibility |
| temperature | 0.10000000149011612 | 0.1 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 25 | Not Present | Medium | Validate removal acceptable |
| maxRpm | 50 | Not Present | Medium | Validate removal acceptable |
| maxExecutionTime | 300 | 90 | Medium | Validate timeout reduction |

### 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | 2 tools present | Not Present | High | Validate tool removal |

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available

Now I'll create the CSV file with the required format:

Action: GitHub File Writer Tool
Action Input: {"repo": "ELANSURIYAA/AAVA_Testing", "branch": "main", "token": "<REDACTED_GITHUB_TOKEN>", "folder_name": "Metadata/Metadata_Output", "file_name": "DI_Hive_to_PySpark_DocAnalyze/DI_Hive_to_PySpark_DocAnalyze_comparison.csv", "content": "Workflow Comparison Score,Total Agents Compared
78%,3

Agent Name,Agent Score,Risk Level,Key Score Drivers,Migration Action Required
DI_Hive_Documentation,82%,Medium,role/goal/backstory removed; model changed,Validate instruction completeness and model behavior
DI_Hive_to_PySpark_Analyze,81%,Medium,role/goal/backstory removed; model changed,Validate instruction completeness and model behavior
DI_Hive_to_PySpark_Plan,71%,Medium,role/goal/backstory removed; model changed; maxIter/maxRpm removed,Validate instruction completeness and model behavior and runtime limits"}