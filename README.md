# Personal Skills

自用 AI 技能集：可复用的开发规范与实用工作流。采用 [Agent Skills](https://agentskills.io/specification) 格式，可通过 [Skills CLI](https://github.com/vercel-labs/skills) 安装，无需单独发布 npm 包。

## 技能

| 技能 | 版本 | 用途 | 下载 |
| --- | --- | --- | --- |
| [cpp-code-standard](skills/cpp-code-standard/SKILL.md) | 1.0.0 | C/C++ 代码编写、修改与审查规范 | [ZIP](cpp-code-standard-1.0.0.zip) |
| [installer-extract](skills/installer-extract/SKILL.md) | 1.0.1 | Windows 应用解包部署与更新处理 | [ZIP](installer-extract-1.0.1.zip) |

## 一条命令安装

需要已安装 Node.js（含 npm/npx）和 Git。

将两个技能安装到 Codex 的用户级目录，供不同项目使用：

```sh
npx --yes skills add Miaoge-Ge/personal-skills --skill cpp-code-standard installer-extract --agent codex --global --yes
```

只安装其中一个：

```sh
npx --yes skills add Miaoge-Ge/personal-skills --skill cpp-code-standard --agent codex --global --yes
```

将技能名换成 `installer-extract` 即可安装另一个。移除 `--global` 则只安装到当前项目；使用其他支持的工具时，可将 `codex` 换成 `claude-code` 或 `cursor`。

也可以交互式选择技能和目标工具：

```sh
npx skills add Miaoge-Ge/personal-skills
```

## 提示词安装

在支持 `$skill-installer` 的 Codex 中，直接发送：

```text
$skill-installer 请从 https://github.com/Miaoge-Ge/personal-skills 安装以下两个技能到用户级技能目录：
- skills/cpp-code-standard
- skills/installer-extract
如果已有同名技能，先比较版本，保留本地自定义修改。
```

其他具备联网和文件操作能力的 AI 编程工具可使用：

```text
请从 https://github.com/Miaoge-Ge/personal-skills 安装 skills/cpp-code-standard 和 skills/installer-extract。
先阅读技能内容，再将两个完整目录（包括 references、agents 等文件）安装到当前工具支持的用户级技能目录。
如果已有同名技能，先比较版本，保留本地自定义修改。完成后报告安装位置和版本。
```

Codex 会自动发现新技能；未出现时可重启。提示词安装方式参考[官方说明](https://learn.chatgpt.com/docs/build-skills)。

## 使用示例

```text
$cpp-code-standard 按规范审查当前修改，指出不符合项，先不要改代码。
```

```text
$installer-extract 检查这个 Windows 安装包，适合解包部署时帮我安装并创建快捷方式。
```

## 版本与维护

`skills/` 保存技能源码，根目录 ZIP 为对应版本快照。版本号记录在各技能 `SKILL.md` 的 `metadata.version` 中；命令安装使用仓库当前版本，固定版本可下载表格中的 ZIP。
