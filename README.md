# defult-project

一个 Python 项目模板，使用 Poetry 进行依赖管理。

> 模板仓库：https://github.com/moyichuxin/defult-project

## 项目结构

```
defult-project/
├── docs/              # 文档目录
├── scripts/           # 脚本目录
├── src/
│   └── my_project/    # 主要代码
│       ├── api/       # API 相关
│       ├── core/      # 核心功能
│       ├── models/    # 数据模型
│       ├── utils/     # 工具函数
│       └── main.py    # 入口文件
├── tests/             # 测试代码
├── pyproject.toml     # 项目配置
└── poetry.lock        # 依赖锁定文件
```

## 快速开始

### 1. 创建环境

```bash
# 创建 Python 环境（推荐 3.11 或 3.12）
conda create --name my-project python=3.11
conda activate my-project

# 在激活的 my-project 环境中，使用 pip 安装 poetry
pip install poetry
poetry --version
# 配置 Poetry 使用当前的 Conda 环境，而不是让它自己创建新的虚拟环境。
poetry config virtualenvs.create false --local
```

### 2. 项目初始化

```bash
# 初始化项目配置
poetry init

# 添加依赖包
poetry add numpy pandas
```

## 重要提醒

**依赖管理原则：**
- ✅ 所有 Python 包使用 `poetry add` 安装
- ❌ 避免使用 `pip install`
- ⚠️ 仅在以下情况使用 `conda install`：
  - 安装非 Python 二进制依赖（如 cudatoolkit, ffmpeg）
  - 管理 Python 解释器版本

**错误修复：**
- 误用 `pip install`：直接运行 `poetry add <package>` 覆盖
- 误用 `conda install`：先 `conda uninstall <package>`，再 `poetry add <package>`

## 项目复现

如果要克隆并使用这个项目：

```bash
# 克隆项目
git clone <你的仓库地址>
cd <项目目录>

# 创建相同的 Python 环境
conda create --name <环境名> python=3.11
conda activate <环境名>

# 安装 Poetry 并恢复依赖
pip install poetry
poetry install
```

