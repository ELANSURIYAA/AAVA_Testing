ERROR extracting report: sequence item 0: expected str instance, dict found

RAW RESULT:
{
  "data": {
    "result": {
      "cached_prompt_tokens": "0",
      "request": "{\"pipeLineId\": 9727, \"executionId\": \"783caca6-e70b-4f28-a922-84d2d9fb6087\", \"userInputs\": {\"aava1\": \"DAG_Generator_972.json\", \"aava2\": \"DAG_Generator_3836.json\", \"repo\": \"ELANSURIYAA/AAVA_Testing\", \"branch\": \"main\", \"token\": \"<REDACTED_GITHUB_TOKEN>\", \"folder_name\": \"Metadata/Metadata_Output\", \"file_name\": \"DAG_Generator/DAG_Generator_comparison.csv\"}, \"user\": \"harish.kumaresan@ascendion.com\", \"tools\": [], \"userTools\": []}",
      "completion_tokens": "2961",
      "upload_file_id": "Not applicable",
      "prompt_tokens": "56128",
      "successful_requests": "5",
      "response": "{\"pipelineId\": 9727, \"executionId\": \"783caca6-e70b-4f28-a922-84d2d9fb6087\", \"name\": \"DI AAVA METADATA COMPARISON REPORT GENERATOR\", \"user\": \"harish.kumaresan@ascendion.com\", \"description\": \"DI AAVA METADATA COMPARISON REPORT GENERATOR\", \"userInputs\": {\"aava1\": \"DAG_Generator_972.json\", \"aava2\": \"DAG_Generator_3836.json\", \"repo\": \"ELANSURIYAA/AAVA_Testing\", \"branch\": \"main\", \"token\": \"<REDACTED_GITHUB_TOKEN>\", \"folder_name\": \"Metadata/Metadata_Output\", \"file_name\": \"DAG_Generator/DAG_Generator_comparison.csv\"}, \"managerLlm\": null, \"pipeLineAgents\": [{\"serial\": 1, \"agent\": {\"id\": 20483, \"name\": \"DI AAVA METADATA COMPARISON REPORT GENERATOR\", \"role\": \"Senior Quality Engineering Comparison and Validation Agent\", \"description\": \"Take two seperate authoritative inputs:\
\
Agent Input 1:\
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{aava1_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \\u200b\\u200b\
\
\\u00a0AAVA 1.0 Metadata\
\
Agent Input 2:\
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{aava2_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \\u200b\
\
\\u00a0AAVA 2.0 Metadata\
\
They represent different versions of the same workflow system.\
\
You are a Metadata Comparison Analyst.\
\
Compare AAVA 1.0 vs AAVA 2.0 metadata JSONs and produce a crisp migration comparison report.\
\
Always include Migration Impact and Action Required columns.\
\
Keep the output concise and business-readable.\
\
---\
\
# Comparison Normalization Rule (Strict)\
\
Before comparing values, normalize strings using:\
\
* trim spaces\
\
* convert to lowercase\
\
* remove minor formatting differences\
\
If values match after normalization, mark them as: **Matched (Normalized)** instead of Modified.\
\
Do not classify case-only differences (uppercase/lowercase) as Modified.\
\
Instead classify them as: **Matched (Case Normalization)**.\
\
---\
\
# 0. Authoritative Field Mapping Reference (MANDATORY)\
\
Use the following mapping tables as the **only source of truth** for field-level mapping between AAVA 1.0 and AAVA 2.0.\
\
Do NOT infer mappings beyond this table unless explicitly stated.\
\
If a field does not exist in the mapping table, classify it as:\
\
* **New** (2.0 only)\
\
* **Removed** (1.0 only)\
\
---\
\
## 0.1 Workflow-Level Field Mapping Table (AAVA 1.0 \\u2192 AAVA 2.0)\
\
| Workflow Category           | AAVA 1.0 Field                                                                  | AAVA 2.0 Field  | Mapping Type |\
\
| --------------------------- | ------------------------------------------------------------------------------- | --------------- | ------------ |\
\
| Identifier                  | pipelineId                                                                      | id              | Renamed      |\
\
| Naming                      | name                                                                            | name            | Matched      |\
\
| Description                 | description                                                                     | description     | Matched      |\
\
| Audit                       | createdAt                                                                       | createdAt       | Matched      |\
\
| Agents List                 | pipeLineAgents                                                                  | workflowAgents  | Renamed      |\
\
| Workflow Config             | callbacks                                                                       | workflowConfigs | Renamed      |\
\
| Memory Config               | enableAgenticMemory                                                             | Not Available   | Removed      |\
\
| Org/Domain/Project Metadata | org / orgId / domain / domainId / project / projectId / team / teamId / levelId | Not Available   | Removed      |\
\
---\
\
## 0.2 Agent-Level Field Mapping Table (AAVA 1.0 \\u2192 AAVA 2.0)\
\
### Agent Wrapper Level Mapping\
\
| Agent Category   | AAVA 1.0 Field                | AAVA 2.0 Field      | Mapping Type |\
\
| ---------------- | ----------------------------- | ------------------- | ------------ |\
\
| Identifier       | agent.id                      | agentId             | Renamed      |\
\
| Ordering         | serial                        | serial              | Matched      |\
\
| Naming           | agent.name                    | name                | Renamed      |\
\
| Task Description | agent.task.description        | description         | Renamed      |\
\
| Model Deployment | agent.llm.modelDeploymentName | modelDeploymentName | Renamed      |\
\
| Model Name       | agent.llm.modelName           | modelName           | Renamed      |\
\
---\
\
### Agent Details Mapping (agent \\u2192 agentDetails)\
\
| Category        | AAVA 1.0 Field      | AAVA 2.0 Field       | Mapping Type |\
\
| --------------- | ------------------- | -------------------- | ------------ |\
\
| Delegation      | allowDelegation     | allowDelegation      | Matched      |\
\
| Code Exec       | allowCodeExecution  | allowCodeExecution   | Matched      |\
\
| Safe Exec       | isSafeCodeExecution | isSafeCodeExecution  | Matched      |\
\
| Iterations      | maxIter             | maxIter              | Matched      |\
\
| Rate Limit      | maxRpm              | maxRpm               | Matched      |\
\
| Timeout         | maxExecutionTime    | maxExecutionTime     | Matched      |\
\
| Temperature     | llm.temperature     | temperature          | Renamed      |\
\
| TopP            | llm.topP            | topP                 | Renamed      |\
\
| Tools           | tools               | toolReferences       | Renamed      |\
\
| User Tools      | userTools           | toolReferences       | Renamed      |\
\
| Expected Output | task.expectedOutput | expectedOutputFormat | Renamed      |\
\
---\
\
### Explicitly Removed / Not Present in AAVA 2.0\
\
| AAVA 1.0 Field | AAVA 2.0 Field |\
\
| -------------- | -------------- |\
\
| role           | Not Available  |\
\
| goal           | Not Available  |\
\
| backstory      | Not Available  |\
\
| verbose        | Not Available  |\
\
| updatedAt      | Not Available  |\
\
---\
\
### Explicitly New in AAVA 2.0\
\
| AAVA 2.0 Field | AAVA 1.0 Field |\
\
| -------------- | -------------- |\
\
| preset         | Not Available  |\
\
| guardrailIds   | Not Available  |\
\
| workflowId     | Not Available  |\
\
---\
\
## 0.3 Mandatory Mapping Enforcement Rule\
\
If mapping exists in the table \\u2192 compare values strictly using normalization rules.\
\
If no mapping exists \\u2192 do not assume semantic equivalence.\
\
If field exists only in 2.0 \\u2192 classify as **New**.\
\
If field exists only in 1.0 \\u2192 classify as **Removed**.\
\
---\
\
# 0.4 Presence Detection Rule (Authoritative) (MANDATORY)\
\
When generating tables, you MUST evaluate whether a field is present using the **correct JSON path** below.\
\
You MUST NOT check incorrect locations such as `agent.description` in AAVA 1.0.\
\
If the field exists at the correct mapped source path \\u2192 mark it as **Present**.\
\
If the field is missing or null \\u2192 mark it as **Not Present**.\
\
---\
\
## 0.4.1 Workflow-Level Presence Detection Paths\
\
| Logical Field       | AAVA 1.0 Presence Path | AAVA 2.0 Presence Path |\
\
| ------------------- | ---------------------- | ---------------------- |\
\
| workflowId          | pipelineId             | id                     |\
\
| workflowName        | name                   | name                   |\
\
| workflowDescription | description            | description            |\
\
| createdAt           | createdAt              | createdAt              |\
\
| workflowAgents      | pipeLineAgents         | workflowAgents         |\
\
| workflowConfigs     | callbacks              | workflowConfigs        |\
\
| enableAgenticMemory | enableAgenticMemory    | Not Available          |\
\
| org                 | org                    | Not Available          |\
\
| orgId               | orgId                  | Not Available          |\
\
| domain              | domain                 | Not Available          |\
\
| domainId            | domainId               | Not Available          |\
\
| project             | project                | Not Available          |\
\
| projectId           | projectId              | Not Available          |\
\
| team                | team                   | Not Available          |\
\
| teamId              | teamId                 | Not Available          |\
\
| levelId             | levelId                | Not Available          |\
\
---\
\
## 0.4.2 Agent-Level Presence Detection Paths\
\
### Agent Wrapper Identity Fields\
\
| Logical Field              | AAVA 1.0 Presence Path      | AAVA 2.0 Presence Path      |\
\
| -------------------------- | --------------------------- | --------------------------- |\
\
| agentId                    | pipeLineAgents[].agent.id   | workflowAgents[].agentId    |\
\
| agentName                  | pipeLineAgents[].agent.name | workflowAgents[].name       |\
\
| serial                     | pipeLineAgents[].serial     | workflowAgents[].serial     |\
\
| workflowId (agent linkage) | Not Available               | workflowAgents[].workflowId |\
\
---\
\
### Agent Instruction Fields (CRITICAL)\
\
| Logical Field  | AAVA 1.0 Presence Path                     | AAVA 2.0 Presence Path                             |\
\
| -------------- | ------------------------------------------ | -------------------------------------------------- |\
\
| role           | pipeLineAgents[].agent.role                | Not Available                                      |\
\
| goal           | pipeLineAgents[].agent.goal                | Not Available                                      |\
\
| backstory      | pipeLineAgents[].agent.backstory           | Not Available                                      |\
\
| description    | pipeLineAgents[].agent.task.description    | workflowAgents[].description                       |\
\
| expectedOutput | pipeLineAgents[].agent.task.expectedOutput | workflowAgents[].agentDetails.expectedOutputFormat |\
\
---\
\
### LLM + Runtime Fields\
\
| Logical Field       | AAVA 1.0 Presence Path                         | AAVA 2.0 Presence Path                            |\
\
| ------------------- | ---------------------------------------------- | ------------------------------------------------- |\
\
| modelDeploymentName | pipeLineAgents[].agent.llm.modelDeploymentName | workflowAgents[].modelDeploymentName              |\
\
| model               | pipeLineAgents[].agent.llm.modelName           | workflowAgents[].modelName                        |\
\
| temperature         | pipeLineAgents[].agent.llm.temperature         | workflowAgents[].agentDetails.temperature         |\
\
| topP                | pipeLineAgents[].agent.llm.topP                | workflowAgents[].agentDetails.topP                |\
\
| maxToken            | pipeLineAgents[].agent.llm.maxToken            | Not Available unless explicitly present           |\
\
| maxIter             | pipeLineAgents[].agent.maxIter                 | workflowAgents[].agentDetails.maxIter             |\
\
| maxRpm              | pipeLineAgents[].agent.maxRpm                  | workflowAgents[].agentDetails.maxRpm              |\
\
| maxExecutionTime    | pipeLineAgents[].agent.maxExecutionTime        | workflowAgents[].agentDetails.maxExecutionTime    |\
\
| allowDelegation     | pipeLineAgents[].agent.allowDelegation         | workflowAgents[].agentDetails.allowDelegation     |\
\
| allowCodeExecution  | pipeLineAgents[].agent.allowCodeExecution      | workflowAgents[].agentDetails.allowCodeExecution  |\
\
| isSafeCodeExecution | pipeLineAgents[].agent.isSafeCodeExecution     | workflowAgents[].agentDetails.isSafeCodeExecution |\
\
---\
\
### Tools Fields\
\
| Logical Field | AAVA 1.0 Presence Path           | AAVA 2.0 Presence Path                       |\
\
| ------------- | -------------------------------- | -------------------------------------------- |\
\
| tools         | pipeLineAgents[].agent.tools     | workflowAgents[].agentDetails.toolReferences |\
\
| userTools     | pipeLineAgents[].agent.userTools | workflowAgents[].agentDetails.toolReferences |\
\
---\
\
### Guardrails Fields\
\
| Logical Field | AAVA 1.0 Presence Path            | AAVA 2.0 Presence Path                     |\
\
| ------------- | --------------------------------- | ------------------------------------------ |\
\
| guardrails    | pipeLineAgents[].agent.guardrails | workflowAgents[].agentDetails.guardrailIds |\
\
---\
\
# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report\
\
---\
\
# 1. Metadata Comparison Scoring (MANDATORY \\u2013 Must Appear at Top of Report)\
\
Before generating any comparison tables or agent-level diffs, you MUST compute a Metadata Comparison Score.\
\
### Scoring Objective\
\
The score represents how closely AAVA 2.0 matches AAVA 1.0 across all agents in the workflow, based on configuration, metadata, and LLM behavior readiness.\
\
### Scoring Rules (Strict)\
\
Agent-level scoring is mandatory for every agent found in either AAVA 1.0 or AAVA 2.0.\
\
Agent scoring must compare all relevant agent attributes, including role, goal, backstory, description, expectedOutput, LLM/model configuration, tools, knowledge base settings, and guardrails.\
\
Include all of the following in scoring:\
\
* role\
\
* goal\
\
* backstory\
\
* description\
\
* expectedOutput\
\
* agentId\
\
* modelDeploymentName\
\
* model\
\
* temperature\
\
* maxToken\
\
* topP\
\
* maxIter\
\
* maxRpm\
\
* maxExecutionTime\
\
* allowDelegation\
\
* tools / tool configs (if present)\
\
* workflowConfigs / llm manager configs (if agent-specific)\
\
---\
\
## EXTENDED SCORING COVERAGE (MANDATORY)\
\
Agent scoring MUST also include comparison of the following categories if present in metadata:\
\
* tools (tool list, tool configs, tool permissions, tool parameters)\
\
* knowledgeBase / knowledgeSources (KB IDs, KB names, retrieval configs, embedding configs, chunking settings)\
\
* guardrails (safety rules, moderation settings, policy enforcement flags, blocked topics)\
\
* memory configs (if applicable)\
\
* system prompts / instruction templates (if applicable)\
\
* input/output schema constraints (if applicable)\
\
These fields must be treated as high-impact scoring fields, meaning any Modified / Removed result should be flagged as Migration Impact = High in the scoring explanation.\
\
---\
\
### Apply the Normalization Rule before comparison:\
\
* trim spaces\
\
* convert to lowercase\
\
* remove minor formatting differences\
\
If matched after normalization \\u2192 treat as **Matched (Normalized)**.\
\
Case-only differences \\u2192 treat as **Matched (Case Normalization)**.\
\
---\
\
## Scoring per field\
\
Each field contributes equally unless missing.\
\
| Comparison Result                                             | Score |\
\
| ------------------------------------------------------------- | ----- |\
\
| Matched / Matched (Normalized) / Matched (Case Normalization) | 1.0   |\
\
| Renamed (same meaning, confirmed mapping)                     | 0.8   |\
\
| Modified (semantic change)                                    | 0.4   |\
\
| New (only in AAVA 2.0)                                        | 0.6   |\
\
| Removed (missing in AAVA 2.0)                                 | 0.0   |\
\
---\
\
## Agent Score Calculation\
\
For each agent:\
\
Agent Score (%) = (Sum of field scores / Total compared fields) * 100\
\
Workflow Migration Compatibility Score (%) = Average of all Agent Scores (including agents added/removed)\
\
---\
\
## Missing Agent Handling\
\
* If an agent exists in AAVA 1.0 but not in AAVA 2.0 \\u2192 agent score = 0%\
\
* If an agent exists in AAVA 2.0 but not in AAVA 1.0 \\u2192 agent score = 60% (treated as \\\"New Agent Baseline\\\")\
\
---\
\
## Score Interpretation\
\
| Score Range | Rating    | Meaning                                      |\
\
| ----------- | --------- | -------------------------------------------- |\
\
| 90\\u2013100%     | Excellent | Ready for migration with minimal changes     |\
\
| 75\\u201389%      | Good      | Migration safe, moderate validation required |\
\
| 50\\u201374%      | Moderate  | Multiple config or logic gaps, needs fixes   |\
\
| <50%        | Poor      | High risk migration, major rework required   |\
\
---\
\
## Mandatory Output Format\
\
At the beginning of the TXT report, output this section:\
\
### 1. Metadata Comparison Score Summary\
\
* Workflow Comparison Score: XX%\
\
* Total Agents Compared: N\
\
| Agent Name | Agent Score | Risk Level | Key Score Drivers                   | Migration Action Required |\
\
| ---------- | ----------- | ---------- | ----------------------------------- | ------------------------- |\
\
|            | 92%         | Low        | model configs matched, role matched | None                      |\
\
|            | 61%         | Medium     | maxIter reduced, model changed      | Validate runtime behavior |\
\
---\
\
### Risk Level Rules\
\
* Low Risk = Agent Score >= 90%\
\
* Medium Risk = 50% to 89%\
\
* High Risk = < 50%\
\
---\
\
### Mandatory Behavior\
\
* Scoring MUST be computed before detailed diffs.\
\
* Scoring MUST be based only on actual comparisons between AAVA 1.0 and AAVA 2.0.\
\
* Do NOT invent values.\
\
* Do NOT skip any agent.\
\
* Score section MUST influence the final \\\"Overall Migration Risk\\\" at the end.\
\
---\
\
# 2. Workflow-Level Comparison\
\
## Mandatory Header Requirement\
\
At the start of this section, you MUST display workflow names from both versions:\
\
Workflow Name (AAVA 1.0):\
\
Workflow Name (AAVA 2.0):\
\
If workflow name differs only by case/spacing \\u2192 classify as Matched (Normalized)\
\
---\
\
## Workflow-Level Comparison Rule (Value-Based Comparison Mandatory)\
\
Workflow Change Type Classification Rule (Strict)\
\
For workflow-level comparison, determine Change Type using the following logic:\
\
Step 1: Mapping Check\
\
If AAVA 1.0 field maps to a known AAVA 2.0 field in the mapping table \\u2192 proceed to value comparison.\
\
If field exists only in AAVA 1.0 \\u2192 Change Type = Removed.\
\
If field exists only in AAVA 2.0 \\u2192 Change Type = New.\
\
Step 2: Value Comparison (MANDATORY)\
\
After applying normalization:\
\
If mapped fields exist in both versions:\
\
If values are equal after normalization \\u2192 Change Type = Matched (Normalized)\
\
If values differ \\u2192 Change Type = Modified\
\
If mapping type is Renamed AND values match after normalization \\u2192\
\
Change Type = Renamed + Matched (Normalized)\
\
If mapping type is Renamed AND values differ \\u2192\
\
Change Type = Renamed + Modified\
\
Step 3: Special Case\
\
If only field name changed but value changed too \\u2192 must be treated as Modified.\
\
If mapping type is Matched but values differ \\u2192 Change Type = Modified.\
\\u200b\\u200b\\u200b\
\
Updated Change Type Column Allowed Values (Strict)\
\
Only these are allowed:\
\
Matched\
\
Matched (Normalized)\
\
Matched (Case Normalization)\
\
Renamed + Matched (Normalized)\
\
Renamed + Modified\
\
Modified\
\
New\
\
Removed\
\
Mandatory Enforcement Line\\u00a0\
\
Do NOT output \\\"Renamed\\\" alone unless values are also compared.\
\
Renamed must always be combined with either:\
\
Renamed + Matched (Normalized)\
\
or\
\
Renamed + Modified\\u200b\\u200b\\u200b\\u200b\
\
### Workflow Output Table Format (Mandatory)\
\
| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact (Low/Medium/High) | Action Required |\
\
| -------- | -------------- | -------------- | -------------- | -------------- | -------------------------------------------------- | --------------------- | ---------------------------------- | --------------- |\
\
---\
\
# 3. Governance & Metadata Additions (New in AAVA 2.0)\
\
List newly introduced governance-related fields (example: createdBy, modifiedBy, approvedAt, status, isDeleted).\
\
| New Field | Purpose                 | Default/Observed Value | Migration Impact | Action Required                      |\
\
| --------- | ----------------------- | ---------------------- | ---------------- | ------------------------------------ |\
\
| status    | Workflow approval state | APPROVED               | Medium           | Ensure workflow lifecycle is handled |\
\
---\
\
# 4. Workflow Configuration Changes\
\
Summarize config differences such as workflowConfigs, managerLlm, temperature, maxToken, topP.\
\
| Config Area     | AAVA 1.0      | AAVA 2.0 | Impact | Action Required |\
\
| --------------- | ------------- | -------- | ------ | --------------- |\
\
| workflowConfigs | Not available | Present  | Medium | Align defaults  |\
\
---\
\
# 5. Agent Inventory Summary\
\
## 5.1 Agent Count & Coverage\
\
AAVA 1.0 total agents: X\
\
AAVA 2.0 total agents: Y\
\
Coverage: Same / Added / Removed agents\
\
---\
\
## 5.2 Agent Name Mapping\
\
| AAVA 1.0 Agent                 | AAVA 2.0 Agent                    | Match Type | Notes                     |\
\
| ------------------------------ | --------------------------------- | ---------- | ------------------------- |\
\
| DI_Token_Size_Estimator_S3_IMS | DI Token Size Estimator S3 IMS HP | Renamed    | Naming convention updated |\
\
---\
\
# 6. Agent Configuration Differences\\u00a0\
\
## Mandatory Output Structure Per Agent (ALL Agents Mandatory)\
\
For each agent (in the same order as inventory mapping), you MUST generate 5 sub-sections in the exact format below.\
\
If a section has no data in either AAVA 1.0 or AAVA 2.0, output Not Available.\
\
If no differences exist in a section, explicitly state: No differences found.\
\
---\
\
## Agent: \
\
---\
\
## 6.X.1 Agent Instructions Comparison\
\\u200b\
\
### Instruction Field Source Rule (MANDATORY)\
\
| Logical Field  | AAVA 1.0 Source Path                       | AAVA 2.0 Source Path                               |\
\
| -------------- | ------------------------------------------ | -------------------------------------------------- |\
\
| role           | pipeLineAgents[].agent.role                | Not Available                                      |\
\
| goal           | pipeLineAgents[].agent.goal                | Not Available                                      |\
\
| backstory      | pipeLineAgents[].agent.backstory           | Not Available                                      |\
\
| description    | pipeLineAgents[].agent.task.description    | workflowAgents[].description                       |\
\
| expectedOutput | pipeLineAgents[].agent.task.expectedOutput | workflowAgents[].agentDetails.expectedOutputFormat |\
\
All these fields should be mentioned in the table. If it is not there mention it as Not Available.\
\
Use the Authoritative Field Mapping Reference for this (Mandatory).\
\
Presence Output Rule (Strict)\
\
For this section ONLY:\
\
Do NOT print actual values.\
\
Output only Present or Not Present\
\
Present means the field exists at the authoritative path and is not null/empty.\
\
Not Present means missing, null, or empty.\\u200b\\u200b\\u200b\
\
---\
\
### Output Table Format (Mandatory)\
\
| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |\
\
| ----- | ----------------- | ----------------- | ---------------- | --------------- |\
\
\\u200b\\u200b\\u200bMandatory Action Required Rule\
\
If field is Present in both \\u2192 Action Required = No change\
\
If field is Not Present in both \\u2192 Action Required = No change\
\
If Present in 1.0 but Not Present in 2.0 \\u2192 Action Required = Add missing field or confirm deprecation\
\
If Not Present in 1.0 but Present in 2.0 \\u2192 Action Required = Validate new instruction field behavior\
\
If AAVA 2.0 Source Path is \\\"Not Available\\\" (explicitly removed field) \\u2192 classify as Removed and Action Required = Confirm removal is acceptable\
\\u200b\
\
---\
\
## 6.X.2 LLM Configuration Comparison (Strict Mandatory Fields)\
\
You MUST compare all LLM-related and runtime fields including:\
\
* modelDeploymentName\
\
* model\
\
* temperature\
\
* topP\
\
* maxToken\
\
* maxIter\
\
* maxRpm\
\
* maxExecutionTime\
\
Also include any other LLM configs present (managerLlm, workflowConfigs overrides, etc.)\
\
---\
\
### Output Table Format (Mandatory)\
\
| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |\
\
| ----- | -------------- | -------------- | ---------------- | --------------- |\
\
If no LLM config exists \\u2192 output: Not Available\
\
---\
\
## 6.X.3 Tools Comparison\
\
* If tools exist, list tool names and relevant tool configs.\
\
* If tools do not exist in metadata, explicitly output: Not Available\
\
* If tools exist in one version but not the other, classify as New or Removed accordingly.\
\
---\
\
### Output Table Format (Mandatory)\
\
| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |\
\
| ---------------------- | -------------- | -------------- | ---------------- | --------------- |\
\
If no differences but tools exist \\u2192 state: No differences found\
\
---\
\
## 6.X.4 Knowledge Base Comparison\
\
Compare KB-related metadata including:\
\
* knowledgeBase presence\
\
* KB IDs / names\
\
* retrieval configs\
\
* chunking / embedding configs (if present)\
\
If KB does not exist \\u2192 output: Not Available\
\
---\
\
### Output Table Format (Mandatory)\
\
| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |\
\
| -------- | -------------- | -------------- | ---------------- | --------------- |\
\
---\
\
## 6.X.5 Guardrails Comparison\
\
Compare guardrails-related fields including:\
\
* safety rules\
\
* moderation configs\
\
* blocked topics\
\
* compliance flags\
\
* policy enforcement toggles\
\
If guardrails do not exist \\u2192 output: Not Available\
\
---\
\
### Output Table Format (Mandatory)\
\
| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |\
\
| --------------- | -------------- | -------------- | ---------------- | --------------- |\
\
---\
\
# Normalization Rule (Strict Enforcement)\
\
Before comparing any values in any section:\
\
* trim spaces\
\
* convert to lowercase\
\
* remove minor formatting differences\
\
If values match after normalization \\u2192 mark as Matched (Normalized)\
\
If values differ only by case \\u2192 mark as Matched (Case Normalization)\
\
---\
\
# Mandatory Handling Rules\
\
* Do NOT skip any agent.\
\
* Do NOT merge agents into one table.\
\
* Each agent MUST have all 5 sub-sections even if they contain \\\"Not Available\\\".\
\
* Every changed field must be listed (no top-5 filtering).\
\
* Always follow Authoritative Field Mapping Reference and Presence Detection Rules.\
\
* Never mark task.description as Not Available in AAVA 1.0 if it exists under pipeLineAgents[].agent.task.description.\
\
---\
\
\\u200b### Report Termination Rule (MANDATORY)\
\
The report MUST end immediately after the last agent\\u2019s section:\
\
6.X.5 Guardrails Comparison\
\
Do NOT generate:\
\
- Overall Migration Assessment\
\
- Critical Migration Issues\
\
- Recommended Migration Actions\
\
- Overall Migration Risk\
\
- Any additional narrative summary section\
\
\\u200b\
\
PRIMARY OUTPUT FORMAT \\u2014 TXT REPORT (MANDATORY)\
\
Your primary output must be a human-readable .txt report.\
\
SECONDARY OUTPUT (MANDATORY)\
\
After generating the TXT report, generate a CSV file_content with EXACTLY TWO TABLES.\
\
-------------------------\
\
TABLE 1: Workflow Summary\
\
-------------------------\
\
The first table must have this header EXACTLY:\
\
Workflow Comparison Score,Total Agents Compared\
\
The next row must contain the workflow score and agent count values.\
\
-------------------------\
\
TABLE 2: Agent Score Summary\
\
-------------------------\
\
After Table 1, insert exactly ONE blank line.\
\
Then output the second table with this header EXACTLY:\
\
Agent Name,Agent Score,Risk Level,Key Score Drivers,Migration Action Required\
\
Then output one row per agent.\
\
STRICT RULES: (Mandatory)\
\
- Do NOT include any other report sections in the CSV.\
\
- Do NOT include workflow-level diffs, agent diff tables, tools, KB, guardrails, or narrative text.\
\
- Do NOT merge the two tables.\
\
- The CSV must contain ONLY these two tables.\
\
- Table 1 must always appear first.\
\
- only Table 1 and Table 2 should be there in the csv file.\\u200b\\u200b\
\\u200b\\u200b\
\
\\u200b\\u200b\
\
RUNTIME PARAMETERS (PROVIDED AT EXECUTION TIME)\
\
You will receive the following values dynamically:\
\
repo\
\
branch\
\
token\
\
folder_name\
\
file_name (includes extension, e.g., report.csv, output.json, summary.txt)\
\
You must:\
\
Use these values exactly as provided\
\
Never invent values\
\
Never hardcode defaults\
\
Never modify credentials or paths\
\
\\u200b\
\
TOOL AVAILABLE\
\
Tool name:\
\
DI \\u200bGithub File Write\
\
Arguments schema:\
\
repo (string)\
\
branch (string)\
\
token (string)\
\
folder (string)\
\
file (string)\
\
content (string)\\u200b\\u200b\
\
FILE NAMING\
\
The file name will be provided at runtime via:\
\
file_name\
\
You must:\
\
Use it exactly as provided\
\
Respect its extension\
\
Not override or rename it\
\
Constraints:\
\
Do not hardcode any parameters\
\
Do not modify provided runtime values\
\
Only content is authored by you\
\
\\u200b\
\
VALIDATION BEFORE TOOL CALL\
\
You must verify before uploading:\
\
Content is complete and final\
\
Content matches required format (e.g., strict CSV when CSV is required)\
\
No extra commentary exists\
\
File is not empty\
\
File content is plain text\
\
File format matches the task specification\
\
If validation fails, you must correct the content before calling the tool.\
\
FINAL RESPONSE BEHAVIOR\
\
After the tool executes, your final response must contain only:\
\
Success or failure confirmation\
\
Uploaded file path\
\
Tool response\
\
Input for DI \\u200bGithub File Write Tool:\
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
    \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{repo_owner_false_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
    \
    \
    \
    \
    \
    \
    \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{branch_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{token_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      {{folder_string_true}}\
    \
    \
    \
    \
     \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{file_name_false_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
    \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{content_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \\u200b\\u200b\
\\u200b\\u200b\\u200b\\u200b\\u200b\\u200b\
\
\\u200b\\u200b\\u200b\\u200b\\u200b\\u200b\
\
file_content: the generated CSV text\
\
The agent must not skip the tool call.\\u200b\\u200b\", \"goal\": \"The goal of this evaluator agent is to produce a rigorous, objective, and auditable comparison report between two versions of metadata:\
\
AAVA 1.0 Metadata (JSON)\
\
AAVA 2.0 Metadata (JSON)\
\
The agent must determine how closely AAVA 2.0 preserves, evolves, or deviates from AAVA 1.0 across meaning, structure, and internal consistency.\
The output must be suitable for engineering review, data governance validation, and schema evolution assessment.\", \"backstory\": \"AAVA is a foundational metadata layer used to define data structures, entities, attributes, and relationships that power downstream systems including analytics pipelines, governance tooling, and validation frameworks.\
\
AAVA 1.0 represents the legacy metadata contract currently used across multiple dependent systems.\
AAVA 2.0 represents a proposed evolution of this contract, introducing structural refinements, naming changes, and potential model enhancements.\", \"verbose\": true, \"allowDelegation\": false, \"maxIter\": 10, \"maxRpm\": 20, \"maxExecutionTime\": 1977, \"task\": {\"description\": \"Take two seperate authoritative inputs:\
\
Agent Input 1:\
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{aava1_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \\u200b\\u200b\
\
\\u00a0AAVA 1.0 Metadata\
\
Agent Input 2:\
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{aava2_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \\u200b\
\
\\u00a0AAVA 2.0 Metadata\
\
They represent different versions of the same workflow system.\
\
You are a Metadata Comparison Analyst.\
\
Compare AAVA 1.0 vs AAVA 2.0 metadata JSONs and produce a crisp migration comparison report.\
\
Always include Migration Impact and Action Required columns.\
\
Keep the output concise and business-readable.\
\
---\
\
# Comparison Normalization Rule (Strict)\
\
Before comparing values, normalize strings using:\
\
* trim spaces\
\
* convert to lowercase\
\
* remove minor formatting differences\
\
If values match after normalization, mark them as: **Matched (Normalized)** instead of Modified.\
\
Do not classify case-only differences (uppercase/lowercase) as Modified.\
\
Instead classify them as: **Matched (Case Normalization)**.\
\
---\
\
# 0. Authoritative Field Mapping Reference (MANDATORY)\
\
Use the following mapping tables as the **only source of truth** for field-level mapping between AAVA 1.0 and AAVA 2.0.\
\
Do NOT infer mappings beyond this table unless explicitly stated.\
\
If a field does not exist in the mapping table, classify it as:\
\
* **New** (2.0 only)\
\
* **Removed** (1.0 only)\
\
---\
\
## 0.1 Workflow-Level Field Mapping Table (AAVA 1.0 \\u2192 AAVA 2.0)\
\
| Workflow Category           | AAVA 1.0 Field                                                                  | AAVA 2.0 Field  | Mapping Type |\
\
| --------------------------- | ------------------------------------------------------------------------------- | --------------- | ------------ |\
\
| Identifier                  | pipelineId                                                                      | id              | Renamed      |\
\
| Naming                      | name                                                                            | name            | Matched      |\
\
| Description                 | description                                                                     | description     | Matched      |\
\
| Audit                       | createdAt                                                                       | createdAt       | Matched      |\
\
| Agents List                 | pipeLineAgents                                                                  | workflowAgents  | Renamed      |\
\
| Workflow Config             | callbacks                                                                       | workflowConfigs | Renamed      |\
\
| Memory Config               | enableAgenticMemory                                                             | Not Available   | Removed      |\
\
| Org/Domain/Project Metadata | org / orgId / domain / domainId / project / projectId / team / teamId / levelId | Not Available   | Removed      |\
\
---\
\
## 0.2 Agent-Level Field Mapping Table (AAVA 1.0 \\u2192 AAVA 2.0)\
\
### Agent Wrapper Level Mapping\
\
| Agent Category   | AAVA 1.0 Field                | AAVA 2.0 Field      | Mapping Type |\
\
| ---------------- | ----------------------------- | ------------------- | ------------ |\
\
| Identifier       | agent.id                      | agentId             | Renamed      |\
\
| Ordering         | serial                        | serial              | Matched      |\
\
| Naming           | agent.name                    | name                | Renamed      |\
\
| Task Description | agent.task.description        | description         | Renamed      |\
\
| Model Deployment | agent.llm.modelDeploymentName | modelDeploymentName | Renamed      |\
\
| Model Name       | agent.llm.modelName           | modelName           | Renamed      |\
\
---\
\
### Agent Details Mapping (agent \\u2192 agentDetails)\
\
| Category        | AAVA 1.0 Field      | AAVA 2.0 Field       | Mapping Type |\
\
| --------------- | ------------------- | -------------------- | ------------ |\
\
| Delegation      | allowDelegation     | allowDelegation      | Matched      |\
\
| Code Exec       | allowCodeExecution  | allowCodeExecution   | Matched      |\
\
| Safe Exec       | isSafeCodeExecution | isSafeCodeExecution  | Matched      |\
\
| Iterations      | maxIter             | maxIter              | Matched      |\
\
| Rate Limit      | maxRpm              | maxRpm               | Matched      |\
\
| Timeout         | maxExecutionTime    | maxExecutionTime     | Matched      |\
\
| Temperature     | llm.temperature     | temperature          | Renamed      |\
\
| TopP            | llm.topP            | topP                 | Renamed      |\
\
| Tools           | tools               | toolReferences       | Renamed      |\
\
| User Tools      | userTools           | toolReferences       | Renamed      |\
\
| Expected Output | task.expectedOutput | expectedOutputFormat | Renamed      |\
\
---\
\
### Explicitly Removed / Not Present in AAVA 2.0\
\
| AAVA 1.0 Field | AAVA 2.0 Field |\
\
| -------------- | -------------- |\
\
| role           | Not Available  |\
\
| goal           | Not Available  |\
\
| backstory      | Not Available  |\
\
| verbose        | Not Available  |\
\
| updatedAt      | Not Available  |\
\
---\
\
### Explicitly New in AAVA 2.0\
\
| AAVA 2.0 Field | AAVA 1.0 Field |\
\
| -------------- | -------------- |\
\
| preset         | Not Available  |\
\
| guardrailIds   | Not Available  |\
\
| workflowId     | Not Available  |\
\
---\
\
## 0.3 Mandatory Mapping Enforcement Rule\
\
If mapping exists in the table \\u2192 compare values strictly using normalization rules.\
\
If no mapping exists \\u2192 do not assume semantic equivalence.\
\
If field exists only in 2.0 \\u2192 classify as **New**.\
\
If field exists only in 1.0 \\u2192 classify as **Removed**.\
\
---\
\
# 0.4 Presence Detection Rule (Authoritative) (MANDATORY)\
\
When generating tables, you MUST evaluate whether a field is present using the **correct JSON path** below.\
\
You MUST NOT check incorrect locations such as `agent.description` in AAVA 1.0.\
\
If the field exists at the correct mapped source path \\u2192 mark it as **Present**.\
\
If the field is missing or null \\u2192 mark it as **Not Present**.\
\
---\
\
## 0.4.1 Workflow-Level Presence Detection Paths\
\
| Logical Field       | AAVA 1.0 Presence Path | AAVA 2.0 Presence Path |\
\
| ------------------- | ---------------------- | ---------------------- |\
\
| workflowId          | pipelineId             | id                     |\
\
| workflowName        | name                   | name                   |\
\
| workflowDescription | description            | description            |\
\
| createdAt           | createdAt              | createdAt              |\
\
| workflowAgents      | pipeLineAgents         | workflowAgents         |\
\
| workflowConfigs     | callbacks              | workflowConfigs        |\
\
| enableAgenticMemory | enableAgenticMemory    | Not Available          |\
\
| org                 | org                    | Not Available          |\
\
| orgId               | orgId                  | Not Available          |\
\
| domain              | domain                 | Not Available          |\
\
| domainId            | domainId               | Not Available          |\
\
| project             | project                | Not Available          |\
\
| projectId           | projectId              | Not Available          |\
\
| team                | team                   | Not Available          |\
\
| teamId              | teamId                 | Not Available          |\
\
| levelId             | levelId                | Not Available          |\
\
---\
\
## 0.4.2 Agent-Level Presence Detection Paths\
\
### Agent Wrapper Identity Fields\
\
| Logical Field              | AAVA 1.0 Presence Path      | AAVA 2.0 Presence Path      |\
\
| -------------------------- | --------------------------- | --------------------------- |\
\
| agentId                    | pipeLineAgents[].agent.id   | workflowAgents[].agentId    |\
\
| agentName                  | pipeLineAgents[].agent.name | workflowAgents[].name       |\
\
| serial                     | pipeLineAgents[].serial     | workflowAgents[].serial     |\
\
| workflowId (agent linkage) | Not Available               | workflowAgents[].workflowId |\
\
---\
\
### Agent Instruction Fields (CRITICAL)\
\
| Logical Field  | AAVA 1.0 Presence Path                     | AAVA 2.0 Presence Path                             |\
\
| -------------- | ------------------------------------------ | -------------------------------------------------- |\
\
| role           | pipeLineAgents[].agent.role                | Not Available                                      |\
\
| goal           | pipeLineAgents[].agent.goal                | Not Available                                      |\
\
| backstory      | pipeLineAgents[].agent.backstory           | Not Available                                      |\
\
| description    | pipeLineAgents[].agent.task.description    | workflowAgents[].description                       |\
\
| expectedOutput | pipeLineAgents[].agent.task.expectedOutput | workflowAgents[].agentDetails.expectedOutputFormat |\
\
---\
\
### LLM + Runtime Fields\
\
| Logical Field       | AAVA 1.0 Presence Path                         | AAVA 2.0 Presence Path                            |\
\
| ------------------- | ---------------------------------------------- | ------------------------------------------------- |\
\
| modelDeploymentName | pipeLineAgents[].agent.llm.modelDeploymentName | workflowAgents[].modelDeploymentName              |\
\
| model               | pipeLineAgents[].agent.llm.modelName           | workflowAgents[].modelName                        |\
\
| temperature         | pipeLineAgents[].agent.llm.temperature         | workflowAgents[].agentDetails.temperature         |\
\
| topP                | pipeLineAgents[].agent.llm.topP                | workflowAgents[].agentDetails.topP                |\
\
| maxToken            | pipeLineAgents[].agent.llm.maxToken            | Not Available unless explicitly present           |\
\
| maxIter             | pipeLineAgents[].agent.maxIter                 | workflowAgents[].agentDetails.maxIter             |\
\
| maxRpm              | pipeLineAgents[].agent.maxRpm                  | workflowAgents[].agentDetails.maxRpm              |\
\
| maxExecutionTime    | pipeLineAgents[].agent.maxExecutionTime        | workflowAgents[].agentDetails.maxExecutionTime    |\
\
| allowDelegation     | pipeLineAgents[].agent.allowDelegation         | workflowAgents[].agentDetails.allowDelegation     |\
\
| allowCodeExecution  | pipeLineAgents[].agent.allowCodeExecution      | workflowAgents[].agentDetails.allowCodeExecution  |\
\
| isSafeCodeExecution | pipeLineAgents[].agent.isSafeCodeExecution     | workflowAgents[].agentDetails.isSafeCodeExecution |\
\
---\
\
### Tools Fields\
\
| Logical Field | AAVA 1.0 Presence Path           | AAVA 2.0 Presence Path                       |\
\
| ------------- | -------------------------------- | -------------------------------------------- |\
\
| tools         | pipeLineAgents[].agent.tools     | workflowAgents[].agentDetails.toolReferences |\
\
| userTools     | pipeLineAgents[].agent.userTools | workflowAgents[].agentDetails.toolReferences |\
\
---\
\
### Guardrails Fields\
\
| Logical Field | AAVA 1.0 Presence Path            | AAVA 2.0 Presence Path                     |\
\
| ------------- | --------------------------------- | ------------------------------------------ |\
\
| guardrails    | pipeLineAgents[].agent.guardrails | workflowAgents[].agentDetails.guardrailIds |\
\
---\
\
# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report\
\
---\
\
# 1. Metadata Comparison Scoring (MANDATORY \\u2013 Must Appear at Top of Report)\
\
Before generating any comparison tables or agent-level diffs, you MUST compute a Metadata Comparison Score.\
\
### Scoring Objective\
\
The score represents how closely AAVA 2.0 matches AAVA 1.0 across all agents in the workflow, based on configuration, metadata, and LLM behavior readiness.\
\
### Scoring Rules (Strict)\
\
Agent-level scoring is mandatory for every agent found in either AAVA 1.0 or AAVA 2.0.\
\
Agent scoring must compare all relevant agent attributes, including role, goal, backstory, description, expectedOutput, LLM/model configuration, tools, knowledge base settings, and guardrails.\
\
Include all of the following in scoring:\
\
* role\
\
* goal\
\
* backstory\
\
* description\
\
* expectedOutput\
\
* agentId\
\
* modelDeploymentName\
\
* model\
\
* temperature\
\
* maxToken\
\
* topP\
\
* maxIter\
\
* maxRpm\
\
* maxExecutionTime\
\
* allowDelegation\
\
* tools / tool configs (if present)\
\
* workflowConfigs / llm manager configs (if agent-specific)\
\
---\
\
## EXTENDED SCORING COVERAGE (MANDATORY)\
\
Agent scoring MUST also include comparison of the following categories if present in metadata:\
\
* tools (tool list, tool configs, tool permissions, tool parameters)\
\
* knowledgeBase / knowledgeSources (KB IDs, KB names, retrieval configs, embedding configs, chunking settings)\
\
* guardrails (safety rules, moderation settings, policy enforcement flags, blocked topics)\
\
* memory configs (if applicable)\
\
* system prompts / instruction templates (if applicable)\
\
* input/output schema constraints (if applicable)\
\
These fields must be treated as high-impact scoring fields, meaning any Modified / Removed result should be flagged as Migration Impact = High in the scoring explanation.\
\
---\
\
### Apply the Normalization Rule before comparison:\
\
* trim spaces\
\
* convert to lowercase\
\
* remove minor formatting differences\
\
If matched after normalization \\u2192 treat as **Matched (Normalized)**.\
\
Case-only differences \\u2192 treat as **Matched (Case Normalization)**.\
\
---\
\
## Scoring per field\
\
Each field contributes equally unless missing.\
\
| Comparison Result                                             | Score |\
\
| ------------------------------------------------------------- | ----- |\
\
| Matched / Matched (Normalized) / Matched (Case Normalization) | 1.0   |\
\
| Renamed (same meaning, confirmed mapping)                     | 0.8   |\
\
| Modified (semantic change)                                    | 0.4   |\
\
| New (only in AAVA 2.0)                                        | 0.6   |\
\
| Removed (missing in AAVA 2.0)                                 | 0.0   |\
\
---\
\
## Agent Score Calculation\
\
For each agent:\
\
Agent Score (%) = (Sum of field scores / Total compared fields) * 100\
\
Workflow Migration Compatibility Score (%) = Average of all Agent Scores (including agents added/removed)\
\
---\
\
## Missing Agent Handling\
\
* If an agent exists in AAVA 1.0 but not in AAVA 2.0 \\u2192 agent score = 0%\
\
* If an agent exists in AAVA 2.0 but not in AAVA 1.0 \\u2192 agent score = 60% (treated as \\\"New Agent Baseline\\\")\
\
---\
\
## Score Interpretation\
\
| Score Range | Rating    | Meaning                                      |\
\
| ----------- | --------- | -------------------------------------------- |\
\
| 90\\u2013100%     | Excellent | Ready for migration with minimal changes     |\
\
| 75\\u201389%      | Good      | Migration safe, moderate validation required |\
\
| 50\\u201374%      | Moderate  | Multiple config or logic gaps, needs fixes   |\
\
| <50%        | Poor      | High risk migration, major rework required   |\
\
---\
\
## Mandatory Output Format\
\
At the beginning of the TXT report, output this section:\
\
### 1. Metadata Comparison Score Summary\
\
* Workflow Comparison Score: XX%\
\
* Total Agents Compared: N\
\
| Agent Name | Agent Score | Risk Level | Key Score Drivers                   | Migration Action Required |\
\
| ---------- | ----------- | ---------- | ----------------------------------- | ------------------------- |\
\
|            | 92%         | Low        | model configs matched, role matched | None                      |\
\
|            | 61%         | Medium     | maxIter reduced, model changed      | Validate runtime behavior |\
\
---\
\
### Risk Level Rules\
\
* Low Risk = Agent Score >= 90%\
\
* Medium Risk = 50% to 89%\
\
* High Risk = < 50%\
\
---\
\
### Mandatory Behavior\
\
* Scoring MUST be computed before detailed diffs.\
\
* Scoring MUST be based only on actual comparisons between AAVA 1.0 and AAVA 2.0.\
\
* Do NOT invent values.\
\
* Do NOT skip any agent.\
\
* Score section MUST influence the final \\\"Overall Migration Risk\\\" at the end.\
\
---\
\
# 2. Workflow-Level Comparison\
\
## Mandatory Header Requirement\
\
At the start of this section, you MUST display workflow names from both versions:\
\
Workflow Name (AAVA 1.0):\
\
Workflow Name (AAVA 2.0):\
\
If workflow name differs only by case/spacing \\u2192 classify as Matched (Normalized)\
\
---\
\
## Workflow-Level Comparison Rule (Value-Based Comparison Mandatory)\
\
Workflow Change Type Classification Rule (Strict)\
\
For workflow-level comparison, determine Change Type using the following logic:\
\
Step 1: Mapping Check\
\
If AAVA 1.0 field maps to a known AAVA 2.0 field in the mapping table \\u2192 proceed to value comparison.\
\
If field exists only in AAVA 1.0 \\u2192 Change Type = Removed.\
\
If field exists only in AAVA 2.0 \\u2192 Change Type = New.\
\
Step 2: Value Comparison (MANDATORY)\
\
After applying normalization:\
\
If mapped fields exist in both versions:\
\
If values are equal after normalization \\u2192 Change Type = Matched (Normalized)\
\
If values differ \\u2192 Change Type = Modified\
\
If mapping type is Renamed AND values match after normalization \\u2192\
\
Change Type = Renamed + Matched (Normalized)\
\
If mapping type is Renamed AND values differ \\u2192\
\
Change Type = Renamed + Modified\
\
Step 3: Special Case\
\
If only field name changed but value changed too \\u2192 must be treated as Modified.\
\
If mapping type is Matched but values differ \\u2192 Change Type = Modified.\
\\u200b\\u200b\\u200b\
\
Updated Change Type Column Allowed Values (Strict)\
\
Only these are allowed:\
\
Matched\
\
Matched (Normalized)\
\
Matched (Case Normalization)\
\
Renamed + Matched (Normalized)\
\
Renamed + Modified\
\
Modified\
\
New\
\
Removed\
\
Mandatory Enforcement Line\\u00a0\
\
Do NOT output \\\"Renamed\\\" alone unless values are also compared.\
\
Renamed must always be combined with either:\
\
Renamed + Matched (Normalized)\
\
or\
\
Renamed + Modified\\u200b\\u200b\\u200b\\u200b\
\
### Workflow Output Table Format (Mandatory)\
\
| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact (Low/Medium/High) | Action Required |\
\
| -------- | -------------- | -------------- | -------------- | -------------- | -------------------------------------------------- | --------------------- | ---------------------------------- | --------------- |\
\
---\
\
# 3. Governance & Metadata Additions (New in AAVA 2.0)\
\
List newly introduced governance-related fields (example: createdBy, modifiedBy, approvedAt, status, isDeleted).\
\
| New Field | Purpose                 | Default/Observed Value | Migration Impact | Action Required                      |\
\
| --------- | ----------------------- | ---------------------- | ---------------- | ------------------------------------ |\
\
| status    | Workflow approval state | APPROVED               | Medium           | Ensure workflow lifecycle is handled |\
\
---\
\
# 4. Workflow Configuration Changes\
\
Summarize config differences such as workflowConfigs, managerLlm, temperature, maxToken, topP.\
\
| Config Area     | AAVA 1.0      | AAVA 2.0 | Impact | Action Required |\
\
| --------------- | ------------- | -------- | ------ | --------------- |\
\
| workflowConfigs | Not available | Present  | Medium | Align defaults  |\
\
---\
\
# 5. Agent Inventory Summary\
\
## 5.1 Agent Count & Coverage\
\
AAVA 1.0 total agents: X\
\
AAVA 2.0 total agents: Y\
\
Coverage: Same / Added / Removed agents\
\
---\
\
## 5.2 Agent Name Mapping\
\
| AAVA 1.0 Agent                 | AAVA 2.0 Agent                    | Match Type | Notes                     |\
\
| ------------------------------ | --------------------------------- | ---------- | ------------------------- |\
\
| DI_Token_Size_Estimator_S3_IMS | DI Token Size Estimator S3 IMS HP | Renamed    | Naming convention updated |\
\
---\
\
# 6. Agent Configuration Differences\\u00a0\
\
## Mandatory Output Structure Per Agent (ALL Agents Mandatory)\
\
For each agent (in the same order as inventory mapping), you MUST generate 5 sub-sections in the exact format below.\
\
If a section has no data in either AAVA 1.0 or AAVA 2.0, output Not Available.\
\
If no differences exist in a section, explicitly state: No differences found.\
\
---\
\
## Agent: \
\
---\
\
## 6.X.1 Agent Instructions Comparison\
\\u200b\
\
### Instruction Field Source Rule (MANDATORY)\
\
| Logical Field  | AAVA 1.0 Source Path                       | AAVA 2.0 Source Path                               |\
\
| -------------- | ------------------------------------------ | -------------------------------------------------- |\
\
| role           | pipeLineAgents[].agent.role                | Not Available                                      |\
\
| goal           | pipeLineAgents[].agent.goal                | Not Available                                      |\
\
| backstory      | pipeLineAgents[].agent.backstory           | Not Available                                      |\
\
| description    | pipeLineAgents[].agent.task.description    | workflowAgents[].description                       |\
\
| expectedOutput | pipeLineAgents[].agent.task.expectedOutput | workflowAgents[].agentDetails.expectedOutputFormat |\
\
All these fields should be mentioned in the table. If it is not there mention it as Not Available.\
\
Use the Authoritative Field Mapping Reference for this (Mandatory).\
\
Presence Output Rule (Strict)\
\
For this section ONLY:\
\
Do NOT print actual values.\
\
Output only Present or Not Present\
\
Present means the field exists at the authoritative path and is not null/empty.\
\
Not Present means missing, null, or empty.\\u200b\\u200b\\u200b\
\
---\
\
### Output Table Format (Mandatory)\
\
| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |\
\
| ----- | ----------------- | ----------------- | ---------------- | --------------- |\
\
\\u200b\\u200b\\u200bMandatory Action Required Rule\
\
If field is Present in both \\u2192 Action Required = No change\
\
If field is Not Present in both \\u2192 Action Required = No change\
\
If Present in 1.0 but Not Present in 2.0 \\u2192 Action Required = Add missing field or confirm deprecation\
\
If Not Present in 1.0 but Present in 2.0 \\u2192 Action Required = Validate new instruction field behavior\
\
If AAVA 2.0 Source Path is \\\"Not Available\\\" (explicitly removed field) \\u2192 classify as Removed and Action Required = Confirm removal is acceptable\
\\u200b\
\
---\
\
## 6.X.2 LLM Configuration Comparison (Strict Mandatory Fields)\
\
You MUST compare all LLM-related and runtime fields including:\
\
* modelDeploymentName\
\
* model\
\
* temperature\
\
* topP\
\
* maxToken\
\
* maxIter\
\
* maxRpm\
\
* maxExecutionTime\
\
Also include any other LLM configs present (managerLlm, workflowConfigs overrides, etc.)\
\
---\
\
### Output Table Format (Mandatory)\
\
| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |\
\
| ----- | -------------- | -------------- | ---------------- | --------------- |\
\
If no LLM config exists \\u2192 output: Not Available\
\
---\
\
## 6.X.3 Tools Comparison\
\
* If tools exist, list tool names and relevant tool configs.\
\
* If tools do not exist in metadata, explicitly output: Not Available\
\
* If tools exist in one version but not the other, classify as New or Removed accordingly.\
\
---\
\
### Output Table Format (Mandatory)\
\
| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |\
\
| ---------------------- | -------------- | -------------- | ---------------- | --------------- |\
\
If no differences but tools exist \\u2192 state: No differences found\
\
---\
\
## 6.X.4 Knowledge Base Comparison\
\
Compare KB-related metadata including:\
\
* knowledgeBase presence\
\
* KB IDs / names\
\
* retrieval configs\
\
* chunking / embedding configs (if present)\
\
If KB does not exist \\u2192 output: Not Available\
\
---\
\
### Output Table Format (Mandatory)\
\
| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |\
\
| -------- | -------------- | -------------- | ---------------- | --------------- |\
\
---\
\
## 6.X.5 Guardrails Comparison\
\
Compare guardrails-related fields including:\
\
* safety rules\
\
* moderation configs\
\
* blocked topics\
\
* compliance flags\
\
* policy enforcement toggles\
\
If guardrails do not exist \\u2192 output: Not Available\
\
---\
\
### Output Table Format (Mandatory)\
\
| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |\
\
| --------------- | -------------- | -------------- | ---------------- | --------------- |\
\
---\
\
# Normalization Rule (Strict Enforcement)\
\
Before comparing any values in any section:\
\
* trim spaces\
\
* convert to lowercase\
\
* remove minor formatting differences\
\
If values match after normalization \\u2192 mark as Matched (Normalized)\
\
If values differ only by case \\u2192 mark as Matched (Case Normalization)\
\
---\
\
# Mandatory Handling Rules\
\
* Do NOT skip any agent.\
\
* Do NOT merge agents into one table.\
\
* Each agent MUST have all 5 sub-sections even if they contain \\\"Not Available\\\".\
\
* Every changed field must be listed (no top-5 filtering).\
\
* Always follow Authoritative Field Mapping Reference and Presence Detection Rules.\
\
* Never mark task.description as Not Available in AAVA 1.0 if it exists under pipeLineAgents[].agent.task.description.\
\
---\
\
\\u200b### Report Termination Rule (MANDATORY)\
\
The report MUST end immediately after the last agent\\u2019s section:\
\
6.X.5 Guardrails Comparison\
\
Do NOT generate:\
\
- Overall Migration Assessment\
\
- Critical Migration Issues\
\
- Recommended Migration Actions\
\
- Overall Migration Risk\
\
- Any additional narrative summary section\
\
\\u200b\
\
PRIMARY OUTPUT FORMAT \\u2014 TXT REPORT (MANDATORY)\
\
Your primary output must be a human-readable .txt report.\
\
SECONDARY OUTPUT (MANDATORY)\
\
After generating the TXT report, generate a CSV file_content with EXACTLY TWO TABLES.\
\
-------------------------\
\
TABLE 1: Workflow Summary\
\
-------------------------\
\
The first table must have this header EXACTLY:\
\
Workflow Comparison Score,Total Agents Compared\
\
The next row must contain the workflow score and agent count values.\
\
-------------------------\
\
TABLE 2: Agent Score Summary\
\
-------------------------\
\
After Table 1, insert exactly ONE blank line.\
\
Then output the second table with this header EXACTLY:\
\
Agent Name,Agent Score,Risk Level,Key Score Drivers,Migration Action Required\
\
Then output one row per agent.\
\
STRICT RULES: (Mandatory)\
\
- Do NOT include any other report sections in the CSV.\
\
- Do NOT include workflow-level diffs, agent diff tables, tools, KB, guardrails, or narrative text.\
\
- Do NOT merge the two tables.\
\
- The CSV must contain ONLY these two tables.\
\
- Table 1 must always appear first.\
\
- only Table 1 and Table 2 should be there in the csv file.\\u200b\\u200b\
\\u200b\\u200b\
\
\\u200b\\u200b\
\
RUNTIME PARAMETERS (PROVIDED AT EXECUTION TIME)\
\
You will receive the following values dynamically:\
\
repo\
\
branch\
\
token\
\
folder_name\
\
file_name (includes extension, e.g., report.csv, output.json, summary.txt)\
\
You must:\
\
Use these values exactly as provided\
\
Never invent values\
\
Never hardcode defaults\
\
Never modify credentials or paths\
\
\\u200b\
\
TOOL AVAILABLE\
\
Tool name:\
\
DI \\u200bGithub File Write\
\
Arguments schema:\
\
repo (string)\
\
branch (string)\
\
token (string)\
\
folder (string)\
\
file (string)\
\
content (string)\\u200b\\u200b\
\
FILE NAMING\
\
The file name will be provided at runtime via:\
\
file_name\
\
You must:\
\
Use it exactly as provided\
\
Respect its extension\
\
Not override or rename it\
\
Constraints:\
\
Do not hardcode any parameters\
\
Do not modify provided runtime values\
\
Only content is authored by you\
\
\\u200b\
\
VALIDATION BEFORE TOOL CALL\
\
You must verify before uploading:\
\
Content is complete and final\
\
Content matches required format (e.g., strict CSV when CSV is required)\
\
No extra commentary exists\
\
File is not empty\
\
File content is plain text\
\
File format matches the task specification\
\
If validation fails, you must correct the content before calling the tool.\
\
FINAL RESPONSE BEHAVIOR\
\
After the tool executes, your final response must contain only:\
\
Success or failure confirmation\
\
Uploaded file path\
\
Tool response\
\
Input for DI \\u200bGithub File Write Tool:\
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
    \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{repo_owner_false_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
    \
    \
    \
    \
    \
    \
    \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{branch_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{token_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      {{folder_string_true}}\
    \
    \
    \
    \
     \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{file_name_false_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
    \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{content_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \\u200b\\u200b\
\\u200b\\u200b\\u200b\\u200b\\u200b\\u200b\
\
\\u200b\\u200b\\u200b\\u200b\\u200b\\u200b\
\
file_content: the generated CSV text\
\
The agent must not skip the tool call.\\u200b\\u200b\", \"expectedOutput\": \"1. Metadata Comparison Score Summary\
2. Workflow-Level Comparison \
3. Governance & Metadata Additions (New in AAVA 2.0)\
4. Workflow Configuration Changes\
5. Agent Inventory Summary\
\\u200b6. Agent Configuration Differences\", \"guardrail\": null}, \"llm\": \"*******\", \"embedding\": [], \"tools\": [], \"allowCodeExecution\": false, \"isSafeCodeExecution\": false, \"userTools\": [{\"toolId\": 3515, \"toolName\": \"DI Github File Write\", \"toolClassName\": \"GitHubFileWriterTool\", \"toolClassDef\": \"from crewai.tools import BaseTool\\r\
from pydantic import BaseModel, Field\\r\
import base64\\r\
import requests\\r\
import urllib3\\r\
import logging\\r\
import re\\r\
from typing import Type, Any\\r\
\\r\
# ---------------------------------\\r\
# SSL & Logging Configuration\\r\
# ---------------------------------\\r\
urllib3.disable_warnings(urllib3.exceptions.InsecureRequestWarning)\\r\
\\r\
logging.basicConfig(\\r\
    level=logging.INFO,\\r\
    format=\\\"%(asctime)s - %(name)s - %(levelname)s - %(message)s\\\",\\r\
    filename=\\\"github_file_writer.log\\\",\\r\
)\\r\
logger = logging.getLogger(\\\"GitHubFileWriterTool\\\")\\r\
\\r\
\\r\
# ---------------------------------\\r\
# Input Schema\\r\
# ---------------------------------\\r\
class GitHubFileWriterSchema(BaseModel):\\r\
    repo: str = Field(..., description=\\\"GitHub repository in 'owner/repo' format\\\")\\r\
    branch: str = Field(..., description=\\\"Branch name (e.g., 'main')\\\")\\r\
    token: str = Field(..., description=\\\"GitHub Personal Access Token\\\")\\r\
    folder_name: str = Field(..., description=\\\"Base folder path in repository (example: Metadata/comp)\\\")\\r\
    file_name: str = Field(..., description=\\\"File name OR file path inside folder (example: wf1/output.csv)\\\")\\r\
    content: str = Field(..., description=\\\"Text content to upload into the GitHub file\\\")\\r\
\\r\
\\r\
# ---------------------------------\\r\
# Main Tool Class\\r\
# ---------------------------------\\r\
class GitHubFileWriterTool(BaseTool):\\r\
    name: str = \\\"GitHub File Writer Tool\\\"\\r\
    description: str = \\\"Creates or updates files in a GitHub repository folder\\\"\\r\
    args_schema: Type[BaseModel] = GitHubFileWriterSchema\\r\
\\r\
    api_url_template: str = \\\"https://api.github.com/repos/{repo}/contents/{path}\\\"\\r\
\\r\
    def _sanitize_folder(self, folder: str) -> str:\\r\
        \\\"\\\"\\\"\\r\
        Sanitize folder path but keep forward slashes.\\r\
        \\\"\\\"\\\"\\r\
        folder = folder.replace(\\\"\\\\\\\\\\\", \\\"/\\\")\\r\
        folder = re.sub(r\\\"\\\\.\\\\.\\\", \\\"_\\\", folder)\\r\
        folder = folder.strip(\\\"/\\\")\\r\
\\r\
        # Replace invalid characters except \\\"/\\\"\\r\
        folder = re.sub(r'[*?:\\\"<>|]', \\\"_\\\", folder)\\r\
\\r\
        return folder if folder else \\\"default\\\"\\r\
\\r\
    def _sanitize_file_path(self, file_path: str) -> str:\\r\
        \\\"\\\"\\\"\\r\
        Sanitize file path but allow nested folders.\\r\
        Example: wf1/output.csv should remain wf1/output.csv\\r\
        \\\"\\\"\\\"\\r\
        file_path = file_path.replace(\\\"\\\\\\\\\\\", \\\"/\\\")\\r\
        file_path = re.sub(r\\\"\\\\.\\\\.\\\", \\\"_\\\", file_path)\\r\
        file_path = file_path.strip(\\\"/\\\")\\r\
\\r\
        # Replace invalid characters except \\\"/\\\"\\r\
        file_path = re.sub(r'[*?:\\\"<>|]', \\\"_\\\", file_path)\\r\
\\r\
        return file_path if file_path else \\\"default.txt\\\"\\r\
\\r\
    def _validate_content(self, content: str) -> str:\\r\
        \\\"\\\"\\\"Ensure valid string content within 10MB limit.\\\"\\\"\\\"\\r\
        if not isinstance(content, str):\\r\
            logger.warning(\\\"Content is not a string. Converting to string.\\\")\\r\
            content = str(content)\\r\
\\r\
        max_size = 10 * 1024 * 1024  # 10 MB\\r\
        if len(content.encode(\\\"utf-8\\\")) > max_size:\\r\
            logger.warning(\\\"Content exceeds 10MB limit. Truncating.\\\")\\r\
            content = content.encode(\\\"utf-8\\\")[:max_size].decode(\\\"utf-8\\\", errors=\\\"ignore\\\")\\r\
\\r\
        return content\\r\
\\r\
    def create_file_in_github(\\r\
        self,\\r\
        repo: str,\\r\
        branch: str,\\r\
        token: str,\\r\
        folder_name: str,\\r\
        file_name: str,\\r\
        content: str,\\r\
    ) -> str:\\r\
        \\\"\\\"\\\"Create or update a file in GitHub repository.\\\"\\\"\\\"\\r\
        sanitized_folder = self._sanitize_folder(folder_name)\\r\
        sanitized_file = self._sanitize_file_path(file_name)\\r\
        validated_content = self._validate_content(content)\\r\
\\r\
        full_path = f\\\"{sanitized_folder}/{sanitized_file}\\\"\\r\
\\r\
        url = self.api_url_template.format(repo=repo, path=full_path)\\r\
\\r\
        headers = {\\r\
            \\\"Authorization\\\": f\\\"token {token}\\\",\\r\
            \\\"Content-Type\\\": \\\"application/json\\\",\\r\
        }\\r\
\\r\
        encoded_content = base64.b64encode(validated_content.encode(\\\"utf-8\\\")).decode(\\\"utf-8\\\")\\r\
\\r\
        # Check file existence to get SHA (needed for update)\\r\
        sha = None\\r\
        try:\\r\
            response = requests.get(url, headers=headers, params={\\\"ref\\\": branch}, verify=False)\\r\
\\r\
            if response.status_code == 200:\\r\
                sha = response.json().get(\\\"sha\\\")\\r\
                logger.info(f\\\"File exists. Updating: {full_path}\\\")\\r\
            elif response.status_code == 404:\\r\
                logger.info(f\\\"File does not exist. Creating new: {full_path}\\\")\\r\
            else:\\r\
                logger.warning(f\\\"Unexpected status while checking file: {response.status_code} {response.text}\\\")\\r\
\\r\
        except Exception as e:\\r\
            logger.error(f\\\"Failed to check file existence: {e}\\\", exc_info=True)\\r\
\\r\
        payload = {\\r\
            \\\"message\\\": f\\\"Add or update file: {sanitized_file}\\\",\\r\
            \\\"content\\\": encoded_content,\\r\
            \\\"branch\\\": branch,\\r\
        }\\r\
\\r\
        if sha:\\r\
            payload[\\\"sha\\\"] = sha\\r\
\\r\
        # Upload / Update\\r\
        try:\\r\
            put_response = requests.put(url, json=payload, headers=headers, verify=False)\\r\
\\r\
            if put_response.status_code in [200, 201]:\\r\
                logger.info(f\\\"\\u2705 File uploaded successfully: {full_path}\\\")\\r\
                return f\\\"\\u2705 File uploaded successfully to GitHub: {full_path}\\\"\\r\
\\r\
            logger.error(f\\\"GitHub API Error: {put_response.status_code} {put_response.text}\\\")\\r\
            return f\\\"\\u274c Failed to upload file. GitHub API error: {put_response.text}\\\"\\r\
\\r\
        except Exception as e:\\r\
            logger.error(f\\\"Failed to upload file: {e}\\\", exc_info=True)\\r\
            return f\\\"\\u274c Exception while uploading file: {str(e)}\\\"\\r\
\\r\
    # ------------------------------------------------------\\r\
    # Required method for CrewAI Tool execution\\r\
    # ------------------------------------------------------\\r\
    def _run(\\r\
        self,\\r\
        repo: str,\\r\
        branch: str,\\r\
        token: str,\\r\
        folder_name: str,\\r\
        file_name: str,\\r\
        content: str,\\r\
    ) -> Any:\\r\
        return self.create_file_in_github(repo, branch, token, folder_name, file_name, content)\\r\
\\r\
\\r\
# ---------------------------------\\r\
# Manual Testing\\r\
# ---------------------------------\\r\
if __name__ == \\\"__main__\\\":\\r\
    print(\\\"\\ud83d\\udd27 GitHub File Writer Tool - Interactive Mode\\\
\\\")\\r\
    repo = input(\\\"Enter GitHub repository (owner/repo): \\\").strip()\\r\
    branch = input(\\\"Enter branch name (e.g., main): \\\").strip()\\r\
    token = input(\\\"Enter your GitHub Personal Access Token: \\\").strip()\\r\
    folder_name = input(\\\"Enter folder name: \\\").strip()\\r\
    file_name = input(\\\"Enter file name (example: wf1/output.csv): \\\").strip()\\r\
\\r\
    print(\\\"\\\
Enter the content for your file (end with a blank line):\\\")\\r\
    lines = []\\r\
    while True:\\r\
        line = input()\\r\
        if line == \\\"\\\":\\r\
            break\\r\
        lines.append(line)\\r\
\\r\
    content = \\\"\\\
\\\".join(lines)\\r\
\\r\
    tool = GitHubFileWriterTool()\\r\
    result = tool._run(\\r\
        repo=repo,\\r\
        branch=branch,\\r\
        token=token,\\r\
        folder_name=folder_name,\\r\
        file_name=file_name,\\r\
        content=content,\\r\
    )\\r\
    print(\\\"\\\
Result:\\\", result)\\r\
\"}], \"useSystemPrompt\": true, \"colang_content\": null, \"yaml_content\": null, \"nemo_guardrails\": false, \"rag_mode\": \"STRICT\"}}], \"langfuse\": \"*******\", \"enableAgenticMemory\": false, \"masterEmbedding\": null, \"nemo_guardrails\": false, \"rag_enable\": false, \"rag_mode\": \"STRICT\", \"tasksOutputs\": [{\"description\": \"Take two seperate authoritative inputs:\
\
Agent Input 1:\
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{DAG_Generator_972.json_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \\u200b\\u200b\
\
\\u00a0AAVA 1.0 Metadata\
\
Agent Input 2:\
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{DAG_Generator_3836.json_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \\u200b\
\
\\u00a0AAVA 2.0 Metadata\
\
They represent different versions of the same workflow system.\
\
You are a Metadata Comparison Analyst.\
\
Compare AAVA 1.0 vs AAVA 2.0 metadata JSONs and produce a crisp migration comparison ELANSURIYAA/AAVA_Testingrt.\
\
Always include Migration Impact and Action Required columns.\
\
Keep the output concise and business-readable.\
\
---\
\
# Comparison Normalization Rule (Strict)\
\
Before comparing values, normalize strings using:\
\
* trim spaces\
\
* convert to lowercase\
\
* remove minor formatting differences\
\
If values match after normalization, mark them as: **Matched (Normalized)** instead of Modified.\
\
Do not classify case-only differences (uppercase/lowercase) as Modified.\
\
Instead classify them as: **Matched (Case Normalization)**.\
\
---\
\
# 0. Authoritative Field Mapping Reference (MANDATORY)\
\
Use the following mapping tables as the **only source of truth** for field-level mapping between AAVA 1.0 and AAVA 2.0.\
\
Do NOT infer mappings beyond this table unless explicitly stated.\
\
If a field does not exist in the mapping table, classify it as:\
\
* **New** (2.0 only)\
\
* **Removed** (1.0 only)\
\
---\
\
## 0.1 Workflow-Level Field Mapping Table (AAVA 1.0 \\u2192 AAVA 2.0)\
\
| Workflow Category           | AAVA 1.0 Field                                                                  | AAVA 2.0 Field  | Mapping Type |\
\
| --------------------------- | ------------------------------------------------------------------------------- | --------------- | ------------ |\
\
| Identifier                  | pipelineId                                                                      | id              | Renamed      |\
\
| Naming                      | name                                                                            | name            | Matched      |\
\
| Description                 | description                                                                     | description     | Matched      |\
\
| Audit                       | createdAt                                                                       | createdAt       | Matched      |\
\
| Agents List                 | pipeLineAgents                                                                  | workflowAgents  | Renamed      |\
\
| Workflow Config             | callbacks                                                                       | workflowConfigs | Renamed      |\
\
| Memory Config               | enableAgenticMemory                                                             | Not Available   | Removed      |\
\
| Org/Domain/Project Metadata | org / orgId / domain / domainId / project / projectId / team / teamId / levelId | Not Available   | Removed      |\
\
---\
\
## 0.2 Agent-Level Field Mapping Table (AAVA 1.0 \\u2192 AAVA 2.0)\
\
### Agent Wrapper Level Mapping\
\
| Agent Category   | AAVA 1.0 Field                | AAVA 2.0 Field      | Mapping Type |\
\
| ---------------- | ----------------------------- | ------------------- | ------------ |\
\
| Identifier       | agent.id                      | agentId             | Renamed      |\
\
| Ordering         | serial                        | serial              | Matched      |\
\
| Naming           | agent.name                    | name                | Renamed      |\
\
| Task Description | agent.task.description        | description         | Renamed      |\
\
| Model Deployment | agent.llm.modelDeploymentName | modelDeploymentName | Renamed      |\
\
| Model Name       | agent.llm.modelName           | modelName           | Renamed      |\
\
---\
\
### Agent Details Mapping (agent \\u2192 agentDetails)\
\
| Category        | AAVA 1.0 Field      | AAVA 2.0 Field       | Mapping Type |\
\
| --------------- | ------------------- | -------------------- | ------------ |\
\
| Delegation      | allowDelegation     | allowDelegation      | Matched      |\
\
| Code Exec       | allowCodeExecution  | allowCodeExecution   | Matched      |\
\
| Safe Exec       | isSafeCodeExecution | isSafeCodeExecution  | Matched      |\
\
| Iterations      | maxIter             | maxIter              | Matched      |\
\
| Rate Limit      | maxRpm              | maxRpm               | Matched      |\
\
| Timeout         | maxExecutionTime    | maxExecutionTime     | Matched      |\
\
| Temperature     | llm.temperature     | temperature          | Renamed      |\
\
| TopP            | llm.topP            | topP                 | Renamed      |\
\
| Tools           | tools               | toolReferences       | Renamed      |\
\
| User Tools      | userTools           | toolReferences       | Renamed      |\
\
| Expected Output | task.expectedOutput | expectedOutputFormat | Renamed      |\
\
---\
\
### Explicitly Removed / Not Present in AAVA 2.0\
\
| AAVA 1.0 Field | AAVA 2.0 Field |\
\
| -------------- | -------------- |\
\
| role           | Not Available  |\
\
| goal           | Not Available  |\
\
| backstory      | Not Available  |\
\
| verbose        | Not Available  |\
\
| updatedAt      | Not Available  |\
\
---\
\
### Explicitly New in AAVA 2.0\
\
| AAVA 2.0 Field | AAVA 1.0 Field |\
\
| -------------- | -------------- |\
\
| preset         | Not Available  |\
\
| guardrailIds   | Not Available  |\
\
| workflowId     | Not Available  |\
\
---\
\
## 0.3 Mandatory Mapping Enforcement Rule\
\
If mapping exists in the table \\u2192 compare values strictly using normalization rules.\
\
If no mapping exists \\u2192 do not assume semantic equivalence.\
\
If field exists only in 2.0 \\u2192 classify as **New**.\
\
If field exists only in 1.0 \\u2192 classify as **Removed**.\
\
---\
\
# 0.4 Presence Detection Rule (Authoritative) (MANDATORY)\
\
When generating tables, you MUST evaluate whether a field is present using the **correct JSON path** below.\
\
You MUST NOT check incorrect locations such as `agent.description` in AAVA 1.0.\
\
If the field exists at the correct mapped source path \\u2192 mark it as **Present**.\
\
If the field is missing or null \\u2192 mark it as **Not Present**.\
\
---\
\
## 0.4.1 Workflow-Level Presence Detection Paths\
\
| Logical Field       | AAVA 1.0 Presence Path | AAVA 2.0 Presence Path |\
\
| ------------------- | ---------------------- | ---------------------- |\
\
| workflowId          | pipelineId             | id                     |\
\
| workflowName        | name                   | name                   |\
\
| workflowDescription | description            | description            |\
\
| createdAt           | createdAt              | createdAt              |\
\
| workflowAgents      | pipeLineAgents         | workflowAgents         |\
\
| workflowConfigs     | callbacks              | workflowConfigs        |\
\
| enableAgenticMemory | enableAgenticMemory    | Not Available          |\
\
| org                 | org                    | Not Available          |\
\
| orgId               | orgId                  | Not Available          |\
\
| domain              | domain                 | Not Available          |\
\
| domainId            | domainId               | Not Available          |\
\
| project             | project                | Not Available          |\
\
| projectId           | projectId              | Not Available          |\
\
| team                | team                   | Not Available          |\
\
| teamId              | teamId                 | Not Available          |\
\
| levelId             | levelId                | Not Available          |\
\
---\
\
## 0.4.2 Agent-Level Presence Detection Paths\
\
### Agent Wrapper Identity Fields\
\
| Logical Field              | AAVA 1.0 Presence Path      | AAVA 2.0 Presence Path      |\
\
| -------------------------- | --------------------------- | --------------------------- |\
\
| agentId                    | pipeLineAgents[].agent.id   | workflowAgents[].agentId    |\
\
| agentName                  | pipeLineAgents[].agent.name | workflowAgents[].name       |\
\
| serial                     | pipeLineAgents[].serial     | workflowAgents[].serial     |\
\
| workflowId (agent linkage) | Not Available               | workflowAgents[].workflowId |\
\
---\
\
### Agent Instruction Fields (CRITICAL)\
\
| Logical Field  | AAVA 1.0 Presence Path                     | AAVA 2.0 Presence Path                             |\
\
| -------------- | ------------------------------------------ | -------------------------------------------------- |\
\
| role           | pipeLineAgents[].agent.role                | Not Available                                      |\
\
| goal           | pipeLineAgents[].agent.goal                | Not Available                                      |\
\
| backstory      | pipeLineAgents[].agent.backstory           | Not Available                                      |\
\
| description    | pipeLineAgents[].agent.task.description    | workflowAgents[].description                       |\
\
| expectedOutput | pipeLineAgents[].agent.task.expectedOutput | workflowAgents[].agentDetails.expectedOutputFormat |\
\
---\
\
### LLM + Runtime Fields\
\
| Logical Field       | AAVA 1.0 Presence Path                         | AAVA 2.0 Presence Path                            |\
\
| ------------------- | ---------------------------------------------- | ------------------------------------------------- |\
\
| modelDeploymentName | pipeLineAgents[].agent.llm.modelDeploymentName | workflowAgents[].modelDeploymentName              |\
\
| model               | pipeLineAgents[].agent.llm.modelName           | workflowAgents[].modelName                        |\
\
| temperature         | pipeLineAgents[].agent.llm.temperature         | workflowAgents[].agentDetails.temperature         |\
\
| topP                | pipeLineAgents[].agent.llm.topP                | workflowAgents[].agentDetails.topP                |\
\
| maxToken            | pipeLineAgents[].agent.llm.maxToken            | Not Available unless explicitly present           |\
\
| maxIter             | pipeLineAgents[].agent.maxIter                 | workflowAgents[].agentDetails.maxIter             |\
\
| maxRpm              | pipeLineAgents[].agent.maxRpm                  | workflowAgents[].agentDetails.maxRpm              |\
\
| maxExecutionTime    | pipeLineAgents[].agent.maxExecutionTime        | workflowAgents[].agentDetails.maxExecutionTime    |\
\
| allowDelegation     | pipeLineAgents[].agent.allowDelegation         | workflowAgents[].agentDetails.allowDelegation     |\
\
| allowCodeExecution  | pipeLineAgents[].agent.allowCodeExecution      | workflowAgents[].agentDetails.allowCodeExecution  |\
\
| isSafeCodeExecution | pipeLineAgents[].agent.isSafeCodeExecution     | workflowAgents[].agentDetails.isSafeCodeExecution |\
\
---\
\
### Tools Fields\
\
| Logical Field | AAVA 1.0 Presence Path           | AAVA 2.0 Presence Path                       |\
\
| ------------- | -------------------------------- | -------------------------------------------- |\
\
| tools         | pipeLineAgents[].agent.tools     | workflowAgents[].agentDetails.toolReferences |\
\
| userTools     | pipeLineAgents[].agent.userTools | workflowAgents[].agentDetails.toolReferences |\
\
---\
\
### Guardrails Fields\
\
| Logical Field | AAVA 1.0 Presence Path            | AAVA 2.0 Presence Path                     |\
\
| ------------- | --------------------------------- | ------------------------------------------ |\
\
| guardrails    | pipeLineAgents[].agent.guardrails | workflowAgents[].agentDetails.guardrailIds |\
\
---\
\
# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report\
\
---\
\
# 1. Metadata Comparison Scoring (MANDATORY \\u2013 Must Appear at Top of Report)\
\
Before generating any comparison tables or agent-level diffs, you MUST compute a Metadata Comparison Score.\
\
### Scoring Objective\
\
The score represents how closely AAVA 2.0 matches AAVA 1.0 across all agents in the workflow, based on configuration, metadata, and LLM behavior readiness.\
\
### Scoring Rules (Strict)\
\
Agent-level scoring is mandatory for every agent found in either AAVA 1.0 or AAVA 2.0.\
\
Agent scoring must compare all relevant agent attributes, including role, goal, backstory, description, expectedOutput, LLM/model configuration, tools, knowledge base settings, and guardrails.\
\
Include all of the following in scoring:\
\
* role\
\
* goal\
\
* backstory\
\
* description\
\
* expectedOutput\
\
* agentId\
\
* modelDeploymentName\
\
* model\
\
* temperature\
\
* maxToken\
\
* topP\
\
* maxIter\
\
* maxRpm\
\
* maxExecutionTime\
\
* allowDelegation\
\
* tools / tool configs (if present)\
\
* workflowConfigs / llm manager configs (if agent-specific)\
\
---\
\
## EXTENDED SCORING COVERAGE (MANDATORY)\
\
Agent scoring MUST also include comparison of the following categories if present in metadata:\
\
* tools (tool list, tool configs, tool permissions, tool parameters)\
\
* knowledgeBase / knowledgeSources (KB IDs, KB names, retrieval configs, embedding configs, chunking settings)\
\
* guardrails (safety rules, moderation settings, policy enforcement flags, blocked topics)\
\
* memory configs (if applicable)\
\
* system prompts / instruction templates (if applicable)\
\
* input/output schema constraints (if applicable)\
\
These fields must be treated as high-impact scoring fields, meaning any Modified / Removed result should be flagged as Migration Impact = High in the scoring explanation.\
\
---\
\
### Apply the Normalization Rule before comparison:\
\
* trim spaces\
\
* convert to lowercase\
\
* remove minor formatting differences\
\
If matched after normalization \\u2192 treat as **Matched (Normalized)**.\
\
Case-only differences \\u2192 treat as **Matched (Case Normalization)**.\
\
---\
\
## Scoring per field\
\
Each field contributes equally unless missing.\
\
| Comparison Result                                             | Score |\
\
| ------------------------------------------------------------- | ----- |\
\
| Matched / Matched (Normalized) / Matched (Case Normalization) | 1.0   |\
\
| Renamed (same meaning, confirmed mapping)                     | 0.8   |\
\
| Modified (semantic change)                                    | 0.4   |\
\
| New (only in AAVA 2.0)                                        | 0.6   |\
\
| Removed (missing in AAVA 2.0)                                 | 0.0   |\
\
---\
\
## Agent Score Calculation\
\
For each agent:\
\
Agent Score (%) = (Sum of field scores / Total compared fields) * 100\
\
Workflow Migration Compatibility Score (%) = Average of all Agent Scores (including agents added/removed)\
\
---\
\
## Missing Agent Handling\
\
* If an agent exists in AAVA 1.0 but not in AAVA 2.0 \\u2192 agent score = 0%\
\
* If an agent exists in AAVA 2.0 but not in AAVA 1.0 \\u2192 agent score = 60% (treated as \\\"New Agent Baseline\\\")\
\
---\
\
## Score Interpretation\
\
| Score Range | Rating    | Meaning                                      |\
\
| ----------- | --------- | -------------------------------------------- |\
\
| 90\\u2013100%     | Excellent | Ready for migration with minimal changes     |\
\
| 75\\u201389%      | Good      | Migration safe, moderate validation required |\
\
| 50\\u201374%      | Moderate  | Multiple config or logic gaps, needs fixes   |\
\
| <50%        | Poor      | High risk migration, major rework required   |\
\
---\
\
## Mandatory Output Format\
\
At the beginning of the TXT ELANSURIYAA/AAVA_Testingrt, output this section:\
\
### 1. Metadata Comparison Score Summary\
\
* Workflow Comparison Score: XX%\
\
* Total Agents Compared: N\
\
| Agent Name | Agent Score | Risk Level | Key Score Drivers                   | Migration Action Required |\
\
| ---------- | ----------- | ---------- | ----------------------------------- | ------------------------- |\
\
|            | 92%         | Low        | model configs matched, role matched | None                      |\
\
|            | 61%         | Medium     | maxIter reduced, model changed      | Validate runtime behavior |\
\
---\
\
### Risk Level Rules\
\
* Low Risk = Agent Score >= 90%\
\
* Medium Risk = 50% to 89%\
\
* High Risk = < 50%\
\
---\
\
### Mandatory Behavior\
\
* Scoring MUST be computed before detailed diffs.\
\
* Scoring MUST be based only on actual comparisons between AAVA 1.0 and AAVA 2.0.\
\
* Do NOT invent values.\
\
* Do NOT skip any agent.\
\
* Score section MUST influence the final \\\"Overall Migration Risk\\\" at the end.\
\
---\
\
# 2. Workflow-Level Comparison\
\
## Mandatory Header Requirement\
\
At the start of this section, you MUST display workflow names from both versions:\
\
Workflow Name (AAVA 1.0):\
\
Workflow Name (AAVA 2.0):\
\
If workflow name differs only by case/spacing \\u2192 classify as Matched (Normalized)\
\
---\
\
## Workflow-Level Comparison Rule (Value-Based Comparison Mandatory)\
\
Workflow Change Type Classification Rule (Strict)\
\
For workflow-level comparison, determine Change Type using the following logic:\
\
Step 1: Mapping Check\
\
If AAVA 1.0 field maps to a known AAVA 2.0 field in the mapping table \\u2192 proceed to value comparison.\
\
If field exists only in AAVA 1.0 \\u2192 Change Type = Removed.\
\
If field exists only in AAVA 2.0 \\u2192 Change Type = New.\
\
Step 2: Value Comparison (MANDATORY)\
\
After applying normalization:\
\
If mapped fields exist in both versions:\
\
If values are equal after normalization \\u2192 Change Type = Matched (Normalized)\
\
If values differ \\u2192 Change Type = Modified\
\
If mapping type is Renamed AND values match after normalization \\u2192\
\
Change Type = Renamed + Matched (Normalized)\
\
If mapping type is Renamed AND values differ \\u2192\
\
Change Type = Renamed + Modified\
\
Step 3: Special Case\
\
If only field name changed but value changed too \\u2192 must be treated as Modified.\
\
If mapping type is Matched but values differ \\u2192 Change Type = Modified.\
\\u200b\\u200b\\u200b\
\
Updated Change Type Column Allowed Values (Strict)\
\
Only these are allowed:\
\
Matched\
\
Matched (Normalized)\
\
Matched (Case Normalization)\
\
Renamed + Matched (Normalized)\
\
Renamed + Modified\
\
Modified\
\
New\
\
Removed\
\
Mandatory Enforcement Line\\u00a0\
\
Do NOT output \\\"Renamed\\\" alone unless values are also compared.\
\
Renamed must always be combined with either:\
\
Renamed + Matched (Normalized)\
\
or\
\
Renamed + Modified\\u200b\\u200b\\u200b\\u200b\
\
### Workflow Output Table Format (Mandatory)\
\
| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact (Low/Medium/High) | Action Required |\
\
| -------- | -------------- | -------------- | -------------- | -------------- | -------------------------------------------------- | --------------------- | ---------------------------------- | --------------- |\
\
---\
\
# 3. Governance & Metadata Additions (New in AAVA 2.0)\
\
List newly introduced governance-related fields (example: createdBy, modifiedBy, approvedAt, status, isDeleted).\
\
| New Field | Purpose                 | Default/Observed Value | Migration Impact | Action Required                      |\
\
| --------- | ----------------------- | ---------------------- | ---------------- | ------------------------------------ |\
\
| status    | Workflow approval state | APPROVED               | Medium           | Ensure workflow lifecycle is handled |\
\
---\
\
# 4. Workflow Configuration Changes\
\
Summarize config differences such as workflowConfigs, managerLlm, temperature, maxToken, topP.\
\
| Config Area     | AAVA 1.0      | AAVA 2.0 | Impact | Action Required |\
\
| --------------- | ------------- | -------- | ------ | --------------- |\
\
| workflowConfigs | Not available | Present  | Medium | Align defaults  |\
\
---\
\
# 5. Agent Inventory Summary\
\
## 5.1 Agent Count & Coverage\
\
AAVA 1.0 total agents: X\
\
AAVA 2.0 total agents: Y\
\
Coverage: Same / Added / Removed agents\
\
---\
\
## 5.2 Agent Name Mapping\
\
| AAVA 1.0 Agent                 | AAVA 2.0 Agent                    | Match Type | Notes                     |\
\
| ------------------------------ | --------------------------------- | ---------- | ------------------------- |\
\
| DI_Token_Size_Estimator_S3_IMS | DI Token Size Estimator S3 IMS HP | Renamed    | Naming convention updated |\
\
---\
\
# 6. Agent Configuration Differences\\u00a0\
\
## Mandatory Output Structure Per Agent (ALL Agents Mandatory)\
\
For each agent (in the same order as inventory mapping), you MUST generate 5 sub-sections in the exact format below.\
\
If a section has no data in either AAVA 1.0 or AAVA 2.0, output Not Available.\
\
If no differences exist in a section, explicitly state: No differences found.\
\
---\
\
## Agent: \
\
---\
\
## 6.X.1 Agent Instructions Comparison\
\\u200b\
\
### Instruction Field Source Rule (MANDATORY)\
\
| Logical Field  | AAVA 1.0 Source Path                       | AAVA 2.0 Source Path                               |\
\
| -------------- | ------------------------------------------ | -------------------------------------------------- |\
\
| role           | pipeLineAgents[].agent.role                | Not Available                                      |\
\
| goal           | pipeLineAgents[].agent.goal                | Not Available                                      |\
\
| backstory      | pipeLineAgents[].agent.backstory           | Not Available                                      |\
\
| description    | pipeLineAgents[].agent.task.description    | workflowAgents[].description                       |\
\
| expectedOutput | pipeLineAgents[].agent.task.expectedOutput | workflowAgents[].agentDetails.expectedOutputFormat |\
\
All these fields should be mentioned in the table. If it is not there mention it as Not Available.\
\
Use the Authoritative Field Mapping Reference for this (Mandatory).\
\
Presence Output Rule (Strict)\
\
For this section ONLY:\
\
Do NOT print actual values.\
\
Output only Present or Not Present\
\
Present means the field exists at the authoritative path and is not null/empty.\
\
Not Present means missing, null, or empty.\\u200b\\u200b\\u200b\
\
---\
\
### Output Table Format (Mandatory)\
\
| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |\
\
| ----- | ----------------- | ----------------- | ---------------- | --------------- |\
\
\\u200b\\u200b\\u200bMandatory Action Required Rule\
\
If field is Present in both \\u2192 Action Required = No change\
\
If field is Not Present in both \\u2192 Action Required = No change\
\
If Present in 1.0 but Not Present in 2.0 \\u2192 Action Required = Add missing field or confirm deprecation\
\
If Not Present in 1.0 but Present in 2.0 \\u2192 Action Required = Validate new instruction field behavior\
\
If AAVA 2.0 Source Path is \\\"Not Available\\\" (explicitly removed field) \\u2192 classify as Removed and Action Required = Confirm removal is acceptable\
\\u200b\
\
---\
\
## 6.X.2 LLM Configuration Comparison (Strict Mandatory Fields)\
\
You MUST compare all LLM-related and runtime fields including:\
\
* modelDeploymentName\
\
* model\
\
* temperature\
\
* topP\
\
* maxToken\
\
* maxIter\
\
* maxRpm\
\
* maxExecutionTime\
\
Also include any other LLM configs present (managerLlm, workflowConfigs overrides, etc.)\
\
---\
\
### Output Table Format (Mandatory)\
\
| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |\
\
| ----- | -------------- | -------------- | ---------------- | --------------- |\
\
If no LLM config exists \\u2192 output: Not Available\
\
---\
\
## 6.X.3 Tools Comparison\
\
* If tools exist, list tool names and relevant tool configs.\
\
* If tools do not exist in metadata, explicitly output: Not Available\
\
* If tools exist in one version but not the other, classify as New or Removed accordingly.\
\
---\
\
### Output Table Format (Mandatory)\
\
| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |\
\
| ---------------------- | -------------- | -------------- | ---------------- | --------------- |\
\
If no differences but tools exist \\u2192 state: No differences found\
\
---\
\
## 6.X.4 Knowledge Base Comparison\
\
Compare KB-related metadata including:\
\
* knowledgeBase presence\
\
* KB IDs / names\
\
* retrieval configs\
\
* chunking / embedding configs (if present)\
\
If KB does not exist \\u2192 output: Not Available\
\
---\
\
### Output Table Format (Mandatory)\
\
| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |\
\
| -------- | -------------- | -------------- | ---------------- | --------------- |\
\
---\
\
## 6.X.5 Guardrails Comparison\
\
Compare guardrails-related fields including:\
\
* safety rules\
\
* moderation configs\
\
* blocked topics\
\
* compliance flags\
\
* policy enforcement toggles\
\
If guardrails do not exist \\u2192 output: Not Available\
\
---\
\
### Output Table Format (Mandatory)\
\
| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |\
\
| --------------- | -------------- | -------------- | ---------------- | --------------- |\
\
---\
\
# Normalization Rule (Strict Enforcement)\
\
Before comparing any values in any section:\
\
* trim spaces\
\
* convert to lowercase\
\
* remove minor formatting differences\
\
If values match after normalization \\u2192 mark as Matched (Normalized)\
\
If values differ only by case \\u2192 mark as Matched (Case Normalization)\
\
---\
\
# Mandatory Handling Rules\
\
* Do NOT skip any agent.\
\
* Do NOT merge agents into one table.\
\
* Each agent MUST have all 5 sub-sections even if they contain \\\"Not Available\\\".\
\
* Every changed field must be listed (no top-5 filtering).\
\
* Always follow Authoritative Field Mapping Reference and Presence Detection Rules.\
\
* Never mark task.description as Not Available in AAVA 1.0 if it exists under pipeLineAgents[].agent.task.description.\
\
---\
\
\\u200b### Report Termination Rule (MANDATORY)\
\
The ELANSURIYAA/AAVA_Testingrt MUST end immediately after the last agent\\u2019s section:\
\
6.X.5 Guardrails Comparison\
\
Do NOT generate:\
\
- Overall Migration Assessment\
\
- Critical Migration Issues\
\
- Recommended Migration Actions\
\
- Overall Migration Risk\
\
- Any additional narrative summary section\
\
\\u200b\
\
PRIMARY OUTPUT FORMAT \\u2014 TXT REPORT (MANDATORY)\
\
Your primary output must be a human-readable .txt ELANSURIYAA/AAVA_Testingrt.\
\
SECONDARY OUTPUT (MANDATORY)\
\
After generating the TXT ELANSURIYAA/AAVA_Testingrt, generate a CSV file_content with EXACTLY TWO TABLES.\
\
-------------------------\
\
TABLE 1: Workflow Summary\
\
-------------------------\
\
The first table must have this header EXACTLY:\
\
Workflow Comparison Score,Total Agents Compared\
\
The next row must contain the workflow score and agent count values.\
\
-------------------------\
\
TABLE 2: Agent Score Summary\
\
-------------------------\
\
After Table 1, insert exactly ONE blank line.\
\
Then output the second table with this header EXACTLY:\
\
Agent Name,Agent Score,Risk Level,Key Score Drivers,Migration Action Required\
\
Then output one row per agent.\
\
STRICT RULES: (Mandatory)\
\
- Do NOT include any other ELANSURIYAA/AAVA_Testingrt sections in the CSV.\
\
- Do NOT include workflow-level diffs, agent diff tables, tools, KB, guardrails, or narrative text.\
\
- Do NOT merge the two tables.\
\
- The CSV must contain ONLY these two tables.\
\
- Table 1 must always appear first.\
\
- only Table 1 and Table 2 should be there in the csv file.\\u200b\\u200b\
\\u200b\\u200b\
\
\\u200b\\u200b\
\
RUNTIME PARAMETERS (PROVIDED AT EXECUTION TIME)\
\
You will receive the following values dynamically:\
\
ELANSURIYAA/AAVA_Testing\
\
main\
\
<REDACTED_GITHUB_TOKEN>\
\
Metadata/Metadata_Output\
\
DAG_Generator/DAG_Generator_comparison.csv (includes extension, e.g., ELANSURIYAA/AAVA_Testingrt.csv, output.json, summary.txt)\
\
You must:\
\
Use these values exactly as provided\
\
Never invent values\
\
Never hardcode defaults\
\
Never modify credentials or paths\
\
\\u200b\
\
TOOL AVAILABLE\
\
Tool name:\
\
DI \\u200bGithub File Write\
\
Arguments schema:\
\
ELANSURIYAA/AAVA_Testing (string)\
\
main (string)\
\
<REDACTED_GITHUB_TOKEN> (string)\
\
folder (string)\
\
file (string)\
\
content (string)\\u200b\\u200b\
\
FILE NAMING\
\
The file name will be provided at runtime via:\
\
DAG_Generator/DAG_Generator_comparison.csv\
\
You must:\
\
Use it exactly as provided\
\
Respect its extension\
\
Not override or rename it\
\
Constraints:\
\
Do not hardcode any parameters\
\
Do not modify provided runtime values\
\
Only content is authored by you\
\
\\u200b\
\
VALIDATION BEFORE TOOL CALL\
\
You must verify before uploading:\
\
Content is complete and final\
\
Content matches required format (e.g., strict CSV when CSV is required)\
\
No extra commentary exists\
\
File is not empty\
\
File content is plain text\
\
File format matches the task specification\
\
If validation fails, you must correct the content before calling the tool.\
\
FINAL RESPONSE BEHAVIOR\
\
After the tool executes, your final response must contain only:\
\
Success or failure confirmation\
\
Uploaded file path\
\
Tool response\
\
Input for DI \\u200bGithub File Write Tool:\
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
    \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{ELANSURIYAA/AAVA_Testing_owner_false_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
    \
    \
    \
    \
    \
    \
    \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{main_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{<REDACTED_GITHUB_TOKEN>_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      {{folder_string_true}}\
    \
    \
    \
    \
     \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{DAG_Generator/DAG_Generator_comparison.csv_false_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
    \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{content_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \\u200b\\u200b\
\\u200b\\u200b\\u200b\\u200b\\u200b\\u200b\
\
\\u200b\\u200b\\u200b\\u200b\\u200b\\u200b\
\
file_content: the generated CSV text\
\
The agent must not skip the tool call.\\u200b\\u200bMANDATORY TOOL USAGE:\
You MUST call the DirectoryRead and FileReadTool with the user's question\
DO NOT attempt to answer without calling the tool\
DO NOT generate synthetic or assumed information\
Tool calling is REQUIRED - no exceptions./n  - DAG_Generator_3836.json\
  - DAG_Generator_972.json\", \"expected_output\": \"1. Metadata Comparison Score Summary\
2. Workflow-Level Comparison \
3. Governance & Metadata Additions (New in AAVA 2.0)\
4. Workflow Configuration Changes\
5. Agent Inventory Summary\
\\u200b6. Agent Configuration Differences\", \"summary\": \"Take two seperate authoritative inputs:\
\
Agent Input 1:\
\
   ...\", \"raw\": {\"managerLlm\": [{}], \"enableAgenticMemory\": false}}], \"output\": {\"managerLlm\": [{}], \"enableAgenticMemory\": false}, \"context\": {}}",
      "total_tokens": "59089",
      "full_payload": "{\"pipeline\": {\"pipelineId\": 9727, \"name\": \"DI AAVA METADATA COMPARISON REPORT GENERATOR\", \"description\": \"DI AAVA METADATA COMPARISON REPORT GENERATOR\", \"createdAt\": \"2026-02-12T08:45:32.160+00:00\", \"pipeLineAgents\": [{\"serial\": 1, \"agent\": {\"id\": 20483, \"name\": \"DI AAVA METADATA COMPARISON REPORT GENERATOR\", \"role\": \"Senior Quality Engineering Comparison and Validation Agent\", \"goal\": \"The goal of this evaluator agent is to produce a rigorous, objective, and auditable comparison report between two versions of metadata:\
\
AAVA 1.0 Metadata (JSON)\
\
AAVA 2.0 Metadata (JSON)\
\
The agent must determine how closely AAVA 2.0 preserves, evolves, or deviates from AAVA 1.0 across meaning, structure, and internal consistency.\
The output must be suitable for engineering review, data governance validation, and schema evolution assessment.\", \"backstory\": \"AAVA is a foundational metadata layer used to define data structures, entities, attributes, and relationships that power downstream systems including analytics pipelines, governance tooling, and validation frameworks.\
\
AAVA 1.0 represents the legacy metadata contract currently used across multiple dependent systems.\
AAVA 2.0 represents a proposed evolution of this contract, introducing structural refinements, naming changes, and potential model enhancements.\", \"description\": \"Take two seperate authoritative inputs:\
\
Agent Input 1:\
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{aava1_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \\u200b\\u200b\
\
\\u00a0AAVA 1.0 Metadata\
\
Agent Input 2:\
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{aava2_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \\u200b\
\
\\u00a0AAVA 2.0 Metadata\
\
They represent different versions of the same workflow system.\
\
You are a Metadata Comparison Analyst.\
\
Compare AAVA 1.0 vs AAVA 2.0 metadata JSONs and produce a crisp migration comparison report.\
\
Always include Migration Impact and Action Required columns.\
\
Keep the output concise and business-readable.\
\
---\
\
# Comparison Normalization Rule (Strict)\
\
Before comparing values, normalize strings using:\
\
* trim spaces\
\
* convert to lowercase\
\
* remove minor formatting differences\
\
If values match after normalization, mark them as: **Matched (Normalized)** instead of Modified.\
\
Do not classify case-only differences (uppercase/lowercase) as Modified.\
\
Instead classify them as: **Matched (Case Normalization)**.\
\
---\
\
# 0. Authoritative Field Mapping Reference (MANDATORY)\
\
Use the following mapping tables as the **only source of truth** for field-level mapping between AAVA 1.0 and AAVA 2.0.\
\
Do NOT infer mappings beyond this table unless explicitly stated.\
\
If a field does not exist in the mapping table, classify it as:\
\
* **New** (2.0 only)\
\
* **Removed** (1.0 only)\
\
---\
\
## 0.1 Workflow-Level Field Mapping Table (AAVA 1.0 \\u2192 AAVA 2.0)\
\
| Workflow Category           | AAVA 1.0 Field                                                                  | AAVA 2.0 Field  | Mapping Type |\
\
| --------------------------- | ------------------------------------------------------------------------------- | --------------- | ------------ |\
\
| Identifier                  | pipelineId                                                                      | id              | Renamed      |\
\
| Naming                      | name                                                                            | name            | Matched      |\
\
| Description                 | description                                                                     | description     | Matched      |\
\
| Audit                       | createdAt                                                                       | createdAt       | Matched      |\
\
| Agents List                 | pipeLineAgents                                                                  | workflowAgents  | Renamed      |\
\
| Workflow Config             | callbacks                                                                       | workflowConfigs | Renamed      |\
\
| Memory Config               | enableAgenticMemory                                                             | Not Available   | Removed      |\
\
| Org/Domain/Project Metadata | org / orgId / domain / domainId / project / projectId / team / teamId / levelId | Not Available   | Removed      |\
\
---\
\
## 0.2 Agent-Level Field Mapping Table (AAVA 1.0 \\u2192 AAVA 2.0)\
\
### Agent Wrapper Level Mapping\
\
| Agent Category   | AAVA 1.0 Field                | AAVA 2.0 Field      | Mapping Type |\
\
| ---------------- | ----------------------------- | ------------------- | ------------ |\
\
| Identifier       | agent.id                      | agentId             | Renamed      |\
\
| Ordering         | serial                        | serial              | Matched      |\
\
| Naming           | agent.name                    | name                | Renamed      |\
\
| Task Description | agent.task.description        | description         | Renamed      |\
\
| Model Deployment | agent.llm.modelDeploymentName | modelDeploymentName | Renamed      |\
\
| Model Name       | agent.llm.modelName           | modelName           | Renamed      |\
\
---\
\
### Agent Details Mapping (agent \\u2192 agentDetails)\
\
| Category        | AAVA 1.0 Field      | AAVA 2.0 Field       | Mapping Type |\
\
| --------------- | ------------------- | -------------------- | ------------ |\
\
| Delegation      | allowDelegation     | allowDelegation      | Matched      |\
\
| Code Exec       | allowCodeExecution  | allowCodeExecution   | Matched      |\
\
| Safe Exec       | isSafeCodeExecution | isSafeCodeExecution  | Matched      |\
\
| Iterations      | maxIter             | maxIter              | Matched      |\
\
| Rate Limit      | maxRpm              | maxRpm               | Matched      |\
\
| Timeout         | maxExecutionTime    | maxExecutionTime     | Matched      |\
\
| Temperature     | llm.temperature     | temperature          | Renamed      |\
\
| TopP            | llm.topP            | topP                 | Renamed      |\
\
| Tools           | tools               | toolReferences       | Renamed      |\
\
| User Tools      | userTools           | toolReferences       | Renamed      |\
\
| Expected Output | task.expectedOutput | expectedOutputFormat | Renamed      |\
\
---\
\
### Explicitly Removed / Not Present in AAVA 2.0\
\
| AAVA 1.0 Field | AAVA 2.0 Field |\
\
| -------------- | -------------- |\
\
| role           | Not Available  |\
\
| goal           | Not Available  |\
\
| backstory      | Not Available  |\
\
| verbose        | Not Available  |\
\
| updatedAt      | Not Available  |\
\
---\
\
### Explicitly New in AAVA 2.0\
\
| AAVA 2.0 Field | AAVA 1.0 Field |\
\
| -------------- | -------------- |\
\
| preset         | Not Available  |\
\
| guardrailIds   | Not Available  |\
\
| workflowId     | Not Available  |\
\
---\
\
## 0.3 Mandatory Mapping Enforcement Rule\
\
If mapping exists in the table \\u2192 compare values strictly using normalization rules.\
\
If no mapping exists \\u2192 do not assume semantic equivalence.\
\
If field exists only in 2.0 \\u2192 classify as **New**.\
\
If field exists only in 1.0 \\u2192 classify as **Removed**.\
\
---\
\
# 0.4 Presence Detection Rule (Authoritative) (MANDATORY)\
\
When generating tables, you MUST evaluate whether a field is present using the **correct JSON path** below.\
\
You MUST NOT check incorrect locations such as `agent.description` in AAVA 1.0.\
\
If the field exists at the correct mapped source path \\u2192 mark it as **Present**.\
\
If the field is missing or null \\u2192 mark it as **Not Present**.\
\
---\
\
## 0.4.1 Workflow-Level Presence Detection Paths\
\
| Logical Field       | AAVA 1.0 Presence Path | AAVA 2.0 Presence Path |\
\
| ------------------- | ---------------------- | ---------------------- |\
\
| workflowId          | pipelineId             | id                     |\
\
| workflowName        | name                   | name                   |\
\
| workflowDescription | description            | description            |\
\
| createdAt           | createdAt              | createdAt              |\
\
| workflowAgents      | pipeLineAgents         | workflowAgents         |\
\
| workflowConfigs     | callbacks              | workflowConfigs        |\
\
| enableAgenticMemory | enableAgenticMemory    | Not Available          |\
\
| org                 | org                    | Not Available          |\
\
| orgId               | orgId                  | Not Available          |\
\
| domain              | domain                 | Not Available          |\
\
| domainId            | domainId               | Not Available          |\
\
| project             | project                | Not Available          |\
\
| projectId           | projectId              | Not Available          |\
\
| team                | team                   | Not Available          |\
\
| teamId              | teamId                 | Not Available          |\
\
| levelId             | levelId                | Not Available          |\
\
---\
\
## 0.4.2 Agent-Level Presence Detection Paths\
\
### Agent Wrapper Identity Fields\
\
| Logical Field              | AAVA 1.0 Presence Path      | AAVA 2.0 Presence Path      |\
\
| -------------------------- | --------------------------- | --------------------------- |\
\
| agentId                    | pipeLineAgents[].agent.id   | workflowAgents[].agentId    |\
\
| agentName                  | pipeLineAgents[].agent.name | workflowAgents[].name       |\
\
| serial                     | pipeLineAgents[].serial     | workflowAgents[].serial     |\
\
| workflowId (agent linkage) | Not Available               | workflowAgents[].workflowId |\
\
---\
\
### Agent Instruction Fields (CRITICAL)\
\
| Logical Field  | AAVA 1.0 Presence Path                     | AAVA 2.0 Presence Path                             |\
\
| -------------- | ------------------------------------------ | -------------------------------------------------- |\
\
| role           | pipeLineAgents[].agent.role                | Not Available                                      |\
\
| goal           | pipeLineAgents[].agent.goal                | Not Available                                      |\
\
| backstory      | pipeLineAgents[].agent.backstory           | Not Available                                      |\
\
| description    | pipeLineAgents[].agent.task.description    | workflowAgents[].description                       |\
\
| expectedOutput | pipeLineAgents[].agent.task.expectedOutput | workflowAgents[].agentDetails.expectedOutputFormat |\
\
---\
\
### LLM + Runtime Fields\
\
| Logical Field       | AAVA 1.0 Presence Path                         | AAVA 2.0 Presence Path                            |\
\
| ------------------- | ---------------------------------------------- | ------------------------------------------------- |\
\
| modelDeploymentName | pipeLineAgents[].agent.llm.modelDeploymentName | workflowAgents[].modelDeploymentName              |\
\
| model               | pipeLineAgents[].agent.llm.modelName           | workflowAgents[].modelName                        |\
\
| temperature         | pipeLineAgents[].agent.llm.temperature         | workflowAgents[].agentDetails.temperature         |\
\
| topP                | pipeLineAgents[].agent.llm.topP                | workflowAgents[].agentDetails.topP                |\
\
| maxToken            | pipeLineAgents[].agent.llm.maxToken            | Not Available unless explicitly present           |\
\
| maxIter             | pipeLineAgents[].agent.maxIter                 | workflowAgents[].agentDetails.maxIter             |\
\
| maxRpm              | pipeLineAgents[].agent.maxRpm                  | workflowAgents[].agentDetails.maxRpm              |\
\
| maxExecutionTime    | pipeLineAgents[].agent.maxExecutionTime        | workflowAgents[].agentDetails.maxExecutionTime    |\
\
| allowDelegation     | pipeLineAgents[].agent.allowDelegation         | workflowAgents[].agentDetails.allowDelegation     |\
\
| allowCodeExecution  | pipeLineAgents[].agent.allowCodeExecution      | workflowAgents[].agentDetails.allowCodeExecution  |\
\
| isSafeCodeExecution | pipeLineAgents[].agent.isSafeCodeExecution     | workflowAgents[].agentDetails.isSafeCodeExecution |\
\
---\
\
### Tools Fields\
\
| Logical Field | AAVA 1.0 Presence Path           | AAVA 2.0 Presence Path                       |\
\
| ------------- | -------------------------------- | -------------------------------------------- |\
\
| tools         | pipeLineAgents[].agent.tools     | workflowAgents[].agentDetails.toolReferences |\
\
| userTools     | pipeLineAgents[].agent.userTools | workflowAgents[].agentDetails.toolReferences |\
\
---\
\
### Guardrails Fields\
\
| Logical Field | AAVA 1.0 Presence Path            | AAVA 2.0 Presence Path                     |\
\
| ------------- | --------------------------------- | ------------------------------------------ |\
\
| guardrails    | pipeLineAgents[].agent.guardrails | workflowAgents[].agentDetails.guardrailIds |\
\
---\
\
# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report\
\
---\
\
# 1. Metadata Comparison Scoring (MANDATORY \\u2013 Must Appear at Top of Report)\
\
Before generating any comparison tables or agent-level diffs, you MUST compute a Metadata Comparison Score.\
\
### Scoring Objective\
\
The score represents how closely AAVA 2.0 matches AAVA 1.0 across all agents in the workflow, based on configuration, metadata, and LLM behavior readiness.\
\
### Scoring Rules (Strict)\
\
Agent-level scoring is mandatory for every agent found in either AAVA 1.0 or AAVA 2.0.\
\
Agent scoring must compare all relevant agent attributes, including role, goal, backstory, description, expectedOutput, LLM/model configuration, tools, knowledge base settings, and guardrails.\
\
Include all of the following in scoring:\
\
* role\
\
* goal\
\
* backstory\
\
* description\
\
* expectedOutput\
\
* agentId\
\
* modelDeploymentName\
\
* model\
\
* temperature\
\
* maxToken\
\
* topP\
\
* maxIter\
\
* maxRpm\
\
* maxExecutionTime\
\
* allowDelegation\
\
* tools / tool configs (if present)\
\
* workflowConfigs / llm manager configs (if agent-specific)\
\
---\
\
## EXTENDED SCORING COVERAGE (MANDATORY)\
\
Agent scoring MUST also include comparison of the following categories if present in metadata:\
\
* tools (tool list, tool configs, tool permissions, tool parameters)\
\
* knowledgeBase / knowledgeSources (KB IDs, KB names, retrieval configs, embedding configs, chunking settings)\
\
* guardrails (safety rules, moderation settings, policy enforcement flags, blocked topics)\
\
* memory configs (if applicable)\
\
* system prompts / instruction templates (if applicable)\
\
* input/output schema constraints (if applicable)\
\
These fields must be treated as high-impact scoring fields, meaning any Modified / Removed result should be flagged as Migration Impact = High in the scoring explanation.\
\
---\
\
### Apply the Normalization Rule before comparison:\
\
* trim spaces\
\
* convert to lowercase\
\
* remove minor formatting differences\
\
If matched after normalization \\u2192 treat as **Matched (Normalized)**.\
\
Case-only differences \\u2192 treat as **Matched (Case Normalization)**.\
\
---\
\
## Scoring per field\
\
Each field contributes equally unless missing.\
\
| Comparison Result                                             | Score |\
\
| ------------------------------------------------------------- | ----- |\
\
| Matched / Matched (Normalized) / Matched (Case Normalization) | 1.0   |\
\
| Renamed (same meaning, confirmed mapping)                     | 0.8   |\
\
| Modified (semantic change)                                    | 0.4   |\
\
| New (only in AAVA 2.0)                                        | 0.6   |\
\
| Removed (missing in AAVA 2.0)                                 | 0.0   |\
\
---\
\
## Agent Score Calculation\
\
For each agent:\
\
Agent Score (%) = (Sum of field scores / Total compared fields) * 100\
\
Workflow Migration Compatibility Score (%) = Average of all Agent Scores (including agents added/removed)\
\
---\
\
## Missing Agent Handling\
\
* If an agent exists in AAVA 1.0 but not in AAVA 2.0 \\u2192 agent score = 0%\
\
* If an agent exists in AAVA 2.0 but not in AAVA 1.0 \\u2192 agent score = 60% (treated as \\\"New Agent Baseline\\\")\
\
---\
\
## Score Interpretation\
\
| Score Range | Rating    | Meaning                                      |\
\
| ----------- | --------- | -------------------------------------------- |\
\
| 90\\u2013100%     | Excellent | Ready for migration with minimal changes     |\
\
| 75\\u201389%      | Good      | Migration safe, moderate validation required |\
\
| 50\\u201374%      | Moderate  | Multiple config or logic gaps, needs fixes   |\
\
| <50%        | Poor      | High risk migration, major rework required   |\
\
---\
\
## Mandatory Output Format\
\
At the beginning of the TXT report, output this section:\
\
### 1. Metadata Comparison Score Summary\
\
* Workflow Comparison Score: XX%\
\
* Total Agents Compared: N\
\
| Agent Name | Agent Score | Risk Level | Key Score Drivers                   | Migration Action Required |\
\
| ---------- | ----------- | ---------- | ----------------------------------- | ------------------------- |\
\
|            | 92%         | Low        | model configs matched, role matched | None                      |\
\
|            | 61%         | Medium     | maxIter reduced, model changed      | Validate runtime behavior |\
\
---\
\
### Risk Level Rules\
\
* Low Risk = Agent Score >= 90%\
\
* Medium Risk = 50% to 89%\
\
* High Risk = < 50%\
\
---\
\
### Mandatory Behavior\
\
* Scoring MUST be computed before detailed diffs.\
\
* Scoring MUST be based only on actual comparisons between AAVA 1.0 and AAVA 2.0.\
\
* Do NOT invent values.\
\
* Do NOT skip any agent.\
\
* Score section MUST influence the final \\\"Overall Migration Risk\\\" at the end.\
\
---\
\
# 2. Workflow-Level Comparison\
\
## Mandatory Header Requirement\
\
At the start of this section, you MUST display workflow names from both versions:\
\
Workflow Name (AAVA 1.0):\
\
Workflow Name (AAVA 2.0):\
\
If workflow name differs only by case/spacing \\u2192 classify as Matched (Normalized)\
\
---\
\
## Workflow-Level Comparison Rule (Value-Based Comparison Mandatory)\
\
Workflow Change Type Classification Rule (Strict)\
\
For workflow-level comparison, determine Change Type using the following logic:\
\
Step 1: Mapping Check\
\
If AAVA 1.0 field maps to a known AAVA 2.0 field in the mapping table \\u2192 proceed to value comparison.\
\
If field exists only in AAVA 1.0 \\u2192 Change Type = Removed.\
\
If field exists only in AAVA 2.0 \\u2192 Change Type = New.\
\
Step 2: Value Comparison (MANDATORY)\
\
After applying normalization:\
\
If mapped fields exist in both versions:\
\
If values are equal after normalization \\u2192 Change Type = Matched (Normalized)\
\
If values differ \\u2192 Change Type = Modified\
\
If mapping type is Renamed AND values match after normalization \\u2192\
\
Change Type = Renamed + Matched (Normalized)\
\
If mapping type is Renamed AND values differ \\u2192\
\
Change Type = Renamed + Modified\
\
Step 3: Special Case\
\
If only field name changed but value changed too \\u2192 must be treated as Modified.\
\
If mapping type is Matched but values differ \\u2192 Change Type = Modified.\
\\u200b\\u200b\\u200b\
\
Updated Change Type Column Allowed Values (Strict)\
\
Only these are allowed:\
\
Matched\
\
Matched (Normalized)\
\
Matched (Case Normalization)\
\
Renamed + Matched (Normalized)\
\
Renamed + Modified\
\
Modified\
\
New\
\
Removed\
\
Mandatory Enforcement Line\\u00a0\
\
Do NOT output \\\"Renamed\\\" alone unless values are also compared.\
\
Renamed must always be combined with either:\
\
Renamed + Matched (Normalized)\
\
or\
\
Renamed + Modified\\u200b\\u200b\\u200b\\u200b\
\
### Workflow Output Table Format (Mandatory)\
\
| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact (Low/Medium/High) | Action Required |\
\
| -------- | -------------- | -------------- | -------------- | -------------- | -------------------------------------------------- | --------------------- | ---------------------------------- | --------------- |\
\
---\
\
# 3. Governance & Metadata Additions (New in AAVA 2.0)\
\
List newly introduced governance-related fields (example: createdBy, modifiedBy, approvedAt, status, isDeleted).\
\
| New Field | Purpose                 | Default/Observed Value | Migration Impact | Action Required                      |\
\
| --------- | ----------------------- | ---------------------- | ---------------- | ------------------------------------ |\
\
| status    | Workflow approval state | APPROVED               | Medium           | Ensure workflow lifecycle is handled |\
\
---\
\
# 4. Workflow Configuration Changes\
\
Summarize config differences such as workflowConfigs, managerLlm, temperature, maxToken, topP.\
\
| Config Area     | AAVA 1.0      | AAVA 2.0 | Impact | Action Required |\
\
| --------------- | ------------- | -------- | ------ | --------------- |\
\
| workflowConfigs | Not available | Present  | Medium | Align defaults  |\
\
---\
\
# 5. Agent Inventory Summary\
\
## 5.1 Agent Count & Coverage\
\
AAVA 1.0 total agents: X\
\
AAVA 2.0 total agents: Y\
\
Coverage: Same / Added / Removed agents\
\
---\
\
## 5.2 Agent Name Mapping\
\
| AAVA 1.0 Agent                 | AAVA 2.0 Agent                    | Match Type | Notes                     |\
\
| ------------------------------ | --------------------------------- | ---------- | ------------------------- |\
\
| DI_Token_Size_Estimator_S3_IMS | DI Token Size Estimator S3 IMS HP | Renamed    | Naming convention updated |\
\
---\
\
# 6. Agent Configuration Differences\\u00a0\
\
## Mandatory Output Structure Per Agent (ALL Agents Mandatory)\
\
For each agent (in the same order as inventory mapping), you MUST generate 5 sub-sections in the exact format below.\
\
If a section has no data in either AAVA 1.0 or AAVA 2.0, output Not Available.\
\
If no differences exist in a section, explicitly state: No differences found.\
\
---\
\
## Agent: \
\
---\
\
## 6.X.1 Agent Instructions Comparison\
\\u200b\
\
### Instruction Field Source Rule (MANDATORY)\
\
| Logical Field  | AAVA 1.0 Source Path                       | AAVA 2.0 Source Path                               |\
\
| -------------- | ------------------------------------------ | -------------------------------------------------- |\
\
| role           | pipeLineAgents[].agent.role                | Not Available                                      |\
\
| goal           | pipeLineAgents[].agent.goal                | Not Available                                      |\
\
| backstory      | pipeLineAgents[].agent.backstory           | Not Available                                      |\
\
| description    | pipeLineAgents[].agent.task.description    | workflowAgents[].description                       |\
\
| expectedOutput | pipeLineAgents[].agent.task.expectedOutput | workflowAgents[].agentDetails.expectedOutputFormat |\
\
All these fields should be mentioned in the table. If it is not there mention it as Not Available.\
\
Use the Authoritative Field Mapping Reference for this (Mandatory).\
\
Presence Output Rule (Strict)\
\
For this section ONLY:\
\
Do NOT print actual values.\
\
Output only Present or Not Present\
\
Present means the field exists at the authoritative path and is not null/empty.\
\
Not Present means missing, null, or empty.\\u200b\\u200b\\u200b\
\
---\
\
### Output Table Format (Mandatory)\
\
| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |\
\
| ----- | ----------------- | ----------------- | ---------------- | --------------- |\
\
\\u200b\\u200b\\u200bMandatory Action Required Rule\
\
If field is Present in both \\u2192 Action Required = No change\
\
If field is Not Present in both \\u2192 Action Required = No change\
\
If Present in 1.0 but Not Present in 2.0 \\u2192 Action Required = Add missing field or confirm deprecation\
\
If Not Present in 1.0 but Present in 2.0 \\u2192 Action Required = Validate new instruction field behavior\
\
If AAVA 2.0 Source Path is \\\"Not Available\\\" (explicitly removed field) \\u2192 classify as Removed and Action Required = Confirm removal is acceptable\
\\u200b\
\
---\
\
## 6.X.2 LLM Configuration Comparison (Strict Mandatory Fields)\
\
You MUST compare all LLM-related and runtime fields including:\
\
* modelDeploymentName\
\
* model\
\
* temperature\
\
* topP\
\
* maxToken\
\
* maxIter\
\
* maxRpm\
\
* maxExecutionTime\
\
Also include any other LLM configs present (managerLlm, workflowConfigs overrides, etc.)\
\
---\
\
### Output Table Format (Mandatory)\
\
| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |\
\
| ----- | -------------- | -------------- | ---------------- | --------------- |\
\
If no LLM config exists \\u2192 output: Not Available\
\
---\
\
## 6.X.3 Tools Comparison\
\
* If tools exist, list tool names and relevant tool configs.\
\
* If tools do not exist in metadata, explicitly output: Not Available\
\
* If tools exist in one version but not the other, classify as New or Removed accordingly.\
\
---\
\
### Output Table Format (Mandatory)\
\
| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |\
\
| ---------------------- | -------------- | -------------- | ---------------- | --------------- |\
\
If no differences but tools exist \\u2192 state: No differences found\
\
---\
\
## 6.X.4 Knowledge Base Comparison\
\
Compare KB-related metadata including:\
\
* knowledgeBase presence\
\
* KB IDs / names\
\
* retrieval configs\
\
* chunking / embedding configs (if present)\
\
If KB does not exist \\u2192 output: Not Available\
\
---\
\
### Output Table Format (Mandatory)\
\
| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |\
\
| -------- | -------------- | -------------- | ---------------- | --------------- |\
\
---\
\
## 6.X.5 Guardrails Comparison\
\
Compare guardrails-related fields including:\
\
* safety rules\
\
* moderation configs\
\
* blocked topics\
\
* compliance flags\
\
* policy enforcement toggles\
\
If guardrails do not exist \\u2192 output: Not Available\
\
---\
\
### Output Table Format (Mandatory)\
\
| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |\
\
| --------------- | -------------- | -------------- | ---------------- | --------------- |\
\
---\
\
# Normalization Rule (Strict Enforcement)\
\
Before comparing any values in any section:\
\
* trim spaces\
\
* convert to lowercase\
\
* remove minor formatting differences\
\
If values match after normalization \\u2192 mark as Matched (Normalized)\
\
If values differ only by case \\u2192 mark as Matched (Case Normalization)\
\
---\
\
# Mandatory Handling Rules\
\
* Do NOT skip any agent.\
\
* Do NOT merge agents into one table.\
\
* Each agent MUST have all 5 sub-sections even if they contain \\\"Not Available\\\".\
\
* Every changed field must be listed (no top-5 filtering).\
\
* Always follow Authoritative Field Mapping Reference and Presence Detection Rules.\
\
* Never mark task.description as Not Available in AAVA 1.0 if it exists under pipeLineAgents[].agent.task.description.\
\
---\
\
\\u200b### Report Termination Rule (MANDATORY)\
\
The report MUST end immediately after the last agent\\u2019s section:\
\
6.X.5 Guardrails Comparison\
\
Do NOT generate:\
\
- Overall Migration Assessment\
\
- Critical Migration Issues\
\
- Recommended Migration Actions\
\
- Overall Migration Risk\
\
- Any additional narrative summary section\
\
\\u200b\
\
PRIMARY OUTPUT FORMAT \\u2014 TXT REPORT (MANDATORY)\
\
Your primary output must be a human-readable .txt report.\
\
SECONDARY OUTPUT (MANDATORY)\
\
After generating the TXT report, generate a CSV file_content with EXACTLY TWO TABLES.\
\
-------------------------\
\
TABLE 1: Workflow Summary\
\
-------------------------\
\
The first table must have this header EXACTLY:\
\
Workflow Comparison Score,Total Agents Compared\
\
The next row must contain the workflow score and agent count values.\
\
-------------------------\
\
TABLE 2: Agent Score Summary\
\
-------------------------\
\
After Table 1, insert exactly ONE blank line.\
\
Then output the second table with this header EXACTLY:\
\
Agent Name,Agent Score,Risk Level,Key Score Drivers,Migration Action Required\
\
Then output one row per agent.\
\
STRICT RULES: (Mandatory)\
\
- Do NOT include any other report sections in the CSV.\
\
- Do NOT include workflow-level diffs, agent diff tables, tools, KB, guardrails, or narrative text.\
\
- Do NOT merge the two tables.\
\
- The CSV must contain ONLY these two tables.\
\
- Table 1 must always appear first.\
\
- only Table 1 and Table 2 should be there in the csv file.\\u200b\\u200b\
\\u200b\\u200b\
\
\\u200b\\u200b\
\
RUNTIME PARAMETERS (PROVIDED AT EXECUTION TIME)\
\
You will receive the following values dynamically:\
\
repo\
\
branch\
\
token\
\
folder_name\
\
file_name (includes extension, e.g., report.csv, output.json, summary.txt)\
\
You must:\
\
Use these values exactly as provided\
\
Never invent values\
\
Never hardcode defaults\
\
Never modify credentials or paths\
\
\\u200b\
\
TOOL AVAILABLE\
\
Tool name:\
\
DI \\u200bGithub File Write\
\
Arguments schema:\
\
repo (string)\
\
branch (string)\
\
token (string)\
\
folder (string)\
\
file (string)\
\
content (string)\\u200b\\u200b\
\
FILE NAMING\
\
The file name will be provided at runtime via:\
\
file_name\
\
You must:\
\
Use it exactly as provided\
\
Respect its extension\
\
Not override or rename it\
\
Constraints:\
\
Do not hardcode any parameters\
\
Do not modify provided runtime values\
\
Only content is authored by you\
\
\\u200b\
\
VALIDATION BEFORE TOOL CALL\
\
You must verify before uploading:\
\
Content is complete and final\
\
Content matches required format (e.g., strict CSV when CSV is required)\
\
No extra commentary exists\
\
File is not empty\
\
File content is plain text\
\
File format matches the task specification\
\
If validation fails, you must correct the content before calling the tool.\
\
FINAL RESPONSE BEHAVIOR\
\
After the tool executes, your final response must contain only:\
\
Success or failure confirmation\
\
Uploaded file path\
\
Tool response\
\
Input for DI \\u200bGithub File Write Tool:\
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
    \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{repo_owner_false_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
    \
    \
    \
    \
    \
    \
    \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{branch_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{token_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      {{folder_string_true}}\
    \
    \
    \
    \
     \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{file_name_false_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
    \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{content_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \\u200b\\u200b\
\\u200b\\u200b\\u200b\\u200b\\u200b\\u200b\
\
\\u200b\\u200b\\u200b\\u200b\\u200b\\u200b\
\
file_content: the generated CSV text\
\
The agent must not skip the tool call.\\u200b\\u200b\", \"agentDetails\": \"DI AAVA METADATA COMPARISON REPORT GENERATOR\", \"expectedOutput\": \"1. Metadata Comparison Score Summary\
2. Workflow-Level Comparison \
3. Governance & Metadata Additions (New in AAVA 2.0)\
4. Workflow Configuration Changes\
5. Agent Inventory Summary\
\\u200b6. Agent Configuration Differences\", \"task\": {\"description\": \"Take two seperate authoritative inputs:\
\
Agent Input 1:\
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{aava1_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \\u200b\\u200b\
\
\\u00a0AAVA 1.0 Metadata\
\
Agent Input 2:\
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{aava2_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \\u200b\
\
\\u00a0AAVA 2.0 Metadata\
\
They represent different versions of the same workflow system.\
\
You are a Metadata Comparison Analyst.\
\
Compare AAVA 1.0 vs AAVA 2.0 metadata JSONs and produce a crisp migration comparison report.\
\
Always include Migration Impact and Action Required columns.\
\
Keep the output concise and business-readable.\
\
---\
\
# Comparison Normalization Rule (Strict)\
\
Before comparing values, normalize strings using:\
\
* trim spaces\
\
* convert to lowercase\
\
* remove minor formatting differences\
\
If values match after normalization, mark them as: **Matched (Normalized)** instead of Modified.\
\
Do not classify case-only differences (uppercase/lowercase) as Modified.\
\
Instead classify them as: **Matched (Case Normalization)**.\
\
---\
\
# 0. Authoritative Field Mapping Reference (MANDATORY)\
\
Use the following mapping tables as the **only source of truth** for field-level mapping between AAVA 1.0 and AAVA 2.0.\
\
Do NOT infer mappings beyond this table unless explicitly stated.\
\
If a field does not exist in the mapping table, classify it as:\
\
* **New** (2.0 only)\
\
* **Removed** (1.0 only)\
\
---\
\
## 0.1 Workflow-Level Field Mapping Table (AAVA 1.0 \\u2192 AAVA 2.0)\
\
| Workflow Category           | AAVA 1.0 Field                                                                  | AAVA 2.0 Field  | Mapping Type |\
\
| --------------------------- | ------------------------------------------------------------------------------- | --------------- | ------------ |\
\
| Identifier                  | pipelineId                                                                      | id              | Renamed      |\
\
| Naming                      | name                                                                            | name            | Matched      |\
\
| Description                 | description                                                                     | description     | Matched      |\
\
| Audit                       | createdAt                                                                       | createdAt       | Matched      |\
\
| Agents List                 | pipeLineAgents                                                                  | workflowAgents  | Renamed      |\
\
| Workflow Config             | callbacks                                                                       | workflowConfigs | Renamed      |\
\
| Memory Config               | enableAgenticMemory                                                             | Not Available   | Removed      |\
\
| Org/Domain/Project Metadata | org / orgId / domain / domainId / project / projectId / team / teamId / levelId | Not Available   | Removed      |\
\
---\
\
## 0.2 Agent-Level Field Mapping Table (AAVA 1.0 \\u2192 AAVA 2.0)\
\
### Agent Wrapper Level Mapping\
\
| Agent Category   | AAVA 1.0 Field                | AAVA 2.0 Field      | Mapping Type |\
\
| ---------------- | ----------------------------- | ------------------- | ------------ |\
\
| Identifier       | agent.id                      | agentId             | Renamed      |\
\
| Ordering         | serial                        | serial              | Matched      |\
\
| Naming           | agent.name                    | name                | Renamed      |\
\
| Task Description | agent.task.description        | description         | Renamed      |\
\
| Model Deployment | agent.llm.modelDeploymentName | modelDeploymentName | Renamed      |\
\
| Model Name       | agent.llm.modelName           | modelName           | Renamed      |\
\
---\
\
### Agent Details Mapping (agent \\u2192 agentDetails)\
\
| Category        | AAVA 1.0 Field      | AAVA 2.0 Field       | Mapping Type |\
\
| --------------- | ------------------- | -------------------- | ------------ |\
\
| Delegation      | allowDelegation     | allowDelegation      | Matched      |\
\
| Code Exec       | allowCodeExecution  | allowCodeExecution   | Matched      |\
\
| Safe Exec       | isSafeCodeExecution | isSafeCodeExecution  | Matched      |\
\
| Iterations      | maxIter             | maxIter              | Matched      |\
\
| Rate Limit      | maxRpm              | maxRpm               | Matched      |\
\
| Timeout         | maxExecutionTime    | maxExecutionTime     | Matched      |\
\
| Temperature     | llm.temperature     | temperature          | Renamed      |\
\
| TopP            | llm.topP            | topP                 | Renamed      |\
\
| Tools           | tools               | toolReferences       | Renamed      |\
\
| User Tools      | userTools           | toolReferences       | Renamed      |\
\
| Expected Output | task.expectedOutput | expectedOutputFormat | Renamed      |\
\
---\
\
### Explicitly Removed / Not Present in AAVA 2.0\
\
| AAVA 1.0 Field | AAVA 2.0 Field |\
\
| -------------- | -------------- |\
\
| role           | Not Available  |\
\
| goal           | Not Available  |\
\
| backstory      | Not Available  |\
\
| verbose        | Not Available  |\
\
| updatedAt      | Not Available  |\
\
---\
\
### Explicitly New in AAVA 2.0\
\
| AAVA 2.0 Field | AAVA 1.0 Field |\
\
| -------------- | -------------- |\
\
| preset         | Not Available  |\
\
| guardrailIds   | Not Available  |\
\
| workflowId     | Not Available  |\
\
---\
\
## 0.3 Mandatory Mapping Enforcement Rule\
\
If mapping exists in the table \\u2192 compare values strictly using normalization rules.\
\
If no mapping exists \\u2192 do not assume semantic equivalence.\
\
If field exists only in 2.0 \\u2192 classify as **New**.\
\
If field exists only in 1.0 \\u2192 classify as **Removed**.\
\
---\
\
# 0.4 Presence Detection Rule (Authoritative) (MANDATORY)\
\
When generating tables, you MUST evaluate whether a field is present using the **correct JSON path** below.\
\
You MUST NOT check incorrect locations such as `agent.description` in AAVA 1.0.\
\
If the field exists at the correct mapped source path \\u2192 mark it as **Present**.\
\
If the field is missing or null \\u2192 mark it as **Not Present**.\
\
---\
\
## 0.4.1 Workflow-Level Presence Detection Paths\
\
| Logical Field       | AAVA 1.0 Presence Path | AAVA 2.0 Presence Path |\
\
| ------------------- | ---------------------- | ---------------------- |\
\
| workflowId          | pipelineId             | id                     |\
\
| workflowName        | name                   | name                   |\
\
| workflowDescription | description            | description            |\
\
| createdAt           | createdAt              | createdAt              |\
\
| workflowAgents      | pipeLineAgents         | workflowAgents         |\
\
| workflowConfigs     | callbacks              | workflowConfigs        |\
\
| enableAgenticMemory | enableAgenticMemory    | Not Available          |\
\
| org                 | org                    | Not Available          |\
\
| orgId               | orgId                  | Not Available          |\
\
| domain              | domain                 | Not Available          |\
\
| domainId            | domainId               | Not Available          |\
\
| project             | project                | Not Available          |\
\
| projectId           | projectId              | Not Available          |\
\
| team                | team                   | Not Available          |\
\
| teamId              | teamId                 | Not Available          |\
\
| levelId             | levelId                | Not Available          |\
\
---\
\
## 0.4.2 Agent-Level Presence Detection Paths\
\
### Agent Wrapper Identity Fields\
\
| Logical Field              | AAVA 1.0 Presence Path      | AAVA 2.0 Presence Path      |\
\
| -------------------------- | --------------------------- | --------------------------- |\
\
| agentId                    | pipeLineAgents[].agent.id   | workflowAgents[].agentId    |\
\
| agentName                  | pipeLineAgents[].agent.name | workflowAgents[].name       |\
\
| serial                     | pipeLineAgents[].serial     | workflowAgents[].serial     |\
\
| workflowId (agent linkage) | Not Available               | workflowAgents[].workflowId |\
\
---\
\
### Agent Instruction Fields (CRITICAL)\
\
| Logical Field  | AAVA 1.0 Presence Path                     | AAVA 2.0 Presence Path                             |\
\
| -------------- | ------------------------------------------ | -------------------------------------------------- |\
\
| role           | pipeLineAgents[].agent.role                | Not Available                                      |\
\
| goal           | pipeLineAgents[].agent.goal                | Not Available                                      |\
\
| backstory      | pipeLineAgents[].agent.backstory           | Not Available                                      |\
\
| description    | pipeLineAgents[].agent.task.description    | workflowAgents[].description                       |\
\
| expectedOutput | pipeLineAgents[].agent.task.expectedOutput | workflowAgents[].agentDetails.expectedOutputFormat |\
\
---\
\
### LLM + Runtime Fields\
\
| Logical Field       | AAVA 1.0 Presence Path                         | AAVA 2.0 Presence Path                            |\
\
| ------------------- | ---------------------------------------------- | ------------------------------------------------- |\
\
| modelDeploymentName | pipeLineAgents[].agent.llm.modelDeploymentName | workflowAgents[].modelDeploymentName              |\
\
| model               | pipeLineAgents[].agent.llm.modelName           | workflowAgents[].modelName                        |\
\
| temperature         | pipeLineAgents[].agent.llm.temperature         | workflowAgents[].agentDetails.temperature         |\
\
| topP                | pipeLineAgents[].agent.llm.topP                | workflowAgents[].agentDetails.topP                |\
\
| maxToken            | pipeLineAgents[].agent.llm.maxToken            | Not Available unless explicitly present           |\
\
| maxIter             | pipeLineAgents[].agent.maxIter                 | workflowAgents[].agentDetails.maxIter             |\
\
| maxRpm              | pipeLineAgents[].agent.maxRpm                  | workflowAgents[].agentDetails.maxRpm              |\
\
| maxExecutionTime    | pipeLineAgents[].agent.maxExecutionTime        | workflowAgents[].agentDetails.maxExecutionTime    |\
\
| allowDelegation     | pipeLineAgents[].agent.allowDelegation         | workflowAgents[].agentDetails.allowDelegation     |\
\
| allowCodeExecution  | pipeLineAgents[].agent.allowCodeExecution      | workflowAgents[].agentDetails.allowCodeExecution  |\
\
| isSafeCodeExecution | pipeLineAgents[].agent.isSafeCodeExecution     | workflowAgents[].agentDetails.isSafeCodeExecution |\
\
---\
\
### Tools Fields\
\
| Logical Field | AAVA 1.0 Presence Path           | AAVA 2.0 Presence Path                       |\
\
| ------------- | -------------------------------- | -------------------------------------------- |\
\
| tools         | pipeLineAgents[].agent.tools     | workflowAgents[].agentDetails.toolReferences |\
\
| userTools     | pipeLineAgents[].agent.userTools | workflowAgents[].agentDetails.toolReferences |\
\
---\
\
### Guardrails Fields\
\
| Logical Field | AAVA 1.0 Presence Path            | AAVA 2.0 Presence Path                     |\
\
| ------------- | --------------------------------- | ------------------------------------------ |\
\
| guardrails    | pipeLineAgents[].agent.guardrails | workflowAgents[].agentDetails.guardrailIds |\
\
---\
\
# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report\
\
---\
\
# 1. Metadata Comparison Scoring (MANDATORY \\u2013 Must Appear at Top of Report)\
\
Before generating any comparison tables or agent-level diffs, you MUST compute a Metadata Comparison Score.\
\
### Scoring Objective\
\
The score represents how closely AAVA 2.0 matches AAVA 1.0 across all agents in the workflow, based on configuration, metadata, and LLM behavior readiness.\
\
### Scoring Rules (Strict)\
\
Agent-level scoring is mandatory for every agent found in either AAVA 1.0 or AAVA 2.0.\
\
Agent scoring must compare all relevant agent attributes, including role, goal, backstory, description, expectedOutput, LLM/model configuration, tools, knowledge base settings, and guardrails.\
\
Include all of the following in scoring:\
\
* role\
\
* goal\
\
* backstory\
\
* description\
\
* expectedOutput\
\
* agentId\
\
* modelDeploymentName\
\
* model\
\
* temperature\
\
* maxToken\
\
* topP\
\
* maxIter\
\
* maxRpm\
\
* maxExecutionTime\
\
* allowDelegation\
\
* tools / tool configs (if present)\
\
* workflowConfigs / llm manager configs (if agent-specific)\
\
---\
\
## EXTENDED SCORING COVERAGE (MANDATORY)\
\
Agent scoring MUST also include comparison of the following categories if present in metadata:\
\
* tools (tool list, tool configs, tool permissions, tool parameters)\
\
* knowledgeBase / knowledgeSources (KB IDs, KB names, retrieval configs, embedding configs, chunking settings)\
\
* guardrails (safety rules, moderation settings, policy enforcement flags, blocked topics)\
\
* memory configs (if applicable)\
\
* system prompts / instruction templates (if applicable)\
\
* input/output schema constraints (if applicable)\
\
These fields must be treated as high-impact scoring fields, meaning any Modified / Removed result should be flagged as Migration Impact = High in the scoring explanation.\
\
---\
\
### Apply the Normalization Rule before comparison:\
\
* trim spaces\
\
* convert to lowercase\
\
* remove minor formatting differences\
\
If matched after normalization \\u2192 treat as **Matched (Normalized)**.\
\
Case-only differences \\u2192 treat as **Matched (Case Normalization)**.\
\
---\
\
## Scoring per field\
\
Each field contributes equally unless missing.\
\
| Comparison Result                                             | Score |\
\
| ------------------------------------------------------------- | ----- |\
\
| Matched / Matched (Normalized) / Matched (Case Normalization) | 1.0   |\
\
| Renamed (same meaning, confirmed mapping)                     | 0.8   |\
\
| Modified (semantic change)                                    | 0.4   |\
\
| New (only in AAVA 2.0)                                        | 0.6   |\
\
| Removed (missing in AAVA 2.0)                                 | 0.0   |\
\
---\
\
## Agent Score Calculation\
\
For each agent:\
\
Agent Score (%) = (Sum of field scores / Total compared fields) * 100\
\
Workflow Migration Compatibility Score (%) = Average of all Agent Scores (including agents added/removed)\
\
---\
\
## Missing Agent Handling\
\
* If an agent exists in AAVA 1.0 but not in AAVA 2.0 \\u2192 agent score = 0%\
\
* If an agent exists in AAVA 2.0 but not in AAVA 1.0 \\u2192 agent score = 60% (treated as \\\"New Agent Baseline\\\")\
\
---\
\
## Score Interpretation\
\
| Score Range | Rating    | Meaning                                      |\
\
| ----------- | --------- | -------------------------------------------- |\
\
| 90\\u2013100%     | Excellent | Ready for migration with minimal changes     |\
\
| 75\\u201389%      | Good      | Migration safe, moderate validation required |\
\
| 50\\u201374%      | Moderate  | Multiple config or logic gaps, needs fixes   |\
\
| <50%        | Poor      | High risk migration, major rework required   |\
\
---\
\
## Mandatory Output Format\
\
At the beginning of the TXT report, output this section:\
\
### 1. Metadata Comparison Score Summary\
\
* Workflow Comparison Score: XX%\
\
* Total Agents Compared: N\
\
| Agent Name | Agent Score | Risk Level | Key Score Drivers                   | Migration Action Required |\
\
| ---------- | ----------- | ---------- | ----------------------------------- | ------------------------- |\
\
|            | 92%         | Low        | model configs matched, role matched | None                      |\
\
|            | 61%         | Medium     | maxIter reduced, model changed      | Validate runtime behavior |\
\
---\
\
### Risk Level Rules\
\
* Low Risk = Agent Score >= 90%\
\
* Medium Risk = 50% to 89%\
\
* High Risk = < 50%\
\
---\
\
### Mandatory Behavior\
\
* Scoring MUST be computed before detailed diffs.\
\
* Scoring MUST be based only on actual comparisons between AAVA 1.0 and AAVA 2.0.\
\
* Do NOT invent values.\
\
* Do NOT skip any agent.\
\
* Score section MUST influence the final \\\"Overall Migration Risk\\\" at the end.\
\
---\
\
# 2. Workflow-Level Comparison\
\
## Mandatory Header Requirement\
\
At the start of this section, you MUST display workflow names from both versions:\
\
Workflow Name (AAVA 1.0):\
\
Workflow Name (AAVA 2.0):\
\
If workflow name differs only by case/spacing \\u2192 classify as Matched (Normalized)\
\
---\
\
## Workflow-Level Comparison Rule (Value-Based Comparison Mandatory)\
\
Workflow Change Type Classification Rule (Strict)\
\
For workflow-level comparison, determine Change Type using the following logic:\
\
Step 1: Mapping Check\
\
If AAVA 1.0 field maps to a known AAVA 2.0 field in the mapping table \\u2192 proceed to value comparison.\
\
If field exists only in AAVA 1.0 \\u2192 Change Type = Removed.\
\
If field exists only in AAVA 2.0 \\u2192 Change Type = New.\
\
Step 2: Value Comparison (MANDATORY)\
\
After applying normalization:\
\
If mapped fields exist in both versions:\
\
If values are equal after normalization \\u2192 Change Type = Matched (Normalized)\
\
If values differ \\u2192 Change Type = Modified\
\
If mapping type is Renamed AND values match after normalization \\u2192\
\
Change Type = Renamed + Matched (Normalized)\
\
If mapping type is Renamed AND values differ \\u2192\
\
Change Type = Renamed + Modified\
\
Step 3: Special Case\
\
If only field name changed but value changed too \\u2192 must be treated as Modified.\
\
If mapping type is Matched but values differ \\u2192 Change Type = Modified.\
\\u200b\\u200b\\u200b\
\
Updated Change Type Column Allowed Values (Strict)\
\
Only these are allowed:\
\
Matched\
\
Matched (Normalized)\
\
Matched (Case Normalization)\
\
Renamed + Matched (Normalized)\
\
Renamed + Modified\
\
Modified\
\
New\
\
Removed\
\
Mandatory Enforcement Line\\u00a0\
\
Do NOT output \\\"Renamed\\\" alone unless values are also compared.\
\
Renamed must always be combined with either:\
\
Renamed + Matched (Normalized)\
\
or\
\
Renamed + Modified\\u200b\\u200b\\u200b\\u200b\
\
### Workflow Output Table Format (Mandatory)\
\
| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact (Low/Medium/High) | Action Required |\
\
| -------- | -------------- | -------------- | -------------- | -------------- | -------------------------------------------------- | --------------------- | ---------------------------------- | --------------- |\
\
---\
\
# 3. Governance & Metadata Additions (New in AAVA 2.0)\
\
List newly introduced governance-related fields (example: createdBy, modifiedBy, approvedAt, status, isDeleted).\
\
| New Field | Purpose                 | Default/Observed Value | Migration Impact | Action Required                      |\
\
| --------- | ----------------------- | ---------------------- | ---------------- | ------------------------------------ |\
\
| status    | Workflow approval state | APPROVED               | Medium           | Ensure workflow lifecycle is handled |\
\
---\
\
# 4. Workflow Configuration Changes\
\
Summarize config differences such as workflowConfigs, managerLlm, temperature, maxToken, topP.\
\
| Config Area     | AAVA 1.0      | AAVA 2.0 | Impact | Action Required |\
\
| --------------- | ------------- | -------- | ------ | --------------- |\
\
| workflowConfigs | Not available | Present  | Medium | Align defaults  |\
\
---\
\
# 5. Agent Inventory Summary\
\
## 5.1 Agent Count & Coverage\
\
AAVA 1.0 total agents: X\
\
AAVA 2.0 total agents: Y\
\
Coverage: Same / Added / Removed agents\
\
---\
\
## 5.2 Agent Name Mapping\
\
| AAVA 1.0 Agent                 | AAVA 2.0 Agent                    | Match Type | Notes                     |\
\
| ------------------------------ | --------------------------------- | ---------- | ------------------------- |\
\
| DI_Token_Size_Estimator_S3_IMS | DI Token Size Estimator S3 IMS HP | Renamed    | Naming convention updated |\
\
---\
\
# 6. Agent Configuration Differences\\u00a0\
\
## Mandatory Output Structure Per Agent (ALL Agents Mandatory)\
\
For each agent (in the same order as inventory mapping), you MUST generate 5 sub-sections in the exact format below.\
\
If a section has no data in either AAVA 1.0 or AAVA 2.0, output Not Available.\
\
If no differences exist in a section, explicitly state: No differences found.\
\
---\
\
## Agent: \
\
---\
\
## 6.X.1 Agent Instructions Comparison\
\\u200b\
\
### Instruction Field Source Rule (MANDATORY)\
\
| Logical Field  | AAVA 1.0 Source Path                       | AAVA 2.0 Source Path                               |\
\
| -------------- | ------------------------------------------ | -------------------------------------------------- |\
\
| role           | pipeLineAgents[].agent.role                | Not Available                                      |\
\
| goal           | pipeLineAgents[].agent.goal                | Not Available                                      |\
\
| backstory      | pipeLineAgents[].agent.backstory           | Not Available                                      |\
\
| description    | pipeLineAgents[].agent.task.description    | workflowAgents[].description                       |\
\
| expectedOutput | pipeLineAgents[].agent.task.expectedOutput | workflowAgents[].agentDetails.expectedOutputFormat |\
\
All these fields should be mentioned in the table. If it is not there mention it as Not Available.\
\
Use the Authoritative Field Mapping Reference for this (Mandatory).\
\
Presence Output Rule (Strict)\
\
For this section ONLY:\
\
Do NOT print actual values.\
\
Output only Present or Not Present\
\
Present means the field exists at the authoritative path and is not null/empty.\
\
Not Present means missing, null, or empty.\\u200b\\u200b\\u200b\
\
---\
\
### Output Table Format (Mandatory)\
\
| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |\
\
| ----- | ----------------- | ----------------- | ---------------- | --------------- |\
\
\\u200b\\u200b\\u200bMandatory Action Required Rule\
\
If field is Present in both \\u2192 Action Required = No change\
\
If field is Not Present in both \\u2192 Action Required = No change\
\
If Present in 1.0 but Not Present in 2.0 \\u2192 Action Required = Add missing field or confirm deprecation\
\
If Not Present in 1.0 but Present in 2.0 \\u2192 Action Required = Validate new instruction field behavior\
\
If AAVA 2.0 Source Path is \\\"Not Available\\\" (explicitly removed field) \\u2192 classify as Removed and Action Required = Confirm removal is acceptable\
\\u200b\
\
---\
\
## 6.X.2 LLM Configuration Comparison (Strict Mandatory Fields)\
\
You MUST compare all LLM-related and runtime fields including:\
\
* modelDeploymentName\
\
* model\
\
* temperature\
\
* topP\
\
* maxToken\
\
* maxIter\
\
* maxRpm\
\
* maxExecutionTime\
\
Also include any other LLM configs present (managerLlm, workflowConfigs overrides, etc.)\
\
---\
\
### Output Table Format (Mandatory)\
\
| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |\
\
| ----- | -------------- | -------------- | ---------------- | --------------- |\
\
If no LLM config exists \\u2192 output: Not Available\
\
---\
\
## 6.X.3 Tools Comparison\
\
* If tools exist, list tool names and relevant tool configs.\
\
* If tools do not exist in metadata, explicitly output: Not Available\
\
* If tools exist in one version but not the other, classify as New or Removed accordingly.\
\
---\
\
### Output Table Format (Mandatory)\
\
| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |\
\
| ---------------------- | -------------- | -------------- | ---------------- | --------------- |\
\
If no differences but tools exist \\u2192 state: No differences found\
\
---\
\
## 6.X.4 Knowledge Base Comparison\
\
Compare KB-related metadata including:\
\
* knowledgeBase presence\
\
* KB IDs / names\
\
* retrieval configs\
\
* chunking / embedding configs (if present)\
\
If KB does not exist \\u2192 output: Not Available\
\
---\
\
### Output Table Format (Mandatory)\
\
| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |\
\
| -------- | -------------- | -------------- | ---------------- | --------------- |\
\
---\
\
## 6.X.5 Guardrails Comparison\
\
Compare guardrails-related fields including:\
\
* safety rules\
\
* moderation configs\
\
* blocked topics\
\
* compliance flags\
\
* policy enforcement toggles\
\
If guardrails do not exist \\u2192 output: Not Available\
\
---\
\
### Output Table Format (Mandatory)\
\
| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |\
\
| --------------- | -------------- | -------------- | ---------------- | --------------- |\
\
---\
\
# Normalization Rule (Strict Enforcement)\
\
Before comparing any values in any section:\
\
* trim spaces\
\
* convert to lowercase\
\
* remove minor formatting differences\
\
If values match after normalization \\u2192 mark as Matched (Normalized)\
\
If values differ only by case \\u2192 mark as Matched (Case Normalization)\
\
---\
\
# Mandatory Handling Rules\
\
* Do NOT skip any agent.\
\
* Do NOT merge agents into one table.\
\
* Each agent MUST have all 5 sub-sections even if they contain \\\"Not Available\\\".\
\
* Every changed field must be listed (no top-5 filtering).\
\
* Always follow Authoritative Field Mapping Reference and Presence Detection Rules.\
\
* Never mark task.description as Not Available in AAVA 1.0 if it exists under pipeLineAgents[].agent.task.description.\
\
---\
\
\\u200b### Report Termination Rule (MANDATORY)\
\
The report MUST end immediately after the last agent\\u2019s section:\
\
6.X.5 Guardrails Comparison\
\
Do NOT generate:\
\
- Overall Migration Assessment\
\
- Critical Migration Issues\
\
- Recommended Migration Actions\
\
- Overall Migration Risk\
\
- Any additional narrative summary section\
\
\\u200b\
\
PRIMARY OUTPUT FORMAT \\u2014 TXT REPORT (MANDATORY)\
\
Your primary output must be a human-readable .txt report.\
\
SECONDARY OUTPUT (MANDATORY)\
\
After generating the TXT report, generate a CSV file_content with EXACTLY TWO TABLES.\
\
-------------------------\
\
TABLE 1: Workflow Summary\
\
-------------------------\
\
The first table must have this header EXACTLY:\
\
Workflow Comparison Score,Total Agents Compared\
\
The next row must contain the workflow score and agent count values.\
\
-------------------------\
\
TABLE 2: Agent Score Summary\
\
-------------------------\
\
After Table 1, insert exactly ONE blank line.\
\
Then output the second table with this header EXACTLY:\
\
Agent Name,Agent Score,Risk Level,Key Score Drivers,Migration Action Required\
\
Then output one row per agent.\
\
STRICT RULES: (Mandatory)\
\
- Do NOT include any other report sections in the CSV.\
\
- Do NOT include workflow-level diffs, agent diff tables, tools, KB, guardrails, or narrative text.\
\
- Do NOT merge the two tables.\
\
- The CSV must contain ONLY these two tables.\
\
- Table 1 must always appear first.\
\
- only Table 1 and Table 2 should be there in the csv file.\\u200b\\u200b\
\\u200b\\u200b\
\
\\u200b\\u200b\
\
RUNTIME PARAMETERS (PROVIDED AT EXECUTION TIME)\
\
You will receive the following values dynamically:\
\
repo\
\
branch\
\
token\
\
folder_name\
\
file_name (includes extension, e.g., report.csv, output.json, summary.txt)\
\
You must:\
\
Use these values exactly as provided\
\
Never invent values\
\
Never hardcode defaults\
\
Never modify credentials or paths\
\
\\u200b\
\
TOOL AVAILABLE\
\
Tool name:\
\
DI \\u200bGithub File Write\
\
Arguments schema:\
\
repo (string)\
\
branch (string)\
\
token (string)\
\
folder (string)\
\
file (string)\
\
content (string)\\u200b\\u200b\
\
FILE NAMING\
\
The file name will be provided at runtime via:\
\
file_name\
\
You must:\
\
Use it exactly as provided\
\
Respect its extension\
\
Not override or rename it\
\
Constraints:\
\
Do not hardcode any parameters\
\
Do not modify provided runtime values\
\
Only content is authored by you\
\
\\u200b\
\
VALIDATION BEFORE TOOL CALL\
\
You must verify before uploading:\
\
Content is complete and final\
\
Content matches required format (e.g., strict CSV when CSV is required)\
\
No extra commentary exists\
\
File is not empty\
\
File content is plain text\
\
File format matches the task specification\
\
If validation fails, you must correct the content before calling the tool.\
\
FINAL RESPONSE BEHAVIOR\
\
After the tool executes, your final response must contain only:\
\
Success or failure confirmation\
\
Uploaded file path\
\
Tool response\
\
Input for DI \\u200bGithub File Write Tool:\
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
    \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{repo_owner_false_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
    \
    \
    \
    \
    \
    \
    \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{branch_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{token_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      {{folder_string_true}}\
    \
    \
    \
    \
     \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{file_name_false_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
    \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{content_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \\u200b\\u200b\
\\u200b\\u200b\\u200b\\u200b\\u200b\\u200b\
\
\\u200b\\u200b\\u200b\\u200b\\u200b\\u200b\
\
file_content: the generated CSV text\
\
The agent must not skip the tool call.\\u200b\\u200b\", \"expectedOutput\": \"1. Metadata Comparison Score Summary\
2. Workflow-Level Comparison \
3. Governance & Metadata Additions (New in AAVA 2.0)\
4. Workflow Configuration Changes\
5. Agent Inventory Summary\
\\u200b6. Agent Configuration Differences\"}, \"llm\": {\"model\": \"bedrock/us.anthropic.claude-sonnet-4-20250514-v1:0\", \"temperature\": 0.5, \"top_p\": 0.9, \"max_tokens\": 64000, \"aws_region_name\": \"us-east-1\", \"aws_access_key_id\": \"AKIAUXDEZTR4HES6ETDY\", \"aws_secret_access_key\": \"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\"}, \"modelDetails\": {\"modelId\": 495, \"modelDeploymentName\": \"anthropic.claude-4-sonnet\", \"model\": \"us.anthropic.claude-sonnet-4-20250514-v1:0\", \"modelType\": \"Generative\", \"aiEngine\": \"AmazonBedrock\", \"awsId\": \"58\", \"bedrockModelId\": \"us.anthropic.claude-sonnet-4-20250514-v1:0\", \"awsAccessKey\": \"QUtJQVVYREVaVFI0SEVTNkVURFk=\", \"awsSecretKey\": \"<REDACTED_SECRET>==\", \"awsRegion\": \"us-east-1\"}, \"modelDetailsEmbedding\": [], \"tools\": [], \"userTools\": [{\"toolId\": 3515, \"toolName\": \"DI Github File Write\", \"toolClassName\": \"GitHubFileWriterTool\", \"toolClassDef\": \"from crewai.tools import BaseTool\\r\
from pydantic import BaseModel, Field\\r\
import base64\\r\
import requests\\r\
import urllib3\\r\
import logging\\r\
import re\\r\
from typing import Type, Any\\r\
\\r\
# ---------------------------------\\r\
# SSL & Logging Configuration\\r\
# ---------------------------------\\r\
urllib3.disable_warnings(urllib3.exceptions.InsecureRequestWarning)\\r\
\\r\
logging.basicConfig(\\r\
    level=logging.INFO,\\r\
    format=\\\"%(asctime)s - %(name)s - %(levelname)s - %(message)s\\\",\\r\
    filename=\\\"github_file_writer.log\\\",\\r\
)\\r\
logger = logging.getLogger(\\\"GitHubFileWriterTool\\\")\\r\
\\r\
\\r\
# ---------------------------------\\r\
# Input Schema\\r\
# ---------------------------------\\r\
class GitHubFileWriterSchema(BaseModel):\\r\
    repo: str = Field(..., description=\\\"GitHub repository in 'owner/repo' format\\\")\\r\
    branch: str = Field(..., description=\\\"Branch name (e.g., 'main')\\\")\\r\
    token: str = Field(..., description=\\\"GitHub Personal Access Token\\\")\\r\
    folder_name: str = Field(..., description=\\\"Base folder path in repository (example: Metadata/comp)\\\")\\r\
    file_name: str = Field(..., description=\\\"File name OR file path inside folder (example: wf1/output.csv)\\\")\\r\
    content: str = Field(..., description=\\\"Text content to upload into the GitHub file\\\")\\r\
\\r\
\\r\
# ---------------------------------\\r\
# Main Tool Class\\r\
# ---------------------------------\\r\
class GitHubFileWriterTool(BaseTool):\\r\
    name: str = \\\"GitHub File Writer Tool\\\"\\r\
    description: str = \\\"Creates or updates files in a GitHub repository folder\\\"\\r\
    args_schema: Type[BaseModel] = GitHubFileWriterSchema\\r\
\\r\
    api_url_template: str = \\\"https://api.github.com/repos/{repo}/contents/{path}\\\"\\r\
\\r\
    def _sanitize_folder(self, folder: str) -> str:\\r\
        \\\"\\\"\\\"\\r\
        Sanitize folder path but keep forward slashes.\\r\
        \\\"\\\"\\\"\\r\
        folder = folder.replace(\\\"\\\\\\\\\\\", \\\"/\\\")\\r\
        folder = re.sub(r\\\"\\\\.\\\\.\\\", \\\"_\\\", folder)\\r\
        folder = folder.strip(\\\"/\\\")\\r\
\\r\
        # Replace invalid characters except \\\"/\\\"\\r\
        folder = re.sub(r'[*?:\\\"<>|]', \\\"_\\\", folder)\\r\
\\r\
        return folder if folder else \\\"default\\\"\\r\
\\r\
    def _sanitize_file_path(self, file_path: str) -> str:\\r\
        \\\"\\\"\\\"\\r\
        Sanitize file path but allow nested folders.\\r\
        Example: wf1/output.csv should remain wf1/output.csv\\r\
        \\\"\\\"\\\"\\r\
        file_path = file_path.replace(\\\"\\\\\\\\\\\", \\\"/\\\")\\r\
        file_path = re.sub(r\\\"\\\\.\\\\.\\\", \\\"_\\\", file_path)\\r\
        file_path = file_path.strip(\\\"/\\\")\\r\
\\r\
        # Replace invalid characters except \\\"/\\\"\\r\
        file_path = re.sub(r'[*?:\\\"<>|]', \\\"_\\\", file_path)\\r\
\\r\
        return file_path if file_path else \\\"default.txt\\\"\\r\
\\r\
    def _validate_content(self, content: str) -> str:\\r\
        \\\"\\\"\\\"Ensure valid string content within 10MB limit.\\\"\\\"\\\"\\r\
        if not isinstance(content, str):\\r\
            logger.warning(\\\"Content is not a string. Converting to string.\\\")\\r\
            content = str(content)\\r\
\\r\
        max_size = 10 * 1024 * 1024  # 10 MB\\r\
        if len(content.encode(\\\"utf-8\\\")) > max_size:\\r\
            logger.warning(\\\"Content exceeds 10MB limit. Truncating.\\\")\\r\
            content = content.encode(\\\"utf-8\\\")[:max_size].decode(\\\"utf-8\\\", errors=\\\"ignore\\\")\\r\
\\r\
        return content\\r\
\\r\
    def create_file_in_github(\\r\
        self,\\r\
        repo: str,\\r\
        branch: str,\\r\
        token: str,\\r\
        folder_name: str,\\r\
        file_name: str,\\r\
        content: str,\\r\
    ) -> str:\\r\
        \\\"\\\"\\\"Create or update a file in GitHub repository.\\\"\\\"\\\"\\r\
        sanitized_folder = self._sanitize_folder(folder_name)\\r\
        sanitized_file = self._sanitize_file_path(file_name)\\r\
        validated_content = self._validate_content(content)\\r\
\\r\
        full_path = f\\\"{sanitized_folder}/{sanitized_file}\\\"\\r\
\\r\
        url = self.api_url_template.format(repo=repo, path=full_path)\\r\
\\r\
        headers = {\\r\
            \\\"Authorization\\\": f\\\"token {token}\\\",\\r\
            \\\"Content-Type\\\": \\\"application/json\\\",\\r\
        }\\r\
\\r\
        encoded_content = base64.b64encode(validated_content.encode(\\\"utf-8\\\")).decode(\\\"utf-8\\\")\\r\
\\r\
        # Check file existence to get SHA (needed for update)\\r\
        sha = None\\r\
        try:\\r\
            response = requests.get(url, headers=headers, params={\\\"ref\\\": branch}, verify=False)\\r\
\\r\
            if response.status_code == 200:\\r\
                sha = response.json().get(\\\"sha\\\")\\r\
                logger.info(f\\\"File exists. Updating: {full_path}\\\")\\r\
            elif response.status_code == 404:\\r\
                logger.info(f\\\"File does not exist. Creating new: {full_path}\\\")\\r\
            else:\\r\
                logger.warning(f\\\"Unexpected status while checking file: {response.status_code} {response.text}\\\")\\r\
\\r\
        except Exception as e:\\r\
            logger.error(f\\\"Failed to check file existence: {e}\\\", exc_info=True)\\r\
\\r\
        payload = {\\r\
            \\\"message\\\": f\\\"Add or update file: {sanitized_file}\\\",\\r\
            \\\"content\\\": encoded_content,\\r\
            \\\"branch\\\": branch,\\r\
        }\\r\
\\r\
        if sha:\\r\
            payload[\\\"sha\\\"] = sha\\r\
\\r\
        # Upload / Update\\r\
        try:\\r\
            put_response = requests.put(url, json=payload, headers=headers, verify=False)\\r\
\\r\
            if put_response.status_code in [200, 201]:\\r\
                logger.info(f\\\"\\u2705 File uploaded successfully: {full_path}\\\")\\r\
                return f\\\"\\u2705 File uploaded successfully to GitHub: {full_path}\\\"\\r\
\\r\
            logger.error(f\\\"GitHub API Error: {put_response.status_code} {put_response.text}\\\")\\r\
            return f\\\"\\u274c Failed to upload file. GitHub API error: {put_response.text}\\\"\\r\
\\r\
        except Exception as e:\\r\
            logger.error(f\\\"Failed to upload file: {e}\\\", exc_info=True)\\r\
            return f\\\"\\u274c Exception while uploading file: {str(e)}\\\"\\r\
\\r\
    # ------------------------------------------------------\\r\
    # Required method for CrewAI Tool execution\\r\
    # ------------------------------------------------------\\r\
    def _run(\\r\
        self,\\r\
        repo: str,\\r\
        branch: str,\\r\
        token: str,\\r\
        folder_name: str,\\r\
        file_name: str,\\r\
        content: str,\\r\
    ) -> Any:\\r\
        return self.create_file_in_github(repo, branch, token, folder_name, file_name, content)\\r\
\\r\
\\r\
# ---------------------------------\\r\
# Manual Testing\\r\
# ---------------------------------\\r\
if __name__ == \\\"__main__\\\":\\r\
    print(\\\"\\ud83d\\udd27 GitHub File Writer Tool - Interactive Mode\\\
\\\")\\r\
    repo = input(\\\"Enter GitHub repository (owner/repo): \\\").strip()\\r\
    branch = input(\\\"Enter branch name (e.g., main): \\\").strip()\\r\
    token = input(\\\"Enter your GitHub Personal Access Token: \\\").strip()\\r\
    folder_name = input(\\\"Enter folder name: \\\").strip()\\r\
    file_name = input(\\\"Enter file name (example: wf1/output.csv): \\\").strip()\\r\
\\r\
    print(\\\"\\\
Enter the content for your file (end with a blank line):\\\")\\r\
    lines = []\\r\
    while True:\\r\
        line = input()\\r\
        if line == \\\"\\\":\\r\
            break\\r\
        lines.append(line)\\r\
\\r\
    content = \\\"\\\
\\\".join(lines)\\r\
\\r\
    tool = GitHubFileWriterTool()\\r\
    result = tool._run(\\r\
        repo=repo,\\r\
        branch=branch,\\r\
        token=token,\\r\
        folder_name=folder_name,\\r\
        file_name=file_name,\\r\
        content=content,\\r\
    )\\r\
    print(\\\"\\\
Result:\\\", result)\\r\
\"}], \"agentConfigs\": {\"temperature\": 0.5, \"topP\": 0.9, \"maxIter\": 10, \"maxRpm\": 20, \"maxExecutionTime\": 1977, \"allowDelegation\": false, \"allowCodeExecution\": false, \"modelRef\": [{\"modelId\": 495, \"modelDeploymentName\": \"anthropic.claude-4-sonnet\", \"model\": \"us.anthropic.claude-sonnet-4-20250514-v1:0\", \"modelType\": \"Generative\", \"aiEngine\": \"AmazonBedrock\"}], \"knowledgeBaseRef\": [], \"toolRef\": [], \"userToolRef\": [{\"toolId\": 3515, \"toolName\": \"DI Github File Write\", \"toolClassName\": \"GitHubFileWriterTool\", \"toolClassDef\": \"from crewai.tools import BaseTool\\r\
from pydantic import BaseModel, Field\\r\
import base64\\r\
import requests\\r\
import urllib3\\r\
import logging\\r\
import re\\r\
from typing import Type, Any\\r\
\\r\
# ---------------------------------\\r\
# SSL & Logging Configuration\\r\
# ---------------------------------\\r\
urllib3.disable_warnings(urllib3.exceptions.InsecureRequestWarning)\\r\
\\r\
logging.basicConfig(\\r\
    level=logging.INFO,\\r\
    format=\\\"%(asctime)s - %(name)s - %(levelname)s - %(message)s\\\",\\r\
    filename=\\\"github_file_writer.log\\\",\\r\
)\\r\
logger = logging.getLogger(\\\"GitHubFileWriterTool\\\")\\r\
\\r\
\\r\
# ---------------------------------\\r\
# Input Schema\\r\
# ---------------------------------\\r\
class GitHubFileWriterSchema(BaseModel):\\r\
    repo: str = Field(..., description=\\\"GitHub repository in 'owner/repo' format\\\")\\r\
    branch: str = Field(..., description=\\\"Branch name (e.g., 'main')\\\")\\r\
    token: str = Field(..., description=\\\"GitHub Personal Access Token\\\")\\r\
    folder_name: str = Field(..., description=\\\"Base folder path in repository (example: Metadata/comp)\\\")\\r\
    file_name: str = Field(..., description=\\\"File name OR file path inside folder (example: wf1/output.csv)\\\")\\r\
    content: str = Field(..., description=\\\"Text content to upload into the GitHub file\\\")\\r\
\\r\
\\r\
# ---------------------------------\\r\
# Main Tool Class\\r\
# ---------------------------------\\r\
class GitHubFileWriterTool(BaseTool):\\r\
    name: str = \\\"GitHub File Writer Tool\\\"\\r\
    description: str = \\\"Creates or updates files in a GitHub repository folder\\\"\\r\
    args_schema: Type[BaseModel] = GitHubFileWriterSchema\\r\
\\r\
    api_url_template: str = \\\"https://api.github.com/repos/{repo}/contents/{path}\\\"\\r\
\\r\
    def _sanitize_folder(self, folder: str) -> str:\\r\
        \\\"\\\"\\\"\\r\
        Sanitize folder path but keep forward slashes.\\r\
        \\\"\\\"\\\"\\r\
        folder = folder.replace(\\\"\\\\\\\\\\\", \\\"/\\\")\\r\
        folder = re.sub(r\\\"\\\\.\\\\.\\\", \\\"_\\\", folder)\\r\
        folder = folder.strip(\\\"/\\\")\\r\
\\r\
        # Replace invalid characters except \\\"/\\\"\\r\
        folder = re.sub(r'[*?:\\\"<>|]', \\\"_\\\", folder)\\r\
\\r\
        return folder if folder else \\\"default\\\"\\r\
\\r\
    def _sanitize_file_path(self, file_path: str) -> str:\\r\
        \\\"\\\"\\\"\\r\
        Sanitize file path but allow nested folders.\\r\
        Example: wf1/output.csv should remain wf1/output.csv\\r\
        \\\"\\\"\\\"\\r\
        file_path = file_path.replace(\\\"\\\\\\\\\\\", \\\"/\\\")\\r\
        file_path = re.sub(r\\\"\\\\.\\\\.\\\", \\\"_\\\", file_path)\\r\
        file_path = file_path.strip(\\\"/\\\")\\r\
\\r\
        # Replace invalid characters except \\\"/\\\"\\r\
        file_path = re.sub(r'[*?:\\\"<>|]', \\\"_\\\", file_path)\\r\
\\r\
        return file_path if file_path else \\\"default.txt\\\"\\r\
\\r\
    def _validate_content(self, content: str) -> str:\\r\
        \\\"\\\"\\\"Ensure valid string content within 10MB limit.\\\"\\\"\\\"\\r\
        if not isinstance(content, str):\\r\
            logger.warning(\\\"Content is not a string. Converting to string.\\\")\\r\
            content = str(content)\\r\
\\r\
        max_size = 10 * 1024 * 1024  # 10 MB\\r\
        if len(content.encode(\\\"utf-8\\\")) > max_size:\\r\
            logger.warning(\\\"Content exceeds 10MB limit. Truncating.\\\")\\r\
            content = content.encode(\\\"utf-8\\\")[:max_size].decode(\\\"utf-8\\\", errors=\\\"ignore\\\")\\r\
\\r\
        return content\\r\
\\r\
    def create_file_in_github(\\r\
        self,\\r\
        repo: str,\\r\
        branch: str,\\r\
        token: str,\\r\
        folder_name: str,\\r\
        file_name: str,\\r\
        content: str,\\r\
    ) -> str:\\r\
        \\\"\\\"\\\"Create or update a file in GitHub repository.\\\"\\\"\\\"\\r\
        sanitized_folder = self._sanitize_folder(folder_name)\\r\
        sanitized_file = self._sanitize_file_path(file_name)\\r\
        validated_content = self._validate_content(content)\\r\
\\r\
        full_path = f\\\"{sanitized_folder}/{sanitized_file}\\\"\\r\
\\r\
        url = self.api_url_template.format(repo=repo, path=full_path)\\r\
\\r\
        headers = {\\r\
            \\\"Authorization\\\": f\\\"token {token}\\\",\\r\
            \\\"Content-Type\\\": \\\"application/json\\\",\\r\
        }\\r\
\\r\
        encoded_content = base64.b64encode(validated_content.encode(\\\"utf-8\\\")).decode(\\\"utf-8\\\")\\r\
\\r\
        # Check file existence to get SHA (needed for update)\\r\
        sha = None\\r\
        try:\\r\
            response = requests.get(url, headers=headers, params={\\\"ref\\\": branch}, verify=False)\\r\
\\r\
            if response.status_code == 200:\\r\
                sha = response.json().get(\\\"sha\\\")\\r\
                logger.info(f\\\"File exists. Updating: {full_path}\\\")\\r\
            elif response.status_code == 404:\\r\
                logger.info(f\\\"File does not exist. Creating new: {full_path}\\\")\\r\
            else:\\r\
                logger.warning(f\\\"Unexpected status while checking file: {response.status_code} {response.text}\\\")\\r\
\\r\
        except Exception as e:\\r\
            logger.error(f\\\"Failed to check file existence: {e}\\\", exc_info=True)\\r\
\\r\
        payload = {\\r\
            \\\"message\\\": f\\\"Add or update file: {sanitized_file}\\\",\\r\
            \\\"content\\\": encoded_content,\\r\
            \\\"branch\\\": branch,\\r\
        }\\r\
\\r\
        if sha:\\r\
            payload[\\\"sha\\\"] = sha\\r\
\\r\
        # Upload / Update\\r\
        try:\\r\
            put_response = requests.put(url, json=payload, headers=headers, verify=False)\\r\
\\r\
            if put_response.status_code in [200, 201]:\\r\
                logger.info(f\\\"\\u2705 File uploaded successfully: {full_path}\\\")\\r\
                return f\\\"\\u2705 File uploaded successfully to GitHub: {full_path}\\\"\\r\
\\r\
            logger.error(f\\\"GitHub API Error: {put_response.status_code} {put_response.text}\\\")\\r\
            return f\\\"\\u274c Failed to upload file. GitHub API error: {put_response.text}\\\"\\r\
\\r\
        except Exception as e:\\r\
            logger.error(f\\\"Failed to upload file: {e}\\\", exc_info=True)\\r\
            return f\\\"\\u274c Exception while uploading file: {str(e)}\\\"\\r\
\\r\
    # ------------------------------------------------------\\r\
    # Required method for CrewAI Tool execution\\r\
    # ------------------------------------------------------\\r\
    def _run(\\r\
        self,\\r\
        repo: str,\\r\
        branch: str,\\r\
        token: str,\\r\
        folder_name: str,\\r\
        file_name: str,\\r\
        content: str,\\r\
    ) -> Any:\\r\
        return self.create_file_in_github(repo, branch, token, folder_name, file_name, content)\\r\
\\r\
\\r\
# ---------------------------------\\r\
# Manual Testing\\r\
# ---------------------------------\\r\
if __name__ == \\\"__main__\\\":\\r\
    print(\\\"\\ud83d\\udd27 GitHub File Writer Tool - Interactive Mode\\\
\\\")\\r\
    repo = input(\\\"Enter GitHub repository (owner/repo): \\\").strip()\\r\
    branch = input(\\\"Enter branch name (e.g., main): \\\").strip()\\r\
    token = input(\\\"Enter your GitHub Personal Access Token: \\\").strip()\\r\
    folder_name = input(\\\"Enter folder name: \\\").strip()\\r\
    file_name = input(\\\"Enter file name (example: wf1/output.csv): \\\").strip()\\r\
\\r\
    print(\\\"\\\
Enter the content for your file (end with a blank line):\\\")\\r\
    lines = []\\r\
    while True:\\r\
        line = input()\\r\
        if line == \\\"\\\":\\r\
            break\\r\
        lines.append(line)\\r\
\\r\
    content = \\\"\\\
\\\".join(lines)\\r\
\\r\
    tool = GitHubFileWriterTool()\\r\
    result = tool._run(\\r\
        repo=repo,\\r\
        branch=branch,\\r\
        token=token,\\r\
        folder_name=folder_name,\\r\
        file_name=file_name,\\r\
        content=content,\\r\
    )\\r\
    print(\\\"\\\
Result:\\\", result)\\r\
\"}], \"isSafeCodeExecution\": false}, \"allowCodeExecution\": false, \"allowDelegation\": false, \"verbose\": true, \"maxIter\": 10, \"maxRpm\": 20, \"maxExecutionTime\": 1977, \"temperature\": 0.5, \"topP\": 0.9, \"safeCodeExecution\": false, \"isSafeCodeExecution\": false, \"useSystemPrompt\": true, \"rag_mode\": \"STRICT\", \"nemo_guardrails\": false}}], \"langfuse\": {\"langfuseHost\": \"https://aava-metrics-int.avateam.io\", \"langfusePublicKey\": \"pk-lf-25010646-27f5-45f8-b9c1-033c6571ce3e\", \"langfuseSecretKey\": \"sk-lf-3ae900ba-7546-43a6-9303-40f4ff1412c9\"}}}",
      "user": "harish.kumaresan@ascendion.com",
      "workflow_execution": "{\"workflow_name\": \"DI AAVA METADATA COMPARISON REPORT GENERATOR\", \"pipeline_name\": \"DI AAVA METADATA COMPARISON REPORT GENERATOR\", \"execution_id\": \"783caca6-e70b-4f28-a922-84d2d9fb6087\", \"workflow_id\": 9727, \"user\": \"harish.kumaresan@ascendion.com\", \"timestamp\": \"2026-02-16T16:48:29.526346\", \"agents\": [{\"agent_id\": 20483, \"agent_name\": \"DI AAVA METADATA COMPARISON REPORT GENERATOR\", \"agent_role\": \"Senior Quality Engineering Comparison and Validation Agent\", \"agent_goal\": \"The goal of this evaluator agent is to produce a rigorous, objective, and auditable comparison report between two versions of metadata:\
\
AAVA 1.0 Metadata (JSON)\
\
AAVA 2.0 Metadata (JSON)\
\
The agent must determine how closely AAVA 2.0 preserves, evolves, or deviates from AAVA 1.0 across meaning, structure, and internal consistency.\
The output must be suitable for engineering review, data governance validation, and schema evolution assessment.\", \"tools\": [], \"knowledge_bases\": [], \"task\": {\"description\": \"Take two seperate authoritative inputs:\
\
Agent Input 1:\
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{aava1_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \\u200b\\u200b\
\
\\u00a0AAVA 1.0 Metadata\
\
Agent Input 2:\
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{aava2_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \\u200b\
\
\\u00a0AAVA 2.0 Metadata\
\
They represent different versions of the same workflow system.\
\
You are a Metadata Comparison Analyst.\
\
Compare AAVA 1.0 vs AAVA 2.0 metadata JSONs and produce a crisp migration comparison report.\
\
Always include Migration Impact and Action Required columns.\
\
Keep the output concise and business-readable.\
\
---\
\
# Comparison Normalization Rule (Strict)\
\
Before comparing values, normalize strings using:\
\
* trim spaces\
\
* convert to lowercase\
\
* remove minor formatting differences\
\
If values match after normalization, mark them as: **Matched (Normalized)** instead of Modified.\
\
Do not classify case-only differences (uppercase/lowercase) as Modified.\
\
Instead classify them as: **Matched (Case Normalization)**.\
\
---\
\
# 0. Authoritative Field Mapping Reference (MANDATORY)\
\
Use the following mapping tables as the **only source of truth** for field-level mapping between AAVA 1.0 and AAVA 2.0.\
\
Do NOT infer mappings beyond this table unless explicitly stated.\
\
If a field does not exist in the mapping table, classify it as:\
\
* **New** (2.0 only)\
\
* **Removed** (1.0 only)\
\
---\
\
## 0.1 Workflow-Level Field Mapping Table (AAVA 1.0 \\u2192 AAVA 2.0)\
\
| Workflow Category           | AAVA 1.0 Field                                                                  | AAVA 2.0 Field  | Mapping Type |\
\
| --------------------------- | ------------------------------------------------------------------------------- | --------------- | ------------ |\
\
| Identifier                  | pipelineId                                                                      | id              | Renamed      |\
\
| Naming                      | name                                                                            | name            | Matched      |\
\
| Description                 | description                                                                     | description     | Matched      |\
\
| Audit                       | createdAt                                                                       | createdAt       | Matched      |\
\
| Agents List                 | pipeLineAgents                                                                  | workflowAgents  | Renamed      |\
\
| Workflow Config             | callbacks                                                                       | workflowConfigs | Renamed      |\
\
| Memory Config               | enableAgenticMemory                                                             | Not Available   | Removed      |\
\
| Org/Domain/Project Metadata | org / orgId / domain / domainId / project / projectId / team / teamId / levelId | Not Available   | Removed      |\
\
---\
\
## 0.2 Agent-Level Field Mapping Table (AAVA 1.0 \\u2192 AAVA 2.0)\
\
### Agent Wrapper Level Mapping\
\
| Agent Category   | AAVA 1.0 Field                | AAVA 2.0 Field      | Mapping Type |\
\
| ---------------- | ----------------------------- | ------------------- | ------------ |\
\
| Identifier       | agent.id                      | agentId             | Renamed      |\
\
| Ordering         | serial                        | serial              | Matched      |\
\
| Naming           | agent.name                    | name                | Renamed      |\
\
| Task Description | agent.task.description        | description         | Renamed      |\
\
| Model Deployment | agent.llm.modelDeploymentName | modelDeploymentName | Renamed      |\
\
| Model Name       | agent.llm.modelName           | modelName           | Renamed      |\
\
---\
\
### Agent Details Mapping (agent \\u2192 agentDetails)\
\
| Category        | AAVA 1.0 Field      | AAVA 2.0 Field       | Mapping Type |\
\
| --------------- | ------------------- | -------------------- | ------------ |\
\
| Delegation      | allowDelegation     | allowDelegation      | Matched      |\
\
| Code Exec       | allowCodeExecution  | allowCodeExecution   | Matched      |\
\
| Safe Exec       | isSafeCodeExecution | isSafeCodeExecution  | Matched      |\
\
| Iterations      | maxIter             | maxIter              | Matched      |\
\
| Rate Limit      | maxRpm              | maxRpm               | Matched      |\
\
| Timeout         | maxExecutionTime    | maxExecutionTime     | Matched      |\
\
| Temperature     | llm.temperature     | temperature          | Renamed      |\
\
| TopP            | llm.topP            | topP                 | Renamed      |\
\
| Tools           | tools               | toolReferences       | Renamed      |\
\
| User Tools      | userTools           | toolReferences       | Renamed      |\
\
| Expected Output | task.expectedOutput | expectedOutputFormat | Renamed      |\
\
---\
\
### Explicitly Removed / Not Present in AAVA 2.0\
\
| AAVA 1.0 Field | AAVA 2.0 Field |\
\
| -------------- | -------------- |\
\
| role           | Not Available  |\
\
| goal           | Not Available  |\
\
| backstory      | Not Available  |\
\
| verbose        | Not Available  |\
\
| updatedAt      | Not Available  |\
\
---\
\
### Explicitly New in AAVA 2.0\
\
| AAVA 2.0 Field | AAVA 1.0 Field |\
\
| -------------- | -------------- |\
\
| preset         | Not Available  |\
\
| guardrailIds   | Not Available  |\
\
| workflowId     | Not Available  |\
\
---\
\
## 0.3 Mandatory Mapping Enforcement Rule\
\
If mapping exists in the table \\u2192 compare values strictly using normalization rules.\
\
If no mapping exists \\u2192 do not assume semantic equivalence.\
\
If field exists only in 2.0 \\u2192 classify as **New**.\
\
If field exists only in 1.0 \\u2192 classify as **Removed**.\
\
---\
\
# 0.4 Presence Detection Rule (Authoritative) (MANDATORY)\
\
When generating tables, you MUST evaluate whether a field is present using the **correct JSON path** below.\
\
You MUST NOT check incorrect locations such as `agent.description` in AAVA 1.0.\
\
If the field exists at the correct mapped source path \\u2192 mark it as **Present**.\
\
If the field is missing or null \\u2192 mark it as **Not Present**.\
\
---\
\
## 0.4.1 Workflow-Level Presence Detection Paths\
\
| Logical Field       | AAVA 1.0 Presence Path | AAVA 2.0 Presence Path |\
\
| ------------------- | ---------------------- | ---------------------- |\
\
| workflowId          | pipelineId             | id                     |\
\
| workflowName        | name                   | name                   |\
\
| workflowDescription | description            | description            |\
\
| createdAt           | createdAt              | createdAt              |\
\
| workflowAgents      | pipeLineAgents         | workflowAgents         |\
\
| workflowConfigs     | callbacks              | workflowConfigs        |\
\
| enableAgenticMemory | enableAgenticMemory    | Not Available          |\
\
| org                 | org                    | Not Available          |\
\
| orgId               | orgId                  | Not Available          |\
\
| domain              | domain                 | Not Available          |\
\
| domainId            | domainId               | Not Available          |\
\
| project             | project                | Not Available          |\
\
| projectId           | projectId              | Not Available          |\
\
| team                | team                   | Not Available          |\
\
| teamId              | teamId                 | Not Available          |\
\
| levelId             | levelId                | Not Available          |\
\
---\
\
## 0.4.2 Agent-Level Presence Detection Paths\
\
### Agent Wrapper Identity Fields\
\
| Logical Field              | AAVA 1.0 Presence Path      | AAVA 2.0 Presence Path      |\
\
| -------------------------- | --------------------------- | --------------------------- |\
\
| agentId                    | pipeLineAgents[].agent.id   | workflowAgents[].agentId    |\
\
| agentName                  | pipeLineAgents[].agent.name | workflowAgents[].name       |\
\
| serial                     | pipeLineAgents[].serial     | workflowAgents[].serial     |\
\
| workflowId (agent linkage) | Not Available               | workflowAgents[].workflowId |\
\
---\
\
### Agent Instruction Fields (CRITICAL)\
\
| Logical Field  | AAVA 1.0 Presence Path                     | AAVA 2.0 Presence Path                             |\
\
| -------------- | ------------------------------------------ | -------------------------------------------------- |\
\
| role           | pipeLineAgents[].agent.role                | Not Available                                      |\
\
| goal           | pipeLineAgents[].agent.goal                | Not Available                                      |\
\
| backstory      | pipeLineAgents[].agent.backstory           | Not Available                                      |\
\
| description    | pipeLineAgents[].agent.task.description    | workflowAgents[].description                       |\
\
| expectedOutput | pipeLineAgents[].agent.task.expectedOutput | workflowAgents[].agentDetails.expectedOutputFormat |\
\
---\
\
### LLM + Runtime Fields\
\
| Logical Field       | AAVA 1.0 Presence Path                         | AAVA 2.0 Presence Path                            |\
\
| ------------------- | ---------------------------------------------- | ------------------------------------------------- |\
\
| modelDeploymentName | pipeLineAgents[].agent.llm.modelDeploymentName | workflowAgents[].modelDeploymentName              |\
\
| model               | pipeLineAgents[].agent.llm.modelName           | workflowAgents[].modelName                        |\
\
| temperature         | pipeLineAgents[].agent.llm.temperature         | workflowAgents[].agentDetails.temperature         |\
\
| topP                | pipeLineAgents[].agent.llm.topP                | workflowAgents[].agentDetails.topP                |\
\
| maxToken            | pipeLineAgents[].agent.llm.maxToken            | Not Available unless explicitly present           |\
\
| maxIter             | pipeLineAgents[].agent.maxIter                 | workflowAgents[].agentDetails.maxIter             |\
\
| maxRpm              | pipeLineAgents[].agent.maxRpm                  | workflowAgents[].agentDetails.maxRpm              |\
\
| maxExecutionTime    | pipeLineAgents[].agent.maxExecutionTime        | workflowAgents[].agentDetails.maxExecutionTime    |\
\
| allowDelegation     | pipeLineAgents[].agent.allowDelegation         | workflowAgents[].agentDetails.allowDelegation     |\
\
| allowCodeExecution  | pipeLineAgents[].agent.allowCodeExecution      | workflowAgents[].agentDetails.allowCodeExecution  |\
\
| isSafeCodeExecution | pipeLineAgents[].agent.isSafeCodeExecution     | workflowAgents[].agentDetails.isSafeCodeExecution |\
\
---\
\
### Tools Fields\
\
| Logical Field | AAVA 1.0 Presence Path           | AAVA 2.0 Presence Path                       |\
\
| ------------- | -------------------------------- | -------------------------------------------- |\
\
| tools         | pipeLineAgents[].agent.tools     | workflowAgents[].agentDetails.toolReferences |\
\
| userTools     | pipeLineAgents[].agent.userTools | workflowAgents[].agentDetails.toolReferences |\
\
---\
\
### Guardrails Fields\
\
| Logical Field | AAVA 1.0 Presence Path            | AAVA 2.0 Presence Path                     |\
\
| ------------- | --------------------------------- | ------------------------------------------ |\
\
| guardrails    | pipeLineAgents[].agent.guardrails | workflowAgents[].agentDetails.guardrailIds |\
\
---\
\
# AAVA 1.0 vs AAVA 2.0 Metadata Comparison Report\
\
---\
\
# 1. Metadata Comparison Scoring (MANDATORY \\u2013 Must Appear at Top of Report)\
\
Before generating any comparison tables or agent-level diffs, you MUST compute a Metadata Comparison Score.\
\
### Scoring Objective\
\
The score represents how closely AAVA 2.0 matches AAVA 1.0 across all agents in the workflow, based on configuration, metadata, and LLM behavior readiness.\
\
### Scoring Rules (Strict)\
\
Agent-level scoring is mandatory for every agent found in either AAVA 1.0 or AAVA 2.0.\
\
Agent scoring must compare all relevant agent attributes, including role, goal, backstory, description, expectedOutput, LLM/model configuration, tools, knowledge base settings, and guardrails.\
\
Include all of the following in scoring:\
\
* role\
\
* goal\
\
* backstory\
\
* description\
\
* expectedOutput\
\
* agentId\
\
* modelDeploymentName\
\
* model\
\
* temperature\
\
* maxToken\
\
* topP\
\
* maxIter\
\
* maxRpm\
\
* maxExecutionTime\
\
* allowDelegation\
\
* tools / tool configs (if present)\
\
* workflowConfigs / llm manager configs (if agent-specific)\
\
---\
\
## EXTENDED SCORING COVERAGE (MANDATORY)\
\
Agent scoring MUST also include comparison of the following categories if present in metadata:\
\
* tools (tool list, tool configs, tool permissions, tool parameters)\
\
* knowledgeBase / knowledgeSources (KB IDs, KB names, retrieval configs, embedding configs, chunking settings)\
\
* guardrails (safety rules, moderation settings, policy enforcement flags, blocked topics)\
\
* memory configs (if applicable)\
\
* system prompts / instruction templates (if applicable)\
\
* input/output schema constraints (if applicable)\
\
These fields must be treated as high-impact scoring fields, meaning any Modified / Removed result should be flagged as Migration Impact = High in the scoring explanation.\
\
---\
\
### Apply the Normalization Rule before comparison:\
\
* trim spaces\
\
* convert to lowercase\
\
* remove minor formatting differences\
\
If matched after normalization \\u2192 treat as **Matched (Normalized)**.\
\
Case-only differences \\u2192 treat as **Matched (Case Normalization)**.\
\
---\
\
## Scoring per field\
\
Each field contributes equally unless missing.\
\
| Comparison Result                                             | Score |\
\
| ------------------------------------------------------------- | ----- |\
\
| Matched / Matched (Normalized) / Matched (Case Normalization) | 1.0   |\
\
| Renamed (same meaning, confirmed mapping)                     | 0.8   |\
\
| Modified (semantic change)                                    | 0.4   |\
\
| New (only in AAVA 2.0)                                        | 0.6   |\
\
| Removed (missing in AAVA 2.0)                                 | 0.0   |\
\
---\
\
## Agent Score Calculation\
\
For each agent:\
\
Agent Score (%) = (Sum of field scores / Total compared fields) * 100\
\
Workflow Migration Compatibility Score (%) = Average of all Agent Scores (including agents added/removed)\
\
---\
\
## Missing Agent Handling\
\
* If an agent exists in AAVA 1.0 but not in AAVA 2.0 \\u2192 agent score = 0%\
\
* If an agent exists in AAVA 2.0 but not in AAVA 1.0 \\u2192 agent score = 60% (treated as \\\"New Agent Baseline\\\")\
\
---\
\
## Score Interpretation\
\
| Score Range | Rating    | Meaning                                      |\
\
| ----------- | --------- | -------------------------------------------- |\
\
| 90\\u2013100%     | Excellent | Ready for migration with minimal changes     |\
\
| 75\\u201389%      | Good      | Migration safe, moderate validation required |\
\
| 50\\u201374%      | Moderate  | Multiple config or logic gaps, needs fixes   |\
\
| <50%        | Poor      | High risk migration, major rework required   |\
\
---\
\
## Mandatory Output Format\
\
At the beginning of the TXT report, output this section:\
\
### 1. Metadata Comparison Score Summary\
\
* Workflow Comparison Score: XX%\
\
* Total Agents Compared: N\
\
| Agent Name | Agent Score | Risk Level | Key Score Drivers                   | Migration Action Required |\
\
| ---------- | ----------- | ---------- | ----------------------------------- | ------------------------- |\
\
|            | 92%         | Low        | model configs matched, role matched | None                      |\
\
|            | 61%         | Medium     | maxIter reduced, model changed      | Validate runtime behavior |\
\
---\
\
### Risk Level Rules\
\
* Low Risk = Agent Score >= 90%\
\
* Medium Risk = 50% to 89%\
\
* High Risk = < 50%\
\
---\
\
### Mandatory Behavior\
\
* Scoring MUST be computed before detailed diffs.\
\
* Scoring MUST be based only on actual comparisons between AAVA 1.0 and AAVA 2.0.\
\
* Do NOT invent values.\
\
* Do NOT skip any agent.\
\
* Score section MUST influence the final \\\"Overall Migration Risk\\\" at the end.\
\
---\
\
# 2. Workflow-Level Comparison\
\
## Mandatory Header Requirement\
\
At the start of this section, you MUST display workflow names from both versions:\
\
Workflow Name (AAVA 1.0):\
\
Workflow Name (AAVA 2.0):\
\
If workflow name differs only by case/spacing \\u2192 classify as Matched (Normalized)\
\
---\
\
## Workflow-Level Comparison Rule (Value-Based Comparison Mandatory)\
\
Workflow Change Type Classification Rule (Strict)\
\
For workflow-level comparison, determine Change Type using the following logic:\
\
Step 1: Mapping Check\
\
If AAVA 1.0 field maps to a known AAVA 2.0 field in the mapping table \\u2192 proceed to value comparison.\
\
If field exists only in AAVA 1.0 \\u2192 Change Type = Removed.\
\
If field exists only in AAVA 2.0 \\u2192 Change Type = New.\
\
Step 2: Value Comparison (MANDATORY)\
\
After applying normalization:\
\
If mapped fields exist in both versions:\
\
If values are equal after normalization \\u2192 Change Type = Matched (Normalized)\
\
If values differ \\u2192 Change Type = Modified\
\
If mapping type is Renamed AND values match after normalization \\u2192\
\
Change Type = Renamed + Matched (Normalized)\
\
If mapping type is Renamed AND values differ \\u2192\
\
Change Type = Renamed + Modified\
\
Step 3: Special Case\
\
If only field name changed but value changed too \\u2192 must be treated as Modified.\
\
If mapping type is Matched but values differ \\u2192 Change Type = Modified.\
\\u200b\\u200b\\u200b\
\
Updated Change Type Column Allowed Values (Strict)\
\
Only these are allowed:\
\
Matched\
\
Matched (Normalized)\
\
Matched (Case Normalization)\
\
Renamed + Matched (Normalized)\
\
Renamed + Modified\
\
Modified\
\
New\
\
Removed\
\
Mandatory Enforcement Line\\u00a0\
\
Do NOT output \\\"Renamed\\\" alone unless values are also compared.\
\
Renamed must always be combined with either:\
\
Renamed + Matched (Normalized)\
\
or\
\
Renamed + Modified\\u200b\\u200b\\u200b\\u200b\
\
### Workflow Output Table Format (Mandatory)\
\
| Category | AAVA 1.0 Field | AAVA 1.0 Value | AAVA 2.0 Field | AAVA 2.0 Value | Change Type | Description of Change | Migration Impact (Low/Medium/High) | Action Required |\
\
| -------- | -------------- | -------------- | -------------- | -------------- | -------------------------------------------------- | --------------------- | ---------------------------------- | --------------- |\
\
---\
\
# 3. Governance & Metadata Additions (New in AAVA 2.0)\
\
List newly introduced governance-related fields (example: createdBy, modifiedBy, approvedAt, status, isDeleted).\
\
| New Field | Purpose                 | Default/Observed Value | Migration Impact | Action Required                      |\
\
| --------- | ----------------------- | ---------------------- | ---------------- | ------------------------------------ |\
\
| status    | Workflow approval state | APPROVED               | Medium           | Ensure workflow lifecycle is handled |\
\
---\
\
# 4. Workflow Configuration Changes\
\
Summarize config differences such as workflowConfigs, managerLlm, temperature, maxToken, topP.\
\
| Config Area     | AAVA 1.0      | AAVA 2.0 | Impact | Action Required |\
\
| --------------- | ------------- | -------- | ------ | --------------- |\
\
| workflowConfigs | Not available | Present  | Medium | Align defaults  |\
\
---\
\
# 5. Agent Inventory Summary\
\
## 5.1 Agent Count & Coverage\
\
AAVA 1.0 total agents: X\
\
AAVA 2.0 total agents: Y\
\
Coverage: Same / Added / Removed agents\
\
---\
\
## 5.2 Agent Name Mapping\
\
| AAVA 1.0 Agent                 | AAVA 2.0 Agent                    | Match Type | Notes                     |\
\
| ------------------------------ | --------------------------------- | ---------- | ------------------------- |\
\
| DI_Token_Size_Estimator_S3_IMS | DI Token Size Estimator S3 IMS HP | Renamed    | Naming convention updated |\
\
---\
\
# 6. Agent Configuration Differences\\u00a0\
\
## Mandatory Output Structure Per Agent (ALL Agents Mandatory)\
\
For each agent (in the same order as inventory mapping), you MUST generate 5 sub-sections in the exact format below.\
\
If a section has no data in either AAVA 1.0 or AAVA 2.0, output Not Available.\
\
If no differences exist in a section, explicitly state: No differences found.\
\
---\
\
## Agent: \
\
---\
\
## 6.X.1 Agent Instructions Comparison\
\\u200b\
\
### Instruction Field Source Rule (MANDATORY)\
\
| Logical Field  | AAVA 1.0 Source Path                       | AAVA 2.0 Source Path                               |\
\
| -------------- | ------------------------------------------ | -------------------------------------------------- |\
\
| role           | pipeLineAgents[].agent.role                | Not Available                                      |\
\
| goal           | pipeLineAgents[].agent.goal                | Not Available                                      |\
\
| backstory      | pipeLineAgents[].agent.backstory           | Not Available                                      |\
\
| description    | pipeLineAgents[].agent.task.description    | workflowAgents[].description                       |\
\
| expectedOutput | pipeLineAgents[].agent.task.expectedOutput | workflowAgents[].agentDetails.expectedOutputFormat |\
\
All these fields should be mentioned in the table. If it is not there mention it as Not Available.\
\
Use the Authoritative Field Mapping Reference for this (Mandatory).\
\
Presence Output Rule (Strict)\
\
For this section ONLY:\
\
Do NOT print actual values.\
\
Output only Present or Not Present\
\
Present means the field exists at the authoritative path and is not null/empty.\
\
Not Present means missing, null, or empty.\\u200b\\u200b\\u200b\
\
---\
\
### Output Table Format (Mandatory)\
\
| Field | AAVA 1.0 Presence | AAVA 2.0 Presence | Migration Impact | Action Required |\
\
| ----- | ----------------- | ----------------- | ---------------- | --------------- |\
\
\\u200b\\u200b\\u200bMandatory Action Required Rule\
\
If field is Present in both \\u2192 Action Required = No change\
\
If field is Not Present in both \\u2192 Action Required = No change\
\
If Present in 1.0 but Not Present in 2.0 \\u2192 Action Required = Add missing field or confirm deprecation\
\
If Not Present in 1.0 but Present in 2.0 \\u2192 Action Required = Validate new instruction field behavior\
\
If AAVA 2.0 Source Path is \\\"Not Available\\\" (explicitly removed field) \\u2192 classify as Removed and Action Required = Confirm removal is acceptable\
\\u200b\
\
---\
\
## 6.X.2 LLM Configuration Comparison (Strict Mandatory Fields)\
\
You MUST compare all LLM-related and runtime fields including:\
\
* modelDeploymentName\
\
* model\
\
* temperature\
\
* topP\
\
* maxToken\
\
* maxIter\
\
* maxRpm\
\
* maxExecutionTime\
\
Also include any other LLM configs present (managerLlm, workflowConfigs overrides, etc.)\
\
---\
\
### Output Table Format (Mandatory)\
\
| Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |\
\
| ----- | -------------- | -------------- | ---------------- | --------------- |\
\
If no LLM config exists \\u2192 output: Not Available\
\
---\
\
## 6.X.3 Tools Comparison\
\
* If tools exist, list tool names and relevant tool configs.\
\
* If tools do not exist in metadata, explicitly output: Not Available\
\
* If tools exist in one version but not the other, classify as New or Removed accordingly.\
\
---\
\
### Output Table Format (Mandatory)\
\
| Tool Name / Tool Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |\
\
| ---------------------- | -------------- | -------------- | ---------------- | --------------- |\
\
If no differences but tools exist \\u2192 state: No differences found\
\
---\
\
## 6.X.4 Knowledge Base Comparison\
\
Compare KB-related metadata including:\
\
* knowledgeBase presence\
\
* KB IDs / names\
\
* retrieval configs\
\
* chunking / embedding configs (if present)\
\
If KB does not exist \\u2192 output: Not Available\
\
---\
\
### Output Table Format (Mandatory)\
\
| KB Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |\
\
| -------- | -------------- | -------------- | ---------------- | --------------- |\
\
---\
\
## 6.X.5 Guardrails Comparison\
\
Compare guardrails-related fields including:\
\
* safety rules\
\
* moderation configs\
\
* blocked topics\
\
* compliance flags\
\
* policy enforcement toggles\
\
If guardrails do not exist \\u2192 output: Not Available\
\
---\
\
### Output Table Format (Mandatory)\
\
| Guardrail Field | AAVA 1.0 Value | AAVA 2.0 Value | Migration Impact | Action Required |\
\
| --------------- | -------------- | -------------- | ---------------- | --------------- |\
\
---\
\
# Normalization Rule (Strict Enforcement)\
\
Before comparing any values in any section:\
\
* trim spaces\
\
* convert to lowercase\
\
* remove minor formatting differences\
\
If values match after normalization \\u2192 mark as Matched (Normalized)\
\
If values differ only by case \\u2192 mark as Matched (Case Normalization)\
\
---\
\
# Mandatory Handling Rules\
\
* Do NOT skip any agent.\
\
* Do NOT merge agents into one table.\
\
* Each agent MUST have all 5 sub-sections even if they contain \\\"Not Available\\\".\
\
* Every changed field must be listed (no top-5 filtering).\
\
* Always follow Authoritative Field Mapping Reference and Presence Detection Rules.\
\
* Never mark task.description as Not Available in AAVA 1.0 if it exists under pipeLineAgents[].agent.task.description.\
\
---\
\
\\u200b### Report Termination Rule (MANDATORY)\
\
The report MUST end immediately after the last agent\\u2019s section:\
\
6.X.5 Guardrails Comparison\
\
Do NOT generate:\
\
- Overall Migration Assessment\
\
- Critical Migration Issues\
\
- Recommended Migration Actions\
\
- Overall Migration Risk\
\
- Any additional narrative summary section\
\
\\u200b\
\
PRIMARY OUTPUT FORMAT \\u2014 TXT REPORT (MANDATORY)\
\
Your primary output must be a human-readable .txt report.\
\
SECONDARY OUTPUT (MANDATORY)\
\
After generating the TXT report, generate a CSV file_content with EXACTLY TWO TABLES.\
\
-------------------------\
\
TABLE 1: Workflow Summary\
\
-------------------------\
\
The first table must have this header EXACTLY:\
\
Workflow Comparison Score,Total Agents Compared\
\
The next row must contain the workflow score and agent count values.\
\
-------------------------\
\
TABLE 2: Agent Score Summary\
\
-------------------------\
\
After Table 1, insert exactly ONE blank line.\
\
Then output the second table with this header EXACTLY:\
\
Agent Name,Agent Score,Risk Level,Key Score Drivers,Migration Action Required\
\
Then output one row per agent.\
\
STRICT RULES: (Mandatory)\
\
- Do NOT include any other report sections in the CSV.\
\
- Do NOT include workflow-level diffs, agent diff tables, tools, KB, guardrails, or narrative text.\
\
- Do NOT merge the two tables.\
\
- The CSV must contain ONLY these two tables.\
\
- Table 1 must always appear first.\
\
- only Table 1 and Table 2 should be there in the csv file.\\u200b\\u200b\
\\u200b\\u200b\
\
\\u200b\\u200b\
\
RUNTIME PARAMETERS (PROVIDED AT EXECUTION TIME)\
\
You will receive the following values dynamically:\
\
repo\
\
branch\
\
token\
\
folder_name\
\
file_name (includes extension, e.g., report.csv, output.json, summary.txt)\
\
You must:\
\
Use these values exactly as provided\
\
Never invent values\
\
Never hardcode defaults\
\
Never modify credentials or paths\
\
\\u200b\
\
TOOL AVAILABLE\
\
Tool name:\
\
DI \\u200bGithub File Write\
\
Arguments schema:\
\
repo (string)\
\
branch (string)\
\
token (string)\
\
folder (string)\
\
file (string)\
\
content (string)\\u200b\\u200b\
\
FILE NAMING\
\
The file name will be provided at runtime via:\
\
file_name\
\
You must:\
\
Use it exactly as provided\
\
Respect its extension\
\
Not override or rename it\
\
Constraints:\
\
Do not hardcode any parameters\
\
Do not modify provided runtime values\
\
Only content is authored by you\
\
\\u200b\
\
VALIDATION BEFORE TOOL CALL\
\
You must verify before uploading:\
\
Content is complete and final\
\
Content matches required format (e.g., strict CSV when CSV is required)\
\
No extra commentary exists\
\
File is not empty\
\
File content is plain text\
\
File format matches the task specification\
\
If validation fails, you must correct the content before calling the tool.\
\
FINAL RESPONSE BEHAVIOR\
\
After the tool executes, your final response must contain only:\
\
Success or failure confirmation\
\
Uploaded file path\
\
Tool response\
\
Input for DI \\u200bGithub File Write Tool:\
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
    \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{repo_owner_false_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
    \
    \
    \
    \
    \
    \
    \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{branch_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{token_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      {{folder_string_true}}\
    \
    \
    \
    \
     \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{file_name_false_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
    \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \
\
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      \
      {{content_string_true}}\
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
    \
     \\u200b\\u200b\
\\u200b\\u200b\\u200b\\u200b\\u200b\\u200b\
\
\\u200b\\u200b\\u200b\\u200b\\u200b\\u200b\
\
file_content: the generated CSV text\
\
The agent must not skip the tool call.\\u200b\\u200b\", \"expected_output\": \"1. Metadata Comparison Score Summary\
2. Workflow-Level Comparison \
3. Governance & Metadata Additions (New in AAVA 2.0)\
4. Workflow Configuration Changes\
5. Agent Inventory Summary\
\\u200b6. Agent Configuration Differences\"}}]}"
    },
    "status": "SUCCESS"
  },
  "status": "SUCCESS"
}