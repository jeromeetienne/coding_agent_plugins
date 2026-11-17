# Proposed skill classification

- Created: 16 November 2026
- Last updated: 16 November 2026
- Status: Proposal for discussion
- Related framing: [Agent instructions](../../AGENTS.md)
- Related issue: [Issue 82](https://github.com/jeromeetienne/coding_agent_plugins/issues/82)

## Purpose

For people organizing this collection, this proposal classifies the 16 skills present during the discussion by purpose, role, trigger, and authority. Jérôme Étienne requested several attributes because one exclusive grouping would hide useful distinctions. The table is an assistant proposal, rather than an approved reorganization of the repository.

## Rule types and use frequency

[The Rules of the Repo](../../skills/rules_of_the_repo/SKILL.md) distinguishes static rules, living rules with human approval, and living rules without human approval. A static rule is obeyed rather than changed during ordinary work. “Static” does not describe unrestricted authority to change the rule. A living rule changes with the project; the rule type determines whether the coding agent needs human approval for the rule change.

Repo Folders Constraints and Symbiospec were identified during the conversation as the current skills maintaining human-approved living rules. CONTEXT.md system maintains living notes without human approval. Docs folder system and the adopted coding styles supply static conventions.

Jérôme Étienne also distinguished tools used for particular tasks from rules that apply throughout matching work. Actual frequency depends on the project: Issue Creation can be used every day while still being a task tool. Use triggers describe this distinction more precisely than a prediction of daily frequency. All application described below assumes that the project has adopted the relevant skill.

## Classification of the 16 skills

| Skill | Purpose and role | Use trigger | Rule type or authority boundary |
| --- | --- | --- | --- |
| [The Rules of the Repo](../../skills/rules_of_the_repo/README.md) | Coordinates rule selection and configuration. | Before every repository change. | Defines the framework; holds no project rule itself. |
| [Repo Folders Constraints](../../skills/repo_folders_constraints/README.md) | Maintains folder and package responsibilities and constraints. | Changes affecting governed placement, responsibilities, dependencies, or technologies. | Living rule with human approval. |
| [CONTEXT.md system](../../skills/context_md_system/README.md) | Maintains context and local instructions for coding agents. | Read before matching file changes; maintain notes when responsibilities or exports change. | Living rule without human approval; human-owned constraints take precedence. |
| [Docs folder system](../../skills/docs_folder_system/README.md) | Applies documentation form and navigation conventions. | Every change in the configured documentation folder. | Static rule; document meaning retains its own approval requirements. |
| [Jérôme Étienne's personal TypeScript and JavaScript coding style](../../skills/jerome-typescript-javascript-style/README.md) | Applies personal coding preferences. | Every matching source-file change. | Static rule. |
| [Jérôme Étienne's personal Rust coding style](../../skills/jerome-rust-style/README.md) | Applies personal coding preferences. | Every Rust source-file change. | Static adopted conventions; uncertain adaptations require Jérôme Étienne's approval. |
| [Symbiospec](../../skills/symbio_spec/README.md) | Maintains product definitions and provides design, audit, and reconciliation workflows. | Product changes; initialization, audits, and reconciliation as requested. | Living product rules with human approval; already authorized decisions do not require repeated approval. |
| [Issue Creation](../../skills/issue_creation/README.md) | Writes issues, comments, and attachments on GitHub or GitLab. | Tasks requiring issue creation or issue comments. | Task tool; does not maintain a living project rule. |
| [Pull Request Creation](../../skills/pull_request_creation/README.md) | Explains changes for review on GitHub or GitLab. | Preparing or revising a pull request. | Task tool; publication follows project workflow and authorization. |
| [Issue Fix Workflow](../../skills/issue_fix_workflow/README.md) | Coordinates implementation and delivery of one issue. | A request to fix one issue. | Task workflow with human review and completion approval. |
| [Issue Batch Workflow](../../skills/issue_batch_workflow/README.md) | Coordinates related issues and parallel implementation. | A parent issue with related sub-issues or a batch request. | Task workflow with initial questions, followed by checks and merges without individual developer review. |
| [Git Cleanup Review](../../skills/git_cleanup_review/README.md) | Examines worktrees and branches and recommends cleanup. | A cleanup review request. | Occasional assessment tool; removal requires a separate request. |
| [Keep a Changelog Workflow](../../skills/keep-a-changelog-workflow/README.md) | Creates, updates, or validates changelog entries. | A requested changelog or release-documentation task. | Occasional tool; invocation does not authorize publishing a release. |
| [Symbiospec to documentation](../../skills/symbio_spec_to_docs/README.md) | Generates and maintains audience documentation. | A generation request or configured updates after relevant source changes. | Tool with ongoing maintenance; uses approved product information, with project-defined configuration authority. |
| [symbio_spec_to_ux](../../skills/symbio_spec_to_ux/README.md) | Proposes screens and navigation from product definitions. | A requested interface-design task. | Design tool; proposed product decisions require approval. Draft. |
| [Docs folder agents rules system](../../skills/docs_folder_agents_rules_system/README.md) | Maintains earlier agent-rule documents and glossary. | Applicable changes in existing projects using the skill. | Obsolete and superseded by Symbiospec; the skill does not itself explicitly require human approval for rule updates. |

Dependencies and maturity are useful additional attributes. For example, Symbiospec to documentation requires Symbiospec and project data, while symbio_spec_to_ux is a draft. Lifecycle support provides another independent attribute: a skill can be useful while still lacking a documented removal or migration procedure. See the [capability discussion](discussion_notes.md).
