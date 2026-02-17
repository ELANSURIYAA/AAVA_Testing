# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 84.2%**
**Total Agents Compared: 5**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| Talend to PySpark Conversion | 78% | Medium | Model changed (gpt-4o to gpt-4.1), role/goal/backstory removed, maxIter changed | Validate model compatibility and confirm instruction field removal |
| Talend to PySpark Unit Test | 82% | Medium | Model changed, role/goal/backstory removed, maxIter changed from 0 to null | Validate model compatibility and confirm instruction field removal |
| Talend to PySpark Conversion Tester | 88% | Medium | Model changed, role/goal/backstory removed, description matched | Validate model compatibility and confirm instruction field removal |
| Talend to PySpark Recon Tester | 86% | Medium | Model changed, role/goal/backstory removed, maxIter changed | Validate model compatibility and confirm instruction field removal |
| Talend to PySpark Reviewer | 87% | Medium | Model changed, role/goal/backstory removed, maxIter changed from 0 to null | Validate model compatibility and confirm instruction field removal |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** Talend_to_PySpark_Conversion
**Workflow Name (AAVA 2.0):** Talend to PySpark Conversion

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 1451 | id | 4142 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | Talend_to_PySpark_Conversion | name | Talend to PySpark Conversion | Matched (Case Normalization) | Underscore replaced with spaces | Low | No change needed |
| Description | description | Talend to PySpark Conversion | description | Talend to PySpark Conversion | Matched (Normalized) | Identical after normalization | Low | No change needed |
| Audit | createdAt | 2025-04-07T05:40:17.223+00:00 | createdAt | 2025-11-05T11:53:08.501516 | Matched | Field exists in both, values differ by timestamp | Low | No change needed |
| Agents List | pipeLineAgents | Array[5] | workflowAgents | Array[5] | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update field references |
| Workflow Config | callbacks | [] | workflowConfigs | Object with managerLlm | Renamed + Modified | Field renamed and structure changed | High | Implement new config structure |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Field moved to workflowConfigs | Medium | Update memory configuration handling |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm org metadata handling |
| Domain Metadata | domain | Platform Engineering | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm domain metadata handling |
| Project Metadata | project | AVA | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm project metadata handling |
| Team Metadata | team | Digital Ascender | Not Available | Not Available | Removed | Team metadata removed | Medium | Confirm team metadata handling |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Implement user tracking |
| modifiedBy | User who last modified workflow | default@ascendion.com | Medium | Implement modification tracking |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Implement modification tracking |
| approvedAt | Approval timestamp | 2025-11-05T11:53:09.549716 | Medium | Implement approval workflow |
| status | Workflow approval state | APPROVED | High | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete functionality |
| parentId | Parent workflow reference | -1 | Low | Handle workflow hierarchy |
| realmId | Realm identifier | 1 | Medium | Implement realm-based access |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | High | Implement new config structure |
| managerLlm | Not available | Empty object in workflowConfigs | Medium | Configure manager LLM settings |
| enableAgenticMemory | Top-level field (false) | Nested in workflowConfigs (false) | Medium | Update memory config handling |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5
**AAVA 2.0 total agents:** 5
**Coverage:** Same agent count, all agents mapped

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| Talend_to_PySpark_Conversion | Talend to PySpark Conversion | Renamed | Underscore to space conversion |
| Talend_to_PySpark_Unit_Test | Talend to PySpark Unit Test | Renamed | Underscore to space conversion |
| Talend_to_PySpark_Conversion_Tester | Talend to PySpark Conversion Tester | Renamed | Underscore to space conversion |
| Talend_to_PySpark_Recon_Tester | Talend to PySpark Recon Tester | Renamed | Underscore to space conversion |
| Talend_to_PySpark_Reviewer | Talend to PySpark Reviewer | Renamed | Underscore to space conversion |

---

## 6. Agent Configuration Differences

## Agent: Talend to PySpark Conversion

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Update model reference |
| temperature | 0.30000001192092896 | 0.3 | Low | No significant change |
| topP | 0.949999988079071 | 0.94 | Low | No significant change |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 15 | null | Medium | Validate iteration handling |
| maxRpm | 0 | null | Low | No significant change |
| maxExecutionTime | 0 | 90 | Medium | Update timeout handling |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Available | Medium | Confirm tool removal |
| userTools | DI_Github_File_Writer_Z | Not Available | High | Migrate tool configuration |

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: Talend to PySpark Unit Test

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Update model reference |
| temperature | 0.30000001192092896 | 0.3 | Low | No significant change |
| topP | 0.949999988079071 | 0.94 | Low | No significant change |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Medium | Validate iteration handling |
| maxRpm | 0 | null | Low | No significant change |
| maxExecutionTime | 0 | 90 | Medium | Update timeout handling |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Available | Medium | Confirm tool removal |
| userTools | DI_Github_File_Writer_Z | Not Available | High | Migrate tool configuration |

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: Talend to PySpark Conversion Tester

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Update model reference |
| temperature | 0.20000000298023224 | 0.2 | Low | No significant change |
| topP | 0.949999988079071 | 0.94 | Low | No significant change |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Medium | Validate iteration handling |
| maxRpm | 0 | null | Low | No significant change |
| maxExecutionTime | 0 | 90 | Medium | Update timeout handling |

### 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Available | Medium | Confirm tool removal |
| userTools | [] | Not Available | Medium | Confirm tool removal |

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available

---

## Agent: Talend to PySpark Recon Tester

### 6.4.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.4.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Update model reference |
| temperature | 0.30000001192092896 | 0.3 | Low | No significant change |
| topP | 0.949999988079071 | 0.94 | Low | No significant change |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 15 | null | Medium | Validate iteration handling |
| maxRpm | 0 | null | Low | No significant change |
| maxExecutionTime | 0 | 90 | Medium | Update timeout handling |

### 6.4.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Available | Medium | Confirm tool removal |
| userTools | [] | Not Available | Medium | Confirm tool removal |

### 6.4.4 Knowledge Base Comparison

Not Available

### 6.4.5 Guardrails Comparison

Not Available

---

## Agent: Talend to PySpark Reviewer

### 6.5.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|------------------|------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.5.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4o | gpt-4.1 | High | Validate model compatibility |
| model | gpt-4o | model | High | Update model reference |
| temperature | 0.30000001192092896 | 0.3 | Low | No significant change |
| topP | 0.949999988079071 | 0.94 | Low | No significant change |
| maxToken | 4000 | 4000 | Low | No change |
| maxIter | 0 | null | Medium | Validate iteration handling |
| maxRpm | 0 | null | Low | No significant change |
| maxExecutionTime | 0 | 90 | Medium | Update timeout handling |

### 6.5.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | Not Available | Medium | Confirm tool removal |
| userTools | [] | Not Available | Medium | Confirm tool removal |

### 6.5.4 Knowledge Base Comparison

Not Available

### 6.5.5 Guardrails Comparison

Not Available