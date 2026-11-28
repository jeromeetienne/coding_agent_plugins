# Symbiospec format conversion from 3.1.0 to 3.1.1

## 1. Forward conversion

Read the [3.1.0 definition](format-v3.1.0.md) and [3.1.1 definition](format-v3.1.1.md). Follow the [shared migration procedure](versioning.md#4-prepare-and-apply-migration), including inventory, a verified snapshot, the interruption marker, and atomic version replacement.

During inventory, [inspect existing proposals](proposal_resolution.md#3-inspect-existing-proposals) for open questions, settled wording, and migration reference material. Report proposed cleanup for authorized maintenance. Existing drafts, indexes, decisions, and evidence remain in place during this conversion. There are no obsolete paths or references to replace.

Verify every pre-existing content file byte for byte. Change only the version field in `format-version.md` from `3.1.0` to `3.1.1`, retaining its other metadata. Verify the version field and content again before removing the interruption marker.

## 2. Reverse conversion

On a separate verification copy, change only the version field from `3.1.1` to `3.1.0`. Both versions can represent the same project content. Verify the recovered inventory and bytes against the source snapshot. Authorized proposal maintenance after conversion is separate work. Reversing the version record does not undo that work.

## 3. Verification

Exercise a disposable `3.1.0` folder with open and settled proposal entries, a Glossary definition, and a linked decision. Confirm that inspection identifies the settled entry, both drafts and their links remain available after forward conversion, and reversal reproduces the original inventory and bytes.
