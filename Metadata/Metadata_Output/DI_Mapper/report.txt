# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 31%
**Total Agents Compared:** 3

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_Mapper_01| 0% | High | Agent removed from AAVA 2.0 | Confirm removal is acceptable or recreate agent |
| DI_Mapper_DDL | 0% | High | Agent removed from AAVA 2.0 | Confirm removal is acceptable or recreate agent |
| DI Table Mapper | 60% | Medium | New agent in AAVA 2.0 only | Validate new agent behavior and integration |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_Mapper
**Workflow Name (AAVA 2.0):** DI Table Mapper

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 12512 | id | 8472 | Renamed + Modified | Field renamed and ID value changed | High | Update references to new workflow ID |
| Naming | name | DI_Mapper | name | DI Table Mapper | Matched (Normalized) | Workflow name updated | Medium | Update documentation and references |
| Description | description | DI_Mapper for source and target column Mappings | description | DI Table Mapper | Modified | Description simplified | Low | Review description accuracy |
| Audit | createdAt | 2026-01-19T10:52:01.534+00:00 | createdAt | 2026-01-14T13:41:37.260520 | Matched | Different timestamps as expected | Low | No action required |
| Agents List | pipeLineAgents | 2 agents | workflowAgents | 1 agent | Renamed + Modified | Field renamed and agent count reduced | High | Validate workflow completeness |
| Workflow Config | callbacks | [] | workflowConfigs | Present with nested structure | Renamed + Modified | Enhanced configuration structure | Medium | Configure workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Memory config moved to workflowConfigs | Medium | Verify memory settings in new structure |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Low | Update governance tracking |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Low | Update governance tracking |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Low | Update governance tracking |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Low | Update governance tracking |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Low | Update governance tracking |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Low | Update governance tracking |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Low | Update governance tracking |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Low | Update governance tracking |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Low | Update governance tracking |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | elansuriyaa.p@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | elansuriyaa.p@ascendion.com | Medium | Ensure modification tracking is implemented |
| modifiedAt | Last modification timestamp | 2026-01-14T13:41:37.664261 | Low | Verify timestamp accuracy |
| approvedAt | Workflow approval timestamp | 2026-01-14T13:41:37.665405 | High | Implement approval workflow process |
| status | Workflow approval state | APPROVED | High | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete handling |
| parentId | Parent workflow reference | -1 | Medium | Understand workflow hierarchy |
| realmId | Realm identifier | 79 | Medium | Verify realm-based access control |
| tags | Workflow categorization | [2] | Low | Implement tagging system |
| practiceArea | Practice area classification | 6 | Low | Verify practice area mapping |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with nested structure | Medium | Configure workflow-level settings |
| managerLlm | Not available | Empty array | Medium | Verify manager LLM configuration |
| enableAgenticMemory | Top-level field (false) | Nested in workflowConfigs (false) | Medium | Update memory configuration access |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 2
**AAVA 2.0 total agents:** 1
**Coverage:** Significant agent reduction - 2 agents removed, 1 new agent added

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Mapper_01 | Not Available | Removed | Data mapping specialist agent removed |
| DI_Mapper_DDL | Not Available | Removed | SQL generation specialist agent removed |
| Not Available | DI Table Mapper | New | New generic table mapping agent added |

---

## 6. Agent Configuration Differences

## Agent: DI_Mapper_01

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Confirm removal is acceptable |
| goal | Present | Not Available | High | Confirm removal is acceptable |
| backstory | Present | Not Available | High | Confirm removal is acceptable |
| description | Present | Not Available | High | Add missing field or confirm deprecation |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | anthropic.claude-4_5-sonnet | Not Available | High | Agent removed - no comparison possible |
| model | anthropic.claude-4-5-sonnet | Not Available | High | Agent removed - no comparison possible |
| temperature | 0.30000001192092896 | Not Available | High | Agent removed - no comparison possible |
| topP | 0.949999988079071 | Not Available | High | Agent removed - no comparison possible |
| maxToken | 62000 | Not Available | High | Agent removed - no comparison possible |
| maxIter | 10 | Not Available | High | Agent removed - no comparison possible |
| maxRpm | 0 | Not Available | High | Agent removed - no comparison possible |
| maxExecutionTime | 300 | Not Available | High | Agent removed - no comparison possible |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| FileWriterTool | Present (toolId: 4) | Not Available | High | Agent removed - verify tool availability in new workflow |

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI_Mapper_DDL

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Confirm removal is acceptable |
| goal | Present | Not Available | High | Confirm removal is acceptable |
| backstory | Present | Not Available | High | Confirm removal is acceptable |
| description | Present | Not Available | High | Add missing field or confirm deprecation |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | anthropic.claude-4_5-sonnet | Not Available | High | Agent removed - no comparison possible |
| model | anthropic.claude-4-5-sonnet | Not Available | High | Agent removed - no comparison possible |
| temperature | 0.30000001192092896 | Not Available | High | Agent removed - no comparison possible |
| topP | 0.949999988079071 | Not Available | High | Agent removed - no comparison possible |
| maxToken | 62000 | Not Available | High | Agent removed - no comparison possible |
| maxIter | 10 | Not Available | High | Agent removed - no comparison possible |
| maxRpm | 0 | Not Available | High | Agent removed - no comparison possible |
| maxExecutionTime | 300 | Not Available | High | Agent removed - no comparison possible |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| FileWriterTool | Present (toolId: 4) | Not Available | High | Agent removed - verify tool availability in new workflow |

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DI Table Mapper

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Not Available | Not Available | Low | No change |
| goal | Not Available | Not Available | Low | No change |
| backstory | Not Available | Not Available | Low | No change |
| description | Not Available | Present | Medium | Validate new instruction field behavior |
| expectedOutput | Not Available | Present | Medium | Validate new instruction field behavior |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Not Available | anthropic.claude-4-sonnet | Medium | New agent - validate model configuration |
| model | Not Available | model | Medium | New agent - validate model configuration |
| temperature | Not Available | 0.0 | Medium | New agent - validate temperature setting |
| topP | Not Available | 1.0 | Medium | New agent - validate topP setting |
| maxToken | Not Available | Not Available | Low | No change |
| maxIter | Not Available | 10 | Medium | New agent - validate iteration limit |
| maxRpm | Not Available | 60 | Medium | New agent - validate rate limit |
| maxExecutionTime | Not Available | 300 | Medium | New agent - validate timeout setting |

### 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| toolReferences | Not Available | Empty array | Low | New agent - no tools configured |

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-----------------|----------------|----------------|------------------|-----------------|
| guardrailIds | Not Available | Empty array | Low | New agent - no guardrails configured |