# 归光 · 六爻排盘

纯静态单页六爻排盘工具，App 风格三页：输入、卦局、逐爻。单 HTML 文件、无外部依赖、可离线使用。

## 本地使用

直接浏览器打开 `index.html` 即可离线使用。

## 仓库结构

| 文件 | 说明 |
| --- | --- |
| `index.html` | 唯一应用入口，全部逻辑/样式内联，无外部依赖 |
| `netlify.toml` | Netlify 部署配置（纯静态，publish=`./`） |
| `_redirects` | 任意路由回写首页，配合 SPA / 静态重写 |
| `README.md` | 本说明 |

## 部署 Netlify（自动部署）

前提：将本仓库推送到 GitHub（建议私有仓库 `liuyao-paipan`）。

方式一（推荐 · Git 集成自动部署）：

1. 到 [Netlify](https://app.netlify.com) → `Add new site` → `Import an existing project`。
2. 选择 `GitHub` 并授权，选中仓库 `liuyao-paipan`。
3. 构建设置保持默认：
   - Build command：留空（纯静态）
   - Publish directory：`.`（或 `/`，二者等价均可）
4. `Deploy site`。之后每次 push 到仓库都会自动触发构建发布。

方式二：若只做本地备份、后续手动发布，可直接把整个文件夹拖到 Netlify Drop（[app.netlify.com/drop](https://app.netlify.com/drop)）。

## 配置约定

- Build command：无（纯静态）。
- Publish directory：`.`（根目录）。
- 自动生成 HTTPS；任意路由经 `_redirects`/`[[redirects]]` 回写首页。