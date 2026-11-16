# Initialization

- Created: 16 November 2026
- Last updated: 16 November 2026
- Status: Maintained explanation of a Symbiospec workflow for people
- Related framing: [Agent instructions](../../AGENTS.md)
- Related rules: [docs_folder_system](../../skills/docs_folder_system/SKILL.md)
- Related issue: [Issue 15](https://github.com/jeromeetienne/coding_agent_plugin/issues/15), [Issue 10](https://github.com/jeromeetienne/coding_agent_plugin/issues/10), [Issue 11](https://github.com/jeromeetienne/coding_agent_plugin/issues/11), [Issue 124](https://github.com/jeromeetienne/coding_agent_plugins/issues/124), [Issue 131](https://github.com/jeromeetienne/coding_agent_plugins/issues/131)

Initialize starts Symbiospec in a project.

- New software: the coding agent creates the folder structure. The empty templates are not approved definitions. Then the project starts to use update.
- Existing software: the coding agent uses slow growth. The coding agent finds a few clear concepts, the human approves the concepts, and the coding agent documents a small part of the product around the concepts. Then the cycle starts again with the next concepts. The existing code is evidence, but the existing code is not automatically the intended behaviour.
- Existing specification from another system: the coding agent keeps the content and approvals, and proposes content adoption in small steps. Existing Symbiospec folders first undergo the shared [automatic format migration](../../skills/symbio_spec/references/versioning.md) to the latest installed published format, without a separate migration request.

Slow growth is necessary because an incorrect concept makes errors in all the descriptions that use the concept. Small reviewed steps stop these errors early.

## A small initialization cycle

For the fictional note editor in the [specification example](specification_example.md), the coding agent first inspects saving one Note. The coding agent prepares the Note definition, save expectations, evidence, uncertainties and the relationship to the Save control. The human reviews the prepared decisions and can accept, reject, revise or defer each decision. Questions requiring substantial new investigation move into a later batch.

After actual approval, the coding agent records the source and scope of the decision, updates the topic and coverage records, and checks navigation and consistency. Saving one Note can be an approved baseline while sharing and deletion remain unexamined. An earlier specification is preserved and incrementally migrated rather than discarded; an unknown approval history stays explicit.

## Related workflows and instructions

Read the [workflow overview](README.md) for the other workflows and the [coding-agent workflow reference](../../skills/symbio_spec/references/workflows.md) for the authoritative procedures.
