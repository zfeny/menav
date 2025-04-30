# 贡献指南

感谢您对本项目感兴趣！我们欢迎任何形式的贡献，包括但不限于：功能改进、bug修复、文档完善等。

## 目录

- [行为准则](#行为准则)
- [如何贡献](#如何贡献)
- [开发流程](#开发流程)
- [提交规范](#提交规范)
- [问题反馈](#问题反馈)

## 行为准则

本项目采用 [Contributor Covenant](https://www.contributor-covenant.org/version/2/0/code_of_conduct/) 行为准则。参与本项目即表示您同意遵守此准则。

## 如何贡献

### 1. Fork 项目
1. 访问 [项目主页](https://github.com/yourusername/nav-page)
2. 点击 "Fork" 按钮创建项目副本

### 2. 克隆项目
```bash
git clone https://github.com/your-username/nav-page.git
cd nav-page
```

### 3. 创建分支
```bash
git checkout -b feature/your-feature-name
# 或
git checkout -b fix/your-fix-name
```

### 4. 进行修改
- 遵循项目的代码规范
- 保持代码整洁
- 添加必要的注释
- 更新相关文档

### 5. 提交更改
```bash
git add .
git commit -m "feat: add new feature"
git push origin feature/your-feature-name
```

### 6. 创建 Pull Request
1. 访问您的 Fork 仓库
2. 点击 "Pull Request" 按钮
3. 选择要合并的分支
4. 填写 PR 描述
5. 提交 PR

## 开发流程

### 1. 分支管理
- `main`: 主分支，保持稳定
- `develop`: 开发分支
- `feature/*`: 新功能分支
- `fix/*`: 修复分支
- `docs/*`: 文档更新分支

### 2. 开发步骤
1. 从最新的 develop 分支创建特性分支
2. 在特性分支上进行开发
3. 提交代码前进行自测
4. 创建 Pull Request
5. 等待代码审查
6. 合并到 develop 分支

## 提交规范

### 1. 提交信息格式
```
<type>(<scope>): <subject>

<body>

<footer>
```

### 2. Type 类型
- feat: 新功能
- fix: 修复
- docs: 文档更改
- style: 代码格式
- refactor: 重构
- test: 测试
- chore: 构建过程或辅助工具的变动

### 3. 示例
```
feat(nav): add new navigation item

- Add social media links
- Update navigation styles
- Add hover effects

Closes #123
```

## 问题反馈

### 1. 提交 Issue
- 使用适当的 Issue 模板
- 清晰描述问题
- 提供复现步骤
- 附上相关截图或代码

### 2. Issue 类型
- Bug 报告
- 功能请求
- 文档完善
- 使用疑问

## 审查标准

### 1. 代码审查
- 代码质量
- 命名规范
- 注释完整性
- 测试覆盖
- 性能影响

### 2. 文档审查
- 文档完整性
- 描述准确性
- 示例正确性
- 格式规范

## 发布流程

### 1. 版本号规范
遵循 [语义化版本](https://semver.org/lang/zh-CN/) 规范：
- 主版本号：不兼容的 API 修改
- 次版本号：向下兼容的功能性新增
- 修订号：向下兼容的问题修正

### 2. 发布步骤
1. 更新版本号
2. 更新 CHANGELOG.md
3. 创建发布标签
4. 发布新版本

## 联系方式

如有任何问题，请通过以下方式联系我们：
- 提交 Issue
- 发送邮件
- 加入讨论组

感谢您的贡献！ 