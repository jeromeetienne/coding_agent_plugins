# Skills as software packages: discussion notes

- Created: 16 November 2026
- Last updated: 16 November 2026
- Status: Open discussion notes
- Related framing: [Agent instructions](../../AGENTS.md)
- Related issue: [Issue 82](https://github.com/jeromeetienne/coding_agent_plugins/issues/82)

## Purpose and source

For people maintaining skills, these notes preserve the conversation about applying ordinary software lifecycle expectations to skills. The source is the conversation in which Jérôme Étienne requested this folder. Jérôme Étienne's stated principles and responses are distinguished from assistant proposals and questions that remain unresolved.

The discussion began with [classifying the skills](skill_classification.md), then moved to a second question: what should a skill support when the skill is treated as a software package? This document records the discussion rather than claiming that the proposed capabilities have been implemented or adopted as repository requirements.

## Jérôme Étienne's central principles

Jérôme Étienne describes skills as programs and proposes applying the expectations of ordinary software to skills. Initial examples included installation, removal, configuration, documentation, versioning, and a changelog.

“SKILL.md” means the complete skill as a software package for this discussion. The placement of information inside the entry file, another Markdown file, or another part of the skill folder is outside the current question. The assistant initially divided capabilities by file placement. Jérôme Étienne rejected that distinction because the distinction did not answer whether a capability applies to the complete skill.

Skills are interpreted and handled by coding agents. Jérôme Étienne therefore expects some capabilities to require less formal machinery than conventional software. The presence of a software lifecycle does not by itself justify elaborate documentation or a complicated package system. The useful degree of formalization remains to be determined capability by capability.

## Meaning of applicability

Jérôme Étienne preferred the revised applicability vocabulary below.

| Applicability | Meaning |
| --- | --- |
| Yes | The capability applies to every skill. |
| If the skill needs it | Some skills need the capability and others do not. |
| No | The capability does not apply to skills. |

The earlier labels “reference”, “partly”, and “package concern” have been removed. Those labels mixed the location of information with the relevance of a capability. “When applicable” has been replaced by “If the skill needs it”.

The following table preserves the assistant's proposed applicability assessment, with Jérôme Étienne's subsequent responses alongside the assessment. Acceptance of the vocabulary does not establish approval of every proposed capability or assessment. No capability in the current proposal received “No”; “No” remains available if further examination rejects a capability.

## Capability review

| Capability | Proposed applicability | Meaning for a skill | Jérôme Étienne's response or current discussion state |
| --- | --- | --- | --- |
| Identity and purpose | Yes | A stable name, a clear responsibility, and an identifiable maintainer. | Included in the assistant proposal; no separate decision recorded. |
| Installation | Yes | A documented way to install an identifiable version. | Installation was part of Jérôme Étienne's initial software comparison. The installation mechanism remains undecided here. |
| Removal | Yes | A way to remove the installed skill, with an explicit treatment of remaining configuration and project documents. | Removal was part of Jérôme Étienne's initial comparison. The detailed policy remains open. |
| Configuration | If the skill needs it | Project-specific values are supplied separately from reusable instructions, with required values and defaults explained. | Jérôme Étienne explicitly identified configuration, comparing configuration to the role of `/etc` in ordinary software. No literal `/etc` location was selected. |
| Documentation | Yes | Explain purpose, use, expected results, examples, and limitations. | Jérôme Étienne wants to start with README.md and reach supporting documentation from README.md. Documentation should stay simple; a complex documentation system has not been requested. |
| Versioning | Yes | Identify published versions and the currently installed version. | Jérôme Étienne discussed identifying the installed version and how migration works. No new version storage mechanism or numbering convention was chosen. |
| Changelog | Yes | Explain changes between versions, including changes requiring action. | Jérôme Étienne suggested an approach like Keep a Changelog. Per-skill versus collection-wide history remains undecided. |
| Dependencies | If the skill needs it | Declare required skills, commands, services, or project data. | Jérôme Étienne considers dependencies subtle and does not yet know how dependencies should be handled. |
| Compatibility | Yes | Explain the coding agents, environments, or formats that the skill supports and relevant limits. | Jérôme Étienne does not yet know how compatibility should be handled. A universal compatibility declaration remains an assistant proposal. |
| Updates | Yes | Replace an installed version with a newer version through a defined procedure. | Updates were discussed alongside version identification and migration. No new update mechanism was selected. |
| Migration | If the skill needs it | Convert configuration or project data when the format expected by a newer skill changes. | Jérôme Étienne pointed to the existing Symbiospec approach as a possible model to reuse. |
| Validation and testing | Yes | Examine instruction consistency and exercise representative tasks to assess whether the skill works. | Jérôme Étienne considered validation and testing useful and referred to work by Anthropic on improving skills. No particular Anthropic method was identified or investigated during this discussion. |
| Failure handling | Yes | Describe how the coding agent reports failure, preserves work, and handles an interrupted task. | Jérôme Étienne found the capability unclear. The explanation and required extent remain open. |
| Repeat execution | Yes | Define what happens when the skill is run again against existing or partially completed work. | Jérôme Étienne asked what the capability means. No universal repeat-execution requirement has been agreed. |
| Permissions and ownership | Yes | Explain allowed actions, human decisions, approval boundaries, and ownership of maintained content. | Discussed in connection with the rule types. No additional permission scheme was chosen. |
| Composition | Yes | Explain how skills supply inputs to other skills and use results from other skills. | Included in the assistant proposal; the degree of formalization remains open. |
| Release and distribution | Yes | Make published versions available through an identifiable source and a documented method. | Included in the assistant proposal; no new release or distribution system was chosen. |
| Deprecation and replacement | If the skill needs it | Identify obsolete skills, replacements, and any transition procedure. | Included in the assistant proposal; no new policy was chosen. |
| Scope and exclusions | Yes | Explain what the skill handles and where responsibility ends. | Added by the assistant during review; no separate approval recorded. |

Updates and migration have separate rows because an update can replace installed instructions without converting project data. The earlier table combined both capabilities in one row. Separating the rows preserves the earlier assessments while making the applicability values consistent.

## Documentation with a coding agent as the reader

Jérôme Étienne's starting point is README.md, with supporting documentation accessible from README.md. The coding agent can read the skill and the linked documents. A decision to provide documentation does not require an elaborate documentation site or a rigid description of every possible execution.

An open question is how much information must be explicit for dependable use. The assistant suggested documenting inputs, expected results, limitations, and cooperation between skills. These suggestions have not been adopted as mandatory sections or as a machine-readable format.

## Versioning, updates, and migration

The conversation raised three related concerns: identify the installed skill version, install newer instructions, and convert existing project information when the newer instructions require a different format.

The existing [Symbiospec versioning and migration reference](../../skills/symbio_spec/references/versioning.md) provides a concrete example. Symbiospec distinguishes the installed skill release from the format version of project specifications. The reference describes detecting the project format, following published conversions, preserving data and approvals, verifying conversion, and handling interrupted migration.

Jérôme Étienne suggested that the general skill lifecycle could reuse the Symbiospec approach. This suggestion does not establish that every skill needs a project-data format or that every detail of Symbiospec migration should become a universal requirement. Which parts should be shared remains open.

The [Keep a Changelog Workflow](../../skills/keep-a-changelog-workflow/README.md) is an existing resource for the proposed changelog approach. The conversation has not selected the location, ownership, or release unit of future skill changelogs.

## Dependencies and compatibility

Dependencies and compatibility remain questions for further discussion. A dependency is something a skill requires to do its job. Compatibility concerns whether a particular version of a skill works with a particular environment, coding agent, companion skill, or document format.

The collection already has examples that can inform the discussion: [Symbiospec to documentation](../../skills/symbio_spec_to_docs/README.md) requires Symbiospec and project specification data, while the [obsolete Docs folder agents rules system](../../skills/docs_folder_agents_rules_system/README.md) requires Docs folder system. These examples establish existing relationships, not a chosen general dependency mechanism.

The following are assistant questions for later examination: should dependencies be expressed in ordinary prose, should installed versions be checked, and who installs or updates a required companion skill? Similarly, should compatibility be documented from observed use, tested against selected coding agents, or expressed as a list of known limits? No answer has been chosen.

## Validation and testing

Jérôme Étienne sees potential value in testing skills and referred to Anthropic's work. The conversation did not identify a publication, a test tool, an optimization method, or a benchmark. No claim about a specific external method is established here.

The assistant's distinction was between checking the written instructions and exercising the skill on representative tasks. What counts as a useful task, how success is judged, and how much testing is proportionate remain open. Testing a skill should not be reported as completed merely because the skill's documents exist.

## Clarifications still needed

Failure handling and repeat execution were assistant proposals that Jérôme Étienne found unclear. A proposed failure-handling example is a skill that stops after changing some documents: the coding agent explains which documents changed, which task remains incomplete, and what can safely happen next. The example illustrates the idea without establishing a universal procedure.

A proposed repeat-execution example is asking Keep a Changelog Workflow to reconcile the same release twice: the second run should not create a duplicate release entry. Other skills have different intended effects. Issue Creation can legitimately create a new issue when another issue is requested; a general rule that every repeated invocation leaves all files unchanged would be inappropriate. The desired repeated behavior must be discussed in the context of the task.

Permissions concern what the coding agent may do. Ownership concerns who decides the meaning of maintained information and which documents the skill may maintain. These questions connect to the [rule classifications](skill_classification.md), but an approval step in a workflow does not automatically make that workflow a living rule with human approval.

## What remains to decide

- Which proposed capabilities should become shared requirements for all skills, and which should remain guidance?
- How simple can documentation and configuration remain while still supporting dependable use by coding agents?
- How should the installed skill version be recorded and how should skill updates be performed?
- Should changelogs and releases belong to each skill or to the collection?
- Which parts of Symbiospec format migration are useful for other skills?
- How should dependencies and compatibility be described and checked?
- What would representative testing prove, and who approves the expected results?
- What do failure handling and repeat execution need to mean for each kind of skill?

These notes capture the discussion and preserve the open questions. Creating these notes does not implement a package manager, update the reusable skill instructions, or approve a universal lifecycle standard.
