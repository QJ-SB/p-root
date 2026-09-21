# ROOT — Current Snapshot

**Snapshot Date:** 2026-09-21  
**Stage:** Operational Use  
**Status:** Project routing, Attention Compression Protocol, Human Layer baseline, and downstream bootstrap validation operational

---

## 1. Current Position

ROOT 的最小项目骨架保持稳定，并已完成一次真实 downstream project bootstrap / distribution validation。

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

本轮真实使用中，ROOT 被用于设计并 bootstrap 独立的 Evan-building 项目。该实践验证了：

- ROOT 当前最小骨架能够承载复杂 downstream project 的设计与分发；
- downstream project 可以吸收 ROOT 原则后独立运行；
- ROOT 不需要成为跨项目中央控制器、共享状态源或 runtime dependency；
- 本轮没有出现需要修改 ROOT Foundation、router、Attention Compression Protocol、Human Layer 或测试体系的重复性问题。

因此当前结论是：

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

它在 Git 中维护，但不装载进 GPT Project Files；需要历史依据时，由人类提供相关文件或片段。

### `src/skills/attention-compression-protocol.md`

ROOT 当前唯一启用的 project-local skill。

它在输出形成前选择必要信息，减少不必要的信息成本，同时保护正确理解、判断、行动、核验、不确定性与安全所需的信息。

### `tests/compression-protocol-test/compression-protocol-test-summary.md`

Attention Compression Protocol 当前冻结的最后一次测试汇总，也是长期测试证据索引。

该文件不默认装载进 GPT Project Files。需要 review 测试过程或依据时，应主动请求人类提供它。

---

## 4. This Window: Purpose, Process, and Outcome

### Purpose

将 ROOT 当前已经建立的最小项目范式用于一个真实 downstream project：

> **设计并 bootstrap 独立的 Evan-building capability-building project。**

同时观察 ROOT 在面对长期能力状态、学习运行方式、Session 管理、外部 artifact 与复杂业务 evidence 时，是否会重新产生：

- architecture inflation；
- duplicate state；
- unnecessary protocol；
- cross-project dependency；
- excessive review burden。

### Process

本轮主要经过：

1. 从真实上海 QD Market Truth、Hiring Interface 和 Evan Capability evidence 出发，确认 downstream project 的目标与边界。
2. 依据 ROOT 的 Single Responsibility 和 Minimal Vertical Slice 原则，将能力建设统一收敛为一个 Evan-building project，而不是拆成多个自治学习项目。
3. 讨论并冻结 Active Slice、Session、Capability State、Primary Growth Lane 与 Algorithm Maintenance Lane 的职责边界。
4. 将 AI leverage 与 human internalization 分离，形成 downstream-specific Learning Skill。
5. 将 context-health / rollover / archive concern 分离，形成 downstream-specific Session Stewardship Skill。
6. 将 ROOT 的 Attention Compression 思想迁移为 Evan-building 的本地 project skill，避免 runtime dependency。
7. 保持 Current + Rolling History pattern，并将训练 artifacts 继续留在独立 sibling repositories。
8. 对 Evan-building Foundation、Current、router 和 skills 做 duplication / attention-cost cleanup。
9. Evan-building v1 baseline 由人类独立部署、commit 并同步至远程。
10. 检查 ROOT 本身是否需要扩张；结论为不需要。

### Final Outcome

Evan-building v1 已在独立 repository 中完成 baseline deployment：

```text
eab2df4d8d2458c7f5a0ec0129ecef118bb84690
feat: bootstrap Evan-building capability system
```

本轮对 ROOT 的主要结果不是新增能力，而是一次真实验证：

> **ROOT 当前项目范式足以支持一个复杂 downstream project 从设计到独立分发，同时保持 ROOT 与 downstream runtime 解耦。**

本轮没有修改：

- `foundation/foundation.md`
- `foundation/human-layer-skills.md`
- `project-instruction.md`
- `src/skills/attention-compression-protocol.md`
- tests baseline

也没有新增 ROOT skill、code route、目录或测试体系。

Evan-building 中的 Learning Skill、Session Stewardship、Primary Growth Lane、Algorithm Maintenance Lane 等设计当前仍视为 downstream-specific decisions，不自动升级为 ROOT 通用范式。

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

## 6. Git State

当前主分支：

```text
main
```

当前 ROOT `origin/main` HEAD（本轮归档前）：

```text
173098b8d8dd8cafacaf13317654b268d8bc8553
docs: update human layer project context
```

当前 ROOT implementation baselines 保持：

```text
e77d4f95a5a97c9f0a08babafe665fe6e3a57a0c
feat: add project routing, attention compression protocol, and test baseline
```

```text
0b196dc728408f28944fb78e25daa7ba38efc61c
feat: add human layer collaboration skills
```

本轮没有 ROOT implementation change。

本轮新增的只是：

- `context/archive/history.md` rolling append；
- `context/snap/current.md` context refresh。

承载本次归档自身的 context-only commit 不嵌入本文件；需要时从 Git history 解析。

External downstream distribution evidence：

```text
Evan-building
eab2df4d8d2458c7f5a0ec0129ecef118bb84690
feat: bootstrap Evan-building capability system
```

该 SHA 仅作为本次 distribution validation 的外部证据锚点，不构成 ROOT runtime dependency。

---

## 7. Current Boundaries

已经成立并继续保持的边界：

- Human Layer 与 AI Layer 分离；
- Human Layer 具体 meta-skills 只由 `foundation/human-layer-skills.md` 维护；
- AI 只需要知道 Human Layer 的存在、职责与边界，不默认读取或执行其中内容；
- `project-instruction.md` 的 Active Routes 保持只面向 AI capability；
- Attention Compression Protocol 继续只负责 AI 输出前的信息选择与表达压缩；
- ROOT 不保存 downstream project 的当前状态；
- ROOT 不成为 downstream project 的中央控制器、共享状态源或 runtime dependency；
- downstream-specific patterns 不因单次成功案例自动升级为 ROOT universal rules。

本轮新增的当前 evidence：

> **downstream project 可以吸收 ROOT 原则与骨架后独立运行，ROOT 无需参与其日常 runtime。**

仍需保持警惕：

- Human Layer 如果无证据扩张，可能重新制造人类 review burden；
- externalization 与 stepwise control 应按任务 consequence 动态使用，不能机械 ritualize；
- Attention Compression Protocol 仍存在已知语义覆盖风险；
- 不应因为 Evan-building 一次成功实践，就把其特有 Learning / Session 设计提前泛化到所有项目。

---

## 8. Next Stage

ROOT 继续处于：

> **Operational Use**

下一阶段不是继续扩建 ROOT。

默认行为是：

> **继续使用当前 baseline 支持真实项目设计、重构与分发，并观察是否反复出现相同的架构 friction。**

Evan-building 从此进入独立运行阶段，由其自身负责后续 capability-building runtime。

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
