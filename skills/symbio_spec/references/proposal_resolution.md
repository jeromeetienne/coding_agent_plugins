# Resolve and verify Symbiospec proposals

Use `proposals/` for questions that still need a decision. Each entry in `proposals/index.md` identifies the remaining question or questions and links to the active draft. Mark deferred questions so readers can see their status.

## 1. Update a proposal after a decision

1. Record the outcome and available evidence before changing the draft. Use an existing decision record when it already covers the outcome. Otherwise, record an actual human decision under [Decisions](format.md#42-decisions). Record the precise scope of a partial decision. When the human decides to withdraw a proposal, record acceptance of the withdrawal as the outcome and name the withdrawal as its scope. If a proposer withdraws a draft without a human decision, record the withdrawal and its source in the original review issue or a maintained review record outside Proposals. Verify that readers can reach that record from the review history before removing the draft.
2. Apply accepted wording to the affected specification within the authorized task. Link the specification to the original decision and update the affected indexes and topic summaries. Track pending implementation in the decision or the implementation issue.
3. Before removing wording needed as evidence, add a link from the decision or review record to the draft at the Git revision that contains the wording. For a draft that exists only in local changes, preserve the evidence in the decision or review record before editing the draft. Move source material still needed for a migration to an appropriate reference location under `docs/symbio_spec/`, outside `proposals/`. Update maintained links to the preserved evidence, the new source location, or the current specification as appropriate.
4. If questions remain unresolved, keep those questions and their supporting context in the draft, link to the decisions on settled parts, and remove settled wording. Update the index entry to describe the remaining questions. If every question has been accepted, rejected, or withdrawn, remove the draft and its active index entry. If the index is retained without entries, state that no proposals are awaiting a decision.

## 2. Verify the active index

Before reporting related work complete:

- Compare the draft files under `proposals/` with `proposals/index.md`. Every draft must have an index entry, and every proposal entry must lead to a draft with an unresolved question. Check that deferred questions are marked. An empty index must have no draft files.
- Follow the affected links. From the specification, find the approval for accepted wording. From the decision indexes, find the original decisions and follow acceptance links to the approved wording. From any standing proposal, find its remaining questions and decisions on settled parts. Verify links to historical drafts and moved migration sources where applicable.
- Report any remaining stale entry or unresolved link with its location and the work still needed.

## 3. Inspect existing proposals

During initialization or forward migration, inspect the proposal draft files and index entries and distinguish open questions from recorded decisions, approved specification wording, and material still needed as a migration reference. Use existing approval evidence. Where an outcome is uncertain, preserve the question for review.

During migration, make only the changes defined by the published conversion. Note any additional cleanup and the evidence for it. During authorized initialization or maintenance, use the procedure above to route the material and verify the index. Remove review handoffs and inventories with no open question from Proposals and its index after preserving useful evidence and fixing affected links.

## 4. Example of a partly accepted Glossary proposal

The draft `proposals/saved-view.md` asks whether a Saved View is a named set of filters and whether teammates can share a Saved View. The human accepts the definition and defers sharing.

| Location | After the first review |
| --- | --- |
| Glossary | Publish “A Saved View is a named set of filters” in `glossary/saved-view.md`. Add the Glossary index entry and link the definition to the original acceptance decision. |
| Decisions | Record and index the acceptance of the definition and the deferral of sharing. Link to the Glossary entry and preserve the original two-question draft by linking to its Git revision. |
| Proposals | Keep “Can teammates share a Saved View?” in the draft and mark the question deferred in the draft and index. Remove the accepted wording from the draft and link to the decisions. |

The human later rejects sharing. Record and index the rejection and link it to the earlier deferral. Remove `proposals/saved-view.md` and its entry in `proposals/index.md`. The Glossary still links to its acceptance. The Decisions index leads to the rejection and the earlier decisions, which lead to the original draft at its Git revision.
