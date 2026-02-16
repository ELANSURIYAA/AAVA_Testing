# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 78%
**Total Agents Compared:** 2

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_OptimizeTSQLScript | 76% | Medium | Model changed from claude-4-sonnet to gpt-4.1, maxExecutionTime reduced from 300 to 90, role/goal/backstory removed | Validate model compatibility and runtime behavior |
| DI__AnalyzeErrorLog | 80% | Medium | Model changed from claude-4-sonnet to gpt-4.1, maxExecutionTime reduced from 300 to 90, role/goal/backstory removed | Validate model compatibility and runtime behavior |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI__AnalyzeErrorLog
**Workflow Name (AAVA 2.0):** DI  AnalyzeErrorLog

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 7817 | id | 2467 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to use new ID |
| Naming | name | DI__AnalyzeErrorLog | name | DI  AnalyzeErrorLog | Matched (Normalized) | Minor spacing difference normalized | Low | No change |
| Description | description | To analyze input scripts... | description | To analyze input scripts... | Matched | Same description content | Low | No change |
| Audit | createdAt | 2025-10-26T17:29:17.303+00:00 | createdAt | 2025-11-05T11:00:46.728947 | Matched | Different timestamps as expected | Low | No change |
| Agents List | pipeLineAgents | [2 agents] | workflowAgents | [2 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure enhanced | Medium | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Update memory configuration references |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organizational metadata removed | High | Implement alternative org tracking |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organizational ID removed | High | Implement alternative org ID tracking |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | High | Implement alternative domain tracking |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | High | Implement alternative domain ID tracking |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | High | Implement alternative project tracking |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | High | Implement alternative project ID tracking |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | High | Implement alternative team tracking |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | High | Implement alternative team ID tracking |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Update level tracking mechanism |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | dipali.nale@ascendion.com | Medium | Implement user tracking |
| modifiedBy | User who last modified workflow | dipali.nale@ascendion.com | Medium | Implement modification tracking |
| approvedBy | User who approved workflow | dipali.nale@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T11:00:47.788082 | Medium | Implement approval tracking |
| status | Workflow approval state | APPROVED | High | Ensure workflow lifecycle management |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete handling |
| parentId | Parent workflow reference | -1 | Medium | Handle workflow versioning |
| realmId | Realm/tenant identifier | 32 | High | Implement multi-tenancy support |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | High | Configure workflow-level LLM settings |
| managerLlm | Not available | Empty object {} | Medium | Define manager LLM configuration |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update memory configuration access |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 2
**AAVA 2.0 total agents:** 2
**Coverage:** Same agents with structural changes

### 5.2 Agent Name Mapping
| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_OptimizeTSQLScript | DI OptimizeTSQLScript | Renamed | Underscore removed |
| DI__AnalyzeErrorLog | DI  AnalyzeErrorLog | Renamed | Double underscore to double space |

---

## 6. Agent Configuration Differences

## Agent: DI_OptimizeTSQLScript

### 6.1.1 Agent Instructions Comparison
| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing role field or confirm deprecation |
| goal | Present | Not Present | High | Add missing goal field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing backstory field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing expectedOutput field or confirm deprecation |

### 6.1.2 LLM Configuration Comparison
| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | anthropic.claude-4-sonnet | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision difference |
| topP | 0.949999988079071 | 0.94 | Low | Normalized precision difference |
| maxToken | 24000 | 24000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 300 | 90 | High | Validate timeout impact |

### 6.1.3 Tools Comparison
| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| userTools | 2 tools present | Not Present | High | Migrate tool configurations |
| DI_Github_File_Writer_Z | Present | Not Present | High | Ensure tool availability |
| DI_GitHub_File_Reader_Z | Present | Not Present | High | Ensure tool availability |

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: DI__AnalyzeErrorLog

### 6.2.1 Agent Instructions Comparison
| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing role field or confirm deprecation |
| goal | Present | Not Present | High | Add missing goal field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing backstory field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing expectedOutput field or confirm deprecation |

### 6.2.2 LLM Configuration Comparison
| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | anthropic.claude-4-sonnet | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized precision difference |
| topP | 0.949999988079071 | 0.94 | Low | Normalized precision difference |
| maxToken | 4500 | 4500 | Low | No change |
| maxIter | 10 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 300 | 90 | High | Validate timeout impact |

### 6.2.3 Tools Comparison
| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| userTools | 2 tools present | Not Present | High | Migrate tool configurations |
| DI_Github_File_Writer_Z | Present | Not Present | High | Ensure tool availability |
| DI_GitHub_File_Reader_Z | Present | Not Present | High | Ensure tool availability |

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available