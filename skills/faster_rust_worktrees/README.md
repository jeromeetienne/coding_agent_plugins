# faster_rust_worktrees

**Status: Draft, not yet evaluated on independent repositories.**

## Purpose

Give a coding agent instructions for reusing Cargo build output in independent Rust Git worktrees through copy-on-write cloning. The instructions cover repository discovery, source modification dates, build script path relocation, workflow integration, verification, and maintenance.

This skill consists only of Markdown. No npm package, new repository, executable program, or companion skill is required to install or read this skill. Applying the instructions to a receiving repository is a separate task and follows that repository's rules.

## Install

From a local collection checkout containing the draft:

```bash
npx skills add /absolute/path/to/coding_agent_plugins --skill faster_rust_worktrees
```

After the draft is published in the collection:

```bash
npx skills add jeromeetienne/coding_agent_plugins --skill faster_rust_worktrees
```

Installation adds instructions; installation does not optimize the receiving repository automatically.

## Use and requirements

Example request:

> Use faster_rust_worktrees to examine this Rust repository and propose how its existing worktree workflow can reuse Cargo output. Establish feasibility with the actual build command and file system before implementing the receiving-repository change.

The receiving repository needs Git, Cargo, an existing build to reuse, and a file system capable of copy-on-write cloning. The reference technique uses macOS cloning. Other environments require a real feasibility check; this draft does not claim support for them. Preserve existing commands and configuration. No worktree creation executable is supplied by this skill.

## Evaluation

The first stage writes and reviews this draft. A separate stage will apply the draft to independent real repositories, starting with ripgrep and fd as candidates, record setup effort and manual interventions, measure correctness and efficiency, and improve the instructions. These evaluations have not been performed. Heidrun Data is already optimized and is not the demonstration of reusability.

## Instructions and references

- [SKILL.md](SKILL.md): coding-agent instructions.
- [Technique and limits](references/setup.md): existing implementation reference, Cargo constraints, and maintenance requirements.
