# SQL 与数据库学习

从零学习 SQL 和数据库工程的练习仓库。前期使用 SQLite，后期迁移到 MySQL。主项目是一个带抢课功能的校园选课系统，查询专项练习用 Chinook 示例数据库。

## 目录结构

```
.
├── data/        # 数据库文件（不纳入版本管理，按下文方法获取）
├── exercise/    # 练习，按阶段分子目录
└── notes/       # 学习笔记
```

## 环境准备

需要以下工具：

- Python 3.12
- sqlite3 命令行工具：`winget install SQLite.SQLite`
- DBeaver 社区版（图形客户端，可选）：`winget install DBeaver.DBeaver.Community`

创建并激活虚拟环境：

```bash
python -m venv .venv
source .venv/Scripts/activate      # Git Bash
# .venv\Scripts\Activate.ps1       # PowerShell
```

## 获取 Chinook 示例数据库

数据库文件是二进制文件，并且可以随时重新下载，所以不提交到仓库。需要时用下面的命令下载到 `data/` 目录：

```bash
# Git Bash
curl -L -o data/chinook.db https://github.com/lerocha/chinook-database/releases/download/v1.4.5/Chinook_Sqlite.sqlite

# PowerShell（要写 curl.exe，不能只写 curl）
curl.exe -L -o data/chinook.db https://github.com/lerocha/chinook-database/releases/download/v1.4.5/Chinook_Sqlite.sqlite
```

练习中修改坏了数据，重新执行这条命令就能恢复到初始状态。

验证是否下载成功：

```bash
sqlite3 data/chinook.db "SELECT count(*) FROM Track;"
# 应输出 3503
```
