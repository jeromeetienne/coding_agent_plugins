# symbio_spec_to_ux

**Status: Draft — not tested on a real project.** The test project and trial approach remain open in [issue #25](https://github.com/jeromeetienne/coding_agent_plugins/issues/25).

The [skill instructions](SKILL.md) propose screens and navigation from approved Symbiospec using objects, relationships, calls to action, and attributes. The output includes source links, representative task walkthroughs, and decisions for human review.

The receiving project needs an approved Symbiospec for the selected scope. Missing decisions remain explicit. No visual framework or prototype tool is required.

Normal work requires the latest published Symbiospec format in the installed registry, currently `2.0.0`. The shared [version check and automatic migration procedure](../symbio_spec/references/versioning.md) runs first. Invoking this skill includes authorization to adopt unversioned data and migrate older formats with verified preservation, without a separate migration request. Explicit instructions forbidding changes block required migration and dependent work. Malformed, unknown or newer versions and failed or interrupted migrations stop normal work. Product approval and implementation permissions remain separate from storage conversion.

Example request:

> Use symbio_spec_to_ux to propose screens and navigation for this feature's approved Symbiospec. Identify missing decisions and do not implement the proposal.

The draft is available for deliberate evaluation. Proposal approval, prototype testing, and verification of implemented software are separate results. No real-project trial has been agreed or completed.
