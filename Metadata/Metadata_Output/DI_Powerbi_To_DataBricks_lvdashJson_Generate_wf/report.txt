# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 76%
**Total Agents Compared:** 1

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI Powerbi To DataBricks lvdashJson Generate | 76% | Medium | role/goal/backstory removed, expectedOutput format changed, model name changed | Validate instruction completeness and model compatibility |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_Powerbi_To_DataBricks_lvdashJson_Generate_wf
**Workflow Name (AAVA 2.0):** DI Powerbi To DataBricks lvdashJson Generate wf

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 6026 | id | 2098 | Renamed + Modified | Field renamed and ID value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_Powerbi_To_DataBricks_lvdashJson_Generate_wf | name | DI Powerbi To DataBricks lvdashJson Generate wf | Matched (Normalized) | Name formatting normalized | Low | No change |
| Description | description | bimtodatabricks format creation | description | bimtodatabricks format creation | Matched | Same description | Low | No change |
| Audit | createdAt | 2025-08-12T06:53:19.931+00:00 | createdAt | 2025-11-05T10:47:02.433724 | Matched | Different creation timestamps (expected) | Low | No change |
| Agents List | pipeLineAgents | Present | workflowAgents | Present | Renamed + Matched (Normalized) | Field renamed but agents present | Low | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | Present | Renamed + Modified | Enhanced configuration structure | Medium | Align configuration handling |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Update memory config access path |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm org context handling |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Update org reference logic |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm domain context handling |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Update domain reference logic |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm project context handling |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Medium | Update project reference logic |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm team context handling |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Medium | Update team reference logic |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Update level reference logic |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | bhargav.patel@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified | bhargav.patel@ascendion.com | Medium | Ensure modification tracking works |
| approvedBy | User who approved workflow | bhargav.patel@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking works |
| approvedAt | Approval timestamp | 2025-11-05T10:47:03.626544 | Medium | Implement approval workflow |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete logic |
| parentId | Parent workflow reference | -1 | Low | Handle workflow hierarchy |
| realmId | Realm identifier | 32 | Medium | Ensure realm context is handled |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Align configuration structure |
| managerLlm | Not available | Empty object present | Medium | Configure manager LLM settings |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update memory config access path |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 1
**AAVA 2.0 total agents:** 1
**Coverage:** Same agent count

### 5.2 Agent Name Mapping
| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Powerbi_To_DataBricks_lvdashJson_Generate | DI Powerbi To DataBricks lvdashJson Generate | Renamed | Naming convention updated |

---

## 6. Agent Configuration Differences

## Agent: DI Powerbi To DataBricks lvdashJson Generate

---

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Present | Low | No change |

---

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model compatibility |
| temperature | 0.30000001192092896 | 0.3 | Low | Matched (Normalized) |
| topP | 0.949999988079071 | 0.94 | Low | Matched (Normalized) |
| maxToken | 30000 | 30000 | Low | No change |
| maxIter | 0 | null | Medium | Validate iteration handling |
| maxRpm | 0 | null | Medium | Validate rate limiting |
| maxExecutionTime | 0 | 90 | Medium | Execution timeout changed |

---

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | FileWriterTool (ID: 4) | toolRef: [4] | Medium | Validate tool reference format |
| userTools | [] | Not Available | Medium | Confirm user tools handling |
| toolReferences | Not Available | [] | Medium | Validate new tool reference system |

---

### 6.1.4 Knowledge Base Comparison

Not Available

---

### 6.1.5 Guardrails Comparison

Not Available