# 开发文档

## 快速开始

### 开发环境要求
- 现代浏览器（Chrome/Firefox/Safari/Edge 最新版本）
- 代码编辑器（推荐 VS Code）
- 本地服务器（可选，用于开发）

### 环境设置
1. 克隆项目：
```bash
git clone [repository-url]
cd [project-name]
```

2. VS Code 推荐插件：
- Live Server（实时预览）
- Prettier（代码格式化）
- ESLint（代码检查）
- CSS Peek（CSS 查看）

3. 启动开发服务器：
```bash
# 使用 Python
python -m http.server 8000

# 或使用 VS Code Live Server
# 右键 index.html -> Open with Live Server
```

## 项目架构

### 整体架构
```
[项目根目录]
├── index.html          # 主页面
├── style.css          # 样式文件
├── script.js          # 主脚本
├── README.md          # 项目说明
└── DEVELOPMENT.md     # 开发文档
```

### 核心模块说明

#### 1. 页面管理模块
```javascript
// 页面切换核心函数
function showPage(pageId, skipSearchReset = false) {
    // pageId: 目标页面ID
    // skipSearchReset: 是否跳过搜索重置
}

// 使用示例：
showPage('home');  // 切换到首页
showPage('projects', true);  // 切换到项目页，保持搜索状态
```

#### 2. 搜索引擎模块
```javascript
// 搜索实现核心函数
function performSearch(searchTerm) {
    // searchTerm: 搜索关键词
    // 返回：匹配的结果
}

// 搜索结果处理
function handleSearchResults(results) {
    // results: 搜索结果数组
}
```

#### 3. 动画系统
```css
/* 页面切换动画 */
.page {
    transition: opacity 0.3s ease, transform 0.3s ease;
}

/* 搜索结果动画 */
.search-section {
    transition: opacity 0.3s ease, transform 0.3s ease;
}
```

## 开发指南

### 1. 添加新页面

1. HTML 结构：
```html
<div class="page" id="your-page-id">
    <div class="welcome-section">
        <h2>页面标题</h2>
        <p class="subtitle">页面描述</p>
    </div>
    
    <section class="category">
        <h2><i class="fas fa-icon"></i> 分类标题</h2>
        <div class="sites-grid">
            <!-- 网站卡片 -->
        </div>
    </section>
</div>
```

2. 注册导航：
```html
<a href="#" class="nav-item" data-page="your-page-id">
    <i class="fas fa-icon"></i>
    <span>页面名称</span>
</a>
```

3. 添加样式：
```css
#your-page-id {
    /* 页面特定样式 */
}

#your-page-id .category {
    /* 分类样式 */
}
```

### 2. 自定义搜索范围

1. 修改搜索逻辑：
```javascript
function performSearch(searchTerm) {
    // 1. 在 script.js 中找到 performSearch 函数
    // 2. 添加新的搜索范围：
    const newPageCards = document.querySelectorAll('#your-page-id .site-card');
    newPageCards.forEach(card => {
        // 添加搜索逻辑
    });
}
```

2. 添加结果展示区域：
```html
<section class="category search-section" data-section="your-page-id">
    <h2><i class="fas fa-icon"></i> 新页面匹配项</h2>
    <div class="sites-grid"></div>
</section>
```

### 3. 添加新功能

1. 创建功能模块：
```javascript
// 在 script.js 中添加新模块
const newFeature = {
    init() {
        // 初始化代码
    },
    
    // 功能方法
    someMethod() {
        // 方法实现
    }
};

// 初始化
document.addEventListener('DOMContentLoaded', () => {
    newFeature.init();
});
```

2. 添加相关样式：
```css
/* 在 style.css 中添加样式 */
.new-feature {
    /* 功能相关样式 */
}
```

## 性能优化指南

### 1. 动画性能优化
```css
/* 使用 transform 代替位置属性 */
.element {
    transform: translateX(100px);
    will-change: transform;
}

/* 使用 opacity 代替 visibility */
.element {
    opacity: 0;
    transition: opacity 0.3s ease;
}
```

### 2. 搜索性能优化
```javascript
// 实现防抖
const debounce = (fn, delay) => {
    let timer = null;
    return (...args) => {
        if (timer) clearTimeout(timer);
        timer = setTimeout(() => {
            fn.apply(this, args);
        }, delay);
    };
};

// 使用 Map 优化查找
const searchIndex = new Map();
```

### 3. DOM 操作优化
```javascript
// 使用文档片段
const fragment = document.createDocumentFragment();
elements.forEach(el => fragment.appendChild(el));
container.appendChild(fragment);

// 批量更新
requestAnimationFrame(() => {
    // DOM 更新操作
});
```

## 调试技巧

### 1. 常见问题排查
```javascript
// 页面切换问题
console.log('当前页面:', currentPageId);
console.log('搜索状态:', isSearchActive);

// 搜索问题
console.log('搜索词:', searchTerm);
console.log('结果数:', results.length);
```

### 2. 性能监控
```javascript
// 性能标记
performance.mark('featureStart');
// ... 代码执行 ...
performance.mark('featureEnd');
performance.measure('featureDuration', 'featureStart', 'featureEnd');
```

## 发布流程

### 1. 代码检查
```bash
# 运行代码格式化
prettier --write "**/*.{html,css,js}"

# 运行代码检查
eslint "**/*.js"
```

### 2. 性能测试
- 使用 Chrome DevTools 的 Performance 面板
- 检查页面加载时间
- 检查动画性能
- 内存使用监控

### 3. 部署前检查清单
- [ ] 所有链接可访问
- [ ] 响应式布局正常
- [ ] 搜索功能正常
- [ ] 动画效果流畅
- [ ] 控制台无错误

## 维护指南

### 1. 代码更新
- 遵循语义化版本控制
- 保持文档同步更新
- 记录重要更改

### 2. 性能监控
- 定期检查性能指标
- 分析用户反馈
- 优化改进建议

### 3. 问题追踪
- 使用 GitHub Issues 跟踪问题
- 详细记录问题复现步骤
- 及时响应用户反馈 