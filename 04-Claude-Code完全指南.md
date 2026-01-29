# 第四章：Claude Code 完全指南

> 📖 **难度等级**: ⭐⭐⭐ (中等)
> ⏰ **预计阅读时间**: 40分钟
> 🎯 **学习目标**: 全面掌握Claude Code的使用方法

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
║  Enter your message (or /help):       ║
║  >                                    ║
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

## 📝 本章小结

### 关键要点：

1. **Claude Code是官方工具**：由Anthropic公司开发
2. **功能强大**：可以操作文件、运行命令、理解项目
3. **斜杠命令很有用**：/plan、/read、/run等
4. **CLAUDE.md很重要**：告诉AI关于项目的信息
5. **适合复杂项目**：特别是需要Git集成的场景

### 思考题：

1. Claude Code适合什么场景使用？
2. 你觉得Claude Code的哪个功能最有用？
3. 如何让Claude Code更好地理解你的项目？

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
