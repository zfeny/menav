# <img src="assets/favicon.ico" width="48" style="vertical-align: middle;"> MeNav - 个人导航站

一个个人主页/导航静态网站，自动化构建和部署，帮助你整理和展示你的网络收藏/项目

## 目录

- [在线预览](#在线预览)
- [功能特点](#功能特点)
- [近期更新](#近期更新)
- [技术栈](#技术栈)
- [项目结构](#项目结构)
- [快速开始](#快速开始)
- [部署方式](#部署方式)
  - [快速部署到GitHub Pages](#快速部署到github-pages)
- [书签导入功能](#书签导入功能)
  - [使用方法](#使用方法)
  - [自动化工作流程详解](#自动化工作流程详解)
  - [书签配置自定义](#书签配置自定义)
- [模板说明](#模板说明)
- [配置文件结构](#配置文件结构)
- [设置网站字体](#设置网站字体)
- [设置网站图标](#设置网站图标)
- [添加新的网站链接](#添加新的网站链接)
- [贡献](#贡献)
- [许可证](#许可证)

## 在线预览

访问：[https://rbetree.github.io/menav/](https://rbetree.github.io/menav/)

## 功能特点

- 🎨 简洁美观的界面设计
- 📱 响应式布局，支持移动端
- 🔍 实时搜索功能
- 🎯 分类展示网站链接
- 👥 支持展示社交媒体链接
- 📝 支持多个内容页面（首页、项目、文章、友链）
- 📌 支持从浏览器导入书签

## 近期更新

### 2025/05/02

**1. 页面布局优化**
- ✅ 优化了内容区域和侧边栏的间距，确保各种分辨率下内容不会贴近边缘
- ✅ 卡片与边框始终保持合理间距，避免在窄屏设备上与滚动条贴边
- ✅ 调整了搜索结果区域的边距，与常规分类保持样式一致性

**2. 网站卡片文本优化**
- ✅ 为站点卡片标题添加单行文本截断，过长标题显示省略号
- ✅ 为站点描述添加两行限制和省略号，保持卡片布局整洁
- ✅ 添加卡片悬停提示，方便查看完整信息

**3. 移动端显示增强**
- ✅ 优化了移动端卡片尺寸，一屏可显示更多网址
- ✅ 图标大小自适应，在小屏幕上更加紧凑（从1.8rem减小到1.2-1.5rem）
- ✅ 为不同尺寸移动设备（768px、480px、400px）提供递进式UI优化
- ✅ 减小卡片内边距和元素间距，增加屏幕利用率

**4. 书签导入功能**
- ✅ 支持从Chrome、Firefox和Edge浏览器导入HTML格式书签
- ✅ 自动处理书签文件，解析文件夹结构和链接
- ✅ 智能匹配网站图标，根据URL自动分配合适的Font Awesome图标
- ✅ 生成配置文件，无需手动录入即可批量导入网站链接
- ✅ 与GitHub Actions集成，全自动化的导入和部署流程

## 技术栈

- HTML5 + CSS3
- JavaScript (原生)
- Font Awesome 图标
- GitHub Pages托管

## 项目结构

```
menav/
├── assets/           # 静态资源文件
│   ├── style.css     # 样式表
│   └── favicon.ico   # 网站图标
├── src/              # 源代码
│   ├── generator.js  # 静态网站生成器
│   └── script.js     # 前端JavaScript脚本
├── templates/        # HTML模板
│   └── index.html    # HTML骨架模板文件
├── dist/             # 生成的静态网站（由generator.js生成）
├── bookmarks/        # 书签导入目录
├── config.yml        # 默认配置文件
└── config.user.yml   # 用户自定义配置文件
```

## 快速开始

1. 克隆仓库
```bash
git clone https://github.com/rbetree/menav.git
cd menav
```

2. 安装依赖
```bash
# 清理旧的依赖(如果需要)
rm -rf node_modules
rm -f package-lock.json

# 安装新的依赖
npm install
```

3. 修改配置
- 复制 `config.yml` 为 `config.user.yml`
- 在 `config.user.yml` 中根据你的需求修改网站内容：
   - 修改网站基本信息
   - 添加/修改导航链接
   - 自定义社交媒体链接
   - 更新个人项目展示
   - 添加友情链接等


4. 本地预览
```bash
npm run dev
```

## 部署方式

### 快速部署到GitHub Pages

#### 第一步：前置设置

1. Fork仓库:
   - 点击右上角的 Fork 按钮复制此仓库到您的账号

2. 启用必要功能:
   - 进入仓库的 Settings -> General
   - 找到 Features 部分
   - 勾选 "Issues"

3. 启用Actions:
      - 进入fork后的仓库
      - 点击顶部的 "Actions" 标签页
      - 点击绿色按钮 "I understand my workflows, go ahead and enable them"

4. 配置Pages:
   - 进入仓库的 Settings -> Pages
   - 在 "Build and deployment" 部分
   - Source: 选择 "GitHub Actions"

#### 第二步：自定义配置

1. 创建个人配置文件:
   - 复制 `config.yml` 为 `config.user.yml`
   - 在 `config.user.yml` 中修改配置
   - 提交 `config.user.yml` 到您的仓库，这样GitHub Actions才能使用您的自定义配置进行构建

2. 修改配置信息:
   - 修改网站基本信息
   - 添加/修改导航链接
   - 自定义社交媒体链接
   - 更新个人项目展示
   - 添加友情链接等

完成以上步骤后,系统会自动部署您的网站。部署完成后,您可以在 Settings -> Pages 中找到您的网站地址。

> 重要提示: 请务必使用 `config.user.yml` 进行配置,这样在同步上游更新时不会丢失您的个人设置。同时注意不要在配置文件中包含敏感信息，因为它将被提交到公开仓库。

#### 故障排除

如果遇到部署问题:
1. 请确保完成了所有前置设置步骤
2. 检查每个设置页面是否都点击了 Save 按钮
3. 如果修改设置后部署仍然失败:
   - 进入 Actions 标签页
   - 找到失败的工作流
   - 点击 "Re-run all jobs" 重新运行


## 书签导入功能

### 使用方法

1. **从浏览器导出书签**
   - 在Chrome中: 打开书签管理器 -> 点击"更多"(三个点) -> 导出书签
   - 在Firefox中: 打开书签库 -> 显示所有书签 -> 导入和备份 -> 导出书签为HTML
   - 在Edge中: 设置 -> 收藏夹 -> 管理收藏夹 -> 导出为HTML文件

2. **导入书签到MeNav**
   - 在项目根目录下创建 `bookmarks` 文件夹(如果不存在)
   - 将导出的HTML书签文件放入 `bookmarks` 文件夹
   - 提交并推送变更到仓库
   - GitHub Actions将自动处理书签文件并生成书签配置

3. **书签处理流程**
   - 系统会扫描 `bookmarks` 目录，查找最新的HTML书签文件
   - 解析书签文件中的链接和文件夹结构
   - 自动为书签分配适当的图标
   - 生成 `bookmarks.user.yml` 配置文件（而不是直接修改 `bookmarks.yml`）
   - 处理完成后会自动清空 `bookmarks` 目录(防止重复处理)
   - 重新构建并部署网站

4. **注意事项**
   - 每次只处理一个书签文件，如有多个文件，系统会选择最新的那个
   - 书签导入是构建时的一次性操作，不会在浏览器中保存或同步您的书签
   - 如果想要更新书签，可以直接编辑 `bookmarks.user.yml`，或重新导出书签文件并重新导入
   - 系统会优先使用 `bookmarks.user.yml`，如果同时存在 `bookmarks.yml`，它们的内容会被合并（用户配置优先）

### 自动化工作流程详解

MeNav使用单一的GitHub Actions工作流处理书签导入与网站部署，实现了无缝集成：

1. **触发条件**:
   - 当您推送任何更改到主分支（特别是向 `bookmarks` 目录添加HTML文件）时
   - 手动触发工作流时

2. **书签处理步骤**:
   - 自动检测 `bookmarks` 目录中的HTML文件
   - 使用 `bookmark-processor.js` 脚本处理书签文件
   - 生成/更新 `bookmarks.user.yml` 配置文件
   - 提交更改（如有）并保存至仓库
   - 自动清理已处理的HTML书签文件

3. **网站构建与部署**:
   - 基于最新的配置（包括新生成的书签配置）构建网站
   - 自动将构建结果部署到GitHub Pages

4. **故障排除**:
   - 如果书签未正确显示，请检查导出的HTML文件格式是否标准
   - 可以通过GitHub Actions日志查看处理过程中的详细信息
   - 确保书签文件是有效的HTML格式，且包含正确的书签数据结构

### 书签配置自定义

处理后生成的 `bookmarks.user.yml` 文件可以手动编辑以进一步自定义:

```yaml
# 自动生成的书签配置示例（用户自定义版本）
title: 我的书签
subtitle: 从浏览器导入的书签收藏
categories:
  - name: 开发工具
    icon: fas fa-folder
    sites:
      - name: GitHub
        url: https://github.com
        icon: fab fa-github
        description: "从书签导入: GitHub"
      # 更多网站...
  # 更多分类...
```

您可以：
- 修改分类和网站的名称和描述
- 调整图标（使用Font Awesome图标类）
- 重新组织书签分类结构
- 添加或删除特定书签

**提示**: 
- 尽管自动处理会清理原始HTML文件，但修改后的 `bookmarks.user.yml` 会被保留，您可以随时手动编辑它来更新书签内容
- 如果项目中同时存在 `bookmarks.yml` 和 `bookmarks.user.yml`，系统会合并两者的内容，以 `bookmarks.user.yml` 中的配置为优先
- 这种设计允许您在更新源仓库时保留自己的书签配置

### 模板说明

本项目使用模板与配置文件分离的方式生成网站:

1. `templates/index.html` 是不包含具体内容的HTML骨架模板:
   - 使用占位符 (如 `{{SITE_TITLE}}`, `{{NAVIGATION}}`, `{{HOME_CONTENT}}`) 标记动态内容的位置
   - 只包含页面结构、CSS引用和基本Javascript引用

2. 工作原理:
   - `generator.js` 读取配置文件 (优先使用 `config.user.yml`)
   - 将配置内容注入到模板中的占位符位置
   - 生成最终的静态HTML网站

3. 优点:
   - 清晰分离结构与内容
   - 用户只需修改配置文件,不需要编辑HTML
   - 便于更新与维护


### 配置文件结构

`config.user.yml` 应包含以下主要部分：

```yaml
# 网站基本信息
site:
  title: 网站标题
  description: 网站描述
  author: 作者名
  favicon: favicon.ico  # 网站图标,支持ico、png等格式

# 字体设置
fonts:
  title:  # 标题字体
    family: 字体名称  # 可以是Web安全字体或Google Fonts
    weight: 字重值  # 如400、500、600等
    source: 字体来源  # "google"或"system"
  subtitle:  # 副标题字体
    family: 字体名称
    weight: 字重值
    source: 字体来源
  body:  # 正文字体
    family: 字体名称
    weight: 字重值
    source: 字体来源

# 个人信息
profile:
  title: 欢迎语
  subtitle: 副标题
  description: 描述

# 导航菜单
navigation:
  - name: 菜单名称
    icon: 图标类名
    id: 页面ID
    active: 是否激活

# 更多配置...
```

### 设置网站字体

1. 字体配置选项:
   - `family`: 字体名称，支持Web安全字体或Google Fonts
   - `weight`: 字体粗细，常用值如400(常规)、500(中等)、600(粗体)等
   - `source`: 字体来源，可选"google"或"system"
   
2. 字体分类:
   - `title`: 标题字体，用于大标题
   - `subtitle`: 副标题字体，用于副标题
   - `body`: 正文字体，用于普通文本

3. 使用Google字体示例:
```yaml
fonts:
  body:
    family: "Noto Sans SC"  # Google提供的中文字体
    weight: 400
    source: "google"
```

4. 使用系统字体示例:
```yaml
fonts:
  body:
    family: "Segoe UI, system-ui, -apple-system, sans-serif"
    weight: 400
    source: "system"
```

### 设置网站图标

1. 准备图标文件:
   - 支持.ico、.png等格式
   - 建议尺寸为32x32或16x16像素
   - 将图标文件放在assets目录下
   - 例如: `assets/favicon.ico` 或 `assets/favicon.png`

2. 配置图标:
   - 在`config.yml`或`config.user.yml`的site部分设置favicon
   - 使用相对于仓库根目录的路径
   - 例如: `favicon: favicon.ico`（generator会自动从assets目录查找）
   - 也可以使用在线图标URL

3. 生成和部署:
   - 运行 `npm run generate` 时会自动复制图标文件到dist目录
   - 确保图标文件存在于assets目录中
   - 部署后图标会自动显示在浏览器标签页

> 提示: 如果图标没有显示,请检查:
> 1. 图标文件是否存在于assets目录
> 2. 配置文件中的路径是否正确
> 3. 是否重新运行了生成命令

### 添加新的网站链接

在 `config.user.yml` 中相应的分类下添加新站点：

```yaml
categories:
  - name: 分类名称
    icon: 分类图标
    sites:
      - name: 网站名称
        url: 网站地址
        icon: 网站图标
        description: 网站描述
```

## 贡献

欢迎提交 Issue 和 Pull Request 来帮助改进这个项目。

## 许可证

MIT License 