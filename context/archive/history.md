# ROOT — Rolling Archive

> 本文件是 ROOT 的唯一长期滚动历史归档。
> 每次归档只进行：**压缩、加时间戳、追加。**
>
> 当前项目状态始终以：
>
> `context/snap/current.md`
>
> 为唯一最新事实来源。

---

## 2026-09-18 — ROOT Initial Deployment

### Background

随着 AI 协作项目数量和复杂度增加，项目逐渐出现：

* 架构持续膨胀
* 文档与状态重复
* checkpoint 过多
* 过度优化与过度定制
* 人类 review 与 attention 成本快速上升

因此建立 ROOT，用于设计、维护和验证一套更轻量的 AI 协作项目范式。

### Established

完成 ROOT 最小初始化设计：

* 建立通用一级项目骨架
* 建立 `README.md`
* 建立 `foundation/foundation.md`
* 建立 `context/snap/current.md`
* 确立 Current Snapshot + Rolling Archive 模式
* 确立 Single Responsibility
* 确立 Minimal Vertical Slice
* 确立 Attention Budget
* 确立 Resolution Discipline
* 确立 Evidence-Driven Expansion
* 确立 Output Before Optimization
* 确立 Canonical Truth 原则

### Key Decision

ROOT 不作为其他项目的中央控制器或运行时系统。

不同项目保持独立，由人类负责跨项目的信息选择、传递和组合。

项目默认采用：

> **能删就不加。**
> **能合并就不拆。**
> **能让 AI 判断就不写规则。**
> **能开始产出就停止造系统。**

### Next

完成必要 Git 基础配置后，停止继续扩建 ROOT。

ROOT 的第一次真实使用将是：

> **创建 AI Output Compression Protocol 项目。**

---

## 2026-09-18 — ROOT Operational Baseline Frozen

### Completed

ROOT 第一轮最小初始化正式完成。

已完成：

* `README.md`
* `foundation/foundation.md`
* `context/snap/current.md`
* `context/archive/history.md`
* `.gitignore`
* `.gitattributes`
* `data/.gitkeep`

Git 已完成初始化、首次提交并同步远程。

Baseline commit：

```text
5293f776627a15c6863a84eacf7c248ff5bdbe0d
feat: initialize p-root project
```

当前主分支：

```text
main
```

当前远程状态：

```text
origin/main
```

### Current Decision

ROOT v0 基础架构到此停止扩建。

后续不因“可能有用”继续增加：

* 目录
* protocol
* state
* checkpoint
* router
* automation
* 测试体系

只有真实使用暴露出明确需求时，才进入下一轮建设。

### Next Stage

下一阶段将讨论 ROOT 自身是否需要少量 project-local skill，以降低真实使用中的管理、归档和运行成本。

具体 skill：

* 暂未定义
* 暂不预设数量
* 暂不提前实现

默认仍遵循：

> **先出现真实需求，再增加能力。**
