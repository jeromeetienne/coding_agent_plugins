# Symbiospec to UX

- Created: 16 November 2026
- Last updated: 16 November 2026
- Status: Maintained explanation of the draft Symbiospec to UX skill for people
- Related framing: [About Symbiospec](README.md)
- Related rules: [docs_folder_system](../../skills/docs_folder_system/SKILL.md)
- Related issue: [Issue 124](https://github.com/jeromeetienne/coding_agent_plugins/issues/124)

## 1. Purpose and current status

This page is for a person deciding how approved Symbiospec can guide proposals for screens and navigation. The skill `symbio_spec_to_ux`, named Symbiospec to UX, addresses user experience: how a person finds information, moves through the product and performs permitted actions.

**The skill is a draft and has not been tested on a real project.** The test project and trial approach remain undecided. The workflow is available for deliberate evaluation; written instructions and document checks do not establish readiness.

## 2. From product meaning to interface choices

The starting point is approved Symbiospec for a selected task: product concepts, expected behaviour, existing interface decisions, visual rules and platform constraints. The shared [versioning procedure](../../skills/symbio_spec/references/versioning.md) checks project data before normal work. Missing product decisions stay explicit rather than becoming invented screens, permissions or outcomes.

The skill organizes a proposal around four questions:

| Concern | Question for the interface proposal |
| --- | --- |
| Objects | Which recognizable things does the person identify and act on? |
| Relationships | How are those things connected, and which connections should navigation expose? |
| Calls to action | What actions can the person take, under which conditions? |
| Attributes | Which details does the person need to see or edit for the task? |

These questions help connect product meaning to views and navigation. Every noun does not need a screen. Permissions and outcomes come from approved Behaviour, while choices about grouping information remain proposals until approved. The method does not choose a visual framework or styling system.

## 3. A practical example

Consider a fictional note editor whose approved Symbiospec defines a Note, permits opening and saving a Note, and describes the Note title and text. For the task of editing a Note, an interface proposal might contain:

- A list showing Note titles with a way to open a Note.
- A Note view showing the title and text, with the permitted Save action.
- A return path to the list and the approved save success and failure states.

The proposal links the Note definition and save behaviour to their approved sources. The list, grouping and return path are proposed interface choices unless already approved. If deletion permissions are absent from Symbiospec, the proposal does not assume that every Note can be deleted.

A walkthrough with a fictional Note checks whether the proposed navigation supports opening, editing, saving and returning to the list, including the supported failure path. The walkthrough can reveal an unresolved retry decision or a missing route. Reading the proposal does not prove that an application implements the journey. This example is illustrative and is not the required real-project trial.

## 4. Review and evidence

The output brings together the four lists, proposed screens and navigation, representative task walkthroughs, source links, alternatives and open decisions. Human review decides which choices to accept, reject, revise or defer. Within authorization, accepted interface choices become User Interface specifications; concept definitions remain in Glossary, outcomes in Behaviour and reusable visual rules in Styling.

A request for an interface proposal does not authorize implementation or a prototype. Proposal approval, prototype observations and checks of implemented software are distinct results. To establish readiness, the draft still needs an agreed real project with meaningful interface decisions, a trial, recorded feedback and human acceptance of the readiness change.

## 5. Further reading

- [symbio_spec_to_ux overview](../../skills/symbio_spec_to_ux/README.md) and [skill instructions](../../skills/symbio_spec_to_ux/SKILL.md): current status, authoritative workflow and trial requirements.
- [User scenarios workflow](workflow_user_scenarios.md): user scenarios, approval and the distinction between specification review and software verification.
- [Symbiospec to documentation](symbio_spec_to_docs.md): the separate skill for audience guidance supported by approval and implementation evidence.
