# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 76%
**Total Agents Compared:** 5

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI SAS to Python Converter C | 82% | Medium | Model changed (gemini-2.5-pro to gpt-4.1), role/goal/backstory removed, maxRpm changed | Validate model behavior and confirm instruction field removal |
| SAS to Python Unit Tester | 74% | Medium | Model changed (claude-3.7sonnet to gpt-4.1), task description modified, maxToken changed | Validate model compatibility and task description changes |
| SAS to Python Conversion Tester | 78% | Medium | Model changed (gpt-4 to gpt-4.1), task description modified, maxToken changed | Validate model compatibility and task description changes |
| SAS to Python Recon Tester | 76% | Medium | Model changed (gpt-4 to gpt-4.1), task description modified, maxToken changed | Validate model compatibility and task description changes |
| SAS to Python Reviewer | 72% | Medium | Model changed (gpt-4 to gpt-4.1), task description modified, maxToken changed | Validate model compatibility and task description changes |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_SAS_To_Python_Conversion
**Workflow Name (AAVA 2.0):** DI SAS To Python Conversion

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 1443 | id | 2600 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_SAS_To_Python_Conversion | name | DI SAS To Python Conversion | Matched (Normalized) | Minor formatting difference | Low | No action required |
| Description | description | SAS to Python Conversion. | description | SAS to Python Conversion. | Matched | Exact match | Low | No action required |
| Audit | createdAt | 2025-05-12T06:15:42.917+00:00 | createdAt | 2025-11-05T11:07:28.724766 | Modified | Different creation timestamp | Low | Expected for new workflow version |
| Agents List | pipeLineAgents | [5 agents] | workflowAgents | [5 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm, enableAgenticMemory} | Renamed + Modified | Field renamed and structure changed | Medium | Validate new config structure |
| Memory Config | enableAgenticMemory | false | workflowConfigs.enableAgenticMemory | false | Renamed + Matched (Normalized) | Moved to nested structure | Low | Update config path |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm removal is acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm removal is acceptable |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal is acceptable |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm removal is acceptable |
| Project | project | Conversions | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal is acceptable |
| Project ID | projectId | 149 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm removal is acceptable |
| Team | team | DataEngineer | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm removal is acceptable |
| Team ID | teamId | 150 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm removal is acceptable |
| Level ID | levelId | 150 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Ensure proper user attribution |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Implement modification tracking |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Track modification history |
| approvedAt | Approval timestamp | 2025-11-05T11:07:29.798793 | Low | Track approval history |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete functionality |
| parentId | Parent workflow reference | -1 | Low | Support workflow versioning |
| realmId | Realm/tenant identifier | 1 | Medium | Support multi-tenancy |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| managerLlm | Direct object | Nested in workflowConfigs array | Medium | Update config access patterns |
| workflowConfigs | Not available | Present with nested structure | Medium | Align with new config structure |
| enableAgenticMemory | Direct field | Nested in workflowConfigs | Low | Update config path |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5
**AAVA 2.0 total agents:** 5
**Coverage:** Same agent count, names updated

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_SAS_to_Python_Converter_C | DI SAS to Python Converter C | Renamed | Naming convention updated |
| SAS_to_Python_Unit_Tester | SAS to Python Unit Tester | Renamed | Naming convention updated |
| SAS_to_Python_Conversion_Tester | SAS to Python Conversion Tester | Renamed | Naming convention updated |
| SAS_to_Python_Recon_Tester | SAS to Python Recon Tester | Renamed | Naming convention updated |
| SAS_to_Python_Reviewer | SAS to Python Reviewer | Renamed | Naming convention updated |

---

## 6. Agent Configuration Differences

## Agent: DI SAS to Python Converter C

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Present | Low | No change |

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model compatibility |
| model | gemini-2.5-pro | model | High | Validate model configuration |
| temperature | 0.1 | 0.1 | Low | No change |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 64000 | Not Available | Medium | Validate token limits |
| maxIter | 0 | 10 | Medium | Validate iteration limits |
| maxRpm | 0 | 60 | Medium | Validate rate limits |
| maxExecutionTime | 0 | 90 | Medium | Validate execution timeouts |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison

| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------------|----------------|----------------|------------------|-----------------|
| guardrailIds | Not Available | [] | Low | No guardrails configured |

---

## Agent: SAS to Python Unit Tester

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Medium | Task description modified |
| expectedOutput | Present | Not Present | Medium | Add missing field or confirm deprecation |

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | anthropic.claude-3-7-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | claude-3.7sonnet | model | High | Validate model configuration |
| temperature | 0.3 | 0.3 | Low | No change |
| topP | 0.96 | 0.94 | Low | Minor adjustment |
| maxToken | 30000 | 4000 | High | Validate token limits |
| maxIter | 0 | Not Available | Medium | Validate iteration configuration |
| maxRpm | 0 | Not Available | Medium | Validate rate limit configuration |
| maxExecutionTime | 0 | 90 | Medium | Validate execution timeouts |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: SAS to Python Conversion Tester

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Medium | Task description modified |
| expectedOutput | Present | Not Present | Medium | Add missing field or confirm deprecation |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model configuration |
| temperature | 0.3 | 0.3 | Low | No change |
| topP | 0.95 | 0.94 | Low | Minor adjustment |
| maxToken | 30000 | 8000 | High | Validate token limits |
| maxIter | 0 | Not Available | Medium | Validate iteration configuration |
| maxRpm | 0 | Not Available | Medium | Validate rate limit configuration |
| maxExecutionTime | 0 | 90 | Medium | Validate execution timeouts |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available

---

## Agent: SAS to Python Recon Tester

### 6.4.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Medium | Task description modified |
| expectedOutput | Present | Not Present | Medium | Add missing field or confirm deprecation |

### 6.4.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model configuration |
| temperature | 0.3 | 0.3 | Low | No change |
| topP | 0.95 | 0.94 | Low | Minor adjustment |
| maxToken | 30000 | 4000 | High | Validate token limits |
| maxIter | 0 | Not Available | Medium | Validate iteration configuration |
| maxRpm | 0 | Not Available | Medium | Validate rate limit configuration |
| maxExecutionTime | 0 | 90 | Medium | Validate execution timeouts |

### 6.4.3 Tools Comparison
Not Available

### 6.4.4 Knowledge Base Comparison
Not Available

### 6.4.5 Guardrails Comparison
Not Available

---

## Agent: SAS to Python Reviewer

### 6.5.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Medium | Task description modified |
| expectedOutput | Present | Not Present | Medium | Add missing field or confirm deprecation |

### 6.5.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model configuration |
| temperature | 0.3 | 0.3 | Low | No change |
| topP | 0.95 | 0.94 | Low | Minor adjustment |
| maxToken | 10000 | 4000 | High | Validate token limits |
| maxIter | 0 | Not Available | Medium | Validate iteration configuration |
| maxRpm | 0 | Not Available | Medium | Validate rate limit configuration |
| maxExecutionTime | 0 | 90 | Medium | Validate execution timeouts |

### 6.5.3 Tools Comparison
Not Available

### 6.5.4 Knowledge Base Comparison
Not Available

### 6.5.5 Guardrails Comparison
Not Available