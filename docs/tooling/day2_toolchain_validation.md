# Day 2 Toolchain Validation

日期：2026-06-05  
阶段：Phase 1 / Day 2  
主题：验证 Python 虚拟环境与 CMake + MSVC 最小构建流程

## 1. 验证目标

本次验证用于确认当前 Windows 开发环境能否支撑后续 C++ / Python 工程化学习。

## 2. Python 虚拟环境验证

### 执行命令

```powershell
python --version
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python --version
python -m pip --version
deactivate
```

### 实际结果

`.venv` 创建成功，虚拟环境可以激活。  
激活后可以正常执行 `python --version` 和 `python -m pip --version`。

当前记录：

- Python：Python 3.13.0
- pip：pip 26.1.1

## 3. CMake + MSVC 验证

### 执行命令

```powershell
cmake -S projects/cpp/toolchain_smoke -B projects/cpp/toolchain_smoke/build
cmake --build projects/cpp/toolchain_smoke/build --config Debug
.\projects\cpp\toolchain_smoke\build\Debug\toolchain_smoke.exe
```

### 期望输出

```text
C++ toolchain smoke test passed.
```

### 实际结果

CMake configure 成功。  
CMake build 成功。  
`toolchain_smoke.exe` 可以运行，并输出：

```text
C++ toolchain smoke test passed.
```

## 4. 当前结论

当前 Windows 环境中，Python 虚拟环境可用，pip 可用，CMake 能调用 MSVC 构建最小 C++ 程序。

因此，Phase 1 后续 C++ 学习可以先以 MSVC + CMake 作为主工具链，不急于同时安装 g++ 或 clang++。

## 5. 后续处理

- 后续 C++ 学习先使用 MSVC + CMake。
- Ninja 当前缺失，但不阻塞 Day 2。
- 后续 Python 项目统一使用 `.venv`。
- 后续提交前需要确认 `build/` 和 `.venv/` 没有被 Git 跟踪。
