# MeNav - 个人导航站

一个简洁美观的个人导航网站，帮助你整理和展示你的网络收藏。

## 在线预览

访问：[https://rzlnb.github.io/menav/](https://rzlnb.github.io/menav/)

## 功能特点

- 🎨 简洁美观的界面设计
- 📱 响应式布局，支持移动端
- 🔍 实时搜索功能
- 🎯 分类展示网站链接
- 👥 支持展示社交媒体链接
- 📝 支持多个内容页面（首页、项目、文章、友链）

## 技术栈

- HTML5 + CSS3
- JavaScript (原生)
- Font Awesome 图标
- GitHub Pages / Cloudflare Pages 托管

## 快速开始

1. 克隆仓库
```bash
git clone https://github.com/RZLNB/menav.git
cd menav
```

2. 安装依赖
```bash
npm install
```

3. 修改配置
编辑 `config.yml` 文件，根据你的需求修改网站内容：
- 修改网站基本信息
- 添加/修改导航链接
- 自定义社交媒体链接
- 更新个人项目展示
- 添加友情链接等

4. 本地预览
```bash
npm run generate
```
然后在浏览器中打开 `index.html` 文件

## 部署方式

### GitHub Pages 部署

注意：GitHub Pages 在免费计划下只支持公开仓库。如果你需要保持仓库私有，建议：
- 升级到 GitHub Pro 或更高级的付费计划
- 或使用 Cloudflare Pages 部署（支持私有仓库）

部署步骤：
1. Fork 这个仓库
2. 修改你的配置
3. 推送到GitHub
4. 启用GitHub Pages（选择 gh-pages 分支）

### Cloudflare Pages 部署

支持公开和私有仓库，完全免费。

1. Fork 仓库到你的GitHub账号

2. 登录 Cloudflare Dashboard
   - 进入 Pages 页面
   - 点击 "Create a project"
   - 选择 "Connect to Git"
   - 选择你fork的仓库

3. 设置构建配置
   - 构建命令：`npm run generate`
   - 构建输出目录：`/`
   - Node.js 版本：`16`（或更高版本）

4. 环境变量（可选）
   ```
   NODE_VERSION: 16
   ```

5. 部署
   - 点击 "Save and Deploy"
   - Cloudflare Pages 会自动构建和部署你的网站
   - 部署完成后，你会得到一个 `*.pages.dev` 的域名

6. 自定义域名（可选）
   - 在项目设置中添加你的自定义域名
   - 按照 Cloudflare 的说明配置 DNS 记录

优点：
- 全球 CDN 加速
- 自动 HTTPS
- 持续部署
- 免费额度大
- 可以绑定自定义域名

## 自定义配置

### 配置文件结构

`config.yml` 包含以下主要部分：

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
  description: 描述

# 导航菜单
navigation:
  - name: 菜单名称
    icon: 图标类名
    id: 页面ID
    active: 是否激活

# 更多配置...
```

### 添加新的网站链接

在 `config.yml` 中相应的分类下添加新站点：

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