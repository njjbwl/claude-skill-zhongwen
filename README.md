# 🇨🇳 Claude Code 中文终端界面壳 / Chinese Terminal UI Shell

> 让 Claude Code 的终端界面穿上中文外衣。
> Wrap Claude Code's CLI in a Chinese-language terminal UI.

## 效果预览 / Preview

每次对话自动显示中文顶栏和底栏：

```
╭─ 💬 对话: 开发会话 · 🤖 模型: claude-sonnet-4-6 · 📋 模式: 开发 ────────────────╮
│
  你好！有什么可以帮你的？
╰─ ⌨ /帮助 看命令 · /清屏 清屏 · /模型 切换模型 · Ctrl+C 退出 ──────────────────────╯
```

还支持中文命令映射：输入 `/清屏` 提示 `/clear`，输入 `/模型` 提示 `/model`，等等。

## 安装 / Installation

### 前置要求 / Prerequisites

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code/overview) 已安装

### 步骤 / Steps

```bash
# 1. 创建 skills 目录（如果还没有）
mkdir -p ~/.claude/skills

# 2. 克隆本仓库
git clone https://github.com/njjbwl/claude-skill-zhongwen.git ~/.claude/skills/zhongwen

# 3. 在会话中手动调用
# 输入: /zhongwen
```

### 自动加载（推荐） / Auto-load (Recommended)

在项目根目录（或 `~/.claude/`）的 `CLAUDE.md` 文件中添加一行：

```
- Chinese UI shell → invoke /zhongwen（每次会话主动调用）
```

这样 **每次启动会话** 都会自动加载中文壳，无需手动输入 `/zhongwen`。

## 使用方法 / Usage

| 命令 | 作用 |
|------|------|
| `/zhongwen` | 手动加载中文壳 |
| `/帮助` 或 `/helpzh` | 显示中文命令帮助 |
| `/清屏` | 提示等效命令 `/clear` |
| `/模型` | 显示模型信息，提示 `/model` |
| `/模式` | 提示等效命令 `/mode` |
| `/撤销` | 提示等效命令 `/undo` |
| `/重试` | 提示等效命令 `/retry` |

### 取消中文壳

直接说「取消中文壳」或「恢复英文」即可。

## 文件结构 / File Structure

```
~/.claude/skills/zhongwen/
├── SKILL.md       # 技能定义文件（核心）
└── README.md      # 本文件
```

整个技能就是一个 Markdown 文件 —— 极致轻量。

## 工作原理 / How It Works

Claude Code 的 **Skills 系统** 会在调用 `/zhongwen` 时读取 `SKILL.md`，将其中的指令注入到 AI 的上下文中。AI 据此在回复文本层面模拟中文终端界面，**不修改任何二进制文件或 CLI 行为**。

## 许可 / License

MIT — 随意使用、修改、分发。

---

**用 Claude Code 却说中文？这个技能就是为此而生。**
