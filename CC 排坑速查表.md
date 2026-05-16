# CC 排坑速查表

> 本文档记录 Claude Code 配置与使用过程中遇到的各类问题及解决方案，按问题类型分类，方便快速查找。

---

## 一、安装与配置类

| 坑点 | 现象 | 根因 | 解决方案 |
|------|------|------|----------|
| /v1 地址不兼容 | 报错 `Content block is not a text block` | 使用了 `/v1` 端点 | 改用 `/anthropic` 端点：<br>`ANTHROPIC_BASE_URL`: `https://api.deepseek.com/anthropic` |
| Claude Token View 不显示 | 状态行不显示 Token 消耗 | DeepSeek 中转 API 不返回 `rate_limits` 字段 | 1. 修改脚本使其始终刷新时间戳<br>2. 设置 `claudeTokenView.staleThresholdMinutes = 99999`<br>3. 或改用 `claude-super-monitor` |
| 硅基流动 API 兼容性问题 | 特定任务报错 `Content block is not a text block` | API 非 100% 原生兼容 Claude Code | 核心工作用 DeepSeek 官方 API，降低环境复杂度 |

---

## 二、工具与软件类

| 坑点 | 现象 | 根因 | 解决方案 |
|------|------|------|----------|
| 罗技 G HUB 安装失败 | 卡在加载界面，重装反复失败 | 国内网络连不上更新服务器（502），且不允许离线安装 | 用 Logitech Onboard Memory Manager (OMM) 替代：<br>- 11MB 免安装<br>- 直接写板载内存<br>- 永久生效，无需联网 |
| PowerShell 编码问题 | 规则文件乱码（行内空白丢失、标点变问号） | PowerShell 的 Set-Content/Get-Content 对中文支持问题 | 涉及中文文件修改时，优先用 Read/Write/Edit 工具，不用 PowerShell |
| Git 克隆失败 | 连接 github.com 端口 443 失败 | 科学上网软件只代理浏览器，不代理终端 Git | `git config --global http.proxy http://127.0.0.1:端口号` |

---

## 三、Token 监控类

| 坑点 | 现象 | 根因 | 解决方案 |
|------|------|------|----------|
| Claude Token View 不显示 | 状态行不显示 Token 消耗 | DeepSeek 中转 API 不返回 `rate_limits` 字段 | 改用 `claude-super-monitor`（中文网页仪表盘，本地日志解析） |
| better-ccusage 精度问题 | 命令行报告能输出，但数据不精确 | 底层日志不包含精确计费 Token 信息 | 事后翻日志的工具无法满足精确度需求，需换工具 |
| AIUsage 仓库 404 | AI 推荐地址错误 | 仓库已不存在或地址错误 | 所有 AI 推荐的下载地址必须亲手验证后再执行 |
| claude-monitor 终端乱码 | 影响使用 | 终端显示问题 | 明确自己更倾向于图形化界面 |
| claude-devtools 纯英文界面 | 使用障碍 | 界面语言问题 | 选择中文界面工具（如 claude-super-monitor） |

---

## 四、平台与同步类

| 坑点 | 现象 | 根因 | 解决方案 |
|------|------|------|----------|
| Git 克隆失败 | 端口 443 连接失败 | 代理不生效 | `git config --global http.proxy http://127.0.0.1:端口号` |
| 掘金账号受限 | 无法发布文章 | 账号被限制 | 联系客服，等待回复（1-3 个工作日） |
| Fluent Reader 无安卓版 | 手机端无法使用 | 软件仅支持 Windows | 电脑端 Fluent Reader + 手机端 Feedly，手动管理订阅源 |

---

## 五、快捷键冲突类

| 坑点 | 现象 | 解决方案 |
|------|------|----------|
| Ctrl+Shift+C 冲突 | 与 VS Code 默认"复制行"功能冲突 | 改用 `Ctrl+Shift+Alt+C` |
| Ctrl+Shift+A 冲突 | 与 VS Code 默认"选择所有匹配"功能冲突 | 改用 `Ctrl+Shift+Alt+A` |
| Ctrl+Shift+R 冲突 | 与 VS Code 默认"替换所有"功能冲突 | 改用 `Ctrl+Shift+Alt+R` |

---

## 六、Skills 生态类

| 坑点 | 现象 | 根因 | 解决方案 |
|------|------|------|----------|
| Skills 仓库不存在 | 安装时遇到 404 | `supercent-io/skills-template@technical-writing` 仓库已不存在 | skills.sh 上的技能并非全部可用，安装前必须亲手验证仓库状态 |

---

## 七、写作与范围管理类

| 坑点 | 现象 | 根因 | 解决方案 |
|------|------|------|----------|
| 写作时擅自加不属于标题范围的内容 | 文章中塞了 MCP/Skills 跑题内容 | 未做范围检验 | 以标题为边界做范围检验，超出主题的内容先说明理由再确认是否保留 |

---

## 相关文章

- [《一个初学者的 Claude Code 配置踩坑记录》](https://blog.csdn.net/2604_96046012/article/details/160987982)
- [《Claude Code 进阶踩坑：VS Code 插件 + 多模型切换实践》](https://blog.csdn.net/2604_96046012/article/details/161120160)

---

*最后更新：2026-05-16*
