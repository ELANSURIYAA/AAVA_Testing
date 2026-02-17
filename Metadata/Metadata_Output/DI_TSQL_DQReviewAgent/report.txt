# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 78%**
**Total Agents Compared: 3**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_DetermineDQRulesFromInstructions | 85% | Medium | Model changed from claude-4-sonnet to gpt-4.1, maxExecutionTime reduced, role/goal/backstory removed | Validate model compatibility and runtime behavior |
| DI_OptimizeTSQLScript | 75% | Medium | Model changed from claude-4-sonnet to gpt-4.1, maxExecutionTime reduced, embedding configs removed | Validate model compatibility and knowledge base migration |
| DI_TSQL_DQReviewAgent | 75% | Medium | Model changed from claude-4-sonnet to gpt-4.1, maxExecutionTime reduced, maxIter reduced | Validate model compatibility and runtime behavior |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_TSQL_DQReviewAgent
**Workflow Name (AAVA 2.0):** DI TSQL DQReviewAgent

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 7827 | id | 2495 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_TSQL_DQReviewAgent | name | DI TSQL DQReviewAgent | Matched (Case Normalization) | Minor naming convention change | Low | No change needed |
| Description | description | To thoroughly review and validate... | description | To thoroughly review and validate... | Matched (Normalized) | Same description content | Low | No change needed |
| Audit | createdAt | 2025-10-27T07:44:11.119+00:00 | createdAt | 2025-11-05T11:01:45.691508 | Modified | Different creation timestamps | Low | Expected for new workflow instance |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Enhanced configuration structure | Medium | Configure workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Low | Update configuration access |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Implement alternative org tracking |
| Domain Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Implement alternative domain tracking |
| Project Metadata | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Implement alternative project tracking |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User tracking | dipali.nale@ascendion.com | Medium | Ensure user attribution is handled |
| modifiedBy | Change tracking | dipali.nale@ascendion.com | Medium | Implement modification tracking |
| approvedBy | Approval workflow | dipali.nale@ascendion.com | Medium | Set up approval processes |
| modifiedAt | Change timestamp | 2025-12-03T15:03:31.224436 | Low | Track modification history |
| approvedAt | Approval timestamp | 2025-11-05T11:01:46.750654 | Low | Track approval history |
| status | Workflow state | APPROVED | High | Implement workflow lifecycle management |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete functionality |
| parentId | Hierarchy tracking | -1 | Low | Handle workflow relationships |
| realmId | Multi-tenancy | 32 | Medium | Configure realm-based access |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|---------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Configure workflow-level LLM settings |
| managerLlm | Not available | Empty object {} | Medium | Define manager LLM configuration |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Low | Update configuration access pattern |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agents with naming updates

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_DetermineDQRulesFromInstructions | DI DetermineDQRulesFromInstructions | Renamed | Underscore to space conversion |
| DI_OptimizeTSQLScript | DI OptimizeTSQLScript | Renamed | Underscore to space conversion |
| DI_TSQL_DQReviewAgent | DI TSQL DQReviewAgent | Renamed | Underscore to space conversion |

---

## 6. Agent Configuration Differences

## Agent: DI_DetermineDQRulesFromInstructions

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | Medium | Add missing field or confirm deprecation |

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | anthropic.claude-4-sonnet | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized value |
| topP | 0.949999988079071 | 0.94 | Low | Normalized value |
| maxToken | 24000 | 24000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Validate iteration handling |
| maxRpm | 0 | Not Available | Medium | Validate rate limiting |
| maxExecutionTime | 300 | 90 | High | Validate timeout reduction impact |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| DI_Github_File_Writer_Z | Present | Not Available | High | Migrate tool configuration |
| DI_GitHub_File_Reader_Z | Present | Not Available | High | Migrate tool configuration |
| toolReferences | Not Available | Present (empty) | Medium | Configure tool references |

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI_OptimizeTSQLScript

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | Medium | Add missing field or confirm deprecation |

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | anthropic.claude-4-sonnet | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized value |
| topP | 0.949999988079071 | 0.94 | Low | Normalized value |
| maxToken | 24000 | 24000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Validate iteration handling |
| maxRpm | 0 | Not Available | Medium | Validate rate limiting |
| maxExecutionTime | 300 | 90 | High | Validate timeout reduction impact |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| DI_Github_File_Writer_Z | Present | Not Available | High | Migrate tool configuration |
| DI_GitHub_File_Reader_Z | Present | Not Available | High | Migrate tool configuration |
| toolReferences | Not Available | Present (empty) | Medium | Configure tool references |

### 6.2.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present (AzureOpenAI config) | Not Available | High | Migrate knowledge base configuration |
| chroma_end_point | http://chromadb.da.svc.cluster.local | Not Available | High | Configure embedding endpoint |
| index_collection | tSQLStandardsKb | Not Available | High | Migrate knowledge collection |

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DI_TSQL_DQReviewAgent

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | Medium | Add missing field or confirm deprecation |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility |
| model | anthropic.claude-4-sonnet | model | High | Update model configuration |
| temperature | 0.30000001192092896 | 0.3 | Low | Normalized value |
| topP | 0.949999988079071 | 0.94 | Low | Normalized value |
| maxToken | 4500 | 4500 | Low | No change |
| maxIter | 10 | Not Available | High | Validate iteration handling |
| maxRpm | 0 | Not Available | Medium | Validate rate limiting |
| maxExecutionTime | 1000 | 90 | High | Validate significant timeout reduction |

### 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| DI_Github_File_Writer_Z | Present | Not Available | High | Migrate tool configuration |
| DI_GitHub_File_Reader_Z | Present | Not Available | High | Migrate tool configuration |
| toolReferences | Not Available | Present (empty) | Medium | Configure tool references |

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available