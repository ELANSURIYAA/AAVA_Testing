# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 20%
**Total Agents Compared:** 5

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_DataStage_To_PySpark_Conversion | 20% | High | role removed, goal removed, backstory removed, task structure changed | Validate agent instruction completeness and behavior |
| DI_DataStage_To_PySpark_Unit_Tester | 0% | High | Agent completely missing in AAVA 2.0 | Re-add missing agent or confirm removal |
| DI_DataStage_to_PySpark_Conversion_Tester | 0% | High | Agent completely missing in AAVA 2.0 | Re-add missing agent or confirm removal |
| DI_DataStage_to_PySpark_Recon_Tester | 0% | High | Agent completely missing in AAVA 2.0 | Re-add missing agent or confirm removal |
| DI_DataStage_To_PySpark_Reviewer | 0% | High | Agent completely missing in AAVA 2.0 | Re-add missing agent or confirm removal |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_DataStage_To_PySpark_Conversion
**Workflow Name (AAVA 2.0):** DI DataStage To PySpark Conversion

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 5502 | id | 2054 | Renamed + Modified | Field renamed and value changed | High | Update ID references in dependent systems |
| Naming | name | DI_DataStage_To_PySpark_Conversion | name | DI DataStage To PySpark Conversion | Matched (Case Normalization) | Minor formatting differences | Low | No change |
| Description | description | DI_DataStage_To_PySpark_Conversion | description | This agent reads a DataStage job definition in DSX format along with a corresponding DataStage job mapping graph... | Modified | Description significantly expanded | Medium | Review description alignment |
| Audit | createdAt | 2025-07-24T09:14:07.788+00:00 | createdAt | 2025-11-05T10:45:22.734557 | Modified | Creation timestamp changed | Medium | Validate audit trail |
| Agents List | pipeLineAgents | [5 agents] | workflowAgents | [1 agent] | Renamed + Modified | Field renamed and agent count reduced | High | Validate agent completeness |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure changed | Medium | Align configuration structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field removed from workflow level | Low | Confirm removal is acceptable |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization field removed | Medium | Confirm metadata removal |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm metadata removal |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain field removed | Medium | Confirm metadata removal |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm metadata removal |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project field removed | Medium | Confirm metadata removal |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm metadata removal |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team field removed | Medium | Confirm metadata removal |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm metadata removal |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Confirm metadata removal |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | kiran.krishnakumar@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified | kiran.krishnakumar@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | kiran.krishnakumar@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Ensure modification tracking is implemented |
| approvedAt | Approval timestamp | 2025-11-05T10:45:23.805065 | Medium | Ensure approval workflow is implemented |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure soft delete functionality is implemented |
| parentId | Parent workflow reference | -1 | Low | Validate parent-child relationships |
| realmId | Realm identifier | 32 | Medium | Ensure realm-based access control |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | callbacks: [] | managerLlm: [{}], enableAgenticMemory: false | High | Align configuration structure and validate manager LLM settings |
| enableAgenticMemory | Workflow level: false | Nested in workflowConfigs: false | Medium | Validate memory configuration placement |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5
**AAVA 2.0 total agents:** 1
**Coverage:** 4 agents removed, 1 agent retained with modifications

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_DataStage_To_PySpark_Conversion | DI DataStage To PySpark Conversion | Renamed | Naming convention updated, underscores to spaces |
| DI_DataStage_To_PySpark_Unit_Tester | Not Available | Removed | Agent completely removed |
| DI_DataStage_to_PySpark_Conversion_Tester | Not Available | Removed | Agent completely removed |
| DI_DataStage_to_PySpark_Recon_Tester | Not Available | Removed | Agent completely removed |
| DI_DataStage_To_PySpark_Reviewer | Not Available | Removed | Agent completely removed |

---

## 6. Agent Configuration Differences

## Agent: DI DataStage To PySpark Conversion

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
| model | gpt-4 | model | High | Validate model name change |
| temperature | 0.30000001192092896 | 0.3 | Low | Precision normalized |
| topP | 0.949999988079071 | 0.94 | Low | Precision normalized |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 30 | Not Available | Medium | Validate iteration limit removal |
| maxRpm | 0 | Not Available | Medium | Validate rate limit removal |
| maxExecutionTime | 300 | 90 | High | Execution time significantly reduced |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| FileWriterTool | Present (toolId: 4) | Present (toolRef: [4]) | Medium | Validate tool reference structure change |
| userTools | [] | Not Available | Low | Confirm user tools removal |

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

## Agent: DI_DataStage_To_PySpark_Unit_Tester

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Re-add missing agent or confirm removal |
| goal | Present | Not Present | High | Re-add missing agent or confirm removal |
| backstory | Present | Not Present | High | Re-add missing agent or confirm removal |
| description | Present | Not Present | High | Re-add missing agent or confirm removal |
| expectedOutput | Present | Not Present | High | Re-add missing agent or confirm removal |

### 6.2.2 LLM Configuration Comparison

Not Available

### 6.2.3 Tools Comparison

Not Available

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

## Agent: DI_DataStage_to_PySpark_Conversion_Tester

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Re-add missing agent or confirm removal |
| goal | Present | Not Present | High | Re-add missing agent or confirm removal |
| backstory | Present | Not Present | High | Re-add missing agent or confirm removal |
| description | Present | Not Present | High | Re-add missing agent or confirm removal |
| expectedOutput | Present | Not Present | High | Re-add missing agent or confirm removal |

### 6.3.2 LLM Configuration Comparison

Not Available

### 6.3.3 Tools Comparison

Not Available

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available

## Agent: DI_DataStage_to_PySpark_Recon_Tester

### 6.4.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Re-add missing agent or confirm removal |
| goal | Present | Not Present | High | Re-add missing agent or confirm removal |
| backstory | Present | Not Present | High | Re-add missing agent or confirm removal |
| description | Present | Not Present | High | Re-add missing agent or confirm removal |
| expectedOutput | Present | Not Present | High | Re-add missing agent or confirm removal |

### 6.4.2 LLM Configuration Comparison

Not Available

### 6.4.3 Tools Comparison

Not Available

### 6.4.4 Knowledge Base Comparison

Not Available

### 6.4.5 Guardrails Comparison

Not Available

## Agent: DI_DataStage_To_PySpark_Reviewer

### 6.5.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Re-add missing agent or confirm removal |
| goal | Present | Not Present | High | Re-add missing agent or confirm removal |
| backstory | Present | Not Present | High | Re-add missing agent or confirm removal |
| description | Present | Not Present | High | Re-add missing agent or confirm removal |
| expectedOutput | Present | Not Present | High | Re-add missing agent or confirm removal |

### 6.5.2 LLM Configuration Comparison

Not Available

### 6.5.3 Tools Comparison

Not Available

### 6.5.4 Knowledge Base Comparison

Not Available

### 6.5.5 Guardrails Comparison

Not Available