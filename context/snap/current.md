# ROOT — Current Snapshot

**Snapshot Date:** 2026-10-05  
**Stage:** Operational Use  
**Status:** Project routing, Attention Compression Protocol, Human Layer baseline, and downstream bootstrap / refactor validation operational

---

## 1. Current Position

ROOT 的最小项目骨架保持稳定，并已在真实 downstream project 的 bootstrap、运行后目标调整与 workflow 泛化中继续得到验证。

现有 AI 侧 baseline 保持不变：

```text
src/skills/attention-compression-protocol.md
```

该 skill 继续作为当前唯一启用的 project-local skill，用于降低 AI 输出造成的人类 attention 与 review burden。

Human Layer baseline 继续保持：

```text
foundation/human-layer-skills.md
```

该文件只供人类阅读和维护，不进入 GPT Project Files，不参与 AI routing，也不作为 AI 行为指令。

截至本轮真实使用，ROOT 已验证：

- 当前最小骨架能够支持复杂 downstream project 的设计、独立运行与后续局部 refactor；
- downstream project 在目标发生真实变化后，可以通过修改自身 authoritative sources 完成校准，而不需要 ROOT 参与其 runtime；
- 已经稳定工作的 workflow 可以优先保留，只解除真实暴露出的 hard-coded assumptions，而不必整体重建；
- 本轮没有出现需要修改 ROOT Foundation、router、Attention Compression Protocol、Human Layer 或测试体系的重复性问题。

因此当前结论仍然是：

> **ROOT baseline remains sufficient; no architecture expansion is triggered.**

---

## 2. Current Structure

```text
p-root/
├── .vscode/
│   └── settings.json
├── README.md
├── project-instruction.md
├── foundation/
│   ├── foundation.md
│   └── human-layer-skills.md
├── context/
│   ├── snap/
│   │   └── current.md
│   └── archive/
│       └── history.md
├── src/
│   ├── code/
│   └── skills/
│       └── attention-compression-protocol.md
├── tests/
│   └── compression-protocol-test/
│       └── compression-protocol-test-summary.md
├── data/
│   └── .gitkeep
├── .gitignore
└── .gitattributes
```

`src/code/` 当前仍为空。

ROOT 没有：

- 中央 runtime；
- 跨项目控制系统；
- 自动 checkpoint 系统；
- downstream project state registry。

本轮实际应用没有要求新增目录、skill、code route 或测试层。

---

## 3. Current File Responsibilities

### `README.md`

面向人类的项目入口。负责解释 ROOT 为什么存在、负责什么以及主要导航。

它不承担 AI 行为指令或能力路由职责，默认不装载进 GPT Project Files。

当前也负责把人类导航到 `foundation/human-layer-skills.md`。

### `project-instruction.md`

面向 AI 的项目入口与动态最小 router。

它负责：

- 简要说明 ROOT 的职责与边界；
- 指向长期原则和当前事实；
- 显式登记当前启用的 skill/code；
- 要求每轮输出加载 `attention-compression-protocol.md`。

当前没有 active code route。

`foundation/human-layer-skills.md` 不属于 Active Routes，也不由本文件路由。

### `foundation/foundation.md`

ROOT 的长期设计总纲。

它维护：

- 通用项目范式；
- 长期原则与边界；
- Human Layer 的长期定位；
- project-local routing 的稳定设计。

Foundation 不维护 downstream project 的具体状态、版本或业务设计。

### `foundation/human-layer-skills.md`

ROOT 当前的 Human Layer meta-skills 文件。

它只供人类阅读和维护，用于辅助人类自己的 delegation、attention、externalization 等 AI 协作判断。

该文件：

- 不进入 GPT Project Files；
- 不参与 AI routing；
- 不作为 AI 行为指令；
- 不要求 AI 默认读取或执行其中内容。

### `context/snap/current.md`

ROOT 当前唯一最新事实来源，采用覆盖更新。

### `context/archive/history.md`

ROOT 唯一长期 rolling archive，采用“压缩 → 加时间戳 → 追加”。

它不装载进 GPT Project Files；需要历史依据时，由人类提供相关文件或片段。

### `src/skills/attention-compression-protocol.md`

ROOT 当前唯一启用的 project-local skill。

它在输出形成前选择必要信息，减少不必要的信息成本，同时保护正确理解、判断、行动、核验、不确定性与安全所需的信息。

### `tests/compression-protocol-test/compression-protocol-test-summary.md`

Attention Compression Protocol 当前冻结的最后一次测试汇总，也是长期测试证据索引。

该文件不默认装载进 GPT Project Files。需要 review 测试过程或依据时，应主动请求人类提供它。

---

## 4. This Window: Purpose, Process, and Outcome

### Purpose

继续使用 ROOT 当前 baseline 处理一个已经运行中的 downstream project 与其相邻 workflow 的真实变化：

> **在不扩大 ROOT 自身结构的前提下，对 Evan-building 的职业目标约束和招聘数据工作流进行最小、证据驱动的 refactor。**

同时观察 ROOT 在面对目标演化、已有稳定 workflow、数据 schema 泛化与 downstream project ownership 时，是否会重新产生：

- architecture inflation；
- duplicate state；
- unnecessary protocol；
- cross-project dependency；
- excessive review burden。

### Process

本轮主要经过：

1. 基于 Evan-building 已有 capability state、真实招聘思考与后续 career-entry strategy，识别出旧 North Star 中“第一份工作必须直接进入上海 QD”的过硬约束。
2. 对 Evan-building 做最小 refactor：保留 Quant-directed / QD-primary 方向，同时允许高质量 quant-compatible engineering role 作为有效职业入口。
3. 将成熟 capability 从 isolated demo 逐步走向 leveraged integration / operated artifact 的长期方向写入 downstream Foundation，但没有新增 Product Lane、skill、protocol 或独立 roadmap。
4. 保持 Evan-building 已经正常工作的 Current、Active Slice、Capability Model、Algorithm Lane 与 skills 架构，仅同步真正受新决策影响的 authoritative sources。
5. 对既有 BOSS 招聘数据工作流做保守泛化：保留 raw → canonical → index 三级结构和已经验证的 collector 行为，只解除 QD-specific taxonomy / evidence hard-coding，并修正已有 contract drift。
6. 检查这些实践是否暴露 ROOT 自身需要修正的通用问题；结论为不需要。

### Final Outcome

本轮对 ROOT 的主要结果仍然不是新增能力，而是进一步验证现有原则：

> **真实 downstream project 可以在目标变化后自行完成局部校准；稳定 workflow 可以通过解除已暴露的硬编码实现泛化，而无需触发上层架构扩张。**

本轮没有修改 ROOT 的：

- `foundation/foundation.md`；
- `foundation/human-layer-skills.md`；
- `project-instruction.md`；
- `src/skills/attention-compression-protocol.md`；
- tests baseline。

也没有新增 ROOT skill、code route、目录或测试体系。

Evan-building 本轮形成的 career-entry strategy、capability-to-operated-artifact progression，以及招聘数据 schema taxonomy 仍视为 downstream-specific decisions，不自动升级为 ROOT 通用范式。

---

## 5. GPT Project Files Baseline

ROOT 当前的 AI 项目文件组合保持不变：

```text
foundation.md
current.md
project-instruction.md
attention-compression-protocol.md
```

默认不装载：

- `README.md`：人类入口；
- `human-layer-skills.md`：Human-only meta-skills；
- `history.md`：外部长期归档；
- `compression-protocol-test-summary.md`：仅在 review 测试依据时由人类提供。

---

## 6. Current Boundaries

已经成立并继续保持的边界：

- Human Layer 与 AI Layer 分离；
- Human Layer 具体 meta-skills 只由 `foundation/human-layer-skills.md` 维护；
- AI 只需要知道 Human Layer 的存在、职责与边界，不默认读取或执行其中内容；
- `project-instruction.md` 的 Active Routes 保持只面向 AI capability；
- Attention Compression Protocol 继续只负责 AI 输出前的信息选择与表达压缩；
- ROOT 不保存 downstream project 的当前状态；
- ROOT 不成为 downstream project 的中央控制器、共享状态源或 runtime dependency；
- downstream-specific patterns 不因单次成功案例自动升级为 ROOT universal rules。

截至本轮新增并继续成立的 evidence：

> **downstream project 可以吸收 ROOT 原则后独立运行，并在现实目标变化时通过自身 authoritative sources 完成局部 refactor；稳定 workflow 也可以通过解除已暴露的硬编码进行泛化，而无需 ROOT 参与其 runtime。**

仍需保持警惕：

- Human Layer 如果无证据扩张，可能重新制造人类 review burden；
- externalization 与 stepwise control 应按任务 consequence 动态使用，不能机械 ritualize；
- Attention Compression Protocol 仍存在已知语义覆盖风险；
- 不应因为 Evan-building 的 career-entry strategy、Learning / Session 设计、artifact progression 或招聘 schema 泛化在当前实践中有效，就提前将其泛化为 ROOT universal rules。

---

## 7. Next Stage

ROOT 继续处于：

> **Operational Use**

下一阶段不是继续扩建 ROOT。

默认行为是：

> **继续使用当前 baseline 支持真实项目设计、重构与分发，并观察是否反复出现相同的架构 friction。**

Evan-building 继续独立运行，由其自身负责 capability-building runtime 与后续局部演化。

ROOT 默认不跟踪其日常状态。

只有多个真实项目反复暴露出同类、明显影响：

- correctness；
- controllability；
- human attention；
- review burden；
- maintainability；

的问题时，才重新进入 ROOT 通用范式修正。

否则：

> **保持当前 baseline，继续使用。**
