# Personal Skills

[简体中文](README.md) | [English](README.en.md)

自用 AI 技能集：可复用的开发规范与实用工作流。采用 [Agent Skills](https://agentskills.io/specification) 格式，可通过 [Skills CLI](https://github.com/vercel-labs/skills) 安装，无需单独发布 npm 包。

## 技能

| 技能 | 版本 | 用途 |
| --- | --- | --- |
| [cpp-code-standard](skills/cpp-code-standard/SKILL.md) | 1.0.1 | C/C++ 代码编写、修改与审查规范 |
| [installer-extract](skills/installer-extract/SKILL.md) | 1.0.2 | Windows 应用解包部署与更新处理 |

## 一条命令安装

需要 Node.js（含 npm/npx）和 Git。按使用的工具任选一条，将全部技能安装到用户级目录：

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

只装一个技能时，将 `'*'` 换成对应技能名；仅安装到当前项目时，移除 `--global`。

## 提示词安装

也可以将下面的提示词发给具备联网和文件操作能力的编程助手：

```text
请从 https://github.com/Miaoge-Ge/personal-skills 安装 skills/cpp-code-standard 和 skills/installer-extract。
先阅读技能内容，再将两个完整目录（包括 references、agents 等文件）安装到当前工具支持的用户级技能目录。
如果已有同名技能，先比较版本，保留本地自定义修改。完成后报告安装位置和版本。
```

Codex 中可在提示词前加 `$skill-installer`，调用内置安装技能。

## 使用示例

```text
$cpp-code-standard 按规范审查当前修改，指出不符合项，先不要改代码。
```

```text
$installer-extract 检查这个 Windows 安装包，适合解包部署时帮我安装并创建快捷方式。
```

## 版本与维护

`skills/` 保存技能源码，版本号记录在各技能 `SKILL.md` 的 `metadata.version` 中。命令安装使用仓库当前版本。
