# menav
 A personal navigation page that serves as your web identity card and bookmark collection. 一个作为个人网络身份证和网页收藏夹的导航页面。
# 个人导航站

一个美观、响应式的个人导航网站，集成了搜索功能和分类展示。

## 功能特点

- 🎯 分类展示：首页、项目、文章和友链四大版块
- 🔍 实时搜索：支持跨页面快速搜索
- 📱 响应式设计：完美适配移动端和桌面端
- 🎨 现代化界面：优雅的动画和过渡效果
- 🌙 暗色主题：护眼的深色模式
- 🚀 高性能：优化的动画和渲染性能

## 技术栈

- HTML5
- CSS3 (Flexbox, Grid, 动画)
- JavaScript (ES6+)
- Font Awesome 图标

## 项目结构

```
├── index.html      # 主页面
├── style.css       # 样式文件
├── script.js       # 交互脚本
└── README.md       # 项目文档
```

## 使用说明

1. 克隆项目到本地：
```bash
git clone [repository-url]
```

2. 直接打开 `index.html` 文件或使用本地服务器运行：
```bash
# 使用 Python 启动简单的 HTTP 服务器
python -m http.server 8000
```

3. 在浏览器中访问：
- 直接打开：双击 `index.html`
- 本地服务器：访问 `http://localhost:8000`

## 自定义配置

### 添加新的导航项

在 `index.html` 中的相应分类下添加新的卡片：

```html
<a href="你的链接" class="site-card">
    <i class="fas fa-icon"></i>
    <h3>标题</h3>
    <p>描述</p>
</a>
```

### 修改样式

可以在 `style.css` 中自定义以下样式：

- 主题颜色
- 卡片样式
- 动画效果
- 响应式布局

## 性能优化

项目已实现以下优化：

- 使用 `will-change` 优化动画性能
- 实现搜索防抖
- 批量 DOM 更新
- 使用 `requestAnimationFrame` 优化动画
- CSS 动画硬件加速

## 浏览器支持

- Chrome (推荐)
- Firefox
- Safari
- Edge

## 开发计划

- [ ] 添加明暗主题切换
- [ ] 支持自定义分类
- [ ] 添加更多动画效果
- [ ] 支持数据持久化
- [ ] 添加更多自定义选项

## 贡献指南

1. Fork 项目
2. 创建特性分支：`git checkout -b feature/AmazingFeature`
3. 提交改动：`git commit -m 'Add some AmazingFeature'`
4. 推送分支：`git push origin feature/AmazingFeature`
5. 提交 Pull Request

## 许可证

MIT License - 详见 LICENSE 文件 