# 第四章：Claude Code 完全指南

> 📖 **难度等级**: ⭐⭐⭐ (中等)
> ⏰ **预计阅读时间**: 55分钟（含高级功能）
> 🎯 **学习目标**: 全面掌握Claude Code的使用方法，包括Hooks、Skills、Subagents等进阶功能

---

## 🎯 Claude Code 是什么？

### 官方介绍

**Claude Code** 是 Anthropic 公司推出的官方AI编程工具。它不仅仅是聊天机器人，而是一个完整的编程助手，可以：

- ✅ 直接操作你的代码文件
- ✅ 理解整个项目的结构
- ✅ 自动完成复杂的多文件操作
- ✅ 执行Git命令
- ✅ 运行测试和调试
- ✅ 使用各种扩展和插件

### 为什么选择Claude Code？

| 优势 | 说明 |
|-----|------|
| 🏢 官方出品 | Anthropic公司开发，最稳定可靠 |
| 🧠 智能强大 | 基于Claude模型，代码理解能力强 |
| 🔗 深度集成 | 与Git、IDE等工具深度集成 |
| 🎯 专业级 | 适合复杂项目和团队协作 |
| 📚 文档完善 | 官方文档和社区支持完善 |

---

## 📥 安装Claude Code

### 系统要求

| 系统 | 要求 |
|-----|------|
| Windows | Windows 10/11 + WSL2 |
| macOS | macOS 12+ (推荐M1/M2芯片) |
| Linux | 主流发行版 |

### 安装方法

#### 方法一：使用Homebrew（推荐Mac用户）

```bash
# 1. 更新Homebrew
brew update

# 2. 安装Claude Code
brew install claude-code
```

#### 方法二：使用WinGet（Windows用户）

```powershell
# 1. 打开PowerShell（以管理员身份）

# 2. 安装Claude Code
winget install Claude.ClaudeCode
```

#### 方法三：使用npm（需要Node.js）

```bash
# 1. 确保已安装Node.js
node --version

# 2. 安装Claude Code
npm install -g @anthropic-ai/claude-code
```

#### 方法四：官方安装包

1. 访问官网：https://code.claude.com/docs/en/setup
2. 下载适合你系统的安装包
3. 运行安装程序
4. 按提示完成安装

---

## 🚀 首次启动和登录

### 启动Claude Code

在终端或命令行中输入：

```bash
claude-code
```

### 登录流程

```
Welcome to Claude Code!

你将看到：
========================================
Claude Code v2.x.x

Please sign in to continue:
1. Press Enter to open browser
2. Or visit this URL manually: https://claude.com/auth/code
========================================

操作步骤：
1. 按回车键（会自动打开浏览器）
2. 在浏览器中登录你的Claude账号
3. 授权Claude Code访问
4. 返回终端，看到 "Successfully signed in!"

完成！
```

---

## 💬 基本使用方法

### 第一步：打开一个项目

```bash
# 方式1：在项目目录中启动
cd /path/to/your/project
claude-code

# 方式2：启动后打开项目
claude-code /path/to/your/project
```

### 第二步：开始对话

```
进入Claude Code后，你会看到：

╔════════════════════════════════════════╗
║         Claude Code v2.x.x             ║
║                                        ║
║  Enter your message (or /help):        ║
║  >                                     ║
╚════════════════════════════════════════╝

输入你的问题或需求，然后按回车！
```

### 常用命令示例

```bash
# 查看文件内容
请帮我看看 index.html 里写了什么

# 创建新文件
帮我创建一个名为 utils.js 的文件，写一些常用的工具函数

# 修改文件
把 index.html 里的标题改成"我的第一个网站"

# 运行项目
帮我运行这个项目

# 调试代码
程序报错了，帮我看看是什么问题
```

---

## 🎯 核心功能详解

### 1. 文件操作

#### 读取文件

```
你: 请帮我看看 main.js 的内容

Claude Code:
我会读取并显示文件内容，然后可以帮你：
- 解释代码在做什么
- 指出潜在问题
- 提出改进建议
```

#### 创建文件

```
你: 帮我创建一个 login.html，包含用户名和密码输入框

Claude Code:
会自动创建文件并写入代码，同时告诉你：
- 文件创建的位置
- 代码的主要功能
- 如何使用
```

#### 修改文件

```
你: 把所有 .js 文件里的 console.log 都删掉

Claude Code:
会扫描所有文件，找到并删除 console.log，
然后告诉你修改了哪些文件。
```

### 2. 代码理解

#### 解释代码

```
你: 这段代码是什么意思？（选中一段代码）

Claude Code:
会详细解释：
- 代码的功能
- 每行代码的作用
- 可能的改进建议
- 最佳实践
```

#### 查找问题

```
你: 帮我检查这个项目有没有bug

Claude Code:
会全面检查项目：
- 语法错误
- 逻辑问题
- 安全隐患
- 性能问题
```

### 3. 自动重构

```
你: 这个函数太长了，帮我拆分成更小的函数

Claude Code:
会自动：
- 分析函数结构
- 识别可以拆分的部分
- 重构代码
- 确保功能不变
```

### 4. Git集成

```
你: 创建一个git仓库，提交所有更改

Claude Code:
会自动执行：
git init
git add .
git commit -m "Initial commit"

并告诉你每一步做了什么
```

---

## 🔧 斜杠命令 (Slash Commands)

斜杠命令是Claude Code的强大功能，让你快速执行常用操作。

### 常用斜杠命令列表

| 命令 | 功能 | 示例 |
|-----|------|-----|
| `/help` | 显示帮助信息 | `/help` |
| `/plan` | 进入计划模式 | `/plan 我要做一个待办事项应用` |
| `/read` | 读取文件 | `/read index.html` |
| `/write` | 写入文件 | `/write utils.js` |
| `/edit` | 编辑文件 | `/edit app.js:10-20` |
| `/run` | 运行命令 | `/run npm start` |
| `/test` | 运行测试 | `/test` |
| `/git` | Git操作 | `/git status` |
| `/clear` | 清除对话 | `/clear` |
| `/exit` | 退出 | `/exit` |

### 详细命令说明

#### `/help` - 获取帮助

```bash
/help

显示所有可用命令和基本用法
```

#### `/plan` - 计划模式

```bash
/plan 帮我做一个简单的网页计算器

Claude Code会：
1. 分析你的需求
2. 制定实现计划
3. 分步骤列出需要做什么
4. 等待你确认后再开始实施
```

#### `/read` - 读取文件

```bash
# 读取单个文件
/read index.html

# 读取多个文件
/read *.html

# 读取特定范围
/read app.js:1-50
```

#### `/write` - 写入文件

```bash
/write header.html

Claude Code会提示你输入要写入的内容
```

#### `/run` - 运行命令

```bash
# 运行npm命令
/run npm start

# 运行Python脚本
/run python main.py

# 运行测试
/run npm test
```

#### `/git` - Git操作

```bash
# 查看状态
/git status

# 提交更改
/git commit "fix: 修复了登录问题"

# 查看历史
/git log
```

---

## 🎨 高级功能

### 1. Plan Mode（计划模式）

Plan Mode让你在编写代码之前先制定计划。

```
你: /plan

Claude Code:
进入计划模式！
请告诉我你想做什么...

你: 我想做一个待办事项应用，可以添加、删除、标记完成

Claude Code:
好的，让我为你的待办事项应用制定计划：

📋 实现计划：

第一步：项目结构
├── index.html       # 主页面
├── style.css        # 样式
├── app.js           # 逻辑
└── data.js          # 数据管理

第二步：核心功能
1. 显示待办事项列表
2. 添加新待办事项
3. 删除待办事项
4. 标记完成/未完成

第三步：界面设计
- 简洁现代的卡片式布局
- 不同状态的待办事项有不同颜色
- 平滑的动画效果

第四步：数据持久化
- 使用localStorage保存数据
- 刷新页面数据不丢失

要开始实施吗？(y/n)
```

### 2. Skills（技能）

Skills是Claude Code的自定义功能，让你创建可重用的任务。

```
# 创建一个技能

你: /skill create react-component

Claude Code:
正在创建新技能...
请描述这个技能的功能：

你: 这是一个用于创建React组件的技能，包含：
- 组件模板
- 基本样式
- TypeScript支持

创建成功！使用方法：
/skill use react-component [组件名]
```

### 3. MCP Servers（扩展服务器）

MCP (Model Context Protocol) 允许Claude Code连接外部服务。

```
# 连接数据库MCP
/connect mcp://github.com/anthropics/mcp-server-postgres

# 连接文件系统MCP
/connect mcp://github.com/anthropics/mcp-server-filesystem

# 连接GitHub MCP
/connect mcp://github.com/anthropics/mcp-server-github
```

### 4. CLAUDE.md 项目配置

在项目根目录创建 `CLAUDE.md` 文件，告诉Claude Code关于项目的信息。

```markdown
# CLAUDE.md

## 项目概述
这是一个待办事项应用，帮助用户管理日常任务。

## 技术栈
- HTML5
- CSS3
- JavaScript (ES6+)
- localStorage

## 代码风格
- 使用2空格缩进
- 使用单引号
- 函数名使用驼峰命名
- 常量使用全大写

## 注意事项
- 不要使用alert，使用自定义弹窗
- 所有用户输入都需要验证
- 注意数据类型转换

## 测试
运行 `npm test` 执行测试
```

### 5. Hooks（钩子系统）⭐ 进阶功能

**Hooks** 是 Claude Code 的强大功能，允许你在特定事件发生时**自动执行脚本**。就像"魔法触发器"一样！

#### 什么是 Hooks？

想象一下：
- 🎬 **电影开始前**会播放广告 → 这就是"会话开始钩子"
- 🎬 **电影结束后**会播放片尾字幕 → 这就是"会话结束钩子"
- 🎬 **每个场景切换时**都有过渡动画 → 这就是"工具使用钩子"

Hooks 让你可以在 Claude Code 的各种"时刻"自动执行操作。

#### 常用钩子事件

| 钩子事件 | 触发时机 | 用途示例 |
|---------|---------|---------|
| `SessionStart` | 会话开始时 | 加载环境变量、显示欢迎信息 |
| `SessionEnd` | 会话结束时 | 保存日志、清理临时文件 |
| `PreToolUse` | 工具执行前 | 验证命令、阻止危险操作 |
| `PostToolUse` | 工具执行后 | 自动格式化代码、运行检查 |
| `UserPromptSubmit` | 用户发送消息时 | 添加额外上下文、验证输入 |
| `Stop` | Claude 完成响应时 | 检查任务是否完成 |

#### 配置 Hooks

在 `~/.claude/settings.json` 或 `.claude/settings.json` 中配置：

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Write|Edit",
        "hooks": [
          {
            "type": "command",
            "command": "npm run lint --fix"
          }
        ]
      }
    ]
  }
}
```

**这个配置的意思是**：每次 Claude 写入或编辑文件后，自动运行代码检查！

#### 🧪 试一试：创建你的第一个 Hook

```prompt
帮我创建一个 Claude Code 钩子配置，要求：

1. 每次编辑 .js 文件后，自动运行 ESLint 检查
2. 每次会话开始时，显示项目的 README 内容
3. 阻止删除 package.json 文件

请给我完整的配置文件内容和说明。
```

### 6. Skills（技能系统）⭐ 进阶功能

**Skills** 是 Claude Code 的"可重用魔法咒语"，让你创建自定义的 AI 能力。

#### 什么是 Skills？

把 Skills 想象成**魔法书里的咒语**：
- 📖 你写一次咒语（SKILL.md 文件）
- 🪄 以后随时可以使用（`/技能名` 或自动触发）
- ✨ Claude 会按照你的指示行动

#### 创建 Skill 文件

在 `~/.claude/skills/` 或 `.claude/skills/` 目录下创建：

```
my-skill/
├── SKILL.md          # 主要指令文件（必需）
├── template.md       # 可选的模板文件
└── examples/         # 可选的示例文件夹
```

#### SKILL.md 文件格式

```markdown
---
name: code-reviewer
description: 专业的代码审查助手，帮你检查代码质量和安全问题
allowed-tools: Read, Grep, Glob
---

当审查代码时，请按以下步骤进行：

1. **代码质量检查**
   - 命名是否清晰
   - 函数是否单一职责
   - 是否有重复代码

2. **安全检查**
   - 是否有敏感信息泄露
   - 输入是否经过验证
   - 是否有注入风险

3. **性能检查**
   - 是否有不必要的循环
   - 是否有内存泄漏风险

请给出具体的改进建议和代码示例。
```

#### 使用 Skills

```bash
# 方式1：直接调用
/code-reviewer

# 方式2：Claude 自动识别并使用
"帮我审查一下这个项目的代码"
# Claude 会自动使用 code-reviewer 技能
```

#### 🧪 试一试：创建代码生成技能

```prompt
帮我创建一个 Claude Code 技能，名为 "react-component"

功能：
- 生成符合团队规范的 React 组件
- 使用 TypeScript
- 使用函数组件和 Hooks
- 自动添加 PropTypes 或接口定义
- 包含基础测试文件

请创建完整的 SKILL.md 文件。
```

### 7. Subagents（子代理系统）⭐ 进阶功能

**Subagents** 是 Claude Code 的"分身术"，可以创建专门处理特定任务的 AI 助手。

#### 什么是 Subagents？

想象你是一个项目经理：
- 👨‍💻 **Explore 代理**：专门负责调查和研究（只读，不修改）
- 📝 **Plan 代理**：专门负责制定计划
- 🛠️ **通用代理**：负责实际的编码工作

每个代理都有自己的"职责范围"和"权限"。

#### 内置子代理

| 代理名称 | 模型 | 权限 | 用途 |
|---------|------|------|------|
| **Explore** | Haiku（快速） | 只读 | 搜索代码、分析项目结构 |
| **Plan** | 继承主对话 | 只读 | 制定实现计划 |
| **general-purpose** | 继承主对话 | 全部 | 复杂的多步骤任务 |
| **Bash** | 继承主对话 | 终端 | 运行命令 |

#### 使用子代理

```bash
# 查看所有可用代理
/agents

# 让 Claude 使用特定代理
"使用 Explore 代理帮我分析这个项目的架构"

# Claude 会自动选择合适的代理
"帮我调查一下这个 bug 的原因"  # 自动使用 Explore
```

#### 创建自定义子代理

在 `.claude/agents/` 目录下创建：

```markdown
---
name: security-checker
description: 安全检查专家，检查代码中的安全漏洞
tools: Read, Grep, Glob
model: sonnet
---

你是一个安全专家。检查代码时，重点关注：

1. **SQL 注入风险**
2. **XSS 攻击风险**
3. **敏感信息泄露**
4. **权限控制问题**
5. **依赖包漏洞**

找到问题后，给出风险等级和修复建议。
```

#### 🧪 试一试：创建调试代理

```prompt
帮我创建一个 Claude Code 子代理，名为 "debugger"

功能：
- 专门用于调试代码问题
- 可以读取文件、搜索代码、运行测试
- 使用系统化的调试流程
- 找到问题后给出修复建议

请创建完整的代理配置文件。
```

### 8. Plugins（插件系统）⭐ 进阶功能

**Plugins** 是 Claude Code 的"能力扩展包"，可以打包和分享你的自定义功能。

#### 什么是 Plugins？

插件就像手机的 App：
- 📦 把多个功能打包在一起
- 🔌 一键安装，即插即用
- 🤝 可以和团队共享

#### 插件结构

```
my-plugin/
├── .claude-plugin/
│   └── plugin.json       # 插件配置
├── skills/               # 技能目录
│   └── my-skill/
│       └── SKILL.md
├── agents/               # 代理目录
│   └── my-agent.md
├── hooks/                # 钩子目录
│   └── hooks.json
└── README.md             # 插件说明
```

#### 安装插件

```bash
# 从 GitHub 安装
claude plugin install github:username/plugin-name

# 从本地安装
claude plugin install ./my-plugin

# 查看已安装插件
claude plugin list

# 启用/禁用插件
claude plugin enable my-plugin
claude plugin disable my-plugin
```

#### 发现社区插件

```bash
# 查看推荐插件
/plugins

# 搜索插件
claude plugin search "code review"
```

#### 🧪 试一试：探索插件

```prompt
帮我了解 Claude Code 的插件系统：

1. 有哪些官方推荐的插件？
2. 如何创建一个简单的插件？
3. 如何把我之前创建的 Skills 和 Agents 打包成插件？

请给出详细的步骤说明。
```

### 9. MCP（模型上下文协议）详解 ⭐ 进阶功能

**MCP (Model Context Protocol)** 让 Claude Code 可以连接外部服务，获得"超能力"。

#### 什么是 MCP？

想象 Claude Code 是一台电脑：
- 🖥️ 本身功能有限
- 🔌 通过 USB 接口可以连接各种设备
- 📱 MCP 就是这个"USB 接口"，可以连接各种外部服务

#### 常用 MCP 服务器

| MCP 服务器 | 功能 | 用途 |
|-----------|------|------|
| `mcp-server-github` | GitHub 集成 | 管理仓库、PR、Issues |
| `mcp-server-postgres` | 数据库连接 | 查询和管理数据库 |
| `mcp-server-filesystem` | 文件系统 | 访问更多文件操作 |
| `mcp-server-slack` | Slack 集成 | 发送消息、管理频道 |
| `mcp-server-notion` | Notion 集成 | 读写 Notion 页面 |

#### 配置 MCP 服务器

在设置文件中添加：

```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_TOKEN": "your-token-here"
      }
    },
    "postgres": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-postgres"],
      "env": {
        "DATABASE_URL": "postgresql://..."
      }
    }
  }
}
```

#### 使用 MCP 工具

```bash
# 配置后，可以直接使用
"帮我查看 GitHub 上最近的 Issues"
"从数据库中查询用户数量"
"把这个消息发送到 Slack 的 #dev 频道"
```

#### 🧪 试一试：配置 GitHub MCP

```prompt
帮我配置 Claude Code 的 GitHub MCP 服务器：

1. 需要准备什么？
2. 如何获取 GitHub Token？
3. 配置文件怎么写？
4. 配置好后可以做什么？

请给出详细的步骤指南。
```

---

## 💡 实战示例

### 示例1：创建第一个网页

```bash
# 1. 启动Claude Code
claude-code

# 2. 创建项目
你: 帮我创建一个简单的网页，包含标题和一个按钮

Claude Code:
好的！我将创建以下文件：

index.html - 包含标题和按钮
style.css - 简单的样式

正在创建...

✓ 文件创建完成！
```

### 示例2：调试代码

```bash
# 程序报错了
你: 我的程序报错：Uncaught ReferenceError: x is not defined

Claude Code:
让我帮你调试...

问题分析：
- 代码中使用了变量 x 但没有定义
- 可能是拼写错误或忘记声明

建议修复：
1. 在使用前定义变量 x
2. 或者检查是否是其他变量的拼写错误

要我帮你修复吗？(y/n)
```

### 示例3：添加新功能

```bash
你: 我想给网页添加一个点击按钮改变背景色的功能

Claude Code:
好的！我会：
1. 在HTML中添加按钮
2. 在JavaScript中添加点击事件
3. 添加几种预设颜色

正在实现...

✓ 功能添加完成！
```

---

## ⚡ 最佳实践

### 1. 如何高效提问

| ❌ 不好的提问 | ✅ 好的提问 |
|------------|-----------|
| "帮我修bug" | "点击登录按钮后没有反应，控制台显示xxx错误" |
| "做个网站" | "帮我做一个个人博客，包含文章列表和详情页" |
| "这段代码有问题" | "这个函数应该返回数字，但返回了undefined，原因是什么" |

### 2. 如何组织项目

```
my-project/
├── CLAUDE.md              # Claude Code配置
├── index.html            # 入口文件
├── css/                  # 样式文件夹
│   └── style.css
├── js/                   # 脚本文件夹
│   ├── app.js
│   └── utils.js
├── assets/               # 资源文件夹
│   └── images/
└── README.md            # 项目说明
```

### 3. 如何使用版本控制

```bash
# 经常提交代码
/git commit "feat: 添加了登录功能"

# 使用有意义的提交信息
/git commit "fix: 修复了密码验证的bug"
/git commit "style: 优化了按钮样式"
```

---

## 🐛 常见问题

### Q1: Claude Code连接不上

```
问题：启动后一直显示"Connecting..."

解决方案：
1. 检查网络连接
2. 确认Claude账号状态正常
3. 尝试重新登录：
   claude-code --login
```

### Q2: 响应很慢

```
问题：发送消息后，Claude Code很久才回复

解决方案：
1. 检查网络速度
2. 项目文件太多时，使用 .claudeignore 排除不需要的文件
3. 尝试使用更小范围的操作
```

### Q3: AI不认识我的项目

```
问题：Claude Code不了解项目结构

解决方案：
1. 创建 CLAUDE.md 文件，描述项目
2. 使用 /read 命令让AI读取关键文件
3. 明确告诉AI项目的目标和技术栈
```

---

## 📚 进阶资源

### 官方文档
- [Claude Code 官方文档](https://code.claude.com/docs/en/setup)
- [MCP协议文档](https://modelcontextprotocol.io/)

### 学习资源
- [Claude Code: The Complete Guide](https://www.jitendrazaa.com/blog/ai/claude-code-complete-guide-2026-from-basics-to-advanced-mcp-2/)
- [How I Actually Use Claude Code in 2026](https://levelup.gitconnected.com/how-i-actually-use-claude-code-in-2026-and-why-it-still-needs-a-parent-f029824f4539)
- [Claude Code Ultimate Guide (GitHub)](https://github.com/FlorianBruniaux/claude-code-ultimate-guide)

### 社区
- Claude Code 官方Discord
- Reddit r/ClaudeCode
- GitHub Discussions

---

## 🧪 试一试：Claude Code实战练习

### 练习1：用/plan命令规划项目

启动Claude Code后，输入以下内容：

```prompt
/plan 帮我做一个简单的天气查询网页

要求：
- 输入城市名称
- 显示当前温度和天气状况
- 界面简洁美观
- 使用中文
```

观察Claude Code如何分步骤为你规划整个项目！

### 练习2：创建CLAUDE.md配置文件

让Claude Code帮你创建项目配置：

```prompt
帮我创建一个 CLAUDE.md 文件，内容包括：

项目概述：
这是一个学习vibe coding的练习项目

技术栈：
- HTML5
- CSS3  
- JavaScript

代码规范：
- 使用2空格缩进
- 添加中文注释
- 文件使用小写命名

请直接创建这个文件。
```

### 练习3：常用斜杠命令速查

| 命令 | 用法示例 | 效果 |
|------|----------|------|
| `/plan` | `/plan 做一个计算器` | 先规划再实施 |
| `/read` | `/read index.html` | 查看文件内容 |
| `/run` | `/run npm start` | 运行命令 |
| `/git` | `/git status` | Git操作 |
| `/help` | `/help` | 显示帮助 |

---

## ⚠️ 避坑指南：Claude Code常见问题

### ❌ 问题1：安装失败

**症状**：npm install 报错

**解决方法**：
```bash
# 检查Node.js版本（需要18+）
node --version

# 如果版本太低，去 nodejs.org 下载最新版

# 重新安装
npm install -g @anthropic-ai/claude-code
```

### ❌ 问题2：登录不成功

**症状**：打开浏览器后无法授权

**解决方法**：
```
1. 确认已有Claude付费账号
2. 检查浏览器是否被拦截
3. 尝试手动访问授权链接
4. 检查网络连接
```

### ❌ 问题3：响应很慢

**症状**：等待很久才有回复

**解决方法**：
```
1. 创建 .claudeignore 文件，排除大文件
2. 使用更具体的请求，减少上下文
3. 检查网络连接
4. 高峰期可能较慢，稍后再试
```

### ❌ 问题4：AI不理解项目

**症状**：AI给的建议和项目不匹配

**解决方法**：
```
1. 创建 CLAUDE.md 文件描述项目
2. 使用 /read 命令让AI先阅读关键文件
3. 在对话开头说明项目背景
4. 具体指出要操作的文件
```

### 💡 Claude Code黄金法则

```
1. 用 /plan 先规划再实施
2. 用 CLAUDE.md 让AI了解项目
3. 用 /read 让AI阅读关键文件
4. 一次只做一件事，逐步推进
```

---

## 📝 本章小结

### 关键要点：

1. **Claude Code是官方工具**：由Anthropic公司开发，最专业可靠
2. **功能强大**：可以操作文件、运行命令、理解项目
3. **斜杠命令很有用**：/plan、/read、/run、/agents等
4. **CLAUDE.md很重要**：告诉AI关于项目的信息
5. **适合复杂项目**：特别是需要Git集成的场景

### 高级功能速查表：

| 功能 | 作用 | 适用场景 |
|------|------|---------|
| **Hooks** | 自动化触发器 | 自动格式化、验证、检查 |
| **Skills** | 可重用的AI能力 | 团队规范、重复任务 |
| **Subagents** | 专门化的AI助手 | 代码审查、调试、安全检查 |
| **Plugins** | 功能扩展包 | 团队共享、能力扩展 |
| **MCP** | 外部服务连接 | GitHub、数据库、Slack等 |

### 本章学到的魔法咒语：

| 用途 | 咒语/命令 |
|------|----------|
| 规划项目 | `/plan [项目描述]` |
| 读取文件 | `/read [文件名]` |
| 运行命令 | `/run [命令]` |
| 查看代理 | `/agents` |
| 查看插件 | `/plugins` |
| 创建配置 | "帮我创建CLAUDE.md文件" |
| 创建技能 | "帮我创建一个代码审查的SKILL.md" |

### 思考题：

1. Claude Code适合什么场景使用？
2. 你觉得Claude Code的哪个功能最有用？
3. 如何让Claude Code更好地理解你的项目？
4. Hooks 和 Skills 有什么区别？什么时候用哪个？
5. **动手题**：用 /plan 命令规划一个你想做的小项目！
6. **进阶题**：尝试创建一个简单的 SKILL.md 文件！

---

## 🚀 下一章预告

Claude Code介绍完了！下一章我们将学习另一个强大的工具——Cursor，它有什么特别之处呢？

---

## 📚 参考资料

- [claude - Complete 2026 Guide to AI Coding](https://codewithmukesh.com/blog/claude-code-for-beginners/)
- [Claude Code: The Complete Guide](https://www.jitendrazaa.com/blog/ai/claude-code-complete-guide-2026-from-basics-to-advanced-mcp-2/)
- [How I Actually Use Claude Code in 2026](https://levelup.gitconnected.com/how-i-actually-use-claude-code-in-2026-and-why-it-still-needs-a-parent-f029824f4539)
- [How to Use Claude Code: A Guide to Slash Commands](https://www.producttalk.org/how-to-use-claude-code-features/)
- [Claude Code Ultimate Guide (GitHub)](https://github.com/FlorianBruniaux/claude-code-ultimate-guide)
