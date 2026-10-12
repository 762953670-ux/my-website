# AGENTS.md

MkDocs 个人网站，使用 Material 主题、中文界面（`language: zh`），站点名「Luka的测试站点」。

## 常用命令

- 本地预览：`mkdocs serve`（在项目根目录运行，默认 http://127.0.0.1:8000/）
- 构建产物输出到 `site/`，已被 `.gitignore` 忽略

## 部署方式（自动，无需手动构建）

- push 到 `main` 分支后，GitHub Actions（`.github/workflows/ci.yml`）自动执行 `mkdocs gh-deploy --force` 并发布到 GitHub Pages。
- 仓库：`762953670-ux/my-website`；公开网址：`https://762953670-ux.github.io/my-website/`
- 更新流程：改 `docs/` 下文件 → `git add .` → `git commit` → `git push`，约 1-2 分钟后自动上线。

## 环境注意事项（本机特有，容易踩坑）

- 访问 GitHub 必须走代理 `http://127.0.0.1:7897`，否则 git push / gh 会连接超时。
- git 已配置全局代理（`http.proxy`/`https.proxy`）；gh CLI 需额外设置 `HTTPS_PROXY`/`HTTP_PROXY` 环境变量。
- Python 3.12 在 `C:\Users\86152\AppData\Local\Programs\Python\Python312\`，mkdocs / mkdocs-material 已装。旧终端会话 PATH 可能未更新，需用完整路径或新开终端。

## 内容结构

- 所有页面在 `docs/` 下，每个板块一个子目录并含 `index.md`。
- 导航在 `mkdocs.yml` 的 `nav` 里配置；新增页面需在此注册，否则虽可访问但不会出现在导航菜单。
- 文章格式参照 `docs/course/example.md`。
