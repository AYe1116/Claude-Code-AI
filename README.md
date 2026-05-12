# 设计生的 AI 折腾日志 🏗️🤖

> 一个非科班生的 AI 协作系统全记录——从零配通 Claude Code，到建立长效记忆体系，再到公开分享的全过程。

## 📌 这个项目是什么

我是一名非计算机专业的学生，对电脑数码有浓厚兴趣。这个仓库记录了我怎样从安装报错开始，一步步搭建出自己的 AI 协作环境，并把整个过程中的踩坑、规则、心得整理成可复用的体系。

**核心亮点：**
- 🧠 **长效记忆系统**：用三层文件体系（规则书 + 工作日志 + 月度归档）让 AI 跨会话保持记忆
- 📋 **13 条协作规则**：精确约束 AI 的语言风格、输出规范、反驳义务和对话边界
- 🔄 **规则迭代闭环**：观察 → 诊断 → 立法 → 验证，规则在真实对话中不断进化
- 📝 **公开输出**：已将踩坑经验写成技术文章，发布在 CSDN 和掘金

## 📂 文件说明

| 文件 | 作用 |
| :--- | :--- |
| `项目规则书 & 通用协作规则.md` | 13 条协作规则 v2.2（身份、日志规范、输出约束、反驳义务等） |
| `设计生的 AI 折腾日志.md` | 从 5 月 9 日至今的完整学习记录 |
| `人性化协作启动指南.md` | 新开 AI 会话时的五步初始化流程 |

## 🛠️ 技术栈

- **AI 终端**：Claude Code + VS Code 插件
- **底层模型**：DeepSeek 官方 API (deepseek-v4-pro / deepseek-v4-flash)
- **笔记系统**：Obsidian + 坚果云 Nutstore Sync（手机/电脑同步）
- **配置端点**：`https://api.deepseek.com/anthropic`

## 📝 相关文章

- CSDN：[《一个初学者的 Claude Code 配置踩坑记录》](https://blog.csdn.net/2604_96046012/article/details/160987982)
- 掘金：[《一个初学者的 Claude Code 配置踩坑记录》](https://juejin.cn/post/7638456083297615935)

## ⚡ 快速上手

如果你也想用 DeepSeek API 驱动 Claude Code：

1. **安装 Claude Code**：`npm install -g @anthropic-ai/claude-code`
2. **配置 API 端点**：在 `~/.claude/settings.json` 中填入：
   ```json
   {
     "env": {
       "ANTHROPIC_BASE_URL": "https://api.deepseek.com/anthropic",
       "ANTHROPIC_AUTH_TOKEN": "你的DeepSeek-API-Key"
     }
   }
