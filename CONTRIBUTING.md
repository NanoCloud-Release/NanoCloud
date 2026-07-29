# NanoCloud 内容更新实践

仓库同时维护 GitHub README 和 GitHub Pages。两者面向不同阅读场景，
但涉及产品信息、教程、排障、安全结论、网络观察或外部链接时，
必须在同一个 Pull Request 中同步检查。

## 修改前

1. 明确事实来源和核验日期。产品操作优先引用 NanoCloud 官方教程，Mihomo 配置优先核对当前官方文档。
2. 区分直接测量、部署材料、运营者转述和用户反馈，避免把局部现象写成全国结论。
3. 不提交订阅 URL、UUID、密码、token、浏览器配置或本地测试产物。

## 同步范围

- `README.md`：GitHub 仓库中的完整说明和证据边界。
- `index.html`：Pages 的可浏览版本，应保留与 README 一致的关键结论、操作入口和来源。
- `assets/site.css`、`assets/site.js`：只在页面布局或交互确实需要时修改。

只改 README 不代表 Pages 正文已更新。只改 Pages 也会让 GitHub 读者看到过时内容。

## 提交与部署

1. 从最新 `main` 创建 `codex/<description>` 分支。
2. 只暂存本次相关文件，运行 `git diff --check` 并检查完整差异。
3. 对 Pages 变更执行 HTML 校验，并在桌面和移动视口检查正文、折叠区、表格和 Mermaid。
4. 推送分支并通过 Pull Request 合并，不直接向 `main` 堆叠未经审阅的内容修改。
5. 合并后确认 GitHub Pages Actions 对应的是新的 `main` 提交且结论为 `success`。
6. 打开线上页面验证新增正文标记、链接和交互。删除公开文件时，还要确认原 URL 返回 `404`。

Actions 构建成功只表示当前文件已发布，不能证明 README 的变化已经同步进 `index.html`。部署完成以线上内容检查为准。
