# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 74%**
**Total Agents Compared: 3**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_Powerbi_To_DataBricks_lvdashJson_Generate | 69% | Medium | role/goal/backstory removed, expectedOutput modified, tools restructured | Validate instruction completeness, confirm tool mapping |
| DI_Databricks_LvdashJson_Review_Agent | 78% | Medium | role/goal/backstory removed, embedding config removed, description matched | Validate knowledge base integration, confirm instruction adequacy |
| DI_Databricks_LvdashJson_TestCase_Agent | 75% | Medium | role/goal/backstory removed, expectedOutput removed, description matched | Validate instruction completeness, confirm output format requirements |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_Lvdash_Review_Test_Workflow
**Workflow Name (AAVA 2.0):** DI Lvdash Review Test Workflow

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 6052 | id | 2102 | Renamed + Modified | Field renamed and ID value changed | Medium | Update ID references in dependent systems |
| Naming | name | DI_Lvdash_Review_Test_Workflow | name | DI Lvdash Review Test Workflow | Matched (Normalized) | Minor formatting differences in naming | Low | No change |
| Description | description | Lvdash_Review_Test_Agent Workflow | description | Lvdash_Review_Test_Agent Workflow | Matched | Identical values | Low | No change |
| Audit | createdAt | 2025-08-13T08:09:18.165+00:00 | createdAt | 2025-11-05T10:47:11.074677 | Matched | Field exists in both, different timestamps | Low | No change |
| Agents List | pipeLineAgents | [3 agents] | workflowAgents | [3 agents] | Renamed + Matched (Normalized) | Field renamed, same agent count | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure enhanced | Medium | Validate new config structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Low | Update config references |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm org context handling |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Update org references |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm domain context handling |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Update domain references |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm project context handling |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Medium | Update project references |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm team context handling |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Medium | Update team references |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Low | Update level references |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | sushal.devasari@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | sushal.devasari@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | sushal.devasari@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T10:47:12.142638 | Low | Standard audit field |
| status | Workflow approval state | APPROVED | High | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure deletion handling is implemented |
| parentId | Parent workflow reference | -1 | Low | Standard hierarchy field |
| realmId | Realm/tenant identifier | 32 | Medium | Ensure multi-tenancy is handled |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | callbacks: [] | managerLlm: [{}], enableAgenticMemory: false | Medium | Validate new config structure and defaults |
| managerLlm | Not available | Present (empty object) | Medium | Configure manager LLM settings |
| enableAgenticMemory | Top-level field | Nested in workflowConfigs | Low | Update config path references |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 3
**AAVA 2.0 total agents:** 3
**Coverage:** Same agent count, all agents mapped

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Powerbi_To_DataBricks_lvdashJson_Generate | DI Powerbi To DataBricks lvdashJson Generate | Renamed | Naming convention updated (underscores to spaces) |
| DI_Databricks_LvdashJson_Review_Agent | DI Databricks LvdashJson Review Agent | Renamed | Naming convention updated (underscores to spaces) |
| DI_Databricks_LvdashJson_TestCase_Agent | DI Databricks LvdashJson TestCase Agent | Renamed | Naming convention updated (underscores to spaces) |

---

## 6. Agent Configuration Differences

## Agent: DI_Powerbi_To_DataBricks_lvdashJson_Generate

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
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 30000 | 30000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout changed |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [FileWriterTool] | toolRef: [4] | Medium | Validate tool reference mapping |
| userTools | [] | Not Present | Low | Confirm user tools handling |

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI_Databricks_LvdashJson_Review_Agent

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
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout changed |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | toolRef: [] | Low | No change |
| userTools | [] | Not Present | Low | Confirm user tools handling |

### 6.2.4 Knowledge Base Comparison

| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|----------|----------------|----------------|------------------|-----------------|
| embedding | Present (ChromaDB config) | Not Present | High | Validate knowledge base integration |

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DI_Databricks_LvdashJson_TestCase_Agent

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
| model | gpt-4 | model | Medium | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 0 | Not Present | Medium | Validate iteration handling |
| maxRpm | 0 | Not Present | Medium | Validate rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout changed |

### 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | toolRef: [] | Low | No change |
| userTools | [] | Not Present | Low | Confirm user tools handling |

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available