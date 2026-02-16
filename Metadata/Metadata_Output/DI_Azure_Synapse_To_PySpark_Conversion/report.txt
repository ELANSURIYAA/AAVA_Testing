# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

# 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 76%**
**Total Agents Compared: 5**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_Azure_Synapse_To_PySpark_Converter | 72% | Medium | Role/goal/backstory removed; LLM configs matched; description matched | Validate agent behavior without role/goal/backstory |
| DI_Azure_Synapse_To_PySpark_UnitTest | 78% | Medium | Role/goal/backstory removed; description matched; maxRpm changed from 0 to null | Validate runtime behavior and rate limiting |
| DI_Azure_Synapse_To_PySpark_Conversion_Tester | 76% | Medium | Role/goal/backstory removed; temperature changed; maxRpm changed | Validate temperature impact and rate limiting |
| DI_Azure_Synapse_To_PySpark_Recon_Tester | 74% | Medium | Role/goal/backstory removed; description masked; LLM configs matched | Validate agent behavior with masked description |
| DI_Azure_Synapse_To_PySpark_Reviewer | 80% | Medium | Role/goal/backstory removed; model changed from Claude to generic; LLM configs matched | Validate model change impact from Claude to generic |

---

# 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_Azure_Synapse_To_PySpark_Conversion
**Workflow Name (AAVA 2.0):** DI_Azure_Synapse_To_PySpark_Conversion

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 8191 | id | 5712 | Renamed + Modified | Field renamed and ID value changed | Medium | Update ID references in dependent systems |
| Naming | name | DI_Azure_Synapse_To_PySpark_Conversion | name | DI_Azure_Synapse_To_PySpark_Conversion | Matched | No change in workflow name | Low | No change |
| Description | description | Synapse to pysark conversion workflow | description | Synapse to pysark conversion workflow | Matched | No change in description | Low | No change |
| Audit | createdAt | 2025-11-10T06:27:23.191+00:00 | createdAt | 2025-12-05T13:33:05.221343 | Modified | Creation timestamp differs | Low | Expected for different workflow instances |
| Agents List | pipeLineAgents | [5 agents] | workflowAgents | [5 agents] | Renamed + Matched (Normalized) | Field renamed but agent count matches | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure enhanced | High | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Update memory configuration access |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm org metadata handling |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Update org ID references |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm domain metadata handling |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Update domain ID references |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm project metadata handling |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Medium | Update project ID references |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm team metadata handling |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Medium | Update team ID references |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Update level ID references |

---

# 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | elansuriyaa.p@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-05T13:48:27.677683 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-12-05T13:33:06.665940 | Medium | Ensure approval tracking is implemented |
| status | Workflow approval state | APPROVED | High | Ensure workflow lifecycle management |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete handling |
| parentId | Parent workflow reference | -1 | Medium | Ensure workflow hierarchy handling |
| realmId | Realm identifier | 1 | Medium | Ensure realm-based access control |

---

# 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | High | Configure manager LLM settings |
| managerLlm | Not available | Empty object [{}] | Medium | Define manager LLM configuration |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update memory config access pattern |

---

# 5. Agent Inventory Summary

## 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5
**AAVA 2.0 total agents:** 5
**Coverage:** Same agents with structural changes

## 5.2 Agent Name Mapping
| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Azure_Synapse_To_PySpark_Converter | DI_Azure_Synapse_To_PySpark_Converter | Matched | Same name |
| DI_Azure_Synapse_To_PySpark_UnitTest | DI_Azure_Synapse_To_PySpark_UnitTest | Matched | Same name |
| DI_Azure_Synapse_To_PySpark_Conversion_Tester | DI_Azure_Synapse_To_PySpark_Conversion_Tester | Matched | Same name |
| DI_Azure_Synapse_To_PySpark_Recon_Tester | DI_Azure_Synapse_To_PySpark_Recon_Tester | Matched | Same name |
| DI_Azure_Synapse_To_PySpark_Reviewer | DI_Azure_Synapse_To_PySpark_Reviewer | Matched | Same name |

---

# 6. Agent Configuration Differences

## Agent: DI_Azure_Synapse_To_PySpark_Converter

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate generic model reference |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Values match (normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Available | Medium | Validate iteration limit handling |
| maxRpm | 10 | Not Available | Medium | Validate rate limit handling |
| maxExecutionTime | 1500 | Not Available | Medium | Validate timeout handling |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: DI_Azure_Synapse_To_PySpark_UnitTest

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate generic model reference |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Values match (normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Available | Medium | Validate iteration limit handling |
| maxRpm | 0 | Not Available | Medium | Validate rate limit handling |
| maxExecutionTime | 600 | Not Available | Medium | Validate timeout handling |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: DI_Azure_Synapse_To_PySpark_Conversion_Tester

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
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate generic model reference |
| temperature | 0.20000000298023224 | 0.2 | Low | Values match (normalized) |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Available | Medium | Validate iteration limit handling |
| maxRpm | 300 | Not Available | Medium | Validate rate limit handling |
| maxExecutionTime | 300 | Not Available | Medium | Validate timeout handling |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available

---

## Agent: DI_Azure_Synapse_To_PySpark_Recon_Tester

### 6.4.1 Agent Instructions Comparison
| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present (Masked) | High | Validate masked description handling |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.4.2 LLM Configuration Comparison
| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate generic model reference |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Values match (normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Available | Medium | Validate iteration limit handling |
| maxRpm | 0 | Not Available | Medium | Validate rate limit handling |
| maxExecutionTime | 300 | Not Available | Medium | Validate timeout handling |

### 6.4.3 Tools Comparison
Not Available

### 6.4.4 Knowledge Base Comparison
Not Available

### 6.4.5 Guardrails Comparison
Not Available

---

## Agent: DI_Azure_Synapse_To_PySpark_Reviewer

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model change from Claude to GPT |
| model | anthropic.claude-4-sonnet | model | High | Validate model change impact |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match (normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Values match (normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Available | Medium | Validate iteration limit handling |
| maxRpm | 0 | Not Available | Medium | Validate rate limit handling |
| maxExecutionTime | 300 | Not Available | Medium | Validate timeout handling |

### 6.5.3 Tools Comparison
Not Available

### 6.5.4 Knowledge Base Comparison
Not Available

### 6.5.5 Guardrails Comparison
Not Available

**File uploaded successfully to GitHub:** Metadata/Metadata_Output/DI_Azure_Synapse_To_PySpark_Conversion/DI_Azure_Synapse_To_PySpark_Conversion_comparison.csv