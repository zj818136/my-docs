# my-docs

基于 MkDocs + Material 主题搭建的个人技术文档站，通过 GitHub Actions 自动构建并部署到 GitHub Pages。

- 网站地址：https://zj818136.github.io/my-docs/
- 个人实验报告：[report/README.md](report/README.md)
- 源码仓库：https://github.com/zj818136/my-docs

## 目录说明

| 路径 | 说明 |
| --- | --- |
| `docs/` | 文档源文件，共四个页面：首页、关于、使用指南、API 参考 |
| `site/` | 构建产物，由 MkDocs 自动生成，已写入 `.gitignore` |
| `report/` | 个人实验报告与关键步骤截图 |
| `.github/workflows/deploy.yml` | 自动构建与部署的工作流 |
| `mkdocs.yml` | 站点名称、主题与导航配置 |

## 本地预览

```bash
python -m venv .venv
python -m pip install -r requirements.txt
python -m mkdocs serve
```

然后浏览器打开 http://127.0.0.1:8000/ 。

## 部署方式

推送包含 `docs/**`、`mkdocs.yml`、`requirements.txt` 或工作流文件的提交到 `main` 分支后，工作流自动执行：安装依赖 → `mkdocs build --strict` → 上传 `site/` 产物 → 由官方 Pages 部署动作发布。Pages 发布来源设置为 GitHub Actions，不依赖 `gh-pages` 分支。
