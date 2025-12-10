# setup-uv

GitHub Action：安装并配置 uv Python 包管理器。

## 使用方法

```yaml
steps:
  - uses: actions/checkout@v4

  - uses: 1token-tech/setup-uv@v0.1
    with:
      python-version: '3.13.9'  # 可选，默认 3.13.9
```

## 功能

- 自动安装 uv（如未安装）
- 安装指定版本的 Python
- 自动运行 `uv sync` 同步依赖

## 输入参数

| 参数 | 说明 | 默认值 |
|------|------|--------|
| `python-version` | Python 版本 | `3.13.9` |

## 要求

项目根目录需要有 `pyproject.toml` 文件（用于 `uv sync`）。
