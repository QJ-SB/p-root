# ***ROOT — Current Snapshot***

**Snapshot Date:** 2026-09-18
**Stage:** Initial Deployment
**Status:** Minimal project foundation established

---

## `1. Current Position`

ROOT 已完成最小项目骨架设计，并建立第一版项目入口与 Foundation。

当前目标不是继续扩建 ROOT，而是完成最小初始化后立即进入真实使用。

---

## `2. Current Structure`

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
│
├── src/
│   ├── code/
│   └── skills/
│
├── tests/
│
└── data/
```

当前一级项目骨架已经确定。

各项目未来可以根据自身职责，在现有一级目录内部形成不同的子目录结构。

---

## `3. Current Core Files`

### `README.md`

ROOT 的项目入口。

当前负责说明：

* ROOT 为什么存在
* ROOT 的定位
* ROOT 不负责什么
* 最核心的工作原则

---

### `foundation/foundation.md`

ROOT 当前的核心长期规范。

已经定义：

* Output Before Optimization
* Minimal Vertical Slice
* Single Responsibility
* Attention Budget
* Resolution Discipline
* Evidence-Driven Expansion
* Canonical Truth
* Current Snapshot / Rolling Archive
* 项目结构原则
* Source / Tests / Data 原则
* ROOT 自身职责与成功标准

Foundation 不维护当前项目结构和运行状态。

---

## `4. Current Functional Areas`

### `src/skills/`

当前为空。

未来只存放 ROOT 真正需要长期使用的核心专职 skill。

---

### `src/code/`

当前为空。

未来只存放 ROOT 真正需要的脚本或代码。

---

### `tests/`

当前为空。

保留为项目重构、行为验证和 regression test 的验证空间。

不要求 ROOT 必须建立复杂测试体系。

---

### `data/`

当前为空。

保留给 ROOT 工作过程中真实产生或需要处理的数据。

---

## `5. Current Archive State`

`context/archive/` 已建立。

尚未建立正式 rolling archive。

计划创建：

```text
context/archive/history.md
```

作为唯一长期滚动追加历史。

---

## `6. Current Capability`

ROOT 当前已经具备：

* 一套明确的最小项目骨架
* 一套项目设计与防膨胀原则
* Current Snapshot 机制
* Rolling Archive 设计
* 用于后续新项目设计和既有项目减肥的基础规范

ROOT 当前没有：

* 自动化项目管理系统
* 跨项目 runtime
* router
* 自动 checkpoint 系统
* 中央状态管理
* 专门代码或 skill

这些能力当前也没有建设需求。

---

## `7. Next Step`

完成：

```text
context/archive/history.md
```

以及必要的 Git 基础配置后，ROOT v0 初始化即视为完成。

随后停止继续建设 ROOT 本身，进入第一次真实使用：

> **创建并设计 AI Output Compression Protocol 项目。**

该项目将作为 ROOT 项目范式的第一次实际验证。
