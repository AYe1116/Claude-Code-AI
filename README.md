# AI 学习日志 / AI Learning Log

> 一个非科班生的 AI 协作系统全记录——从零配通 Claude Code，到建立长效记忆体系，再到公开发布的全过程。
> *A complete record of a non-CS student's AI collaboration system — from scratch-configuring Claude Code, to building a long-term memory system, to publishing publicly.*

![CI](https://github.com/AYe1116/Claude-Code-AI/actions/workflows/ci.yml/badge.svg)
![License](https://img.shields.io/badge/license-MIT-blue)
![Last Updated](https://img.shields.io/badge/last%20update-2026--05--18-brightgreen)

---

## 这个项目是什么 / What Is This Project

我是一名非计算机专业的学生，对电脑数码有浓厚兴趣。这个仓库记录了我怎样从安装报错开始，一步步搭建出自己的 AI 协作环境，并把整个过程中的踩坑、规则、心得整理成可复用的体系。

*I'm a non-CS student with a strong interest in tech. This repo documents how I built my AI collaboration environment from scratch — starting from installation errors, all the way to a reusable system of rules and insights.*

**核心亮点 / Highlights：**
- **长效记忆系统 / Long-Term Memory**：用三层文件体系（规则书 + 工作日志 + 月度归档）让 AI 跨会话保持记忆
  *A three-tier file system (rulebook + work log + monthly archive) that keeps AI memory across sessions*
- **17 条协作规则 / 17 Collaboration Rules**：精确约束 AI 的语言风格、输出规范、反驳义务、范围管理和对话边界
  *Precise constraints on AI tone, output format, obligation to disagree, scope management, and conversation boundaries*
- **规则迭代闭环 / Iterative Rule Refinement**：观察 → 诊断 → 立法 → 验证，规则在真实对话中不断进化
  *Observe → Diagnose → Legislate → Verify — rules evolve through real conversations*
- **工具链集成 / Toolchain Integration**：MCP 协议连接微信消息、Obsidian 设计灵感库、GitHub 自动备份
  *MCP protocol bridging WeChat messages, Obsidian design library, and GitHub auto-backup*
- **多平台兼容 / Multi-Platform**：同一套规则体系在 Claude Code 和 Reasonix Code 上均可运行
  *Same rule system runs on both Claude Code and Reasonix Code*

---

## 文件说明 / File Guide

| 文件 / File | 作用 / Purpose |
| :--- | :--- |
| `通用协作规则.md` | 17 条协作规则 v2.5 / 17 collaboration rules v2.5 |
| `学习日志.md` | 完整学习记录 / Full learning log by timeline |
| `CC 排坑速查表.md` | Claude Code 排坑 13 条 / 13 troubleshooting tips for Claude Code |
| `人性化协作启动指南.md` | 新会话五步初始化流程 / 5-step session initialization guide |
| `已装技能清单.md` | Skills 和 MCP 服务器安装记录 / Installed skills & MCP servers log |

---

## 技术栈 / Tech Stack

- **AI 终端 / AI Terminal**：Reasonix Code（主力）+ Claude Code + VS Code 插件
  *Reasonix Code (primary) + Claude Code + VS Code extension*
- **底层模型 / Underlying Model**：DeepSeek 官方 API / Official DeepSeek API（deepseek-v4-pro / deepseek-v4-flash）
- **笔记系统 / Note System**：Obsidian + 坚果云 Nutstore Sync（手机/电脑同步 / Mobile & Desktop sync）
- **AI 工具链 / AI Toolchain**：MCP 协议 / MCP Protocol + skills.sh 技能生态 / Skills Ecosystem + 微信消息桥接 / WeChat Message Bridge
- **配置端点 / API Endpoint**：`https://api.deepseek.com/anthropic`

---

## 环境配置 / Setup

### 在 Reasonix Code 中使用

Reasonix Code 原生支持 DeepSeek API，接入即可使用。本项目的规则和日志可直接跨会话复用——Reasonix 的 `remember` 机制会自动加载项目记忆，新会话无需手动对齐。

*Reasonix Code natively supports the DeepSeek API — just connect and go. All rules and logs in this project carry across sessions automatically via Reasonix's `remember` mechanism.*

---

### 用 Claude Code + DeepSeek API 驱动

如果你使用 Claude Code：
*If you'd like to drive Claude Code with DeepSeek API:*

1. **安装 Claude Code / Install Claude Code**
   ```bash
   npm install -g @anthropic-ai/claude-code
   ```

2. **配置 API 端点 / Configure API Endpoint**
   `~/.claude/settings.json`：
   ```json
   {
     "env": {
       "ANTHROPIC_BASE_URL": "https://api.deepseek.com/anthropic",
       "ANTHROPIC_AUTH_TOKEN": "your-deepseek-api-key",
       "ANTHROPIC_DEFAULT_HAIKU_MODEL": "deepseek-v4-flash",
       "ANTHROPIC_DEFAULT_SONNET_MODEL": "deepseek-v4-pro",
       "ANTHROPIC_DEFAULT_OPUS_MODEL": "deepseek-v4-pro"
     }
   }
   ```

3. **启动 / Launch**
   ```bash
   claude
   ```

> ⚠ 注意 / Note：用 `/v1` 端点会报 `Content block is not a text block`，必须用 `/anthropic` 端点。
> *Using the `/v1` endpoint will throw `Content block is not a text block` — you must use `/anthropic` instead.*

---

## 相关文章 / Related Articles

- [《一个初学者的 Claude Code 配置踩坑记录》](https://blog.csdn.net/2604_96046012/article/details/160987982) — CSDN / 掘金 / 知乎
  *A Beginner's Claude Code Configuration Troubleshooting Log*
- [《Claude Code 进阶踩坑：VS Code 插件 + 多模型切换实践》](https://blog.csdn.net/2604_96046012/article/details/161120160) — CSDN / 知乎
  *Claude Code Advanced Pitfalls: VS Code Extension + Multi-Model Switching Practice*

---

## 关于我 / About Me

目前大一在读，非计算机科班，英语基础较弱，但对电脑数码有浓厚兴趣。这套 AI 协作系统是在 AI 的辅助下从零建起来的——我用 AI 帮我排查配置问题，再把自己踩的坑和总结的规则回馈给 AI，形成正向循环。

*I'm a freshman (non-CS major) with limited English but a strong passion for tech. This AI collaboration system was built from zero with AI assistance — I use AI to debug config issues, then feed my learnings and rules back to the AI, creating a positive feedback loop.*

这套方法论的核心思想：AI 不是用来"聊天"的，而是用来"协作"的。把每一次有价值的对话沉淀下来，AI 就会越来越懂你。

*The core philosophy: AI isn't just for "chatting" — it's for "collaborating." Sink every valuable conversation into the system, and AI will understand you better over time.
