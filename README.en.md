# Personal Skills

[简体中文](README.md) | [English](README.en.md)

A personal collection of reusable coding standards and practical AI agent workflows. Uses the [Agent Skills](https://agentskills.io/specification) format and installs through the [Skills CLI](https://github.com/vercel-labs/skills), with no separate npm package required.

## Skills

| Skill | Version | Purpose |
| --- | --- | --- |
| [cpp-code-standard](skills/cpp-code-standard/SKILL.md) | 1.0.0 | Standards for writing, modifying, and reviewing C/C++ code |
| [installer-extract](skills/installer-extract/SKILL.md) | 1.0.1 | Extract and deploy Windows applications, including update handling |

## Install with one command

Requires Node.js (including npm/npx) and Git. Choose the command for your tool to install all skills at user scope:

**Codex**

```sh
npx --yes skills add Miaoge-Ge/personal-skills --skill '*' --agent codex --global --yes
```

**Claude Code**

```sh
npx --yes skills add Miaoge-Ge/personal-skills --skill '*' --agent claude-code --global --yes
```

**Cursor**

```sh
npx --yes skills add Miaoge-Ge/personal-skills --skill '*' --agent cursor --global --yes
```

To install just one skill, replace `'*'` with its name. To install only in the current project, omit `--global`.

## Install with a prompt

Send this prompt to a coding assistant with network and file access:

```text
Install skills/cpp-code-standard and skills/installer-extract from https://github.com/Miaoge-Ge/personal-skills.
Read the skills first, then install both complete directories (including references, agents, and other supporting files) into this tool's supported user-level skills directory.
If a skill with the same name already exists, compare versions first and preserve local customizations. Report the installation paths and versions when done.
```

In Codex, prefix the prompt with `$skill-installer` to use the built-in installer skill.

## Usage examples

```text
$cpp-code-standard Review the current changes against the coding standards and report violations. Do not modify the code yet.
```

```text
$installer-extract Inspect this Windows installer. If extraction-based deployment is suitable, deploy the application and create a shortcut.
```

## Versions and maintenance

Skill sources live in `skills/`. Each skill records its version in `metadata.version` within `SKILL.md`. CLI installation uses the current repository version.
