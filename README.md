# AI 折腾日志

> 一个非科班生的 AI 协作系统全记录——从零配通 Claude Code，到建立长效记忆体系，再到公开发布的全过程。

![CI](https://github.com/AYe1116/Claude-Code-AI/actions/workflows/ci.yml/badge.svg)
![License](https://img.shields.io/badge/license-MIT-blue)
![Last Updated](https://img.shields.io/badge/last%20update-2026--05--16-brightgreen)

---

## 这个项目是什么

我是一名非计算机专业的学生，对电脑数码有浓厚兴趣。这个仓库记录了我怎样从安装报错开始，一步步搭建出自己的 AI 协作环境，并把整个过程中的踩坑、规则、心得整理成可复用的体系。

**核心亮点：**
- **长效记忆系统**：用三层文件体系（规则书 + 工作日志 + 月度归档）让 AI 跨会话保持记忆
- **17 条协作规则**：精确约束 AI 的语言风格、输出规范、反驳义务、范围管理和对话边界
- **规则迭代闭环**：观察 → 诊断 → 立法 → 验证，规则在真实对话中不断进化
- **工具链集成**：MCP 协议连接微信消息、Obsidian 设计灵感库、GitHub 自动备份

---

## 文件说明

| 文件 | 作用 |
| :--- | :--- |
| `通用协作规则.md` | 17 条协作规则 v2.5（身份、日志规范、输出约束、范围管理、反驳义务等） |
| `设计生的 AI 折腾日志.md` | 完整学习记录，按时间线组织 |
| `CC 排坑速查表.md` | Claude Code 配置与使用过程中的 13 个踩坑记录 |
| `人性化协作启动指南.md` | 新开 AI 会话时的五步初始化流程 |
| `已装技能清单.md` | Skills 和 MCP 服务器安装记录 |

---

## 技术栈

- **AI 终端**：Claude Code + VS Code 插件
- **底层模型**：DeepSeek 官方 API（deepseek-v4-pro / deepseek-v4-flash）
- **笔记系统**：Obsidian + 坚果云 Nutstore Sync（手机/电脑同步）
- **AI 工具链**：MCP 协议 + skills.sh 技能生态 + 微信消息桥接
- **配置端点**：`https://api.deepseek.com/anthropic`

---

## 环境配置

如果你也想用 DeepSeek API 驱动 Claude Code：

1. **安装 Claude Code**
   ```bash
   npm install -g @anthropic-ai/claude-code
   ```

2. **配置 API 端点**
   `~/.claude/settings.json`：
   ```json
   {
     "env": {
       "ANTHROPIC_BASE_URL": "https://api.deepseek.com/anthropic",
       "ANTHROPIC_AUTH_TOKEN": "你的DeepSeek-API-Key",
       "ANTHROPIC_DEFAULT_HAIKU_MODEL": "deepseek-v4-flash",
       "ANTHROPIC_DEFAULT_SONNET_MODEL": "deepseek-v4-pro",
       "ANTHROPIC_DEFAULT_OPUS_MODEL": "deepseek-v4-pro"
     }
   }
   ```

3. **启动**
   ```bash
   claude
   ```

> 注意：用 `/v1` 端点会报 `Content block is not a text block`，必须用 `/anthropic` 端点。

---

## 相关文章

- [《一个初学者的 Claude Code 配置踩坑记录》](https://blog.csdn.net/2604_96046012/article/details/160987982) — CSDN / 掘金 / 知乎
- [《Claude Code 进阶踩坑：VS Code 插件 + 多模型切换实践》](https://blog.csdn.net/2604_96046012/article/details/161120160) — CSDN / 知乎

---

## 关于我

非计算机专业在读，英语基础较弱，但对电脑数码有浓厚兴趣。这套 AI 协作系统是在 AI 的辅助下从零建起来的——我用 AI 帮我排查配置问题，再把自己踩的坑和总结的规则回馈给 AI，形成正向循环。

这套方法论的核心思想：AI 不是用来"聊天"的，而是用来"协作"的。把每一次有价值的对话沉淀下来，AI 就会越来越懂你。
