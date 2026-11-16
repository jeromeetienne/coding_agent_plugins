# Symbiospec to documentation

- Created: 16 November 2026
- Last updated: 16 November 2026
- Status: Maintained explanation of Symbiospec to documentation for people
- Related framing: [About Symbiospec](README.md)
- Related rules: [docs_folder_system](../../skills/docs_folder_system/SKILL.md)
- Related issue: [Issue 124](https://github.com/jeromeetienne/coding_agent_plugins/issues/124)

## 1. Purpose

This page is for a person deciding how approved product information can become useful documentation. The skill `symbio_spec_to_docs`, named Symbiospec to documentation, creates and updates documentation for a configured audience from approved Symbiospec and current implementation evidence.

Symbiospec describes intended product meaning. Audience documentation explains how a reader accomplishes a task. The documentation can follow the reader’s workflow instead of reproducing the six specification areas. A project can have separate documentation sets for users and developers, with different content and destinations.

## 2. Sources and audience

Generation requires the installed `symbio_spec` skill, the project’s Symbiospec data and a complete configuration supplied by the caller. The configuration chooses the audience, goals, included and excluded topics, source evidence, output location, presentation, review record and update procedure. The coding agent does not silently choose an audience or configuration. Configuration belongs to the receiving project, outside the reusable skill.

A documented feature needs both approved Symbiospec and current implementation evidence. An approved but unimplemented feature stays out of the instructions and is reported as a gap. An implemented feature without an approved description also stays out until the product information is resolved. Generation does not silently change approved product meaning to match the application.

Both related skills use the shared version check and automatic migration procedure before normal work with project data. The latest published format is currently `3.1.0`; the authoritative [versioning reference](../../skills/symbio_spec/references/versioning.md) defines migration and stop conditions.

## 3. A practical example

Suppose a fictional note editor has an approved rule for saving a Note and implementation evidence supporting Save, success confirmation and failure messages. The configured audience is people writing Notes; the requested topic is saving a Note.

The resulting help explains how to open a Note, edit the text, select Save and recognize success or failure, provided the sources support each instruction. The help uses the application’s actual labels. The help does not require readers to understand specification folders or implementation details. If automatic saving is approved but unimplemented, the help does not promise automatic saving.

A separate review record maps the help sections to approval and implementation evidence, records omissions and conflicts, and distinguishes source inspection, executed tests and actual application exercises. Without application access, the record states the verification limit; source inspection is not reported as a successful live check.

This example is illustrative. The [configured documentation example](documentation_example.md) shows a complete sample configuration, output and review record; the example is not execution evidence.

## 4. Updates, ownership and publication

Generated documentation belongs to `symbio_spec_to_docs` in the configured destination. Updates can rewrite passages edited by people. Durable corrections therefore belong in Symbiospec or configuration, followed by regeneration. Source mapping identifies affected pages when approved product meaning or implementation changes; accurate, unrelated pages are preserved.

Writing pages, reviewing content, building documentation and publishing a website are separate results. A publication destination in configuration does not itself authorize deployment. Publication needs authorization and the configured checks, including real-browser verification when website publication is in scope. A successful build alone does not establish human acceptance or correct application instructions.

## 5. Further reading

- [symbio_spec_to_docs overview](../../skills/symbio_spec_to_docs/README.md): adoption requirements and expected results.
- [Skill instructions](../../skills/symbio_spec_to_docs/SKILL.md) and [configuration reference](../../skills/symbio_spec_to_docs/references/configuration.md): authoritative procedures and required values.
- [Symbiospec workflows and audits](workflows.md): maintaining the approved information that documentation uses.
- [Symbiospec to UX](symbio_spec_to_ux.md): the separate draft skill for proposing screens and navigation.
