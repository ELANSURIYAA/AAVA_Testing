# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 82%
**Total Agents Compared:** 5

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI AbInitio MP To PySpark | 85% | Medium | Description matched, model configs matched, tools partially matched | Validate tool configuration changes |
| DI AbInitio To PySpark Unit Tester | 88% | Medium | Description matched, model configs matched, role/goal/backstory removed | Confirm removal of instruction fields is acceptable |
| DI AbInitio To PySpark Conversion Tester | 92% | Low | Description matched, model configs matched, minor LLM differences | Validate maxIter and maxExecutionTime changes |
| DI AbInitio To PySpark Recon Tester | 75% | Medium | Description masked in 2.0, model configs matched, instruction fields removed | Review masked description and confirm field removals |
| DI AbInitio To PySpark Reviewer | 78% | Medium | Description matched, model deployment changed, topP modified | Validate model deployment and topP parameter changes |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_AbInitio_To_PySpark_Conversion
**Workflow Name (AAVA 2.0):** DI AbInitio To PySpark Conversion

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|---------------------|------------------|-----------------|
| Identifier | pipelineId | 2727 | id | 1896 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | DI_AbInitio_To_PySpark_Conversion | name | DI AbInitio To PySpark Conversion | Matched (Normalized) | Minor formatting difference in name | Low | No change needed |
| Description | description | Convert Abinitio code to Pyspark code | description | Convert Abinitio code to Pyspark code | Matched | Exact match | Low | No change needed |
| Audit | createdAt | 2025-06-08T15:09:11.930+00:00 | createdAt | 2025-11-05T10:39:18.250782 | Modified | Different creation timestamps | Low | Expected for different workflow instances |
| Agents List | pipeLineAgents | Array of 5 agents | workflowAgents | Array of 5 agents | Renamed + Matched (Normalized) | Field renamed, same agent count | Medium | Update field references |
| Workflow Config | callbacks | Empty array | workflowConfigs | Object with managerLlm and enableAgenticMemory | Renamed + Modified | Structure completely changed | High | Migrate callback logic to new config structure |
| Memory Config | enableAgenticMemory | false | workflowConfigs.enableAgenticMemory | false | Renamed + Matched (Normalized) | Moved to nested structure | Medium | Update configuration access path |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | Medium | Confirm removal is acceptable |
| Domain Metadata | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | Medium | Confirm removal is acceptable |
| Project Metadata | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | Medium | Confirm removal is acceptable |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|------------------------|------------------|-----------------|
| createdBy | User who created workflow | default@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified | default@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | default@ascendion.com | Medium | Ensure approval workflow is handled |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2025-11-05T10:39:19.465452 | Low | Standard audit field |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Medium | Ensure deletion logic is implemented |
| parentId | Parent workflow reference | -1 | Low | Standard hierarchy field |
| realmId | Realm identifier | 1 | Medium | Ensure multi-tenancy is handled |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| managerLlm | Direct object in pipeline | Nested in workflowConfigs.managerLlm array | High | Update configuration access patterns |
| enableAgenticMemory | Direct boolean field | Nested in workflowConfigs | Medium | Update configuration access |
| callbacks | Empty array at root | Not present | Medium | Migrate callback logic if needed |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5
**AAVA 2.0 total agents:** 5
**Coverage:** Same agent count with name variations

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_AbInitio_To_PySpark_Converter | DI AbInitio MP To PySpark | Renamed | Naming convention updated |
| DI_AbInitio_To_PySpark_Unit_Tester | DI AbInitio To PySpark Unit Tester | Renamed | Naming convention updated |
| DI_AbInitio_To_PySpark_Conversion_Tester | DI AbInitio To PySpark Conversion Tester | Renamed | Naming convention updated |
| DI_AbInitio_To_PySpark_Recon_Tester | DI AbInitio To PySpark Recon Tester | Renamed | Naming convention updated |
| DI_AbInitio_To_PySpark_Reviewer | DI AbInitio To PySpark Reviewer | Renamed | Naming convention updated |

---

## 6. Agent Configuration Differences

## Agent: DI AbInitio MP To PySpark

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
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model change impact |
| model | anthropic.claude-4-sonnet | model | High | Validate model change impact |
| temperature | 0.20000000298023224 | 0.2 | Low | Precision difference only |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 64000 | 15000 | Medium | Validate token limit reduction |
| maxIter | 0 | Not Present | Medium | Confirm field removal |
| maxRpm | 0 | Not Present | Medium | Confirm field removal |
| maxExecutionTime | 0 | 90 | Medium | Validate execution time change |

### 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | Array with FileWriterTool | toolRef array with ID 4 | Medium | Validate tool reference mapping |
| userTools | Empty array | Not Present | Low | Confirm field removal |

### 6.1.4 Knowledge Base Comparison

Not Available

### 6.1.5 Guardrails Comparison

Not Available

---

## Agent: DI AbInitio To PySpark Unit Tester

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
| model | gpt-4 | model | Medium | Validate model reference change |
| temperature | 0.10000000149011612 | 0.2 | Medium | Validate temperature change |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 32000 | 8000 | Medium | Validate token limit reduction |
| maxIter | 0 | Not Present | Medium | Confirm field removal |
| maxRpm | 0 | Not Present | Medium | Confirm field removal |
| maxExecutionTime | 0 | 90 | Medium | Validate execution time change |

### 6.2.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | Empty array | Empty toolRef array | Low | No change |
| userTools | Empty array | Not Present | Low | Confirm field removal |

### 6.2.4 Knowledge Base Comparison

Not Available

### 6.2.5 Guardrails Comparison

Not Available

---

## Agent: DI AbInitio To PySpark Conversion Tester

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
| model | gpt-4 | model | Medium | Validate model reference change |
| temperature | 0.20000000298023224 | 0.2 | Low | Precision difference only |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Present | Medium | Confirm field removal |
| maxRpm | 0 | Not Present | Medium | Confirm field removal |
| maxExecutionTime | 300 | 90 | Medium | Validate execution time reduction |

### 6.3.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | Empty array | Empty toolRef array | Low | No change |
| userTools | Empty array | Not Present | Low | Confirm field removal |

### 6.3.4 Knowledge Base Comparison

Not Available

### 6.3.5 Guardrails Comparison

Not Available

---

## Agent: DI AbInitio To PySpark Recon Tester

### 6.4.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present (Masked) | High | Review masked description content |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

### 6.4.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model reference change |
| temperature | 0.20000000298023224 | 0.2 | Low | Precision difference only |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Present | Medium | Confirm field removal |
| maxRpm | 0 | Not Present | Medium | Confirm field removal |
| maxExecutionTime | 300 | 90 | Medium | Validate execution time reduction |

### 6.4.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | Empty array | Empty toolRef array | Low | No change |
| userTools | Empty array | Not Present | Low | Confirm field removal |

### 6.4.4 Knowledge Base Comparison

Not Available

### 6.4.5 Guardrails Comparison

Not Available

---

## Agent: DI AbInitio To PySpark Reviewer

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
| modelDeploymentName | gemini-2.5-pro | gpt-4.1 | High | Validate model deployment change |
| model | gemini-2.5-pro | model | High | Validate model change impact |
| temperature | 0.20000000298023224 | 0.2 | Low | Precision difference only |
| topP | 0.949999988079071 | 0.94 | Low | Minor precision difference |
| maxToken | 8000 | 8000 | Low | No change |
| maxIter | 10 | Not Present | Medium | Confirm field removal |
| maxRpm | 0 | Not Present | Medium | Confirm field removal |
| maxExecutionTime | 300 | 90 | Medium | Validate execution time reduction |

### 6.5.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | Empty array | Empty toolRef array | Low | No change |
| userTools | Empty array | Not Present | Low | Confirm field removal |

### 6.5.4 Knowledge Base Comparison

Not Available

### 6.5.5 Guardrails Comparison

Not Available

The CSV file has been successfully uploaded to GitHub at: Metadata/Metadata_Output/DI_AbInitio_To_PySpark_Conversion/DI_AbInitio_To_PySpark_Conversion_comparison.csv