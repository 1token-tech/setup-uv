# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

GitHub Action for installing and configuring uv Python package manager with a specified Python version. This is a composite action defined in `action.yml`.

## Release Commands

```bash
npm run release:patch   # 发布 patch 版本（无需确认）
npm run release:minor   # 发布 minor 版本（需输入 'y' 5 次确认）
npm run release:major   # 发布 major 版本（需输入 'y' 10 次确认）
```

Release 命令会自动：bump 版本号 → 创建 commit → push 代码 → push tag → 更新 v0.X 短标签

## Action Inputs

- `python-version`: Python 版本，默认 `3.13.9`

## Action 执行流程

1. 添加 `$HOME/.local/bin` 到 PATH
2. 安装 uv（如未安装）
3. 使用 uv 安装指定版本的 Python
4. 运行 `uv sync` 同步依赖
