# 使用指南

## 日常更新流程

1. 修改 `docs/` 目录中的 Markdown 文件。
2. 本地预览并逐个检查页面、表格、代码块与页面间链接。
3. 提交修改并推送到 `main` 分支。
4. 在仓库 Actions 页面查看 build 与 deploy 两个任务的状态。
5. 打开公开网站，必要时用无痕窗口刷新，确认内容已更新。

## 常用命令

```bash
# 安装依赖
python -m pip install -r requirements.txt

# 本地预览，默认地址 http://127.0.0.1:8000/
python -m mkdocs serve

# 严格模式构建，出现警告即视为失败
python -m mkdocs build --strict
```

## 注意事项

- 只改 `report/` 或根目录 `README.md` 不会触发部署，因为工作流只在 `docs/**`、`mkdocs.yml`、`requirements.txt` 变更时运行。
- `site/` 是构建产物，已写入 `.gitignore`，不需要也不应该手工提交。
- YAML 只能用空格缩进；`nav` 中的路径相对于 `docs/`，不要写成 `docs/index.md`。

[返回首页](index.md)
