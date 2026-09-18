# ROOT — Current Snapshot

**Snapshot Date:** 2026-09-18
**Stage:** Operational Baseline
**Status:** ROOT v0 initialization complete

---

## 1. Current Position

ROOT 已完成第一轮最小初始化，并建立可正式投入使用的项目 baseline。

当前阶段不再继续扩建基础架构。

下一阶段将围绕 ROOT 自身真实使用需求，讨论是否需要建立少量 project-local skill，以降低项目管理、归档和运行成本。

---

## 2. Current Structure

```text
p-root/
├── .vscode/
│   └── settings.json
│
├── README.md
│
├── foundation/
│   └── foundation.md
│
├── context/
│   ├── snap/
│   │   └── current.md
│   └── archive/
│       └── history.md
│
├── src/
│   ├── code/
│   └── skills/
│
├── tests/
│
├── data/
│   └── .gitkeep
│
├── .gitignore
└── .gitattributes
```

当前一级项目骨架已经建立。

各项目未来可以根据自身职责，在现有一级目录内部形成不同子结构。

---

## 3. Current Core Files

### `README.md`

ROOT 的项目入口。

当前负责说明：

* ROOT 为什么存在
* ROOT 的定位
* ROOT 不负责什么
* 最核心的工作原则

### `foundation/foundation.md`

ROOT 当前的长期设计总纲。

已经定义：

* Output Before Optimization
* Minimal Vertical Slice
* Single Responsibility
* Attention Budget
* Resolution Discipline
* Evidence-Driven Expansion
* Canonical Truth
* Current Snapshot / Rolling Archive
* Project Structure Principle
* Source / Tests / Data 原则
* ROOT 自身职责与成功标准

Foundation 不维护当前项目结构、当前实现状态或版本信息。

### `context/snap/current.md`

ROOT 当前唯一最新事实来源。

采用覆盖更新。

### `context/archive/history.md`

ROOT 当前唯一长期 rolling archive。

采用：

> 压缩 → 时间戳 → 追加

不承担当前状态说明职责。

---

## 4. Current Functional Areas

### `src/skills/`

当前为空。

未来仅在真实使用证明有必要时，存放 ROOT 自身需要长期使用的专职 skill。

### `src/code/`

当前为空。

未来仅在真实需求出现时，存放 ROOT 所需脚本或代码。

### `tests/`

当前为空。

保留为重构、行为验证和 regression test 的验证空间。

不要求建立复杂测试体系。

### `data/`

当前无正式项目数据。

目录通过 `.gitkeep` 保留，实际数据默认由 `.gitignore` 排除。

---

## 5. Git State

Git baseline 已建立并推送至远程仓库。

当前主分支：

```text
main
```

当前初始化 baseline commit：

```text
5293f776627a15c6863a84eacf7c248ff5bdbe0d
feat: initialize p-root project
```

当前 baseline 已同步至：

```text
origin/main
```

---

## 6. Current Git Configuration

### `.gitignore`

当前忽略：

* `.vscode/`
* Python virtual environment
* Python / pytest / mypy / ruff cache
* 临时文件与日志
* 操作系统生成文件
* `data/` 中的实际项目数据

正式项目定义、source、context、foundation 和长期有效测试不默认忽略。

### `.gitattributes`

当前统一文本行尾：

```text
* text=auto eol=lf
```

---

## 7. Current Capability

ROOT 当前已经具备：

* 稳定的最小项目骨架
* 项目设计与防膨胀原则
* Canonical Current Snapshot
* Rolling Archive
* Git baseline
* 用于后续新项目设计和既有项目减肥的基础规范

ROOT 当前没有：

* 中央项目控制系统
* 跨项目 runtime
* 自动 checkpoint 系统
* router
* 中央状态管理
* 专门代码
* 专门 skill

这些能力均不预设为必需。

---

## 8. Next Stage

本轮基础初始化完成后，ROOT 进入真实使用阶段。

下一阶段：

> **讨论并定义 ROOT 自身是否需要少量专用 skill。**

具体 skill 的职责、数量和设计暂未决定。

默认原则仍然是：

> **先出现真实需求，再增加能力。**

在下一阶段开始前，本轮 artifact 将完成最终归档并冻结为 ROOT 的第一版 operational baseline。
