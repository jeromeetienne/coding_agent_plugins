# Technique and limits

**Status: Supporting reference for a draft skill.** This document describes the existing technique and the checks a coding agent should make when applying the skill. It does not provide or require a new executable package.

## Existing reference implementation

Read [localai_rust worktree_tools](https://github.com/heidrun-org/localai_rust/tree/main/packages/worktree_tools) for the original implementation and its own commands and tests. Those commands belong to that repository; do not present those commands as installed by this skill or copy repository-specific package names into another project.

The technique was applied previously in Heidrun Code and localai_rust. Historical results describe those implementations; they do not evaluate this draft's reusability.

## Shared Cargo output

Reuse an existing suitable Cargo workspace and its checkout-local target folder. When consolidating independent workspaces is needed, compare locked package identities, versions, sources, and dependency edges before and after. Starting from the largest old lockfile may reduce changes, but does not prove dependency preservation. Conflicting locks require an explicit decision.

Inspect Cargo's actual target directory, including environment variables and configuration, rather than assuming the folder is named `target`. Keep output separate from tracked source. A shared writable target directory across worktrees can serialize builds and mix branch output; each worktree instead needs an independent copy-on-write clone.

Run Cargo from the same directories and with the same arguments and environment as the real build and test commands. Invoking Cargo at a workspace root can select different dependency features and miss configuration from a package directory. Apply this rule to maintenance commands too.

## Copy-on-write clone

The macOS reference uses `clonefile` through Python, with `cp -c -R -p` as a fallback. Both are examples from the reference implementation, not executable files shipped with this skill. Prove the chosen operation succeeds on the actual file system. An ordinary copy is not evidence of shared physical storage.

The original checkout must be built first and remain stable during cloning. Missing output or a failed clone must be reported as ordinary worktree creation or an explicit failure, rather than successful optimization. Preserve a comparison without optimization.

## Source dates and build script records

Git writes newly checked-out sources with new modification dates. Cargo can therefore rebuild unchanged packages even when compiled output was cloned. Restore dates only when regular tracked file contents match. For directories, check matching entries and contents relevant to build-script watches; do not restore dates on changed or uncertain trees. Do not follow symbolic links blindly.

Build scripts can write absolute checkout paths into `target/<profile>/build/<unit>/output`. Relocate the original checkout's path prefixes to the corresponding worktree paths in cloned records and keep record dates. Find the actual target and profile directories, including custom profiles or cross-compilation layouts, before selecting records.

This operation does not rewrite paths embedded in compiled programs, arbitrary generated files, native compiler caches, or external state. Verify source-change detection and independence from the original checkout. Treat untested path layouts and Cargo versions as unknown.

## Maintenance

A receiving-repository task may need two cleanup operations:

- Select target folders in registered worktrees whose output has not changed for a configured number of days. Exclude the main checkout and preserve sources. Modification age is a heuristic; an unchanged build may read output without updating modification dates.
- Select obsolete hashed output in the active checkout by running every build variant to preserve, in the correct package directory, with `CARGO_LOG=cargo::core::compiler::fingerprint=debug`. Keep the union of units identified by successful commands. A failing command or unrecognized log must prevent removal. Preserve unknown files and incremental output unless their non-use can be established.

Both operations should preview selected paths and require authorization for removal. Stop builds before removal or use an appropriate locking mechanism. Cargo debug logs are not a stable public interface; inspect actual output rather than assuming a parser remains valid. Configured commands may themselves build out-of-date packages even during a removal preview.

## Evaluation evidence

For independent-repository evaluation, keep source revision, compiler, dependencies, command working directories, features, profiles, and environment fixed between ordinary and optimized worktrees. Warm the original checkout first, repeat measurements, and retain raw commands and logs. Report setup effort and manual help separately from runtime savings. Measure additional physical disk use rather than adding apparent sizes of shared cloned files.

A controlled synthetic test or an already optimized repository cannot establish that a coding agent can apply this draft successfully to an unfamiliar repository.
