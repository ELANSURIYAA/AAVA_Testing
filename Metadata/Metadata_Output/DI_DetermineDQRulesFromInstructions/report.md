# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report

## 1. Metadata Comparison Score Summary

**Workflow Comparison Score:** 76%
**Total Agents Compared:** 1

| Agent Name | Agent Score | Risk Level | Key Score Drivers | Migration Action Required |
|------------|-------------|------------|-------------------|---------------------------|
| DI DetermineDQRulesFromInstructions | 76% | Medium | Model changed from claude-4-sonnet to gpt-4.1, maxExecutionTime reduced from 300 to 90, role/goal/backstory removed | Validate runtime behavior and performance impact |

---

## 2. Workflow-Level Comparison

**Workflow Name (AAVA 1.0):** DI_ DetermineDQRulesFromInstructions
**Workflow Name (AAVA 2.0):** DI  DetermineDQRulesFromInstructions

| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact | Action Required |
|----------|----------------|----------------|----------------|----------------|-------------|----------------------|------------------|-----------------|
| Identifier | pipelineId | 7405 | id | 2351 | Renamed + Modified | Field renamed and value changed | Medium | Update references to new workflow ID |
| Naming | name | DI_ DetermineDQRulesFromInstructions | name | DI  DetermineDQRulesFromInstructions | Matched (Normalized) | Minor spacing difference normalized | Low | No change |
| Description | description | [Long description text] | description | [Same description text] | Matched | Description content identical | Low | No change |
| Audit | createdAt | 2025-10-08T11:43:53.183+00:00 | createdAt | 2025-11-05T10:56:34.568796 | Matched | Field present in both versions | Medium | Verify timestamp handling |
| Agents List | pipeLineAgents | [Agent array] | workflowAgents | [Agent array] | Renamed + Matched (Normalized) | Field renamed, content restructured | Medium | Update agent references |
| Workflow Config | callbacks | [] | workflowConfigs | {managerLlm: [{}], enableAgenticMemory: false} | Renamed + Modified | Field renamed and structure enhanced | Medium | Configure new workflow settings |
| Memory Config | enableAgenticMemory | false | Not Available | Not Available | Removed | Moved to workflowConfigs | Low | Update memory configuration references |
| Org Metadata | org | Ascendion | Not Available | Not Available | Removed | Organization metadata removed | High | Implement alternative org tracking |
| Org ID | orgId | 1 | Not Available | Not Available | Removed | Organization ID removed | High | Implement alternative org ID tracking |
| Domain | domain | Data&Insights | Not Available | Not Available | Removed | Domain metadata removed | High | Implement alternative domain tracking |
| Domain ID | domainId | 96 | Not Available | Not Available | Removed | Domain ID removed | High | Implement alternative domain ID tracking |
| Project | project | AllProjects | Not Available | Not Available | Removed | Project metadata removed | High | Implement alternative project tracking |
| Project ID | projectId | 98 | Not Available | Not Available | Removed | Project ID removed | High | Implement alternative project ID tracking |
| Team | team | AVA Team | Not Available | Not Available | Removed | Team metadata removed | High | Implement alternative team tracking |
| Team ID | teamId | 99 | Not Available | Not Available | Removed | Team ID removed | High | Implement alternative team ID tracking |
| Level ID | levelId | 99 | Not Available | Not Available | Removed | Level ID removed | Medium | Verify level tracking alternatives |

---

## 3. Governance & Metadata Additions (New in AAVA 2.0)

| New Field | Purpose | Default/Observed Value | Migration Impact | Action Required |
|-----------|---------|----------------------|------------------|-----------------|
| createdBy | User who created workflow | dipali.nale@ascendion.com | Medium | Implement user tracking system |
| modifiedBy | User who last modified workflow | dipali.nale@ascendion.com | Medium | Implement modification tracking |
| approvedBy | User who approved workflow | dipali.nale@ascendion.com | Medium | Implement approval workflow |
| modifiedAt | Last modification timestamp | 2025-12-03T15:03:31.224436 | Medium | Implement modification timestamp tracking |
| approvedAt | Approval timestamp | 2025-11-05T10:56:35.644387 | Medium | Implement approval timestamp tracking |
| status | Workflow approval state | APPROVED | High | Implement workflow lifecycle management |
| isDeleted | Soft delete flag | false | Medium | Implement soft delete functionality |
| parentId | Parent workflow reference | -1 | Low | Implement workflow hierarchy if needed |
| realmId | Realm/tenant identifier | 32 | High | Implement multi-tenant support |

---

## 4. Workflow Configuration Changes

| Config Area | AAVA 1.0 | AAVA 2.0 | Impact | Action Required |
|-------------|----------|----------|--------|-----------------|
| workflowConfigs | Not available | Present with managerLlm and enableAgenticMemory | Medium | Configure workflow-level settings |
| managerLlm | Not available | Empty object {} | Medium | Configure manager LLM if needed |
| enableAgenticMemory | Direct field (false) | Nested in workflowConfigs (false) | Low | Update memory configuration references |

---

## 5. Agent Inventory Summary

### 5.1 Agent Count & Coverage
**AAVA 1.0 total agents:** 1
**AAVA 2.0 total agents:** 1
**Coverage:** Same agent count, structure modified

### 5.2 Agent Name Mapping
| AAVA 1.0 Agent | AAVA 2.0 Agent | Match Type | Notes |
|----------------|----------------|------------|-------|
| DI_DetermineDQRulesFromInstructions | DI DetermineDQRulesFromInstructions | Matched (Normalized) | Underscore replaced with space |

---

## 6. Agent Configuration Differences

## Agent: DI DetermineDQRulesFromInstructions

---

## 6.1.1 Agent Instructions Comparison

| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |
|-------|-------------------|-------------------|------------------|-----------------|
| role | Present | Not Present | High | Add missing field or confirm deprecation |
| goal | Present | Not Present | High | Add missing field or confirm deprecation |
| backstory | Present | Not Present | High | Add missing field or confirm deprecation |
| description | Present | Present | Low | No change |
| expectedOutput | Present | Not Present | High | Add missing field or confirm deprecation |

---

## 6.1.2 LLM Configuration Comparison

| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|-------|----------------|----------------|------------------|-----------------|
| modelDeploymentName | Anthropic.claude-4-sonnet | gpt-4.1 | High | Validate model compatibility and performance |
| model | anthropic.claude-4-sonnet | model | High | Update model configuration and test behavior |
| temperature | 0.30000001192092896 | 0.3 | Low | Values match after normalization |
| topP | 0.949999988079071 | 0.94 | Low | Values match after normalization |
| maxToken | 24000 | 24000 | Low | No change |
| maxIter | 0 | null | Low | Both indicate unlimited iterations |
| maxRpm | 0 | null | Low | Both indicate no rate limiting |
| maxExecutionTime | 300 | 90 | High | Execution time significantly reduced - validate timeout handling |
| allowDelegation | true | true | Low | No change |
| allowCodeExecution | false | false | Low | No change |
| isSafeCodeExecution | true | true | Low | No change |

---

## 6.1.3 Tools Comparison

| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |
|------------------------|----------------|----------------|------------------|-----------------|
| tools | [] | [] | Low | No tools configured in either version |
| userTools | [DI_Github_File_Writer_Z, DI_GitHub_File_Reader_Z] | [] | High | User tools removed - verify tool availability |
| toolReferences | Not Available | [] | Medium | New tool reference structure introduced |

---

## 6.1.4 Knowledge Base Comparison

Not Available

---

## 6.1.5 Guardrails Comparison

Not Available