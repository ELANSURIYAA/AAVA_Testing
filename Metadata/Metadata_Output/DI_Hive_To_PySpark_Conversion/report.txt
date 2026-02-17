# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 74%
**Total Agents Compared:** 5

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_Hive_to_PySpark_Conversion | 68% | Medium | Model changed, maxExecutionTime reduced, role/goal/backstory removed | Validate runtime behavior and instruction completeness |
| DI_Hive_to_PySpark_UnitTest | 72% | Medium | Model changed, maxExecutionTime reduced, role/goal/backstory removed | Validate runtime behavior and instruction completeness |
| DI_Hive_to_PySpark_Conversion_Tester | 76% | Medium | Model changed, maxExecutionTime reduced, role/goal/backstory removed | Validate runtime behavior and instruction completeness |
| DI_Hive_to_PySpark_ReconTest | 78% | Medium | Model changed, maxExecutionTime reduced, role/goal/backstory removed | Validate runtime behavior and instruction completeness |
| DI_Hive_to_PySpark_Reviewer | 76% | Medium | Model changed, maxExecutionTime reduced, role/goal/backstory removed | Validate runtime behavior and instruction completeness |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_Hive_To_PySpark_Conversion
**Workflow Name (AAVA 2.0):** DI Hive To PySpark Conversion

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 6060 | id | 2100 | Renamed + Modified | Pipeline ID changed from 6060 to 2100 | High | Update all references to new workflow ID |
| Naming | name | DI_Hive_To_PySpark_Conversion | name | DI Hive To PySpark Conversion | Matched (Normalized) | Minor formatting differences in name | Low | None |
| Description | description | Conversion of the Hive SQL the equal PySpark Code | description | Conversion of the Hive SQL the equal PySpark Code | Matched | Identical descriptions | Low | None |
| Audit | createdAt | 2025-08-14T10:48:44.335+00:00 | createdAt | 2025-11-05T10:47:05.485718 | Modified | Different creation timestamps | Medium | Verify workflow versioning |
| Agents List | pipeLineAgents | [5 agents] | workflowAgents | [5 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm, enableAgenticMemory} | Renamed + Modified | Enhanced configuration structure | Medium | Migrate callback configurations |
| Memory Config | enableAgenticMemory | false | workflowConfigs.enableAgenticMemory | false | Renamed + Matched (Normalized) | Moved to nested structure | Low | Update configuration paths |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm removal is acceptable |
| Domain Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal is acceptable |
| Project Metadata | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | elansuriyaa.p@ascendion.com | Medium | Ensure approval workflow is handled |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T10:47:06.675774 | Medium | Ensure approval workflow is handled |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure deletion handling is implemented |
| parentId | Parent workflow reference | -1 | Low | Validate workflow hierarchy |
| realmId | Realm identifier | 32 | Low | Validate realm assignment |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| managerLlm | Direct nested object | Moved to workflowConfigs.managerLlm | Medium | Update configuration access paths |
| workflowConfigs | Not available | Present with nested structure | Medium | Align configuration handling |
| enableAgenticMemory | Direct field | Moved to workflowConfigs | Low | Update configuration paths |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5
**AAVA 2.0 total agents:** 5
**Coverage:** Same agent count with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Hive_to_PySpark_Conversion | DI Hive to PySpark Conversion | Renamed | Naming convention updated |
| DI_Hive_to_PySpark_UnitTest | DI Hive to PySpark UnitTest | Renamed | Naming convention updated |
| DI_Hive_to_PySpark_Conversion_Tester | DI Hive to PySpark Conversion Tester | Renamed | Naming convention updated |
| DI_Hive_to_PySpark_ReconTest | DI Hive to PySpark ReconTest | Matched | No change |
| DI_Hive_to_PySpark_Reviewer | DI Hive to PySpark Reviewer | Renamed | Naming convention updated |

---

## 6. Agent Configuration Differences

## Agent: DI Hive to PySpark Conversion

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
| temperature | 0.10000000149011612 | 0.1 | Low | No change |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 400 | 90 | High | Validate timeout behavior |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | [DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z] | [] | High | Validate tool availability |

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

## Agent: DI Hive to PySpark UnitTest

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
| temperature | 0.10000000149011612 | 0.1 | Low | No change |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 10 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 400 | 90 | High | Validate timeout behavior |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | [DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z] | [] | High | Validate tool availability |

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

## Agent: DI Hive to PySpark Conversion Tester

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
| temperature | 0.10000000149011612 | 0.1 | Low | No change |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 400 | 90 | High | Validate timeout behavior |

### 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | [DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z] | [] | High | Validate tool availability |

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available

## Agent: DI Hive to PySpark ReconTest

### 6.4.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.4.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | anthropic.claude-4-sonnet | model | High | Validate model compatibility |
| temperature | 0.10000000149011612 | 0.1 | Low | No change |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 400 | 90 | High | Validate timeout behavior |

### 6.4.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | [DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z] | [] | High | Validate tool availability |

### 6.4.4 Knowledge Base Comparison

Not Available

### 6.4.5 Guardrails Comparison

Not Available

## Agent: DI Hive to PySpark Reviewer

### 6.5.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.5.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | anthropic.claude-4-sonnet | model | High | Validate model compatibility |
| temperature | 0.10000000149011612 | 0.1 | Low | No change |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 10 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 400 | 90 | High | Validate timeout behavior |

### 6.5.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No change |
| userTools | [DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z] | [] | High | Validate tool availability |

### 6.5.4 Knowledge Base Comparison

Not Available

### 6.5.5 Guardrails Comparison

Not Available

Now I need to create the CSV file with the required format and upload both files to GitHub:

Action: GitHub File Writer Tool
Action Input: {"repo": "ELANSURIYAA/AAVA_Testing", "branch": "main", "token": "<REDACTED_GITHUB_TOKEN>", "folder_name": "Metadata/Metadata_Output", "file_name": "DI_Hive_To_PySpark_Conversion/DI_Hive_To_PySpark_Conversion_comparison.csv", "content": "Workflow Comparison Score,Total Agents Compared
74%,5

Agent Name,Agent Score,Risk Level,Key Score Drivers,Migration Action Required
DI Hive to PySpark Conversion,68%,Medium,Model changed maxExecutionTime reduced role/goal/backstory removed,Validate runtime behavior and instruction completeness
DI Hive to PySpark UnitTest,72%,Medium,Model changed maxExecutionTime reduced role/goal/backstory removed,Validate runtime behavior and instruction completeness
DI Hive to PySpark Conversion Tester,76%,Medium,Model changed maxExecutionTime reduced role/goal/backstory removed,Validate runtime behavior and instruction completeness
DI Hive to PySpark ReconTest,78%,Medium,Model changed maxExecutionTime reduced role/goal/backstory removed,Validate runtime behavior and instruction completeness
DI Hive to PySpark Reviewer,76%,Medium,Model changed maxExecutionTime reduced role/goal/backstory removed,Validate runtime behavior and instruction completeness"}