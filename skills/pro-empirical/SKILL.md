---
name: pro-empirical
description: >
  EXPLICIT INVOCATION ONLY. Use this skill only when the user explicitly invokes
  the literal token $pro-empirical. Never infer or auto-trigger it from academic,
  empirical, economics, manuscript, or editing context. Applies a cautious,
  evidence-led empirical social-science prose style while preserving substantive
  meaning and authorial control.
metadata:
  version: "0.1.0"
  activation: "explicit-only"
  invocation: "$pro-empirical"
  family: "pro-*"
---

# Cautious Empirical Prose

## Activation Gate

This skill is **manual opt-in only**.

Activate it only when the current user explicitly invokes the literal token
`$pro-empirical`.

Do **not**:

- infer activation from an empirical-paper, economics, statistics, manuscript, or
  editing task;
- carry activation into an unrelated task or new passage;
- suggest or silently apply this style;
- treat prior use as continuing consent.

When invoked together with `$para`, the style remains active for that passage's
revision transaction and then expires.

When invoked without `$para`, it applies only to the current requested writing
or rewriting task unless the user explicitly defines a broader scope.

This skill does not activate `$para`.

## Purpose

Write empirical social-science prose that is precise, measured, evidence-led, and
recognizably authorial.

The goal is not to imitate generic polished academic text. The goal is to make
disciplined choices about what the evidence warrants, what the reader needs, and
what can be left unstated.

Do not optimize for AI detectors. Do not insert errors, awkwardness, or random
variation to appear human.

"Human" prose here means **authorial selectivity**: prioritizing some facts over
others, stopping when the evidence has done the work, and avoiding unnecessary
meta-commentary.

## Canonical Style Profile

Load and follow `profile.yaml` in this skill directory. The operational rules
below resolve ambiguities in that profile.

## Lexical Profile

Prefer:

- precise technical terms over metaphorical or evaluative language;
- discipline-specific terminology when it improves identification or interpretation;
- measured quantifiers and scope qualifiers;
- concrete verbs over strings of abstract nouns.

Useful authorial verbs include:

- `we examine`
- `we estimate`
- `we find`
- `the estimates show`
- `the pattern is consistent with`
- `this suggests`
- `the design identifies`
- `the data do not identify`

Avoid routine use of promotional or certainty-signaling language such as:

- `obviously`
- `clearly`
- `undoubtedly`
- `importantly`
- `notably`
- `crucially`
- `remarkably`
- `groundbreaking`

Avoid `prove` and `definitely` outside settings where proof or certainty is
literally established.

Do not claim novelty with `novel`, `first`, or equivalent wording unless the
evidence for that priority claim is adequate and the claim is necessary.

## Syntax

Favor moderate sentence length.

Subject-initial sentences with `we` are welcome when they make agency,
estimation, or design choices explicit.

Embedded clauses such as `consistent with`, `conditional on`, and, where
substantively appropriate, `as if`, may be used to express qualified
interpretation.

Use parallel structure when it genuinely clarifies comparable objects. Do not
manufacture symmetry merely to make the prose sound polished.

Vary paragraph and sentence architecture according to the argument. Do not force
every paragraph into the same template.

## Empirical Paragraph Logic

A common structure is:

`claim -> evidence -> implication`

This is a default reasoning pattern, not a mandatory paragraph template.

A paragraph may instead:

- report one empirical result and stop;
- define one estimand;
- explain one design choice;
- present one limitation;
- end with a number or factual observation.

Do not append a takeaway sentence when the implication is already evident.

## Narrative and Story

Empirical writing should have a research story without becoming promotional.

A useful high-level sequence is often:

1. the empirical or measurement problem;
2. the unresolved tension or identifying question;
3. the design or comparison that makes the question observable;
4. the headline evidence;
5. the implication for the estimand, interpretation, or research practice.

Do not replace this sequence with a methods inventory or a list of reviewer
concerns.

For abstracts and introductions, foreground the substantive problem and the
empirical tension before secondary diagnostics, robustness details, or procedural
defenses unless those details are themselves the contribution.

## Measured Certainty

Use certainty proportional to the design.

Prefer:

- `we find`
- `the estimates indicate`
- `the pattern is consistent with`
- `this suggests`
- `within this sample/design/case`

Avoid unsupported deterministic language.

State scope conditions directly.

Example:

Good:
> The design identifies the response-format bundle, not its individual components.

Avoid:
> This limitation does not undermine the result because the design was not intended to identify individual components.

## Economics-Specific Rules

### Estimand first

Define what is estimated before assigning a broader interpretation.

Distinguish, when relevant, between:

- sample or cell estimates;
- fixed-procedure estimands;
- mixture or policy-weighted estimands;
- procedure-independent or transportable interpretations.

Do not let rhetoric collapse distinct estimands.

### Conditional scope

Use explicit conditions when a conclusion depends on a maintained assumption,
target population, procedure, equilibrium concept, or identifying restriction.

### Revealed-preference language

`acts as if` can be useful, but only when it describes an observable behavioral
mapping and does not smuggle in an unsupported claim about subjective beliefs,
latent preferences, cognition, or mechanism.

### Tendencies, not determinism

When the evidence supports a tendency or association, write it as such.

Do not upgrade a reduced-form empirical pattern into a mechanism.

## Contrastive Transitions

`However`, `Conversely`, `By contrast`, and `Whereas` are useful when a
real comparison is being made.

Do not build a paragraph around habitual antithesis.

Reduce unnecessary use of:

- `rather than`
- `not X but Y`
- repeated `while X, Y`
- repeated `although X, Y`

Contrast should carry analytical content, not merely rhythm.

## Signposting

Explicit signposts such as `First`, `Second`, and `Finally` are allowed when
the reader genuinely needs an ordered sequence.

Do not use numbered or four-part scaffolds merely to create an impression of
completeness.

If two or three points connect naturally in prose, write them naturally.

## Anti-Defensive Writing

Do not write the manuscript as if it were a response letter to imaginary reviewers.

Avoid habitual constructions such as:

- `This does not imply...`
- `This does not establish...`
- `It is important to emphasize...`
- `One possible concern is...`
- `To address this concern...`
- `These limitations do not undermine...`
- `This limitation should not be interpreted as...`

When a boundary matters, state the boundary directly.

Good:
> The data cover two deployment cases.

Usually worse:
> It is important to emphasize that these findings should not be interpreted as applying to all LLMs.

Use the second form only when the interpretive risk genuinely requires explicit
correction.

## Anti-Template Rules

Avoid recurrent LLM-like rhetorical habits:

- every paragraph ending in a slogan or implication;
- repeated thesis statements across Abstract, Introduction, Discussion, and
  Conclusion;
- contribution lists whose only purpose is artificial completeness;
- repeated caveat-then-defense structures;
- synonym cycling for defined technical terms;
- excessive abstract nouns such as `framework`, `validity`, `portability`,
  `implication`, and `distinction` when a concrete subject and verb will do;
- perfectly balanced sentences repeated throughout a section.

Technical consistency outranks lexical variety. If one estimand has a defined name,
keep that name.

## Section-Specific Guidance

### Abstract

The abstract should normally establish:

- why the empirical question matters;
- what was compared or identified;
- the most informative result;
- the interpretation that follows.

Do not spend scarce abstract space paying every reviewer debt. Secondary
robustness checks belong there only if they materially change the headline
interpretation.

### Introduction

Build the unresolved problem before listing design details.

Position the closest literature directly. Do not manufacture a long numbered
contribution list if the contribution can be stated more naturally.

### Methods

Prefer operational precision. Methods can be denser and more technical than the
rest of the paper.

Do not decorate procedural details with unnecessary narrative sentences.

### Results

Report estimates, uncertainty, and comparisons directly.

Interpret only what is needed to connect the result to the research question.

### Discussion

Prioritize interpretation over recap.

State important limitations once and directly. Do not convert each limitation
into a defense.

### Conclusion

Do not rewrite the abstract. End with the research implication that survives the
paper's scope conditions.

## Revision Discipline

A style edit must not silently change:

- data;
- signs or magnitudes;
- statistical uncertainty;
- causal strength;
- sample or population scope;
- identification claims;
- model assumptions;
- citations;
- defined estimands.

If stronger or weaker wording would change the scientific claim, flag the issue
instead of treating it as a style choice.

## Interaction with Other `pro-*` Skills

This skill is one member of a style namespace.

Future examples may include:

- `$pro-theoretical`
- `$pro-mike`

Do not blend those styles unless the user explicitly invokes more than one and
specifies how to combine them.

If multiple `pro-*` skills conflict, ask the user which style has priority.

## Canonical-Source Rule

The repository version of this file and its `profile.yaml` are the canonical
specification.

When this skill is not locally installed but the user invokes
`$pro-empirical` in a runtime that can read GitHub, load the current canonical
files from:

`https://github.com/metalmaker/academic-research-skills-codex/tree/main/skills/pro-empirical`

Do not rely on an older remembered copy.
