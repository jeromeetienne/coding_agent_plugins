# Update

- Created: 16 November 2026
- Last updated: 16 November 2026
- Status: Maintained explanation of a Symbiospec workflow for people
- Related framing: [Agent instructions](../../AGENTS.md)
- Related rules: [docs_folder_system](../../skills/docs_folder_system/SKILL.md)
- Related issue: [Issue 15](https://github.com/jeromeetienne/coding_agent_plugin/issues/15), [Issue 10](https://github.com/jeromeetienne/coding_agent_plugin/issues/10), [Issue 11](https://github.com/jeromeetienne/coding_agent_plugin/issues/11), [Issue 124](https://github.com/jeromeetienne/coding_agent_plugins/issues/124), [Issue 131](https://github.com/jeromeetienne/coding_agent_plugins/issues/131)

Update keeps Symbiospec current when the software changes. The coding agent changes the software and the affected parts of Symbiospec in the same task.

The human does not approve again a decision that the human already approved for the change. A new product decision that is not in that approval goes to the human for review. An unexpected result of the implementation never becomes an approved requirement silently.

## Example

An authorized request to change save confirmation wording permits the corresponding Behaviour and User Interface updates in the same task without asking again. If implementation exposes a new question about overwriting another Note, that additional product decision needs review. A technical refactoring with unchanged product meaning needs no artificial rewrite of the specification.

## Related workflows and instructions

Read the [workflow overview](README.md) for the other workflows and the [coding-agent workflow reference](../../skills/symbio_spec/references/workflows.md) for the authoritative procedures.
