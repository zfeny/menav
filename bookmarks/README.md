# 书签导入目录

将从浏览器导出的HTML书签文件放在此目录中，系统会自动处理并导入到您的导航站。

## 使用步骤

1. 从浏览器导出书签为HTML文件:
   - **Chrome**: 书签管理器 → 更多 → 导出书签
   - **Firefox**: 书签库 → 显示所有书签 → 导入和备份 → 导出书签为HTML
   - **Edge**: 设置 → 收藏夹 → 管理收藏夹 → 导出为HTML文件

2. 将导出的HTML文件放入此目录中

3. 提交并推送到GitHub:
   ```bash
   git add bookmarks/你的书签文件.html
   git commit -m "添加书签文件"
   git push
   ```

4. GitHub Actions将自动处理书签文件，生成`bookmarks.user.yml`，并重新构建站点

## 注意事项

- 仅支持标准HTML格式的书签文件
- 每次只会处理目录中最新的一个书签文件
- 处理完成后，书签文件会被自动清除，以防止重复处理
- 已导入的书签可以在生成的`bookmarks.user.yml`文件中查看和编辑
- 系统会优先使用`bookmarks.user.yml`的配置，如果存在`bookmarks.yml`，会自动合并两者的内容（用户配置优先） 