# Create, review and maintain user scenarios

## 0. Introduction

### 0.1. Purpose

Use a human-supplied user scenario to start product design, or generate proposed user scenarios from existing Symbiospec. Apply the [shared version check](versioning.md) first and follow [the user scenario format](format-v3.1.0.md#5-user-scenarios). These instructions do not authorize software changes or an audit.

## 1. Establish the source and scope

For a human-supplied user scenario, preserve the person's goal, starting conditions, actions, expected outcome and relevant failure or recovery paths. Ask about information needed to understand the intended journey; do not require all supporting product descriptions before accepting or approving the journey.

For generation from existing Symbiospec, choose and report a bounded scope. Read the relevant approved concepts, Behaviour and User Interface descriptions and their approval evidence. Generate proposals with links to those sources, distinguishing inferred journeys from explicit source statements. Report examined and unexamined areas and ask the human which goals or journeys are missing. Generated proposals can repeat omissions in Symbiospec; the generated set never establishes complete coverage. Do not infer human approval from the approval of source descriptions.

Create one project document per user scenario in `docs/symbio_spec/user_scenarios/` only within authorized work. Maintain the folder overview, folder index and root index. Use the template below with actual values and receiving-project metadata conventions. Never publish placeholders as evidence.

## 2. Walk through Symbiospec

When creating or explicitly reviewing a user scenario, walk through the complete journey using Symbiospec alone. For each step, follow the concept, action, navigation and expected outcome references, including failures and recovery. Record supporting descriptions, missing actions, disconnected navigation, unclear outcomes, contradictions and unresolved product decisions. Link the relevant sections and original approvals; identify the examined specification revision and unreviewed scope.

Do not infer a missing screen or rule from implementation, or invent product choices to make the journey appear supported. A supported journey means only that the examined Symbiospec describes the journey. Record software verification separately, including Software not exercised when appropriate. If a saved coverage examination is needed, follow the existing original examination and summary maintenance procedure and link the examination instead of duplicating the record.

## 3. Design and approve

Present the intended journey and specification findings separately. The human may approve the user scenario with gaps still open. Approval establishes the journey, not every missing screen, action or rule. All user scenarios require human approval, regardless of source.

To resolve a gap, propose a concrete action, expected outcome, reason and affected descriptions. Apply existing authorization where the human already supplied the choice. Otherwise obtain a human decision before adopting new product meaning. Update the responsible Glossary, Behaviour or User Interface descriptions and link the user scenario to those descriptions without copying their rules. Follow [decision maintenance](format-v3.1.0.md#42-decisions) for actual decisions, their sources and approval scope. Approval can cover a user scenario and supporting decisions together only when the human actually authorizes that scope.

## 4. Maintain the approved journey

Apply the [approval, revision and retirement rules](format-v3.1.0.md#53-approval-revision-and-retirement). Put a pending revision in Proposed changes with its motivation, affected descriptions and noticed conflicts. Determine whether the human response requests another proposal, rejects a proposal, or authorizes an exact journey change. Record that response using the existing decision procedure before updating the authorized journey and approval link. Keep document status and Human approval consistent, and retain unresolved proposal scope.

For replacement or retirement, update decision links, affected user scenario references and navigation as required by the format. Check that the retained document still makes the last approved journey and the human decision discoverable.

## 5. Report noticed conflicts

Follow the [review and conflict boundaries](format-v3.1.0.md#54-creation-review-and-conflicts). During rule discussion, report an apparent conflict already noticed by linking the rule and approved user scenario step. State the unresolved choice and leave both approved expectations intact. Report the warning without launching a separate investigation or audit.

## 6. Project document template

Adapt the following template; replace every instruction in angle brackets with actual information or an explicit unknown. For a partly approved document, identify approval at section level.

```markdown
# <User scenario title>

- Created: <actual date>
- Last updated: <actual date>
- Status: <Proposal, Approved, Rejected or Retired; match Human approval>
- Related framing: [User scenarios](README.md)

## 0. Introduction

### 0.1. Purpose

<The person and the goal, with the scope of this document.>

## 1. Source

<Human-supplied or generated by the coding agent; source discussion and links
 to descriptions used; examined and unexamined scope for generation.>

## 2. Human approval

<Proposal, Approved, Rejected or Retired; precise scope and original decision
 links. Explicitly state when approval has not been given.>

## 3. Journey

<Label a proposal until approved.>

### 3.1. Goal and starting conditions

<Person, goal and conditions, with links to existing concepts.>

### 3.2. Actions and expected outcome

<Ordered actions, entry points and expected outcome, linking supporting
 Behaviour and User Interface descriptions or recording missing descriptions.>

### 3.3. Failure and recovery

<Relevant paths and supporting references, or unresolved decisions.>

## 4. Proposed changes

<Pending revisions kept separate from the approved journey, or None.>

## 5. Specification review

<Review date; specification revision and paths; steps reviewed; supporting
 descriptions; missing actions or descriptions; disconnected navigation;
 unclear outcomes; conflicts with links to both descriptions; unresolved
 questions and unreviewed scope. State Not reviewed if no review occurred.>

## 6. Software verification

<Actual checks, evidence, software revision, environment and limitations,
 or Software not exercised. Link original examinations when recorded.>
```

See the [fictional design and conflict example](user_scenario_examples.md) for a complete sequence. The example is guidance, not a project decision or execution evidence.
