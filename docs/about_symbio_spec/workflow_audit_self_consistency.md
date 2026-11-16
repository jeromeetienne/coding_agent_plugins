# Symbiospec Audit for self-consistency

- Created: 16 November 2026
- Last updated: 16 November 2026
- Status: Maintained explanation of a Symbiospec workflow for people
- Related framing: [Agent instructions](../../AGENTS.md)
- Related rules: [docs_folder_system](../../skills/docs_folder_system/SKILL.md)
- Related issue: [Issue 15](https://github.com/jeromeetienne/coding_agent_plugin/issues/15), [Issue 10](https://github.com/jeromeetienne/coding_agent_plugin/issues/10), [Issue 11](https://github.com/jeromeetienne/coding_agent_plugin/issues/11), [Issue 124](https://github.com/jeromeetienne/coding_agent_plugins/issues/124), [Issue 131](https://github.com/jeromeetienne/coding_agent_plugins/issues/131)

**Symbiospec Audit for self-consistency** examines whether approved descriptions agree internally and use consistent terminology. Approved user scenarios in scope must be possible to follow using Symbiospec alone. A rule requiring all readers to sign in conflicts with an approved user scenario requiring access without an account. A missing description of an action needed by a user scenario is also a finding. This review does not establish whether the software works.

The human chooses either audit or both audits, the scope, and the timing. The human may say, “Run Symbiospec Audit for self-consistency for sharing after we finish discussing these rules.” Neither audit runs automatically after every rule change. A conflict already noticed during discussion is mentioned without automatically launching an investigation or requiring an audit before rule approval.

Reports identify examined and unexamined scope, evidence, severity, confidence and recommendations. Reports distinguish confirmed conflicts, missing descriptions, unresolved product decisions and unverified behaviour. A missing test is a coverage gap, not proof of broken software. Findings are presented in the conversation unless saving a report is authorized. Neither findings nor warnings authorize changes to software, tests, approved descriptions or approved user scenarios.

An audit ends with findings and evidence limits. Realignment can continue from findings into authorized corrections. Source inspection, executed tests, and direct application observations establish different evidence; no audit should claim tests that did not run or complete coverage from a partial review. The [workflow overview](../../skills/symbio_spec/references/workflows.md) links to the separate coding-agent procedures.

| Audit | Evidence and result | Limit |
| --- | --- | --- |
| Symbiospec Audit for self-consistency | Approved descriptions, original approval evidence and approved user scenarios in the selected scope; findings link the conflicting or missing descriptions. | Software is not run; agreement within Symbiospec does not prove software compliance. |

## Related workflows and instructions

Read the [workflow overview](README.md) for the other workflows and the [coding-agent workflow reference](../../skills/symbio_spec/references/workflows.md) for the authoritative procedures.
