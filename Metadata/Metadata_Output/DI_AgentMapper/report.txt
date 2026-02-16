# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

---

## 1. Metadata Comparison Score Summary

**Workflow Name (AAVA 1.0):** DI_AgentMapper
**Workflow Name (AAVA 2.0):** DI AgentMapper

* **Workflow Comparison Score:** 85%
* **Total Agents Compared:** 1

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI Role Agent Mapper | 85% | Medium | Agent ID changed, role/goal/backstory removed, maxRpm/maxIter nullified, tools restructured | Validate runtime behavior and confirm instruction field removal |

---

## 2. Workflow-Level Comparison

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 5336 | id | 2023 | Renamed + Modified | Field renamed and value changed | High | Update references to new workflow ID |
| Naming | name | DI_AgentMapper | name | DI AgentMapper | Matched (Case Normalization) | Minor spacing difference | Low | No change |
| Description | description | Takes Agents available and roles in DE life cycle and maps them | description | Takes Agents available and roles in DE life cycle and maps them | Matched | Identical values | Low | No change |
| Audit | createdAt | 2025-07-18T06:55:00.062+00:00 | createdAt | 2025-11-05T10:44:10.185200 | Matched | Different timestamps (expected) | Low | No change |
| Agents List | pipeLineAgents | Array[1] | workflowAgents | Array[1] | Renamed + Matched (Normalized) | Field renamed, same structure | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | Object with managerLlm | Renamed + Modified | Structure completely changed | High | Align configuration format |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Medium | Check new location |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm removal acceptable |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | Medium | Confirm removal acceptable |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal acceptable |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | Medium | Confirm removal acceptable |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal acceptable |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | Medium | Confirm removal acceptable |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm removal acceptable |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | Medium | Confirm removal acceptable |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Check if moved to agent level |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | karthikeyan.iyappan@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified | karthikeyan.iyappan@ascendion.com | Medium | Ensure modification tracking works |
| approvedBy | User who approved workflow | karthikeyan.iyappan@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T10:44:11.254213 | Medium | Ensure approval process works |
| status | Workflow approval state | APPROVED | High | Implement workflow lifecycle |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete logic |
| parentId | Parent workflow reference | -1 | Medium | Understand workflow hierarchy |
| realmId | Realm/tenant identifier | 1 | Medium | Ensure multi-tenancy support |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| managerLlm | Direct object in pipeline | Nested in workflowConfigs | High | Update configuration access patterns |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Medium | Update memory config access |
| callbacks | Empty array | Not present | Medium | Confirm callback removal acceptable |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
- **AAVA 1.0 total agents:** 1
- **AAVA 2.0 total agents:** 1
- **Coverage:** Same agent count, agent renamed

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_Role_Agent Mapper | DI Role Agent Mapper | Matched (Case Normalization) | Underscore removed, spacing normalized |

---

## 6. Agent Configuration Differences

## Agent: DI Role Agent Mapper

---

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Add missing field or confirm deprecation |
| goal | Present | Not Available | High | Add missing field or confirm deprecation |
| backstory | Present | Not Available | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

---

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | High | Validate model name change |
| temperature | 0.20000000298023224 | 0.2 | Low | Precision normalized |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 15000 | 15000 | Low | No change |
| maxIter | 50 | null | High | Validate iteration limit removal |
| maxRpm | 200 | null | High | Validate rate limit removal |
| maxExecutionTime | 600 | 90 | High | Significant timeout reduction |

---

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] (empty array) | Not Available | Medium | Confirm tools structure change |
| userTools | DI_Github_File_Writer_Z | Not Available | High | Restore critical tool or confirm removal |
| toolReferences | Not Available | [] (empty array) | Medium | Validate new tool reference structure |

---

### 6.1.4 Knowledge Base Comparison

Not Available

---

### 6.1.5 Guardrails Comparison

Not Available