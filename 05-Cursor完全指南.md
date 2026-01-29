# 第五章：Cursor 完全指南

> 📖 **难度等级**: ⭐⭐ (简单到中等)
> ⏰ **预计阅读时间**: 60分钟（含高级功能）
> 🎯 **学习目标**: 全面掌握Cursor IDE的使用方法，包括Rules、Skills、Subagents、MCP等进阶功能

---

## 🎯 Cursor 是什么？

### 官方介绍

**Cursor** 是一个为AI时代打造的智能IDE（集成开发环境）。它基于VS Code构建，但从底层就为AI编程进行了优化。

### Cursor的核心特点

| 特点 | 说明 |
|-----|------|
| 🎨 AI原生设计 | 从底层就为AI优化，不是简单添加插件 |
| 🚀 Composer模式 | 强大的多文件自动编辑能力 |
| 🧠 深度上下文理解 | 能理解整个项目结构 |
| 🔄 实时代码补全 | 智能的代码提示和建议 |
| 🌐 VS Code兼容 | 继承VS Code的所有优势 |

### Cursor vs VS Code

| 方面 | VS Code + Copilot | Cursor |
|-----|------------------|--------|
| 设计理念 | 传统IDE + AI插件 | AI原生IDE |
| AI集成程度 | 辅助工具 | 核心功能 |
| 上下文管理 | 有限 | 深度 |
| 多文件编辑 | 手动 | 自动化 |
| 学习曲线 | 熟悉VS Code容易 | 类似VS Code |
| AI能力 | 基础 | 高级 |

---

## 📥 安装Cursor

### 系统要求

| 系统 | 要求 |
|-----|------|
| Windows | Windows 10/11 |
| macOS | macOS 12+ (推荐M1/M2) |
| Linux | Ubuntu 20.04+, Debian 11+ |

### 安装步骤

#### Windows安装

```
1. 访问官网：https://cursor.com/

2. 点击 "Download for Windows"

3. 运行下载的安装程序：
   - CursorSetup-x.x.x.exe

4. 按提示完成安装

5. 打开Cursor
```

#### macOS安装

```
1. 访问官网：https://cursor.com/

2. 点击 "Download for macOS"

3. 打开下载的 .dmg 文件

4. 将Cursor拖到Applications文件夹

5. 打开Cursor
```

#### Linux安装

```bash
# 方式1：下载 .AppImage
wget https://download.todesktop.com/230313mzl4w28u92/cursor-linux-x64.AppImage
chmod +x cursor-linux-x64.AppImage
./cursor-linux-x64.AppImage

# 方式2：使用snap（如果有）
sudo snap install cursor --classic
```

---

## 🚀 首次启动和设置

### 启动Cursor

首次启动后，你会看到欢迎界面：

> **🎯 Welcome to Cursor**
> 
> `[创建新项目]` `[打开项目]` `[登录/注册]`

### 注册/登录

1. **点击登录** → 2. **选择方式** → 3. **选择套餐** → 4. **完成**

| 步骤 | 选项 |
|:---:|------|
| **登录方式** | 📧 邮箱注册 / 🔵 Google账号 / ⚫ GitHub账号 |
| **套餐选择** | Free（免费基础版）/ Pro（专业付费版）|

### 初次设置向导

| 设置项 | 选项 |
|:-----:|------|
| **1. 主题** | Light（浅色）/ Dark（深色）/ High Contrast（高对比度）|
| **2. 字体大小** | Small（小）/ Medium（中）/ Large（大）|
| **3. 编程语言** | JavaScript/TypeScript、Python、Java、C/C++、Go、Rust 等 |

---

## 🎨 Cursor界面介绍

### 主要界面区域

**Cursor 界面采用三栏布局：**

| 区域 | 位置 | 内容 |
|:---:|:---:|------|
| **菜单栏** | 顶部 | File、Edit、Selection、View、Go、Run、Terminal、Help |
| **左侧边栏** | 左侧 | 📁 文件、🔍 搜索、📝 源码管理、🐛 调试、🧩 扩展 |
| **代码编辑区** | 中间 | 💻 主要代码编写区域 |
| **AI助手** | 右侧 | 💬 Chat、⚙️ Composer、🔍 Ask、🎨 Edit、📦 Doc |
| **底部面板** | 底部 | 终端、输出、问题、调试控制台 |

> **界面三栏布局**：左侧文件管理 | 中间代码编辑 | 右侧AI助手

### 左侧边栏功能

| 图标 | 功能 | 说明 |
|-----|------|------|
| 📁 Explorer | 文件浏览器 | 查看和管理项目文件 |
| 🔍 Search | 搜索 | 搜索文件内容 |
| 📝 Source Control | 源码管理 | Git版本控制 |
| 🐛 Run and Debug | 调试 | 运行和调试代码 |
| 🧩 Extensions | 扩展 | 管理插件 |

### AI助手侧边栏

| 模式 | 快捷键 | 功能 |
|-----|-------|------|
| 💬 Chat | `Cmd/Ctrl + L` | AI对话 |
| ⚙️ Composer | `Cmd/Ctrl + I` | 多文件自动编辑 |
| 🔍 Ask | - | 询问代码问题 |
| 🎨 Edit | - | 快速编辑代码 |
| 📦 Doc | - | 查看文档 |

---

## 💬 三大核心模式

### 模式1：Chat（对话模式）

**快捷键**: `Cmd/Ctrl + L`

**功能**: 和AI对话，获取帮助和建议。

> **💬 Chat 面板**
> 
> 输入你的问题或需求 → `[输入框]` → 查看历史对话

**使用场景**：

**场景1：解释代码**
> **你**：这段代码是什么意思？（选中代码）
> 
> **AI**：这段代码实现了一个防抖函数：防止函数在短时间内被多次调用，常用于搜索输入、滚动事件等。

**场景2：提供建议**
> **你**：我应该如何优化这个函数？
> 
> **AI**：我建议从以下几个方面优化：1. 使用更高效的算法；2. 添加错误处理；3. 考虑性能影响...

**场景3：生成代码**
> **你**：帮我写一个登录验证函数
> 
> **AI**：好的，这是一个登录验证函数的示例...（生成完整的代码）

### 模式2：Composer（多文件编辑模式）⭐

**快捷键**: `Cmd/Ctrl + I`

**功能**: 让AI自动规划和编辑多个文件。

> **⚙️ Composer 面板**
> 
> 1. 描述你想要做的改变 → `[输入框]`
> 2. 选择要包含的文件：☑ index.html ☑ style.css ☑ app.js
> 3. 点击 `[生成更改]` 或 `[预览更改]`

**使用场景**：

**场景1：添加新功能**
> **你**：给网站添加一个深色模式切换功能
> 
> **AI Composer**：正在规划更改...
> - ✓ 将创建：`dark-mode-toggle.js`（开关组件）、`dark-mode.css`（深色样式）
> - ✓ 将修改：`index.html`（添加切换按钮）、`style.css`（添加深色样式类）、`app.js`（集成切换逻辑）
> 
> 生成完成后，你可以预览并接受更改

**场景2：重构代码**
> **你**：重构这个项目，使用更现代的代码风格
> 
> **AI Composer**：分析项目结构...识别需要重构的部分...
> - ✓ 计划修改：15个文件
> - ✓ 将 `var` 改为 `let/const`
> - ✓ 使用箭头函数
> - ✓ 添加 ESLint 配置
> 
> 点击「预览更改」→「接受所有更改」

### 模式3：Agent（代理模式）

**功能**: 让AI自主完成复杂任务。

> **你**：`/agent`
> 
> *进入Agent模式...*
> 
> **你**：帮我实现一个完整的用户认证系统
> 
> **AI Agent**：好的，我将为你实现用户认证系统。
> 1. 第一步：分析需求...
> 2. 第二步：设计数据库schema...
> 3. 第三步：创建API端点...
> 4. 第四步：实现前端界面...
> 5. 第五步：添加测试...
> 
> *正在自主执行中... [进度条: 45%]*

---

## 🎯 实用技巧

### 技巧1：上下文选择

**为什么重要？**
Cursor能理解你选中的代码上下文，给出更准确的答案。

**如何使用：**

| 操作方式 | 效果 |
|---------|------|
| ❌ 不选代码 → "帮我解释这个函数" | AI可能理解模糊 |
| ✅ 选中代码 → "帮我解释这个函数"（选中了 `calculateSum`） | AI知道你在问具体的函数，解释更准确 |

### 技巧2：引用文件

**@符号引用**

> **你**：请参考 `@utils.js` 中的格式，创建一个新的工具函数
> 
> **AI**：我会参考 utils.js 的代码风格，创建新的函数...（自动读取 utils.js 的内容）

**#符号引用整个项目**

> **你**：了解整个项目后，帮我添加错误处理
> 
> **AI**：我已经分析了整个项目结构...（AI理解了项目的整体架构）

### 技巧3：命令模式

**常用命令**：

```
/cmd help          # 显示所有可用命令
/cmd explain       # 解释选中的代码
/cmd refactor      # 重构选中的代码
/cmd test          # 为选中的代码生成测试
/cmd debug         # 帮助调试代码
/cmd doc           # 为代码生成文档
```

### 技巧4：快捷键大全

| 快捷键 | 功能 |
|--------|------|
| `Cmd/Ctrl + L` | 打开Chat |
| `Cmd/Ctrl + I` | 打开Composer |
| `Cmd/Ctrl + K` | 快速编辑选中代码 |
| `Cmd/Ctrl + /` | 注释代码 |
| `Cmd/Ctrl + Shift + A` | 搜索文件 |
| `Cmd/Ctrl + P` | 快速打开文件 |
| `F5` | 运行代码 |
| `Cmd/Ctrl + Shift + F` | 全局搜索 |

---

## 💡 实战示例

### 示例1：创建第一个网页

1. **打开Cursor**
2. **创建项目**：打开新文件夹 → 创建 `index.html`
3. **使用AI生成代码**（Chat模式）：
   > **你**：帮我创建一个简单的个人网页，包含：我的名字（张三）、一句自我介绍、一个联系我按钮
   > 
   > **AI**：好的，这是你的网页代码...（生成完整的 HTML + CSS）
4. **预览**：右键 → Open in Default Browser
5. **完成！** 🎉

### 示例2：调试代码

**问题**：点击按钮后没有反应

1. **打开Chat模式**（`Cmd/Ctrl + L`）
2. **描述问题**：
   > **你**：点击提交按钮后，表单没有提交，也没有任何提示
3. **提供上下文**：选中按钮代码、选中表单代码
4. **AI分析**：
   > **AI**：我发现了问题：1. 按钮的type属性设置错误；2. 表单缺少onsubmit处理；3. 建议添加用户提示
5. **应用修复**：逐一修复AI指出的问题 → **问题解决！** ✅

### 示例3：使用Composer重构

**场景**：项目中的API调用代码分散在各个文件中

1. **打开Composer模式**（`Cmd/Ctrl + I`）
2. **描述任务**：
   > **你**：把所有API调用统一到一个 `api.js` 文件中
3. **AI规划**：
   > **AI Composer**：分析项目中的API调用...找到分散的API代码...
   > - ✓ 创建 `api.js`（统一的API模块）
   > - ✓ 修改5个文件（使用新的API模块）
   > - ✓ 保持功能不变
4. **预览更改**：查看每个文件的具体改动
5. **接受更改**：应用所有修改 → **重构完成！** ✅

---

## 🧩 扩展和插件

### 推荐安装的扩展

| 扩展名 | 功能 | 必需？ |
|--------|------|--------|
| Prettier | 代码格式化 | 推荐 |
| ESLint | 代码质量检查 | 推荐 |
| GitLens | Git增强 | 推荐 |
| Material Icon Theme | 文件图标 | 可选 |
| Auto Rename Tag | 自动重命名标签 | 可选 |
| Path Intellisense | 路径自动补全 | 可选 |

### 安装扩展的方法

**方法1：通过扩展面板**
1. 点击左侧扩展图标（🧩）
2. 搜索扩展名称
3. 点击 "Install"

**方法2：通过命令面板**
1. 打开命令面板（`Cmd/Ctrl + Shift + P`）
2. 输入 "Extensions: Install Extensions"
3. 搜索并安装

**方法3：使用AI推荐**
> **你**：推荐一些有用的扩展
> 
> **AI**：根据你的项目，我推荐：1. Prettier - 代码格式化；2. ESLint - 代码检查...

---

## 🐛 常见问题

### Q1: Cursor响应很慢

**问题**：AI回复需要很长时间

**解决方案**：
1. 检查网络连接
2. 减少包含的文件数量
3. 明确你的需求，减少AI思考范围
4. 检查是否超出免费额度限制

### Q2: AI不理解我的项目

**问题**：AI给出的建议和项目不匹配

**解决方案**：
1. 使用 `@` 符号引用相关文件
2. 创建 `.cursorrules` 文件描述项目规范
3. 先用一句话描述项目背景
4. 选中具体的代码再提问

### Q3: 免费额度用完了

**问题**：无法使用AI功能了

**解决方案**：
1. 升级到Pro版本（推荐）
2. 等待额度重置
3. 创建新账号（不推荐）
4. 使用其他AI工具组合使用

### Q4: 如何迁移VS Code配置

**问题**：想把VS Code的设置和插件迁移到Cursor

**解决方案**：
1. 导出VS Code设置
2. Cursor可以自动识别部分设置
3. 手动安装VS Code中的常用扩展
4. 调整主题和字体以匹配之前的环境

---

## ⚙️ 高级配置

### 创建 .cursorrules 文件

在项目根目录创建 `.cursorrules` 文件，定义AI行为规范：

```text
# Cursor Rules

## 项目概述
这是一个电商网站的前端项目

## 技术栈
- React 18
- TypeScript
- Tailwind CSS
- Vite

## 代码规范
- 使用函数组件
- 使用Hooks
- 避免使用any类型
- 组件命名使用PascalCase

## 注意事项
- 所有API调用必须添加错误处理
- 使用async/await而不是Promise
- 组件必须有PropTypes或TypeScript类型

## AI行为规范
- 不要使用class组件
- 优先使用函数式编程
- 保持组件单一职责
```

### 自定义快捷键

```
打开设置 → Keyboard Shortcuts

可以自定义或添加：
{
  "key": "cmd+k cmd+1",
  "command": "cursor.chat.focus"
}

这样就可以用Cmd+K Cmd+1快速打开Chat了
```

---

## 🚀 高级功能详解

### 1. Rules（规则系统）⭐ 进阶功能

**Rules** 是 Cursor 的"AI 行为准则"，让你告诉 AI 应该遵循什么规范。

#### 什么是 Rules？

把 Rules 想象成给 AI 的"工作手册"：
- 📋 **公司规章**：定义代码风格、命名规范
- 🎯 **工作指南**：告诉 AI 该做什么、不该做什么
- 🧠 **长期记忆**：AI 会一直记住这些规则

#### 规则类型

| 类型 | 触发方式 | 用途 |
|------|---------|------|
| **Always** | 始终生效 | 全局代码规范、团队约定 |
| **Auto Attached** | 文件匹配时自动附加 | 特定文件类型的规则 |
| **Agent Requested** | AI 需要时自动请求 | 复杂任务的专门指南 |
| **Manual** | 手动使用 `@ruleName` | 按需使用的特殊规则 |

#### 创建规则

**方法1：通过命令面板**
```
1. 按 Cmd/Ctrl + Shift + P
2. 输入 "New Cursor Rule"
3. 输入规则名称
4. 选择规则类型
5. 编写规则内容
```

**方法2：直接创建文件**
在 `.cursor/rules/` 目录下创建 `.mdc` 文件：

```markdown
---
description: React组件开发规范
globs: ["**/*.tsx", "**/*.jsx"]
alwaysApply: false
---

## React 组件规范

### 必须遵循
- 使用函数组件，不使用 class 组件
- 使用 TypeScript 定义 Props 类型
- 组件名使用 PascalCase
- 文件名与组件名一致

### 代码结构
1. import 语句
2. 类型定义
3. 组件定义
4. 样式（如有）
5. export

### 禁止事项
- 不要在组件内定义组件
- 不要使用 any 类型
- 不要忽略 ESLint 警告
```

#### 规则优先级

```
用户级规则 > 项目级规则 > 默认行为

~/.cursor/rules/        # 用户级（所有项目）
.cursor/rules/          # 项目级（当前项目）
```

#### 🧪 试一试：创建你的第一个规则

```prompt
帮我创建一个 Cursor 规则文件，要求：

名称：chinese-comments
类型：Always（始终生效）

规则内容：
- 所有代码注释必须使用中文
- 变量名使用英文，但要加中文注释说明用途
- 函数要有中文文档说明参数和返回值
- 复杂逻辑要加中文解释

请给我完整的 .mdc 文件内容。
```

### 2. Skills（技能系统）⭐ 进阶功能

**Skills** 是 Cursor 的"专业技能库"，让 AI 拥有特定领域的专业能力。

#### 什么是 Skills？

Skills 就像给 AI 装上"专业证书"：
- 🎓 **前端开发证书**：懂 React、Vue、CSS
- 🎓 **后端开发证书**：懂 Node.js、数据库、API
- 🎓 **DevOps 证书**：懂部署、CI/CD、Docker

#### Skills vs Rules 的区别

| 方面 | Rules | Skills |
|------|-------|--------|
| **作用** | 定义行为规范 | 提供专业能力 |
| **触发** | 自动或手动 | `/skill-name` 或自动 |
| **内容** | 规则和约束 | 详细指令和模板 |
| **场景** | 代码风格 | 完成特定任务 |

#### 创建 Skill

在 `.cursor/skills/` 目录下创建：

```
my-skill/
├── SKILL.md          # 技能定义（必需）
├── templates/        # 模板文件（可选）
└── examples/         # 示例代码（可选）
```

**SKILL.md 示例**：

```markdown
---
name: api-endpoint
description: 创建 RESTful API 端点
argument-hint: [endpoint-name] [method]
allowed-tools: Read, Write, Edit
---

# API 端点生成器

当创建新的 API 端点时：

## 步骤
1. 在 `routes/` 目录创建路由文件
2. 在 `controllers/` 创建控制器
3. 在 `services/` 创建业务逻辑
4. 添加输入验证
5. 添加错误处理
6. 更新 API 文档

## 代码模板

### 路由文件
```javascript
router.${method}('/${endpoint}', validate(schema), controller.${endpoint})
```

### 控制器
```javascript
async function ${endpoint}(req, res, next) {
  try {
    const result = await service.${endpoint}(req.body)
    res.json({ success: true, data: result })
  } catch (error) {
    next(error)
  }
}
```
```

#### 使用 Skills

```bash
# 直接调用
/api-endpoint users GET

# 在对话中使用
"使用 api-endpoint 技能帮我创建一个用户注册接口"
```

#### 🧪 试一试：创建组件生成技能

```prompt
帮我创建一个 Cursor 技能，名为 "vue-component"

功能：
- 生成 Vue 3 组件（使用 Composition API）
- 包含 TypeScript 类型定义
- 包含基础样式（scoped）
- 包含单元测试文件
- 遵循团队命名规范

请创建完整的 SKILL.md 文件和相关模板。
```

### 3. Subagents（子代理系统）⭐ 进阶功能

**Subagents** 是 Cursor 的"专业分工团队"，不同的代理负责不同类型的任务。

#### 什么是 Subagents？

把 Subagents 想象成一个开发团队：
- 👨‍🔬 **Explore 代理**：调研专家，负责查找和分析
- 📐 **Plan 代理**：架构师，负责制定方案
- 👨‍💻 **通用代理**：全栈工程师，负责实现

#### 内置子代理

| 代理 | 模型 | 能力 | 最佳用途 |
|------|------|------|---------|
| **Explore** | 快速模型 | 只读 | 代码搜索、项目分析 |
| **Plan** | 主模型 | 只读 | 制定实现计划 |
| **general-purpose** | 主模型 | 全部 | 复杂的编码任务 |

#### 使用 Subagents

Cursor 会自动选择合适的代理，但你也可以明确指定：

```
"用 Explore 代理帮我分析这个项目的架构"

"用 Plan 代理帮我规划如何重构这个模块"

"这是一个复杂的任务，请使用通用代理来完成"
```

#### 创建自定义代理

在 `.cursor/agents/` 目录下创建 `.md` 文件：

```markdown
---
name: test-writer
description: 专门编写测试用例的代理
tools: Read, Write, Edit, Bash
model: sonnet
---

你是一个专业的测试工程师。

## 职责
- 分析代码功能
- 编写单元测试
- 编写集成测试
- 确保测试覆盖率

## 测试原则
1. 每个函数至少3个测试用例
2. 覆盖正常、边界、异常情况
3. 测试名称要描述测试目的
4. 使用 AAA 模式（Arrange-Act-Assert）

## 输出要求
- 使用项目的测试框架
- 添加中文注释说明测试目的
- 给出测试覆盖率报告
```

#### 🧪 试一试：创建代码审查代理

```prompt
帮我创建一个 Cursor 子代理，名为 "code-reviewer"

功能：
- 专门用于代码审查
- 只有读取权限（安全）
- 检查代码质量、安全性、性能
- 给出改进建议和优先级

请创建完整的代理配置文件。
```

### 4. MCP（模型上下文协议）⭐ 进阶功能

**MCP** 让 Cursor 可以连接外部工具和服务，极大扩展 AI 的能力。

#### 什么是 MCP？

MCP 就像给 Cursor 安装"外挂"：
- 🔌 连接 GitHub → 直接管理仓库和 PR
- 🔌 连接数据库 → 直接查询和分析数据
- 🔌 连接 Slack → 直接发送消息
- 🔌 连接 Notion → 直接读写文档

#### 添加 MCP 服务器

**方法1：通过设置界面**
```
1. 打开 Cursor Settings（Cmd/Ctrl + Shift + J）
2. 找到 "Tools & Integrations"
3. 点击 "New MCP Server"
4. 填写服务器配置
```

**方法2：编辑配置文件**

在 `~/.cursor/mcp.json` 中添加：

```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_TOKEN": "ghp_xxxx"
      }
    },
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/allowed/dir"]
    }
  }
}
```

#### 常用 MCP 服务器

| 服务器 | 功能 | 安装命令 |
|--------|------|---------|
| GitHub | PR、Issues、仓库管理 | `@modelcontextprotocol/server-github` |
| Slack | 消息、频道管理 | `@modelcontextprotocol/server-slack` |
| PostgreSQL | 数据库操作 | `@modelcontextprotocol/server-postgres` |
| Filesystem | 增强文件操作 | `@modelcontextprotocol/server-filesystem` |
| Memory | 持久化记忆 | `@modelcontextprotocol/server-memory` |

#### 使用 MCP 工具

配置好后，直接在对话中使用：

```
"帮我看看 GitHub 上这个仓库最近的 PR"

"查询数据库中活跃用户的数量"

"把这个更新发送到 Slack 的 #dev 频道"
```

#### 🧪 试一试：配置 GitHub MCP

```prompt
帮我配置 Cursor 的 GitHub MCP 服务器：

1. 如何获取 GitHub Personal Access Token？
2. 需要哪些权限？
3. 完整的配置文件怎么写？
4. 配置好后能做什么？

请给出详细的步骤指南。
```

### 5. Hooks（钩子系统）⭐ 进阶功能

**Hooks** 是 Cursor Agent 的"自动化触发器"，在特定事件时自动执行操作。

#### 什么是 Agent Hooks？

Hooks 就像"智能家居"：
- 🏠 回家时自动开灯 → 打开文件时自动加载配置
- 🏠 离家时自动关空调 → 保存文件时自动格式化
- 🏠 有人敲门时通知 → AI 要执行命令时先验证

#### 支持的 Hook 事件

| 事件 | 触发时机 | 用途 |
|------|---------|------|
| `onFileOpen` | 打开文件时 | 加载相关配置 |
| `onFileSave` | 保存文件时 | 自动格式化、lint |
| `beforeToolUse` | AI 使用工具前 | 验证、阻止危险操作 |
| `afterToolUse` | AI 使用工具后 | 自动测试、检查 |

#### 配置 Hooks

在 `.cursor/hooks/` 目录下创建配置：

```json
{
  "hooks": {
    "afterToolUse": [
      {
        "matcher": "Write|Edit",
        "filePattern": "**/*.{js,ts,tsx}",
        "command": "npm run lint:fix"
      }
    ],
    "beforeToolUse": [
      {
        "matcher": "Bash",
        "command": "./scripts/validate-command.sh"
      }
    ]
  }
}
```

#### 🧪 试一试：创建自动格式化 Hook

```prompt
帮我创建一个 Cursor Hook 配置：

功能：
- 每次 AI 编辑 .ts 或 .tsx 文件后
- 自动运行 Prettier 格式化
- 自动运行 ESLint 检查
- 如果有错误，提示 AI 修复

请给出完整的配置文件。
```

---

## 📚 进阶资源

### 官方资源
- [Cursor官网](https://cursor.com/)
- [Cursor功能文档](https://cursor.com/features)
- [Plan Mode介绍](https://cursor.com/blog/plan-mode)
- [Composer博客](https://cursor.com/blog/composer)

### 学习资源
- [Cursor vs VS Code with Copilot: Best AI Code Editor 2026](https://is4.ai/blog/our-blog-1/cursor-vs-vscode-copilot-comparison-2026-165)
- [VS Code is "Legacy" Now: Why I'm Switching to Cursor for 2026](https://medium.com/@hmnshudhmn24/vs-code-is-legacy-now-why-im-switching-to-cursor-for-2026-d8c2fe300fed)
- [Is Cursor Better Than VS Code in 2026?](https://thinkpeak.ai/is-cursor-better-than-vs-code-2026/)
- [Cursor AI Review 2026: We Tested It for 6 Months](https://www.nxcode.io/resources/news/cursor-review-2026)

### 社区
- Cursor官方Discord
- Cursor官方Twitter
- Reddit r/cursor

---

## 🧪 试一试：Cursor实战练习

### 练习1：体验Chat模式

打开Cursor后，按 `Cmd/Ctrl + L` 打开Chat面板，输入：

```prompt
请解释一下Cursor的三种模式（Chat、Composer、Agent）有什么区别？

用简单的比喻帮我理解，比如：
- Chat模式像什么？
- Composer模式像什么？
- Agent模式像什么？
```

### 练习2：体验Composer模式

按 `Cmd/Ctrl + I` 打开Composer，输入：

```prompt
请帮我创建一个简单的网页项目，包含：

文件结构：
- index.html（主页面）
- style.css（样式文件）
- script.js（脚本文件）

功能：
- 显示一个计数器
- 有"加1"和"减1"两个按钮
- 数字变化时有动画效果
- 样式要现代好看
```

观察Composer如何**自动创建多个文件**并完成整个功能！

### 练习3：使用@引用上下文

在Chat中使用@符号引用：

```prompt
@index.html 这个文件有什么问题？

请帮我：
1. 检查代码是否有错误
2. 提出改进建议
3. 优化性能
```

### 练习4：创建.cursorrules文件

让Cursor帮你创建项目规范：

```prompt
帮我创建 .cursorrules 文件，内容：

项目语言：中文
代码风格：
- 使用2空格缩进
- 添加详细注释
- 变量名要有意义

AI行为：
- 生成代码时要解释原理
- 遇到问题先分析再解决
- 使用最新的最佳实践
```

---

## ⚠️ 避坑指南：Cursor常见问题

### ❌ 问题1：安装后打开是空白

**症状**：安装成功但打开后界面空白

**解决方法**：

| 系统 | 步骤 |
|:---:|------|
| **Windows** | 1. 完全关闭Cursor → 2. 删除 `%APPDATA%\Cursor` 文件夹 → 3. 重新打开Cursor |
| **Mac** | 1. 完全关闭Cursor → 2. 删除 `~/Library/Application Support/Cursor` → 3. 重新打开Cursor |

### ❌ 问题2：AI回复很慢或无响应

**症状**：发送消息后一直加载

**解决方法**：
1. 检查网络连接
2. 检查订阅状态（Settings → Account）
3. 尝试切换AI模型（GPT-4 → Claude）
4. 重启Cursor
5. 检查是否有防火墙拦截

### ❌ 问题3：Composer不工作

**症状**：Composer无法修改文件

**解决方法**：
1. 确保已打开项目文件夹（不是单个文件）
2. 确保文件没有被其他程序占用
3. 尝试先用Chat确认AI能正常工作
4. 重新打开项目

### ❌ 问题4：上下文不准确

**症状**：AI好像不理解你的项目

**解决方法**：
1. 手动用 `@` 引用相关文件
2. 创建 `.cursorrules` 描述项目
3. 选中相关代码再提问
4. 明确告诉AI要操作哪些文件

### 💡 Cursor快捷键速查

| 功能 | Windows/Linux | Mac |
|------|--------------|-----|
| 打开Chat | `Ctrl + L` | `Cmd + L` |
| 打开Composer | `Ctrl + I` | `Cmd + I` |
| 内联编辑 | `Ctrl + K` | `Cmd + K` |
| 接受建议 | `Tab` | `Tab` |
| 切换AI模型 | 点击模型名 | 点击模型名 |

### 💡 Cursor黄金法则

1. 复杂任务用 **Composer**，简单问题用 **Chat**
2. 善用 `@` 符号提供上下文
3. 创建 `.cursorrules` 规范AI行为
4. 一次做一件事，逐步推进
5. 不确定时，先让AI解释再执行

---

## 📝 本章小结

### 关键要点：

1. **Cursor是AI原生IDE**：不是简单添加AI插件
2. **Composer模式很强大**：可以自动规划和编辑多个文件
3. **三种核心模式**：Chat、Composer、Agent
4. **上下文很重要**：选中和引用文件可以提高准确性
5. **可高度自定义**：Rules、Skills、Subagents 等高级功能

### 高级功能速查表：

| 功能 | 作用 | 文件位置 |
|------|------|---------|
| **Rules** | 定义AI行为规范 | `.cursor/rules/*.mdc` |
| **Skills** | 可重用的专业能力 | `.cursor/skills/*/SKILL.md` |
| **Subagents** | 专门化的AI助手 | `.cursor/agents/*.md` |
| **MCP** | 连接外部服务 | `~/.cursor/mcp.json` |
| **Hooks** | 自动化触发器 | `.cursor/hooks/` |

### 本章学到的魔法咒语：

| 用途 | 咒语要点 |
|------|----------|
| 创建项目 | Composer + 描述文件结构和功能 |
| 引用文件 | `@文件名` + 你的问题 |
| 使用规则 | `@ruleName` 手动引用规则 |
| 使用技能 | `/skill-name` 调用技能 |
| 检查代码 | "@文件 这个文件有什么问题？" |
| 创建规范 | "帮我创建 Cursor Rule 文件" |

### 思考题：

1. Cursor的Composer模式和传统聊天AI有什么区别？
2. 在什么场景下应该使用Composer而不是Chat？
3. 如何让Cursor更好地理解你的项目？
4. Rules 和 Skills 有什么区别？
5. **动手题**：用Composer创建一个计数器项目！
6. **进阶题**：创建一个代码规范的 Rule 文件！

---

## 🚀 下一章预告

Cursor介绍完了！接下来我们将学习Trae，这个最简单、最友好的AI编程工具！

---

## 📚 参考资料

- [Cursor官网功能介绍](https://cursor.com/features)
- [Cursor AI Code Editor in 2026: The Futuristic AI Pair Programmer](https://medium.com/@aitoolshub/cursor-ai-code-editor-in-2026-the-futuristic-ai-pair-programmer-4dda679321c8)
- [Cursor AI Review 2026: We Tested It for 6 Months](https://www.nxcode.io/resources/news/cursor-review-2026)
- [Cursor AI: A Comprehensive 2026 Review](https://createaiagent.net/tools/cursor/)
- [The 3 Cursor AI Modes (Chat, Composer, Agent)](https://www.thepromptwarrior.com/p/the-3-cursor-ai-modes)
- [Introducing Plan Mode](https://cursor.com/blog/plan-mode)
- [Composer: Building a fast frontier model with RL](https://cursor.com/blog/composer)
- [Cursor 2.0: New AI Model Explained](https://www.codecademy.com/article/cursor-2-0-new-ai-model-explained)
- [Cursor vs VS Code with Copilot: Best AI Code Editor 2026](https://is4.ai/blog/our-blog-1/cursor-vs-vscode-copilot-comparison-2026-165)
- [VS Code is "Legacy" Now: Why I'm Switching to Cursor for 2026](https://medium.com/@hmnshudhmn24/vs-code-is-legacy-now-why-im-switching-to-cursor-for-2026-d8c2fe300fed)
