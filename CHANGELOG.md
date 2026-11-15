# Changelog

Notable changes to the shared coding-agent skills are recorded here.
The format follows [Keep a Changelog 1.1.0](https://keepachangelog.com/en/1.1.0/).

## [Unreleased]

### Release notes

Issue Fix Review now requires explicit approval before committing the reviewed changes, creating and merging the pull request, and closing the issue. Reusable skills must contain Markdown files only, with executable tools maintained in separate repositories. The repository also adds an installed copy of Pull Request Creation for preparing clear titles and descriptions from the complete change and actual validation.

Symbiospec format `3.0.0` separates original coverage examinations from maintained topic summaries, preserving evidence and unexamined scope. Issue and pull request writing now explicitly requires Markdown formatting for readability.

The repository no longer includes its GitHub Pages website configuration.

### Added

- Add the reusable `pull_request_creation` skill, an adoption guide, and collection discovery links for preparing titles and descriptions from complete changes and actual validation. [Pull request 113](https://github.com/jeromeetienne/coding_agent_plugins/pull/113)
- Add an installed copy of `pull_request_creation`, with guidance for describing the complete change, reporting validation accurately, and respecting the receiving repository's review and publication workflow. [Commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/6a30bdeb1061110c5016edb909f4597580614b77)

### Changed

- Introduce Symbiospec format `3.0.0`, with permanent original coverage examination records and maintained topic summaries that distinguish summary freshness from software verification. Provide forward and reverse migration instructions; all three Symbiospec skills require automatic migration through published transitions before normal work. Completed migrations remove obsolete paths without compatibility pages or redirects. [Pull request 114](https://github.com/jeromeetienne/coding_agent_plugins/pull/114)
- Require readable Markdown in issue bodies, issue comments, and pull request descriptions, with formatting proportional to the content and consistent with repository templates and reference rules. [Pull request 116](https://github.com/jeromeetienne/coding_agent_plugins/pull/116)
- Require explicit approval for Issue Fix Completion after explaining the commit, pull request, merge, and issue-closing actions; update the installed Issue Fix Workflow copy to match. [Pull request 112](https://github.com/jeromeetienne/coding_agent_plugins/pull/112), [commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/6a30bdeb1061110c5016edb909f4597580614b77)
- Require Markdown files only throughout `skills/`, including subfolders; keep executable tools in separate repositories and link to those tools from the instructions. [Pull request 110](https://github.com/jeromeetienne/coding_agent_plugins/pull/110)

### Removed

- Remove the Jekyll and GitHub Pages configuration from the repository. [Commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/493f4ba6c2481719bc18444c7c25ccc7b310d344)

## [0.5.0] - 2026-11-15

### Release notes

This release expands the collection with changelog maintenance and a draft workflow for proposing screens and navigation. Practical installation and configuration guides make the skills easier to adopt in another repository.

**Symbiospec decisions and audits**

Symbiospec now provides separately requested audits for specification consistency and software compliance. Format `2.0.0` stores original decisions in dated files with permanent numbers and linked topic summaries. All three Symbiospec skills migrate older project data to the latest published format before normal work, preserving decisions, approvals, and recovery evidence. Completed migrations remove obsolete paths and update known repository references; external links that cannot be updated are reported.

**Collection maintenance**

Git Cleanup Review examines worktrees before branches and keeps cleanup advice separate from permission to remove anything. The project rename tool now lives in its own repository, leaving this collection focused on reusable skills.

### Added

- Add `keep-a-changelog-workflow` for creating, updating, finalizing, and validating changelogs from version tags and pull request evidence. [Pull request 35](https://github.com/jeromeetienne/coding_agent_plugins/pull/35)
- Add `symbio_spec_to_ux` to propose screens and navigation from approved specifications, with source links and human review. The skill remains a draft that has not been tested on a real project. [Pull request 69](https://github.com/jeromeetienne/coding_agent_plugins/pull/69)
- Add explicitly requested Symbiospec audits for self-consistency and software compliance, including checks for undocumented software capabilities. Audit findings do not authorize corrections. [Pull request 95](https://github.com/jeromeetienne/coding_agent_plugins/pull/95)
- Add Symbiospec format definitions, version records, and migration procedures; introduce format `2.0.0` with dated original decisions, permanent numbers, and topic summaries. [Pull request 98](https://github.com/jeromeetienne/coding_agent_plugins/pull/98), [pull request 102](https://github.com/jeromeetienne/coding_agent_plugins/pull/102)
- Add practical guides for installing and combining skills, configuring repository rules, adopting Symbiospec, and maintaining and publishing the collection. [Pull request 54](https://github.com/jeromeetienne/coding_agent_plugins/pull/54), [pull request 55](https://github.com/jeromeetienne/coding_agent_plugins/pull/55), [pull request 56](https://github.com/jeromeetienne/coding_agent_plugins/pull/56), [pull request 57](https://github.com/jeromeetienne/coding_agent_plugins/pull/57), [pull request 58](https://github.com/jeromeetienne/coding_agent_plugins/pull/58)

### Changed

- Rename `git_cleanup_adviser` to `git_cleanup_review`. Review worktrees first, then branches; protect the main checkout and configured branches, report modification dates, and treat ignored files as disposable when assessing redundant worktrees. Reviews remain advice only. [Pull request 32](https://github.com/jeromeetienne/coding_agent_plugins/pull/32), [pull request 34](https://github.com/jeromeetienne/coding_agent_plugins/pull/34), [commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/c739b4443be292d117aec08eb87319ae33b6069f)
- Mark Jérôme Étienne’s personal Rust coding style ready for use, keeping unresolved adaptations separate from approved rules. [Commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/c5d8ad6b673e2fd91e16dcaac408b6d4f4530df1)
- Organize documentation by reader purpose and provide a ready-to-copy configuration prompt after installation. Suggest receiving-project configuration locations while preserving explicit repository choices. [Pull request 81](https://github.com/jeromeetienne/coding_agent_plugins/pull/81), [pull request 90](https://github.com/jeromeetienne/coding_agent_plugins/pull/90), [pull request 92](https://github.com/jeromeetienne/coding_agent_plugins/pull/92)
- Split Symbiospec workflows into individually linked references while preserving the original instructions and authorization boundaries. [Pull request 94](https://github.com/jeromeetienne/coding_agent_plugins/pull/94)
- Require all three Symbiospec skills to adopt unversioned data and migrate older formats to the latest published format before normal work. Explicit prohibitions on changes, unknown or newer formats, and unavailable reliable conversion paths stop dependent work. [Pull request 104](https://github.com/jeromeetienne/coding_agent_plugins/pull/104)
- Require completed Symbiospec migrations to remove obsolete paths rather than retain compatibility pages. Preserve decision and approval evidence, update known references, and report external references that cannot be changed. [Pull request 106](https://github.com/jeromeetienne/coding_agent_plugins/pull/106)

### Deprecated

- Mark `docs_folder_agents_rules_system` obsolete; configuring The Rules of the Repo does not require adopting the obsolete system. [Commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/3c324f82f05e0fe8618b979aeae6a1dfc061a0ba), [pull request 92](https://github.com/jeromeetienne/coding_agent_plugins/pull/92)

### Removed

- Remove `bug_triage_workflow` from the collection. [Commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/3c324f82f05e0fe8618b979aeae6a1dfc061a0ba)
- Move the project rename tool, its history, tests, and recovery guidance to [coding_agent_project_rename](https://github.com/jeromeetienne/coding_agent_project_rename). Remove the original package, workspace configuration, and dependencies from this repository. [Pull request 88](https://github.com/jeromeetienne/coding_agent_plugins/pull/88)

### Fixed

- Correct the publication guide to link to the website configuration source on GitHub rather than an asset that GitHub Pages does not serve. [Pull request 59](https://github.com/jeromeetienne/coding_agent_plugins/pull/59)

## [0.4.0] - 2026-11-08

### Release notes

Projects can now generate documentation for separately configured audiences from approved Symbiospec and implementation evidence. The workflow identifies missing or conflicting source information and keeps review records separate from reader-facing pages.

### Added

- Add `symbio_spec_to_docs`, initially introduced as `symbiospec_to_docs`, for generating and updating configured documentation sets. Each set has its own audience, destination, and review record; unsupported features are omitted and reported. The skill owns its generated documentation. [Pull request 28](https://github.com/jeromeetienne/coding_agent_plugins/pull/28), [rename commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/82b2ebe881040b67423d4f1913b661093a84a343)

## [0.3.0] - 2026-10-30

### Release notes

The collection now supports coordinated batches of related issues and explicit rules for repository folders. The Rules of the Repo provides a single entry point for selecting applicable rule skills and passing their project configuration.

### Added

- Add `issue_batch_workflow` for grouped and ordered sub-issues, with independent groups handled in separate worktrees. Symbiospec proposals can produce grouped and ordered sub-issues. [Pull request 18](https://github.com/jeromeetienne/coding_agent_plugins/pull/18)
- Add `repo_folders_constraints` to define folder responsibilities, permitted dependencies, technologies, and change procedures under human approval. [Pull request 22](https://github.com/jeromeetienne/coding_agent_plugins/pull/22)
- Add `rules_of_the_repo` to select applicable rule skills and supply each skill's configuration. [Pull request 23](https://github.com/jeromeetienne/coding_agent_plugins/pull/23)
- Add reader guides explaining Symbiospec and The Rules of the Repo. [Pull request 17](https://github.com/jeromeetienne/coding_agent_plugins/pull/17), [commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/fede6b4c20528c257af70623b237f485c56e99e4)

### Changed

- Let callers supply the configuration used by `docs_folder_system` and `docs_folder_agents_rules_system`, so the skills can work through The Rules of the Repo or repository instructions. [Pull request 23](https://github.com/jeromeetienne/coding_agent_plugins/pull/23)

## [0.2.0] - 2026-10-27

### Release notes

The shared skills become an independently maintained collection with an MIT license and introductions for people. New skills cover personal coding styles, issue creation, documentation organization, and maintaining approved product specifications with Symbiospec.

### Added

- Add Jérôme Étienne’s personal TypeScript and JavaScript coding style and a first draft of his personal Rust coding style, with unresolved Rust adaptations recorded separately. [TypeScript and JavaScript commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/63b8aabf107cf8cc8ee8cafd9c4de28e9f1424db), [Rust commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/d1c71a9e50149d11f4216d3559d18a64a0911fb1)
- Add `issue_creation` for creating issues, attaching images, and writing linked issue descriptions and comments. [Commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/1135528c1a27f776a024241d60f8f6ebe4134407)
- Add `docs_folder_system` for documentation metadata and folder navigation, and `docs_folder_agents_rules_system` for maintaining agent rules and the glossary. [Pull request 5](https://github.com/jeromeetienne/coding_agent_plugins/pull/5)
- Add `symbio_spec` for initializing and maintaining product specifications and comparing specifications, software, and tests during realignment. [Pull request 14](https://github.com/jeromeetienne/coding_agent_plugins/pull/14)
- Add human-readable introductions explaining each skill's purpose, use, configuration, and installation. [Pull request 6](https://github.com/jeromeetienne/coding_agent_plugins/pull/6)
- License the collection under the MIT license. [Commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/aaab8aee882f8f398e5298145040d4aee5a414ed)

### Changed

- Make this independent repository the authoritative location for skill maintenance and remove temporary package metadata. [Maintenance commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/c427f083ece348a38aa49fdb4bb72893b4924e16), [package metadata commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/2e0511da5f6604dde30e53f367dc5be088c5554d)
- Refocus `bug_triage_workflow` on evidence-based bug priorities and choosing the next stability improvement. Reviews remain read-only, and issue closure requires an explicit request naming the issue. [Commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/0bb25de8a131698b5f28204271c267171724ea7f)

## [0.1.0] - 2026-10-19

### Release notes

The initial collection brings four shared coding-agent workflows together for installation and review: fixing individual issues, reviewing open issues, assessing Git cleanup, and maintaining folder context files.

### Added

- Add `issue_fix_workflow` for fixing one issue through setup, implementation, review, and completion in a temporary worktree. [Commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/46b72f775340e0d92f64d0ebb8ebccd007da0d60)
- Add `bug_triage_workflow` for reviewing open issues and recommending action while leaving issue changes under human control. [Commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/46b72f775340e0d92f64d0ebb8ebccd007da0d60)
- Add `git_cleanup_adviser` for evidence-based advice about branches and worktrees; the review removes nothing. [Commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/46b72f775340e0d92f64d0ebb8ebccd007da0d60)
- Add `context_md_system` for maintaining concise folder purpose, entry points, and rules in `CONTEXT.md` files. [Commit](https://github.com/jeromeetienne/coding_agent_plugins/commit/46b72f775340e0d92f64d0ebb8ebccd007da0d60)

[Unreleased]: https://github.com/jeromeetienne/coding_agent_plugins/compare/0.5.0...HEAD
[0.5.0]: https://github.com/jeromeetienne/coding_agent_plugins/compare/0.4.0...0.5.0
[0.4.0]: https://github.com/jeromeetienne/coding_agent_plugins/compare/0.3.0...0.4.0
[0.3.0]: https://github.com/jeromeetienne/coding_agent_plugins/compare/0.2.0...0.3.0
[0.2.0]: https://github.com/jeromeetienne/coding_agent_plugins/compare/0.1.0...0.2.0
[0.1.0]: https://github.com/jeromeetienne/coding_agent_plugins/tree/0.1.0
