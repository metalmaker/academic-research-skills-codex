---
name: para
description: >
  EXPLICIT INVOCATION ONLY. Use this skill only when the user explicitly invokes
  the literal token $para. Never infer or auto-trigger it from manuscript editing,
  translation, academic writing, revision, or prior use. Provides an
  author-controlled paragraph-by-paragraph revision protocol with a hard approval
  gate before any file edit.
metadata:
  version: "0.1.0"
  activation: "explicit-only"
  invocation: "$para"
  scope: "passage-transaction"
---

# Paragraph Revision Protocol

## Activation Gate

This skill is **manual opt-in only**.

Activate it only when the current user explicitly invokes the literal token
`$para`.

Do **not**:

- infer activation because the task involves a manuscript, paragraph, translation,
  economics, academic writing, or revision;
- activate it because it was used earlier in another passage or conversation;
- suggest that it should be activated;
- silently apply its workflow.

A new passage requires a new `$para` invocation.

Once invoked for a passage, the skill remains active only for that passage's
revision transaction and ends when one of the following occurs:

1. the approved edit is completed and verified;
2. the user explicitly cancels the transaction;
3. the user switches to a different passage.

If the user invokes `$pro-empirical` in the same passage transaction, apply that
style skill only to proposed or approved English prose. It does not alter the
faithful-translation stage.

## Purpose

Keep substantive control with the author. The model may diagnose, plan, and edit,
but it must not skip from reading a passage directly to rewriting it.

The default sequence is:

`SOURCE -> FAITHFUL TRANSLATION -> DISCUSSION -> REVISION PLAN -> AUTHOR APPROVAL -> EDIT -> VERIFY`

Do not collapse these stages unless the user explicitly instructs you to do so.

## Stage 0: Establish the Active Source

Identify the exact passage and the authoritative working file/version.

If the user supplied the passage directly, use that text.

If the user identified a file, section, paragraph, or manuscript version, read the
actual current source before answering. Do not substitute a remembered or older
copy.

Do not modify frozen or historical versions unless the user explicitly authorizes
that exact file.

## Stage 1: Faithful Chinese Translation

The first response for an English passage is a faithful Chinese translation.

Requirements:

- preserve the original meaning, uncertainty, scope, causal strength, and logical
  order;
- preserve technical distinctions, notation, equations, citation keys, labels,
  numbers, model names, and defined terminology;
- translate what the passage says, not what it should have said;
- do not silently repair scientific, logical, rhetorical, or grammatical problems;
- do not add reviewer concerns, missing caveats, literature, or interpretation;
- do not propose revisions in this stage.

If a phrase has no clean Chinese equivalent, give the natural Chinese rendering
and retain the English technical term in parentheses where useful.

After the translation, stop unless the user has explicitly asked a question that
must be answered in the same turn.

## Stage 2: Author Questions and Diagnosis

The author controls the agenda.

Answer the user's specific questions about the passage. Relevant dimensions may
include:

- scientific meaning or identification;
- estimand definition;
- logic and internal consistency;
- narrative role in the paper;
- relation to preceding or following paragraphs;
- evidence-to-claim alignment;
- terminology;
- rhetoric, clarity, or defensive writing;
- likely reader interpretation.

Do not rewrite the passage merely because a problem is visible.

Distinguish source-supported facts from your own inference or editorial judgment.

## Stage 3: Revision Plan

When the user asks how the passage should change, propose a plan before editing.

Use only the categories that are actually relevant:

### Scientific issue
What substantive claim, scope condition, estimand, identification statement, or
evidentiary link needs attention.

### Narrative issue
What role the paragraph should play in the paper's argument and whether information
is arriving too early, too late, or in the wrong order.

### Rhetorical issue
What makes the prose repetitive, defensive, templated, opaque, or unnecessarily
technical.

### Concrete revision plan
State exactly what would be changed, moved, cut, combined, or retained.

The plan should identify the minimum necessary scope of the edit.

Then stop. Do not edit the file.

## Stage 4: Hard Approval Gate

No file edit is permitted until the user explicitly approves the revision plan.

Valid approval must be unambiguous, for example:

- "通過，照這個方案改"
- "好，修改"
- "Approved; implement this plan."

Questions, partial agreement, discussion, or silence are not approval.

If the user modifies the plan, update the plan and wait for approval again.

## Stage 5: Local Edit

After approval:

1. edit only the authorized working version;
2. make only the approved local change;
3. preserve all scientific content not covered by the approved plan;
4. preserve citations, notation, labels, cross-references, and numerical values
   unless the approved plan explicitly changes them;
5. do not opportunistically rewrite adjacent sections.

If another passage appears to require a coordinated change, flag it to the user.
Do not edit it automatically.

## Stage 6: Verification

After editing, verify at minimum:

- the new prose implements the approved plan;
- the scientific meaning has not drifted;
- numbers, signs, units, citations, equations, and defined terms remain consistent;
- no unauthorized file or section changed;
- the target source still parses or compiles when a lightweight check is appropriate.

Do not launch broad re-analysis or expensive computation unless required by the
approved change.

## Stage 7: Report the Edit

Return a concise record:

- what changed;
- where it changed;
- any necessary before/after excerpt or focused diff;
- any unresolved consistency issue that requires the author's decision.

Do not turn the report into a new review of the whole manuscript.

## Locality Rule

This protocol is deliberately conservative about collateral edits.

If changing one paragraph may require consistency changes elsewhere, say where and
why. The author decides whether to open a new `$para` transaction for those
passages.

## Interaction with Style Skills

`$para` is a workflow skill, not a prose-style skill.

It must not automatically invoke `$pro-empirical`, `$pro-theoretical`,
`$pro-mike`, or any future style skill.

Likewise, a style skill does not activate this workflow.

The intended combinations are:

- `$para`: paragraph workflow only;
- `$pro-empirical`: empirical prose style only;
- `$para $pro-empirical`: paragraph workflow plus empirical prose style for the
  revision stage.

## Canonical-Source Rule

The repository version of this file is the canonical specification.

When this skill is not locally installed but the user invokes `$para` in a
runtime that can read GitHub, load the current canonical file from:

`https://github.com/metalmaker/academic-research-skills-codex/blob/main/skills/para/SKILL.md`

Do not rely on an older remembered copy.
