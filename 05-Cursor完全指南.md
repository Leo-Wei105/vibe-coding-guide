# 第五章：Cursor 完全指南

> 📖 **难度等级**: ⭐⭐ (简单到中等)
> ⏰ **预计阅读时间**: 45分钟
> 🎯 **学习目标**: 全面掌握Cursor IDE的使用方法

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

```
┌────────────────────────────────────────┐
│                                        │
│          Welcome to Cursor              │
│                                        │
│   [创建新项目]   [打开项目]             │
│                                        │
│   [登录/注册]                          │
│                                        │
└────────────────────────────────────────┘
```

### 注册/登录

```
1. 点击 "Sign In" 或 "Create Account"

2. 选择登录方式：
   - 使用邮箱注册
   - 使用Google账号登录
   - 使用GitHub账号登录

3. 选择套餐：
   - Free（免费）：基础功能
   - Pro（专业版）：高级功能，付费

4. 完成设置
```

### 初次设置向导

```
1. 选择主题：
   - Light（浅色）
   - Dark（深色）
   - High Contrast（高对比度）

2. 选择字体大小：
   - Small（小）
   - Medium（中）
   - Large（大）

3. 选择编程语言：
   - JavaScript/TypeScript
   - Python
   - Java
   - C/C++
   - Go
   - Rust
   - 其他...

4. 完成设置！
```

---

## 🎨 Cursor界面介绍

### 主要界面区域

```
┌────────────────────────────────────────────────────────────────┐
│  菜单栏：File  Edit  Selection  View  Go  Run  Terminal  Help  │
├────────────────────────────────────────────────────────────────┤
│  │                                                          │
│  │  左侧边栏              主编辑区              AI助手侧边栏 │
│  │                                                          │
│  │  📁 文件                代码编辑区          💬 Chat       │
│  │  🔍 搜索                                    ⚙️ Composer  │
│  │  📝 源码管理                                  🔍 Ask     │
│  │  🐛 调试                                    🎨 Edit     │
│  │  🧩 扩展                                     📦 Doc      │
│  │                                                          │
├────────────────────────────────────────────────────────────────┤
│  底部面板：终端、输出、问题、调试控制台                          │
└────────────────────────────────────────────────────────────────┘
```

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

```
┌─────────────────────────────────────────┐
│  💬 Chat                              │
├─────────────────────────────────────────┤
│  输入你的问题或需求                    │
│  [输入框]                              │
│                                         │
│  历史对话...                            │
└─────────────────────────────────────────┘
```

**使用场景**：

```
场景1：解释代码
你: 这段代码是什么意思？（选中代码）

AI: 这段代码实现了一个防抖函数：
- 防止函数在短时间内被多次调用
- 常用于搜索输入、滚动事件等

场景2：提供建议
你: 我应该如何优化这个函数？

AI: 我建议从以下几个方面优化：
1. 使用更高效的算法
2. 添加错误处理
3. 考虑性能影响
...

场景3：生成代码
你: 帮我写一个登录验证函数

AI: 好的，这是一个登录验证函数的示例...
（生成完整的代码）
```

### 模式2：Composer（多文件编辑模式）⭐

**快捷键**: `Cmd/Ctrl + I`

**功能**: 让AI自动规划和编辑多个文件。

```
┌─────────────────────────────────────────┐
│  ⚙️ Composer                           │
├─────────────────────────────────────────┤
│  描述你想要做的改变                     │
│  [输入框]                              │
│                                         │
│  包含的文件：                           │
│  ☑ index.html                          │
│  ☑ style.css                           │
│  ☑ app.js                              │
│                                         │
│  [生成更改] [预览更改]                  │
└─────────────────────────────────────────┘
```

**使用场景**：

```
场景1：添加新功能
你: 给网站添加一个深色模式切换功能

AI Composer:
正在规划更改...

✓ 将创建：
  - dark-mode-toggle.js（开关组件）
  - dark-mode.css（深色样式）

✓ 将修改：
  - index.html（添加切换按钮）
  - style.css（添加深色样式类）
  - app.js（集成切换逻辑）

生成完成后，你可以预览并接受更改
```

```
场景2：重构代码
你: 重构这个项目，使用更现代的代码风格

AI Composer:
分析项目结构...
识别需要重构的部分...

✓ 计划修改：
  - 15个文件
  - 将var改为let/const
  - 使用箭头函数
  - 添加ESLint配置
  - ...

预览更改 > 接受所有更改
```

### 模式3：Agent（代理模式）

**功能**: 让AI自主完成复杂任务。

```
你: /agent

进入Agent模式...

你: 帮我实现一个完整的用户认证系统

AI Agent:
好的，我将为你实现用户认证系统。

第一步：分析需求...
第二步：设计数据库schema...
第三步：创建API端点...
第四步：实现前端界面...
第五步：添加测试...

正在自主执行中...
[进度条: 45%]
```

---

## 🎯 实用技巧

### 技巧1：上下文选择

**为什么重要？**
Cursor能理解你选中的代码上下文，给出更准确的答案。

**如何使用：**

```
不选代码 → "帮我解释这个函数"
→ AI可能理解模糊

选中代码 → "帮我解释这个函数"（选中了calculateSum）
→ AI知道你在问具体的函数，解释更准确
```

### 技巧2：引用文件

**@符号引用**

```
你: 请参考 @utils.js 中的格式，创建一个新的工具函数

AI:
我会参考 utils.js 的代码风格，创建新的函数...
（自动读取utils.js的内容）
```

**#符号引用整个项目**

```
你: 了解整个项目后，帮我添加错误处理

AI:
我已经分析了整个项目结构...
（AI理解了项目的整体架构）
```

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

```
步骤1：打开Cursor

步骤2：创建项目
- 打开新文件夹
- 创建 index.html

步骤3：使用AI生成代码
Chat模式：
你: 帮我创建一个简单的个人网页，包含：
  - 我的名字：张三
  - 一句自我介绍
  - 一个联系我按钮

AI: 好的，这是你的网页代码...
（生成完整的HTML + CSS）

步骤4：预览
- 右键 → Open in Default Browser

完成！
```

### 示例2：调试代码

```
问题：点击按钮后没有反应

步骤1：打开Chat模式（Cmd/Ctrl + L）

步骤2：描述问题
你: 点击提交按钮后，表单没有提交，也没有任何提示

步骤3：提供上下文
- 选中按钮代码
- 选中表单代码

步骤4：AI分析
AI: 我发现了问题：
1. 按钮的type属性设置错误
2. 表单缺少onsubmit处理
3. 建议添加用户提示

步骤5：应用修复
- 逐一修复AI指出的问题

问题解决！
```

### 示例3：使用Composer重构

```
场景：项目中的API调用代码分散在各个文件中

步骤1：打开Composer模式（Cmd/Ctrl + I）

步骤2：描述任务
你: 把所有API调用统一到一个api.js文件中

步骤3：AI规划
AI Composer:
分析项目中的API调用...
找到分散的API代码...

计划：
✓ 创建 api.js（统一的API模块）
✓ 修改5个文件（使用新的API模块）
✓ 保持功能不变

步骤4：预览更改
查看每个文件的具体改动

步骤5：接受更改
应用所有修改

重构完成！
```

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

```
方法1：通过扩展面板
1. 点击左侧扩展图标（🧩）
2. 搜索扩展名称
3. 点击 "Install"

方法2：通过命令面板
1. 打开命令面板（Cmd/Ctrl + Shift + P）
2. 输入 "Extensions: Install Extensions"
3. 搜索并安装

方法3：使用AI推荐
Chat模式：
你: 推荐一些有用的扩展

AI: 根据你的项目，我推荐：
1. Prettier - 代码格式化
2. ESLint - 代码检查
...
```

---

## 🐛 常见问题

### Q1: Cursor响应很慢

```
问题：AI回复需要很长时间

解决方案：
1. 检查网络连接
2. 减少包含的文件数量
3. 明确你的需求，减少AI思考范围
4. 检查是否超出免费额度限制
```

### Q2: AI不理解我的项目

```
问题：AI给出的建议和项目不匹配

解决方案：
1. 使用@符号引用相关文件
2. 创建.cursorrules文件描述项目规范
3. 先用一句话描述项目背景
4. 选中具体的代码再提问
```

### Q3: 免费额度用完了

```
问题：无法使用AI功能了

解决方案：
1. 升级到Pro版本（推荐）
2. 等待额度重置
3. 创建新账号（不推荐）
4. 使用其他AI工具组合使用
```

### Q4: 如何迁移VS Code配置

```
问题：想把VS Code的设置和插件迁移到Cursor

解决方案：
1. 导出VS Code设置
2. Cursor可以自动识别部分设置
3. 手动安装VS Code中的常用扩展
4. 调整主题和字体以匹配之前的环境
```

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

## 📝 本章小结

### 关键要点：

1. **Cursor是AI原生IDE**：不是简单添加AI插件
2. **Composer模式很强大**：可以自动规划和编辑多个文件
3. **三种核心模式**：Chat、Composer、Agent
4. **上下文很重要**：选中和引用文件可以提高准确性
5. **可高度自定义**：.cursorrules文件可以规范AI行为

### 思考题：

1. Cursor的Composer模式和传统聊天AI有什么区别？
2. 在什么场景下应该使用Composer而不是Chat？
3. 如何让Cursor更好地理解你的项目？

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
