# Symbiospec Audit for software compliance

- Created: 16 November 2026
- Last updated: 16 November 2026
- Status: Maintained explanation of a Symbiospec workflow for people
- Related framing: [Agent instructions](../../AGENTS.md)
- Related rules: [docs_folder_system](../../skills/docs_folder_system/SKILL.md)
- Related issue: [Issue 15](https://github.com/jeromeetienne/coding_agent_plugin/issues/15), [Issue 10](https://github.com/jeromeetienne/coding_agent_plugin/issues/10), [Issue 11](https://github.com/jeromeetienne/coding_agent_plugin/issues/11), [Issue 124](https://github.com/jeromeetienne/coding_agent_plugins/issues/124), [Issue 131](https://github.com/jeromeetienne/coding_agent_plugins/issues/131)

**Symbiospec Audit for software compliance** compares in both directions: does software implement approved expectations, and are software capabilities described in Symbiospec? A sharing feature that displays success after a failed request can violate an approved rule. A feature providing expiring sharing links can be undocumented even when no written rule forbids the feature. Symbiospec remains authoritative; discovering the feature does not approve the feature or authorize adding the feature to Symbiospec.

The human chooses either audit or both audits, the scope, and the timing. The human may say, “Run Symbiospec Audit for self-consistency for sharing after we finish discussing these rules.” Neither audit runs automatically after every rule change. A conflict already noticed during discussion is mentioned without automatically launching an investigation or requiring an audit before rule approval.

Reports identify examined and unexamined scope, evidence, severity, confidence and recommendations. Reports distinguish confirmed conflicts, missing descriptions, unresolved product decisions and unverified behaviour. A missing test is a coverage gap, not proof of broken software. Findings are presented in the conversation unless saving a report is authorized. Neither findings nor warnings authorize changes to software, tests, approved descriptions or approved user scenarios.

An audit ends with findings and evidence limits. Realignment can continue from findings into authorized corrections. Source inspection, executed tests, and direct application observations establish different evidence; no audit should claim tests that did not run or complete coverage from a partial review. The [workflow overview](../../skills/symbio_spec/references/workflows.md) links to the separate coding-agent procedures.

| Audit | Evidence and result | Limit |
| --- | --- | --- |
| Symbiospec Audit for software compliance | Approved expectations compared with independently identified software capabilities, using available source code, tests and permitted application observations. | Reading a test is not executing a test; unavailable checks remain unverified, and partial inspection does not establish whole-product compliance. |

## Related workflows and instructions

Read the [workflow overview](README.md) for the other workflows and the [coding-agent workflow reference](../../skills/symbio_spec/references/workflows.md) for the authoritative procedures.
