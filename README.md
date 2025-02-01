# MeNav - 个人导航站

一个美观、响应式的个人导航网站，集成了搜索功能和分类展示。支持通过配置文件管理网站内容，自动构建部署。

## 功能特点

- 🎯 分类展示：首页、项目、文章和友链四大版块
- 🔍 实时搜索：支持跨页面快速搜索
- 📱 响应式设计：完美适配移动端和桌面端
- 🎨 现代化界面：优雅的动画和过渡效果
- 🌙 暗色主题：护眼的深色模式
- 🚀 自动化部署：支持多种部署方式
- ⚙️ 配置驱动：通过 YAML 文件管理内容

## 部署方式

### 1. GitHub Pages 部署（最简单）

适合个人使用，完全免费，自动部署。

1. Fork 本仓库
```bash
# 1. 点击 GitHub 页面右上角的 Fork 按钮
# 2. 选择你的账号
```

2. 设置仓库（可选）
```bash
# 如果需要，可以将仓库设为私有
Settings -> General -> Change repository visibility -> Private
```

3. 启用 GitHub Pages
```bash
# 1. 进入仓库设置
Settings -> Pages
# 2. 选择 GitHub Actions 作为来源
```

4. 修改配置
```bash
# 编辑 config.yml 文件，添加你的网站内容
git add config.yml
git commit -m "更新配置"
git push
```

GitHub Actions 会自动构建并部署到 GitHub Pages。

### 2. 服务器部署（自动构建）

适合需要自定义域名和更多控制的场景。

1. 克隆仓库到服务器
```bash
git clone https://github.com/你的用户名/menav.git
cd menav
```

2. 安装依赖
```bash
npm install
```

3. 设置定时任务
```bash
# 编辑 crontab
crontab -e

# 添加定时任务（每小时构建一次）
0 * * * * cd /path/to/menav && npm run generate

# 或者使用 watch 模式（需要安装 nodemon）
npm install -g nodemon
nodemon --watch config.yml -e yml --exec "npm run generate"
```

4. 配置 Nginx
```nginx
server {
    listen 80;
    server_name your-domain.com;
    root /path/to/menav;
    index index.html;

    location / {
        try_files $uri $uri/ /index.html;
    }
}
```

### 3. 本地构建部署

适合已有网站空间，只需要静态文件的场景。

1. 克隆仓库
```bash
git clone https://github.com/你的用户名/menav.git
cd menav
```

2. 安装依赖并构建
```bash
npm install
npm run generate
```

3. 部署生成的文件
```bash
# 生成的文件在根目录：
- index.html
- style.css
- script.js

# 将这些文件上传到你的网站空间
```

### 4. Cloudflare Pages 部署

适合需要 CDN 加速和免费托管的场景。

1. Fork 仓库并连接到 Cloudflare
```bash
# 1. Fork 本仓库
# 2. 登录 Cloudflare Dashboard
# 3. Pages -> Create a project -> Connect to Git
# 4. 选择你的仓库
```

2. 配置构建设置
```bash
# Build settings:
Build command: npm run generate
Build output directory: /
```

3. 环境变量（可选）
```bash
NODE_VERSION: 16
```

4. 部署
```bash
# 1. 修改配置
# 2. 推送到 GitHub
# 3. Cloudflare Pages 会自动构建和部署
```

## 配置说明

`config.yml` 文件结构：

```yaml
# 网站基本信息
site:
  title: 网站标题
  description: 网站描述
  author: 作者名

# 个人信息
profile:
  title: 欢迎语
  subtitle: 副标题
  description: 个人描述

# 导航菜单
navigation:
  - name: 菜单名称
    icon: 图标类名
    id: 页面ID
    active: 是否激活

# 分类示例
categories:
  - name: 分类名称
    icon: 分类图标
    sites:
      - name: 网站名称
        url: 网站地址
        icon: 网站图标
        description: 网站描述
```

## 本地开发

1. 克隆仓库
```bash
git clone https://github.com/你的用户名/menav.git
cd menav
```

2. 安装依赖
```bash
npm install
```

3. 修改配置
```bash
# 编辑 config.yml
```

4. 本地预览
```bash
# 生成网站
npm run generate

# 启动本地服务器
python -m http.server 8000
# 或
npm install -g serve
serve .
```

## 更新上游代码

如果你 Fork 了本项目，可以通过以下方式获取更新：

```bash
# 1. 添加上游仓库
git remote add upstream https://github.com/原始用户名/menav.git

# 2. 获取更新
git fetch upstream

# 3. 合并更新（注意处理配置文件的冲突）
git merge upstream/main
```

## 自定义主题

1. 修改 `style.css`
```css
/* 修改主题色 */
:root {
    --primary-color: #你的颜色;
    --background-color: #你的颜色;
    /* 其他颜色变量 */
}
```

2. 添加新的样式
```css
/* 添加自定义样式 */
.your-custom-class {
    /* 你的样式 */
}
```

## 常见问题

1. 如何添加新网站？
- 编辑 `config.yml` 文件
- 在相应分类下添加网站信息
- 提交并推送更改

2. 如何修改图标？
- 使用 Font Awesome 图标
- 在 [Font Awesome 网站](https://fontawesome.com/icons) 查找图标
- 复制图标类名（例如：`fas fa-home`）

3. 部署失败？
- 检查 GitHub Pages 设置
- 确认 Actions 权限
- 查看 Actions 日志

## 贡献指南

1. Fork 项目
2. 创建特性分支
```bash
git checkout -b feature/AmazingFeature
```
3. 提交改动
```bash
git commit -m 'Add some AmazingFeature'
```
4. 推送分支
```bash
git push origin feature/AmazingFeature
```
5. 创建 Pull Request

## 许可证

本项目采用 MIT 许可证 - 详见 [LICENSE](LICENSE) 文件

## 致谢

- [Font Awesome](https://fontawesome.com/) - 图标库
- [GitHub Pages](https://pages.github.com/) - 托管服务
- [GitHub Actions](https://github.com/features/actions) - 自动化部署 