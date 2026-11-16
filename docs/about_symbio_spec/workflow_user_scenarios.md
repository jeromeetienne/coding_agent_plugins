# User scenarios

- Created: 16 November 2026
- Last updated: 16 November 2026
- Status: Maintained explanation of a Symbiospec workflow for people
- Related framing: [Agent instructions](../../AGENTS.md)
- Related rules: [docs_folder_system](../../skills/docs_folder_system/SKILL.md)
- Related issue: [Issue 15](https://github.com/jeromeetienne/coding_agent_plugin/issues/15), [Issue 10](https://github.com/jeromeetienne/coding_agent_plugin/issues/10), [Issue 11](https://github.com/jeromeetienne/coding_agent_plugin/issues/11), [Issue 124](https://github.com/jeromeetienne/coding_agent_plugins/issues/124), [Issue 131](https://github.com/jeromeetienne/coding_agent_plugins/issues/131)

A user scenario describes what a person wants to accomplish: the goal, starting conditions, ordered actions, expected outcome, and relevant failure and recovery paths. User scenarios connect the six specification areas without becoming a seventh area or another place to copy product rules. Project records live under `docs/symbio_spec/user_scenarios/` and link to the responsible descriptions.

A human can supply a batch of user scenarios before all supporting descriptions exist. A coding agent can also propose user scenarios from a selected part of approved Symbiospec or from evidence in existing software. Generated proposals can repeat gaps in the source descriptions, so the coding agent states the examined scope and asks which journeys are missing. Neither source approval nor successful software tests approve a generated user scenario: every user scenario needs human approval.

For example, a person might propose this journey for the fictional note editor: “I open an existing Note, change the text, select Save, and receive confirmation. If saving fails, I see the failure and can retry.” This example is an illustration, not an approved project requirement or an executed application check.

| Record | Question answered in the example |
| --- | --- |
| Human approval | Has the human approved this intended journey, and with what scope? |
| Specification review | Do the linked Behaviour and User Interface descriptions explain opening, editing, saving, failure and retry? Which descriptions or decisions are missing? |
| Software verification | Which actions were actually exercised, on which software revision and environment, with what result? If no exercise occurred, state “Software not exercised.” |

When creating or explicitly reviewing a user scenario, the coding agent walks through the complete journey using Symbiospec alone. The review can reveal missing actions, disconnected navigation, contradictions or unclear outcomes. The human may approve the intended journey while supporting descriptions remain incomplete; approval does not settle every missing product decision. New decisions are proposed separately within the authorized task.

An approved journey stays intact while proposed revisions await a human decision. Rejected revisions do not replace approved text. An authorized replacement or retirement records the decision and keeps the earlier user scenario discoverable. If a new rule apparently conflicts with an approved journey, the coding agent mentions the noticed conflict and leaves the unresolved expectations explicit. Rule changes do not automatically trigger a search through user scenarios, another walkthrough, or an audit.

## Choose a starting point

There are three starting points. The choice depends on whether the useful starting material is the intended product, its written specification, or existing software. The examples below describe a fictional note editor; the examples are suggested requests, not product approvals or software verification evidence.

## Generate proposals from existing Symbiospec

This starting point helps a human review product goals across descriptions already written in different areas. The coding agent proposes journeys from the selected descriptions and shows which descriptions support the journeys. The human checks the proposed journeys and identifies missing goals. A generated set can inherit omissions from Symbiospec and does not establish complete coverage.

Example request:

> Propose user scenarios for editing and saving a Note from our existing Symbiospec. Show the supporting descriptions, missing decisions and examined scope. Present the user scenarios for my review; do not change software.

A possible proposal is “Edit a Note and retain the changes,” linked to the opening, editing and saving descriptions. If failure recovery is missing, that missing description stays visible when the human reviews the proposal. Approval of the source descriptions does not automatically approve the generated journey.

## Generate proposals from existing software

This starting point helps describe an existing product whose user goals are not yet well documented. Code, tests and permitted application observations provide evidence for proposed journeys. The human decides whether the observed or inferred behaviour belongs in the intended product. Existing approved Symbiospec remains the reference when the implementation differs.

Example request:

> Inspect Note duplication in the existing software and propose the user scenarios the software appears to support. Distinguish code inspection from executed checks, link the evidence and report uncertainty. Present the proposals for my review before adopting product meaning. Do not change software.

The coding agent might find a Duplicate control and propose “Create a separate Note from an existing Note.” Reading the duplication code does not establish that duplication works. After the human approves the intended journey and relevant product decisions, supporting Symbiospec descriptions can be developed. A later walkthrough checks those written descriptions alone and records remaining specification gaps.

## Start product design from a human-provided batch

This starting point establishes what people should accomplish before every screen or rule has been decided. The batch may be rough and incomplete. The coding agent preserves the supplied journeys, identifies shared concepts and conflicting expectations, and prepares the missing product choices for human discussion. The human can approve the journeys while leaving some supporting decisions unresolved. An explicit approval already supplied with the batch is recorded without asking for the same approval again.

Example request:

> Start Symbiospec from these user scenarios: create a Note, edit an existing Note, and recover from a failed save. Organize the batch, identify shared concepts and missing decisions, and help me develop the supporting descriptions. Present choices for approval rather than inventing product rules. Do not implement software.

The three user scenario documents can share one Note definition and one save Behaviour description. Whether unsaved text survives a failed save is a shared product decision; documenting three journeys should not force the human to decide that question three times. After authorization, the shared description holds the rule and each affected user scenario links to the shared description. A small useful part can be established while the rest of the batch remains incomplete.

## Combine starting points

The human can supply the important user scenarios and ask the coding agent to propose additional user scenarios from existing Symbiospec or software. Keeping supplied and generated material distinguishable lets the human review the additions without losing the original goals. Approval of the supplied batch does not automatically approve generated additions.

For the authoritative approval and lifecycle definitions, read [User scenarios in format 3.1.0](../../skills/symbio_spec/references/format-v3.1.0.md#5-user-scenarios). The [user scenario workflow](../../skills/symbio_spec/references/workflow_user_scenarios.md) contains the coding-agent procedure and record template.

## Related workflows and instructions

Read the [workflow overview](README.md) for the other workflows and the [coding-agent workflow reference](../../skills/symbio_spec/references/workflows.md) for the authoritative procedures.
