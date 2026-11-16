---
name: faster_rust_worktrees
description: Draft, not yet evaluated on independent repositories. Guide a coding agent in making Rust Git worktrees faster to build and smaller on disk through copy-on-write reuse of Cargo output, correct source dates, and build script path relocation.
---

# Faster Rust worktrees

**Status: Draft.** These instructions have not been evaluated on independent repositories. Do not describe the skill as proven or ready for general adoption.

Guide the receiving repository's Rust worktree optimization. This skill contains Markdown instructions only and does not require a new package or a separate repository. Use existing repository tools where suitable. Read [the technique and its limits](references/setup.md) before changing the receiving repository's worktree workflow.

## Discover the receiving repository

Read the repository rules and worktree instructions. Find the Cargo packages, workspace roots, lockfiles, target folders, build and test commands, command working directories, features, profiles, environment, and package-specific Cargo configuration. Find the configured worktree location, base reference, and optional dependency installation command. Do not assume a package manager, root-level Cargo invocation, or one project's package names.

Preserve a suitable existing Cargo workspace. If independent workspaces prevent shared dependency output, propose consolidation before changing workspace membership. Preserve locked package versions and sources; investigate conflicting locks rather than silently updating dependencies. Run existing tests after a workspace change.

## Establish feasibility

Name the assumption that could prevent reuse and test the smallest representative case against the real receiving repository, actual build command, and actual file system before substantial implementation. Keep exact commands and raw output. A mock clone or successful test on another file system does not establish copy-on-write support here.

Build the original checkout with the commands that worktrees will use. Stop builds in the original checkout while cloning. Keep original and cloned output on the same file system; a nested path alone does not establish this if mounts or symbolic links intervene. Report an unavailable clone or missing build folder explicitly and retain ordinary worktree creation as a comparison.

## Apply the technique

Use the existing worktree creation mechanism where possible. For the requested receiving-repository change:

1. Create a Git worktree at the established location and base reference, retaining the existing branch-fetch policy.
2. Clone the original target folder with an actual copy-on-write operation. Do not substitute hard links, a shared writable target folder, or an ordinary full copy and call the result optimized.
3. Restore original modification dates only for identical regular tracked files and directories with matching contents. Changed files must retain dates that allow Cargo to detect the change.
4. Relocate original-checkout prefixes in cloned Cargo build script output records to the new worktree and preserve record dates. Follow the reference for limits; compiled-in paths are not automatically rewritten.
5. Run the repository's dependency installation command if one exists. Keep a worktree available for diagnosis when installation fails, and report failure.
6. Preserve a way to create an ordinary worktree without the optimization, such as an existing `--without-optimization` option. Do not document an executable command before that executable command exists.

When Issue Fix Workflow is adopted, update the receiving repository's configured worktree creation command in AGENTS.md after verification. Do not change the reusable Issue Fix Workflow skill for one repository. Keep receiving-repository configuration outside the installed skill folder. Writing or reviewing this draft alone does not authorize changing another repository or creating a shared executable tool.

## Verify the receiving-repository change

- Run the same real build command in a new optimized worktree with unchanged sources. Count compiled crates and retain the output; the expected result is zero. Investigate rebuilds before claiming success.
- Change a source file and check actual program or test output. A successful build exit alone does not establish source-change detection. Rebuilding dependent packages can be correct. Restore temporary test changes afterward.
- Check build script paths and independence from the original checkout. Use disposable copies for any check that hides original files; do not rename or remove the developer's working sources.
- Build two worktrees concurrently and confirm independent results. Compare a failing optimized build with ordinary worktree creation when diagnosing a failure.

## Maintenance and report

Explain the receiving repository's existing cleanup commands, if any. For new cleanup behavior authorized by the receiving-repository task, follow [the maintenance requirements](references/setup.md#maintenance). Preview selected paths before removal; do not infer permission to delete from installation of this skill.

Report the exact environment, commands, source changes, correctness checks, and remaining limitations. Separate historical technique results from observations made using this draft. For efficiency evaluation, compare ordinary and optimized worktrees at the same revision with the same compiler, dependency versions, commands, and environment. Repeat measurements of creation time, first-build time, compiled crates, and additional physical disk space; apparent cloned file sizes do not measure additional physical storage.

Independent-repository application and improvements belong to the separately requested evaluation stage. Heidrun Data is already optimized and is not the demonstration of reusability or efficiency. This draft's publication does not establish successful independent adoption.
