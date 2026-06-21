# CLAUDE.md

这是**景一的 Claude Code 技能安装库**。

## 仓库内容

- `skills/` — 自定义技能（风格改写、选题脑暴、知识管线）
- `commands/` — 斜杠命令（/fable-rewrite、/fable-brainstorm、/fable-pipeline）
- `hooks/` — 自动化钩子（预留）
- `rules/` — 全局规则（预留）

## 安装方式

```bash
git clone https://github.com/fable-cc/github-.git ~/.claude/fable-skills
```

然后将 skills 和 commands 目录链接到 Claude Code 配置目录。

## 核心生态

| 仓库 | 用途 |
|------|------|
| `fable-castle` | 寓言城堡主站（Jekyll） |
| `knowledge-pipeline` | 自动化知识引擎（Python） |
| `github-` | 本仓库 — Claude Code 技能库 |
| `vault-backup` | Obsidian 知识库备份 |

## 写作时请注意

- 始终先阅读 fable-castle/03-内容样本/ 中的至少1篇样本
- 严格遵循 skills/fable-style.md 中的风格DNA
- 改写完成后对照冶炼标准4条自检
