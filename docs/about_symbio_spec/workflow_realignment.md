# Realignment

- Created: 16 November 2026
- Last updated: 16 November 2026
- Status: Maintained explanation of a Symbiospec workflow for people
- Related framing: [Agent instructions](../../AGENTS.md)
- Related rules: [docs_folder_system](../../skills/docs_folder_system/SKILL.md)
- Related issue: [Issue 15](https://github.com/jeromeetienne/coding_agent_plugin/issues/15), [Issue 10](https://github.com/jeromeetienne/coding_agent_plugin/issues/10), [Issue 11](https://github.com/jeromeetienne/coding_agent_plugin/issues/11), [Issue 124](https://github.com/jeromeetienne/coding_agent_plugins/issues/124), [Issue 131](https://github.com/jeromeetienne/coding_agent_plugins/issues/131)

Realign finds and corrects drift: a difference between Symbiospec, the software, and the tests that update did not find.

1. The coding agent compares Symbiospec with the software and the tests, and changes nothing.
2. The coding agent reports each difference, with the evidence.
3. The human reviews a prepared batch of corrections. A correction can change the software, Symbiospec, the tests, or more than one of them.
4. The coding agent applies the approved corrections, and does the comparison again.

The approved intent stays the reference. Realign never changes the approved specification only to make an incorrect implementation look correct.

## Example comparison report

A request to review failed saves permits comparison and reporting. For example, a report might contain the following fictional finding:

| Field | Example finding |
| --- | --- |
| Scope | Save failure only; sharing and deletion not examined. |
| Expected | The approved save specification requires a failure message and no success confirmation. |
| Observed and evidence | A permitted application exercise shows a success confirmation after a rejected write; the relevant test expects success. Link the actual observation and test when reporting a real finding. |
| Severity and confidence | High impact because saving appears successful; high confidence within the exercised failure case. |
| Recommendation | Correct the application and conflicting test while preserving approved intent. |
| Decision and resolution | Investigation alone does not authorize corrections. Apply authorized corrections, repeat the failed-save exercise and record resolved or remaining findings. |

A missing test is a coverage gap, not proof of a broken feature. Reports saved with authorization belong in `docs/symbio_spec/reports/`; otherwise findings can remain in the conversation. Approval, executed tests and live observations remain separate evidence.

## Limits and further work

[Issue 11](https://github.com/jeromeetienne/coding_agent_plugin/issues/11) proposed these three operations; the current [workflow reference](../../skills/symbio_spec/references/workflows.md) supplies coding-agent instructions. The skill does not establish a recurring schedule, automatic scope selection, a dedicated executable comparison tool or complete alignment from a partial investigation. Saving a report and correcting software remain subject to the request's authorization.

Review meaningful product differences rather than copying the whole specification into every review record. Reports identify examined and unexamined scope, approval evidence, unresolved questions and checks actually run. Product review complements technical verification; approval of documentation does not establish application correctness.

## Related workflows and instructions

Read the [workflow overview](README.md) for the other workflows and the [coding-agent workflow reference](../../skills/symbio_spec/references/workflows.md) for the authoritative procedures.
