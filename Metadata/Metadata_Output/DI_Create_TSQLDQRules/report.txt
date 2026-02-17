# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 78%
**Total Agents Compared:** 2

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_DetermineDQRulesFromInstructions | 75% | Medium | Model changed, role/goal/backstory removed, tools removed | Validate model behavior and confirm instruction field removal |
| DI_ Create_T-SQLDQRules | 76% | Medium | Model changed, role/goal/backstory removed | Validate model behavior and confirm instruction field removal |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_ Create_T-SQLDQRules
**Workflow Name (AAVA 2.0):** DI  Create T-SQLDQRules

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 7414 | id | 2359 | Renamed + Modified | Field renamed and value changed | High | Update references to new workflow ID |
| Naming | name | DI_ Create_T-SQLDQRules | name | DI  Create T-SQLDQRules | Matched (Normalized) | Minor spacing differences | Low | No change |
| Description | description | Determine the data quality rules and create T-SQL Procs | description | Determine the data quality rules and create T-SQL Procs | Matched | Exact match | Low | No change |
| Audit | createdAt | 2025-10-09T05:30:10.886+00:00 | createdAt | 2025-11-05T10:56:50.909826 | Modified | Different creation timestamp | Medium | Verify workflow versioning |
| Agents List | pipeLineAgents | [2 agents] | workflowAgents | [2 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update agent references |
| Workflow Config | callbacks | [] | workflowConfigs | {"managerLlm":[{}],"enableAgenticMemory":false} | Renamed + Modified | Field renamed and structure changed | High | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Verify memory configuration |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | Low | Confirm removal is acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organizational ID removed | Low | Confirm removal is acceptable |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Low | Confirm removal is acceptable |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Low | Confirm removal is acceptable |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Low | Confirm removal is acceptable |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Low | Confirm removal is acceptable |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Low | Confirm removal is acceptable |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Low | Confirm removal is acceptable |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Low | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | muneeswara.pandian@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | muneeswara.pandian@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | muneeswara.pandian@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T10:56:52.115859 | Medium | Ensure approval tracking is implemented |
| status | Workflow approval state | APPROVED | High | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete functionality is implemented |
| parentId | Parent workflow reference | -1 | Low | Understand workflow hierarchy |
| realmId | Realm identifier | 32 | Low | Understand realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | High | Configure manager LLM settings |
| managerLlm | Not available | Empty object {} | Medium | Define manager LLM configuration |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Verify memory configuration structure |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 2
**AAVA 2.0 total agents:** 2
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_DetermineDQRulesFromInstructions | DI DetermineDQRulesFromInstructions | Renamed | Underscore removed |
| DI_ Create_T-SQLDQRules | DI  Create T-SQLDQRules | Renamed | Spacing normalized |

---

## 6. Agent Configuration Differences

## Agent: DI_DetermineDQRulesFromInstructions

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model behavior change |
| model | anthropic.claude-4-sonnet | model | High | Validate model behavior change |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 24000 | 24000 | Low | No change |
| maxIter | 0 | null | Medium | Verify null handling vs zero |
| maxRpm | 0 | null | Medium | Verify null handling vs zero |
| maxExecutionTime | 300 | 90 | High | Validate timeout reduction impact |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| userTools | 2 tools (DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z) | Empty array | High | Add missing tools or confirm removal |
| tools | Empty array | Empty array | Low | No change |

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI_ Create_T-SQLDQRules

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model behavior change |
| model | gemini-2.5-pro | model | High | Validate model behavior change |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 12000 | 12000 | Low | No change |
| maxIter | 0 | null | Medium | Verify null handling vs zero |
| maxRpm | 0 | null | Medium | Verify null handling vs zero |
| maxExecutionTime | 300 | 90 | High | Validate timeout reduction impact |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| userTools | Empty array | Empty array | Low | No change |
| tools | Empty array | Empty array | Low | No change |

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

Now I'll generate the CSV file with the required format:

Action: GitHub File Writer Tool
Action Input: {"repo": "ELANSURIYAA/AAVA_Testing", "branch": "main", "token": "<REDACTED_GITHUB_TOKEN>", "folder_name": "Metadata/Metadata_Output", "file_name": "DI_Create_TSQLDQRules/DI_Create_TSQLDQRules_comparison.csv", "content": "Workflow Comparison Score,Total Agents Compared
78%,2

Agent Name,Agent Score,Risk Level,Key Score Drivers,Migration Action Required
DI_DetermineDQRulesFromInstructions,75%,Medium,Model changed from Anthropic Claude to GPT-4.1; role/goal/backstory removed; tools removed; maxExecutionTime reduced,Validate model behavior and confirm instruction field removal
DI_ Create_T-SQLDQRules,76%,Medium,Model changed from Gemini 2.5 Pro to GPT-4.1; role/goal/backstory removed; maxExecutionTime reduced,Validate model behavior and confirm instruction field removal"}