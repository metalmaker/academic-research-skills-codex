# Explicit-Only Personal Skills

This repository contains two manual opt-in skills maintained separately from the
vendored `academic-research-suite`.

| Invocation | Skill | Canonical path |
|---|---|---|
| `$para` | Paragraph Revision Protocol | `skills/para/SKILL.md` |
| `$pro-empirical` | Cautious Empirical Prose | `skills/pro-empirical/SKILL.md` |

## Activation Policy

These skills are **never relevance-triggered**.

They must not be selected because a task happens to involve academic writing,
empirical work, economics, translation, manuscript revision, or a paragraph.

The user must explicitly type the corresponding `$...` token.

The two skills are independent:

- `$para` activates the author-controlled paragraph revision workflow.
- `$pro-empirical` activates the empirical prose style.
- `$para $pro-empirical` activates both for the same passage transaction.

Future style skills may use the same `pro-*` namespace, for example
`$pro-theoretical` or `$pro-mike`.

## Install in Codex

Install the two skills separately from this repository so they appear as separate
`$...` skills:

```bash
python3 "$HOME/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py" \
  --repo metalmaker/academic-research-skills-codex \
  --ref main \
  --path skills/para \
  --method git

python3 "$HOME/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py" \
  --repo metalmaker/academic-research-skills-codex \
  --ref main \
  --path skills/pro-empirical \
  --method git
```

Open a new Codex conversation after installation, then verify with `/skills`.

Expected invocations:

```text
$para
```

```text
$pro-empirical
```

or:

```text
$para $pro-empirical
```

## Update in Codex

Remove the local installed copy, reinstall from `main`, and start a new Codex
conversation so the skill cache is refreshed:

```bash
rm -rf "$HOME/.codex/skills/para" "$HOME/.codex/skills/pro-empirical"
```

Then rerun the two install commands above.

## ChatGPT Web / Other Non-Installed Runtimes

The repository is the canonical source.

A web runtime that has not installed these skills must not reconstruct them from
memory. When the user explicitly invokes a token, fetch the current canonical
skill from this repository and follow it for that task.

Loader mapping:

```text
$para
-> https://github.com/metalmaker/academic-research-skills-codex/blob/main/skills/para/SKILL.md

$pro-empirical
-> https://github.com/metalmaker/academic-research-skills-codex/tree/main/skills/pro-empirical
```

If neither token is present, do not load or apply either skill.

A minimal project-level loader instruction for ChatGPT Web is:

```text
When I explicitly type $para or $pro-empirical, fetch the current corresponding
skill from metalmaker/academic-research-skills-codex on GitHub and follow it.
Never activate either skill from task relevance or prior use.
```

That loader contains only routing information. The operative instructions remain
in this repository.
