# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score: 87.2%**
**Total Agents Compared: 5**

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI_AbInitio_To_PySpark_EMR_Glue_Converter | 88.5% | Low | Description matched; model configs changed; role/goal/backstory removed | Validate new model deployment and confirm instruction field removal |
| DI_AbInitio_To_PySpark_EMR_Glue_Unit_Tester | 89.2% | Low | Description matched; model configs changed; role/goal/backstory removed | Validate new model deployment and confirm instruction field removal |
| DI_AbInitio_To_PySpark_EMR_Glue_Conversion_Tester | 89.2% | Low | Description matched; model configs changed; role/goal/backstory removed | Validate new model deployment and confirm instruction field removal |
| DI_AbInitio_To_PySpark_EMR_Glue_Recon_Tester | 84.0% | Medium | Description masked; model configs changed; role/goal/backstory removed | Unmask description and validate new model deployment |
| DI_AbInitio_To_PySpark_EMR_Glue_Reviewer | 85.8% | Medium | Description modified; model configs changed; role/goal/backstory removed | Validate description changes and new model deployment |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_AbInitio_To_PySpark_EMR_Glue_Conversion
**Workflow Name (AAVA 2.0):** DI AbInitio To PySpark EMR Glue Conversion

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 8576 | id | 8480 | Renamed + Modified | Field renamed and value changed | Medium | Update references to use new ID |
| Naming | name | DI_AbInitio_To_PySpark_EMR_Glue_Conversion | name | DI AbInitio To PySpark EMR Glue Conversion | Matched (Case Normalization) | Minor spacing differences | Low | No change required |
| Description | description | Convert Abinitio code to Pyspark EMR Glue code | description | Convert Abinitio code to Pyspark EMR Glue code | Matched | Identical values | Low | No change required |
| Audit | createdAt | 2025-11-19T05:23:11.702+00:00 | createdAt | 2026-01-16T05:31:23.807243 | Modified | Different creation timestamps | Low | Expected for new workflow instance |
| Agents List | pipeLineAgents | Array of 5 agents | workflowAgents | Array of 5 agents | Renamed + Matched (Normalized) | Field renamed but content preserved | Medium | Update field references |
| Workflow Config | callbacks | Empty array | workflowConfigs | Complex object with managerLlm | Renamed + Modified | Structure completely changed | High | Migrate callback logic to new config structure |
| Memory Config | enableAgenticMemory | false | Not Available | - | Removed | Field removed in AAVA 2.0 | Medium | Confirm memory config handling |
| Org Metadata | org | Ascendion | Not Available | - | Removed | Organization metadata removed | Medium | Migrate to new governance structure |
| Domain Metadata | domain | Data&Insights | Not Available | - | Removed | Domain metadata removed | Medium | Migrate to new governance structure |
| Project Metadata | project | AllProjects | Not Available | - | Removed | Project metadata removed | Medium | Migrate to new governance structure |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | nishanth.janarthanan@ascendion.com | Medium | Ensure user tracking is implemented |
| modifiedBy | User who last modified workflow | nishanth.janarthanan@ascendion.com | Medium | Ensure modification tracking is implemented |
| approvedBy | User who approved workflow | nishanth.janarthanan@ascendion.com | Medium | Ensure approval workflow is implemented |
| modifiedAt | Last modification timestamp | 2026-01-16T11:05:42.394548 | Low | Standard audit field |
| approvedAt | Approval timestamp | 2026-01-16T05:31:25.349706 | Low | Standard audit field |
| status | Workflow approval state | APPROVED | Medium | Ensure workflow lifecycle is handled |
| isDeleted | Soft delete flag | false | Low | Standard data management field |
| parentId | Workflow hierarchy reference | -1 | Medium | Ensure workflow relationships are handled |
| realmId | Multi-tenancy identifier | 1 | Medium | Ensure tenant isolation is implemented |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| managerLlm | Direct object in pipeline | Nested in workflowConfigs | High | Migrate LLM config structure |
| callbacks | Empty array | Not present | Medium | Migrate callback handling to workflowConfigs |
| enableAgenticMemory | Direct boolean field | Nested in workflowConfigs | Medium | Update memory config access |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 5
**AAVA 2.0 total agents:** 5
**Coverage:** Same agents with structural changes

### 5.2 Agent Name Mapping

| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_AbInitio_To_PySpark_EMR_Glue_Converter | DI_AbInitio_To_PySpark_EMR_Glue_Converter | Matched | Exact name match |
| DI_AbInitio_To_PySpark_EMR_Glue_Unit_Tester | DI_AbInitio_To_PySpark_EMR_Glue_Unit_Tester | Matched | Exact name match |
| DI_AbInitio_To_PySpark_EMR_Glue_Conversion_Tester | DI_AbInitio_To_PySpark_EMR_Glue_Conversion_Tester | Matched | Exact name match |
| DI_AbInitio_To_PySpark_EMR_Glue_Recon_Tester | DI_AbInitio_To_PySpark_EMR_Glue_Recon_Tester | Matched | Exact name match |
| DI_AbInitio_To_PySpark_EMR_Glue_Reviewer | DI_AbInitio_To_PySpark_EMR_Glue_Reviewer | Matched | Exact name match |

---

## 6. Agent Configuration Differences

## Agent: DI_AbInitio_To_PySpark_EMR_Glue_Converter

### 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Confirm removal is acceptable |
| goal | Present | Not Available | High | Confirm removal is acceptable |
| backstory | Present | Not Available | High | Confirm removal is acceptable |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model change impact |
| model | anthropic.claude-4-sonnet | model | High | Validate model change impact |
| temperature | 0.20000000298023224 | 0.2 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 64000 | 64000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Validate new iteration handling |
| maxRpm | 0 | Not Available | Medium | Validate new rate limiting |
| maxExecutionTime | 0 | Not Available | Medium | Validate new timeout handling |

### 6.1.3 Tools Comparison
Not Available

### 6.1.4 Knowledge Base Comparison
Not Available

### 6.1.5 Guardrails Comparison
Not Available

---

## Agent: DI_AbInitio_To_PySpark_EMR_Glue_Unit_Tester

### 6.2.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Confirm removal is acceptable |
| goal | Present | Not Available | High | Confirm removal is acceptable |
| backstory | Present | Not Available | High | Confirm removal is acceptable |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.2.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model reference change |
| temperature | 0.20000000298023224 | 0.2 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 32000 | 32000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Validate new iteration handling |
| maxRpm | 0 | Not Available | Medium | Validate new rate limiting |
| maxExecutionTime | 0 | Not Available | Medium | Validate new timeout handling |

### 6.2.3 Tools Comparison
Not Available

### 6.2.4 Knowledge Base Comparison
Not Available

### 6.2.5 Guardrails Comparison
Not Available

---

## Agent: DI_AbInitio_To_PySpark_EMR_Glue_Conversion_Tester

### 6.3.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Confirm removal is acceptable |
| goal | Present | Not Available | High | Confirm removal is acceptable |
| backstory | Present | Not Available | High | Confirm removal is acceptable |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.3.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model reference change |
| temperature | 0.20000000298023224 | 0.2 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 32000 | 32000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Validate new iteration handling |
| maxRpm | 0 | Not Available | Medium | Validate new rate limiting |
| maxExecutionTime | 0 | Not Available | Medium | Validate new timeout handling |

### 6.3.3 Tools Comparison
Not Available

### 6.3.4 Knowledge Base Comparison
Not Available

### 6.3.5 Guardrails Comparison
Not Available

---

## Agent: DI_AbInitio_To_PySpark_EMR_Glue_Recon_Tester

### 6.4.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Confirm removal is acceptable |
| goal | Present | Not Available | High | Confirm removal is acceptable |
| backstory | Present | Not Available | High | Confirm removal is acceptable |
| description | Present | Present | High | Description is masked in AAVA 2.0 |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.4.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | gpt-4.1 | gpt-4.1 | Low | No change |
| model | gpt-4 | model | Medium | Validate model reference change |
| temperature | 0.20000000298023224 | 0.2 | Low | Values match after normalization |
| topP | 1.0 | 1.0 | Low | No change |
| maxToken | 32000 | 32000 | Low | No change |
| maxIter | 0 | Not Available | Medium | Validate new iteration handling |
| maxRpm | 0 | Not Available | Medium | Validate new rate limiting |
| maxExecutionTime | 0 | Not Available | Medium | Validate new timeout handling |

### 6.4.3 Tools Comparison
Not Available

### 6.4.4 Knowledge Base Comparison
Not Available

### 6.4.5 Guardrails Comparison
Not Available

---

## Agent: DI_AbInitio_To_PySpark_EMR_Glue_Reviewer

### 6.5.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Available | High | Confirm removal is acceptable |
| goal | Present | Not Available | High | Confirm removal is acceptable |
| backstory | Present | Not Available | High | Confirm removal is acceptable |
| description | Present | Present | Medium | Description content modified |
| expectedOutput | Present | Not Available | High | Add missing field or confirm deprecation |

### 6.5.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | anthropic.claude-3-7-sonnet | gpt-4.1 | High | Validate model change impact |
| model | claude-3.7sonnet | model | High | Validate model change impact |
| temperature | 0.30000001192092896 | 0.2 | Medium | Temperature value changed |
| topP | 0.9599999785423279 | 1.0 | Medium | TopP value changed |
| maxToken | 20000 | 64000 | Medium | Token limit increased |
| maxIter | 0 | Not Available | Medium | Validate new iteration handling |
| maxRpm | 0 | Not Available | Medium | Validate new rate limiting |
| maxExecutionTime | 0 | Not Available | Medium | Validate new timeout handling |

### 6.5.3 Tools Comparison
Not Available

### 6.5.4 Knowledge Base Comparison
Not Available

### 6.5.5 Guardrails Comparison
Not Available