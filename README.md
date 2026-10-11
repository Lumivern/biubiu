# biubiu

BiuBiu酱 的公告托管仓库。

## 怎么发公告

1. 打开仓库里的 `update.json`
2. 点右上角铅笔图标（编辑）
3. 改这几个地方：
   - `version`：加 1（比如 3 改成 4），**必须递增**，否则客户端不会重新弹
   - `title`：公告标题
   - `content`：公告正文（HTML 格式）
   - `show`：`true` 显示，`false` 隐藏
4. 点下方 **Commit changes** 提交

提交后约 1 分钟生效。客户端最多 5 分钟后能看到。

## 字段说明

```jsonc
{
  "announcement": {
    "title": "官方公告",       // 弹窗标题
    "version": 3,              // 整数，必须比上次大才会重新弹
    "show": true,              // false 可临时关闭公告
    "content": "<div>...</div>" // HTML 正文，支持任意 HTML
  }
}
```

## 正文可以写什么

`content` 是 HTML，可以用：

- `<p>` 段落
- `<img src="...">` 图片
- `<strong>` 加粗
- `<details><summary>展开</summary>...</details>` 折叠内容
- `<a href="...">链接</a>`
- 内联 `style="..."` 自定义样式

## 注意

- **不要删 `.nojekyll`** —— 没有它 GitHub 会忽略 `update.json`
- `version` 是整数且必须递增
- 提交后 Pages 需要约 1 分钟重建

## 客户端配置

地址配置在 App 内的 `GH_CONFIG.base`，指向本仓库启用的 Pages 地址。
