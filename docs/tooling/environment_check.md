# Environment Check

日期：2026-06-04  
阶段：Phase 1 / Day 1 扩展任务  
主题：本地开发工具链盘点与验证

## 1. 检查目标

本次检查用于确认当前电脑是否具备后续 C++ / Python 工程化学习的基础工具链。

今天不要求一次性安装所有工具，只要求准确记录：

- 哪些工具已经可用
- 哪些工具缺失
- 哪些工具版本需要后续统一
- 哪些命令需要进一步确认

## 2. 工具检查结果

| 工具 | 作用 | 当前状态 | 版本 / 输出摘要 | 后续处理 |
|---|---|---|---|---|
| Git | 版本控制 | 已可用 | 2.47.0.windows.2 | 必须可用 |
| GitHub CLI | GitHub 命令行操作 | 已可用 | gh version 2.90.0 | 可选 |
| Python | Python 开发 | 已可用 | Python 3.13.0 | 必须可用 |
| pip | Python 包管理 | 已可用 | pip 26.1.1 | 必须可用 |
| g++ | C++ 编译器 | 未找到 | g++ not found | Windows 下可先使用 MSVC |
| clang++ | C++ 编译器 | 未找到 | clang++ not found | Windows 下可先使用 MSVC |
| MSVC cl | Windows C++ 编译器 | 已可用 | 19.43.34810 版 | Windows 下推荐后续作为主 C++ 编译器 |
| CMake | C++ 构建系统 | 已可用 | cmake version 4.3.2 | Phase 1 必须可用 |
| Ninja | 构建加速工具 | 未找到 | ninja not found | 可选但推荐，Day 2 可考虑补齐 |
| VS Code CLI | 编辑器命令行 | 已可用 | 1.122.1 | 可选 |

## 3. 原始命令输出

本次已记录关键版本摘要，但没有完整保留原始命令输出。  
Day 2 正式任务中需要重新执行工具链检查命令，并补充更完整的原始输出记录。

## 4. 当前判断

### 已可用工具

- Git 已可用，可以继续作为版本控制工具。
- GitHub CLI 已可用，后续可以学习用 `gh` 管理仓库和 Issue。
- Python 与 pip 已可用，可以支撑后续 Python 工程化学习。
- MSVC `cl` 已可用，可以作为 Windows 下的 C++ 编译器。
- CMake 已可用，可以支撑后续 C++ 工程构建学习。
- VS Code CLI 已可用，可以从命令行打开项目。

### 缺失或未配置工具

- g++ 当前未找到。
- clang++ 当前未找到。
- Ninja 当前未找到。

### 需要后续确认的问题

- Day 2 需要确认后续 C++ 学习主线使用 MSVC、MinGW、clang++ 还是 WSL。
- Day 2 需要确认 CMake 能否正常调用 MSVC 编译一个最小 C++ 程序。
- Ninja 不是当前阻塞项，但后续建议补齐。

## 5. 明日跟进

- Day 2 正式任务优先验证 CMake + MSVC 是否能构建最小 C++ 项目。
- 暂时不急着安装 g++ / clang++，避免同时维护多套 Windows C++ 工具链。
- Python 侧后续需要确认虚拟环境 `.venv` 创建和 pip 安装流程。
