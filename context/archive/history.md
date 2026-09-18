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

---

## 2026-09-18 — Project Routing and Attention Compression Operational Baseline

### Purpose

本轮开窗用于处理 ROOT 初始化后出现的第一个真实需求：AI 输出能力提高后，人类 attention 与 review bandwidth 成为主要成本。

目标是验证一个独立的 pre-output compression protocol，使 AI 在不改变必要语义的前提下，减少重复、非必要扩展和无助于推进任务的信息。

### Process

围绕 Small Compression Layer Protocol 依次完成三组对照测试：

1. Quant / RSI：比较 control、手动加载和 project-file 加载，确认文件存在或出现引用标识不能证明协议持续生效；由此加入 Activation，并形成最小 router。
2. English learning：发现 compression 会把“有用、可教学、更加完整”误判为“必要”；由此加入 v2 的必要性判据。
3. AI job data workflow：v2 四轮输出均短于 control，总量约减少 20%，范围控制和不确定性保留明显改善；同时观察到 `education_requirement` 字段遗漏等语义覆盖风险。

测试结论随后被冻结。由于单次遗漏尚不足以证明协议需要新增规则，没有继续扩写 protocol 或测试系统。

### Project Pattern Established

真实测试证明，仅把 skill 放入项目文件不足以构成可靠路由，因此 ROOT 正式建立：

- `README.md`：面向人类的项目入口，不承担 AI 指令；
- `project-instruction.md`：面向 AI 的项目入口与动态最小 router；
- `foundation.md`：长期原则与稳定范式；
- `current.md`：当前状态的唯一最新事实来源；
- `src/skills/` 与 `src/code/`：由 `project-instruction.md` 显式登记当前启用能力。

当前规模下，所需文件直接进入 GPT Project Files。只有真实膨胀造成加载或维护问题时，才考虑更复杂的路由机制。

`history.md` 继续在外部与 Git 中维护，不装载进 GPT Project Files；需要历史依据时由人类提供。

### Final Skill

测试中的 `skill.md` 被正式命名并纳入：

```text
src/skills/attention-compression-protocol.md
```

Attention Compression Protocol 在输出形成前选择必要信息，目标是降低信息成本，而不是机械追求短文本。它必须保护会影响正确理解、判断、行动、核验、不确定性或安全的信息。

虽然仍存在已知的语义覆盖风险，但它已经切实解决实际问题。依据 ROOT 的 Output Before Optimization 原则，人类决定将其从 candidate baseline 提升为 operational use；后续仅由重复的真实证据触发修正。

### Frozen Test Evidence

```text
tests/compression-protocol-test/compression-protocol-test-summary.md
```

这是 Attention Compression Protocol 当前冻结的最后一次测试汇总，也是本轮测试结论的长期证据索引。

该文件不在 GPT Project Files 的默认装载集合中。后续如果需要 review 此 skill 的测试过程、依据、边界或历史表现，AI 必须主动请求人类提供该文件，不得假定可以直接读取。

测试汇总保留冻结时的 `candidate baseline` 结论；本归档记录其后由人类作出的 operational adoption 决定，两者对应不同时间点。

### Final Artifacts

本轮最终形成并纳入 Git：

```text
README.md
foundation/foundation.md
project-instruction.md
src/skills/attention-compression-protocol.md
tests/compression-protocol-test/compression-protocol-test-summary.md
```

ROOT 当前 GPT Project Files baseline 为：

```text
foundation.md
current.md
project-instruction.md
attention-compression-protocol.md
```

### Implementation Baseline

```text
e77d4f95a5a97c9f0a08babafe665fe6e3a57a0c
feat: add project routing, attention compression protocol, and test baseline
```

该提交位于 `main` 与 `origin/main`，表示修改 Current 与 History 之前的完整实现状态。

承载本归档条目的 commit 不嵌入文件，以 Git history 为准。

### Next

停止继续扩建协议和测试系统。进入实际使用阶段，在 ROOT 与后续项目重构中复用该最小范式，并只根据反复出现的真实问题决定是否进行窄幅修正。
