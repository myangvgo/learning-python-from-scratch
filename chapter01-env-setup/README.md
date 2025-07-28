# Chapter 1: Python Environment Setup [Python 开发环境搭建]

## 1.1 安装 UV [Install UV]

UV 是一个用 Rust 编写的 Python 包和项目管理器，提供了一体化的工具链，用于管理 Python 项目的依赖、构建和发布。

> 安装 UV：https://docs.astral.sh/uv/getting-started/installation/

我使用的是 Windows 11，可以直接使用 `winget` 快速安装

```bash
winget install --id=astral-sh.uv  -e
```
后续如果要升级 UV，可以使用 `winget` 进行升级

```bash
winget upgrade uv
```
安装完成之后验证 UV 是否安装成功

```bash
uv --version
# uv 0.8.3 (7e78f54e7 2025-07-24)
```

## 1.2 安装 Python [Install Python]

> 安装 Python：https://docs.astral.sh/uv/guides/install-python/

使用 uv 安装 Python，如果没有指定 python 版本，将会安装最新版的 Python

```bash
uv python install
```

安装指定版本的 Python

```bash
uv python install 3.10

uv python install 3.11 3.12 # 同时安装多个版本的 Python
```

安装完成之后可以使用 `uv python list` 查看已安装的 Python 版本

```bash
# 查看所有已安装的 Python 版本
uv python list --only-installed
# cpython-3.10.18-windows-x86_64-none    C:\Users\myang\AppData\Roaming\uv\python\cpython-3.10.18-windows-x86_64-none\python.exe
# cpython-3.9.7-windows-x86_64-none      C:\Users\myang\AppData\Roaming\uv\python\cpython-3.9.7-windows-x86_64-none\python.exe
```

## 1.3 创建项目 [Create Project]

> 创建项目：https://docs.astral.sh/uv/guides/projects/

使用 `uv init` 可以初始化新项目，项目目录里面包含了默认的配置文件，例如 `pyproject.toml`、`uv.toml`、`uv.lock` 等。

```bash
uv init pyproject
```

本学习项目将每一章作为一个独立的 Python 子项目，每个子项目使用 uv 来管理依赖和虚拟环境。

```bash
# 由于整个项目使用同一的 Git 管理，所以子项目通过 --vcs none 不再另外使用 Git 管理
uv init chapter01-env-setup --vcs none --description "Chapter 01 - Python Environment Setup"

cd chapter01-env-setup
```

整个 `chapter01-env-setup` 项目文件结构如下：

```bash
├── .python-version
├── README.md
├── main.py
└── pyproject.toml
```

通过 `uv run` 运行项目

```bash
uv run main.py
```

第一次运行的时候，会自动创建虚拟环境，并且安装项目依赖。

```bash
$ uv run main.py 
Using CPython 3.10.18
Creating virtual environment at: .venv
Hello from chapter01-env-setup! 
```

## 1.4 使用 Jupyter Notebook [Use Jupyter Notebook]

> UV 中使用 Jupyter Notebook：https://docs.astral.sh/uv/guides/integration/jupyter/#using-jupyter-as-a-standalone-tool

```bash
mkdir notebooks
cd notebooks

uv venv --seed
uv pip install pydantic
uv pip install jupyterlab

# 在 Git Bash 中启动 Jupyter Notebook
./venv/Scripts/jupyter lab
```

通过 `uv pip install` 安装新的依赖，例如 pandas、numpy、matplotlib 等。

```bash
uv pip install pandas numpy matplotlib
```

## 1.5 使用 AI IDE 进行 Python 开发

>  https://code.visualstudio.com/docs/languages/python

使用 VS Code 或其他的 VS Code Fork，例如 Cursor, Trae, CodeBuddy, Lingma 进行 Python 开发。

- 安装 Microsoft Python Extension
- 安装 Jupyter Extension