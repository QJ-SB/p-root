# ROOT — Current Snapshot

**Snapshot Date:** 2026-09-18  
**Stage:** Operational Use  
**Status:** Project routing baseline and first project-local skill operational

---

## 1. Current Position

ROOT 的最小项目骨架保持稳定，并已完成第一轮由真实需求驱动的能力扩展。

本轮开窗的目的，是降低 AI 输出对人类 attention 与 review bandwidth 的占用，并验证一个独立的 pre-output compression protocol 是否能在保留必要语义的同时减少信息成本。

经过三组对照测试、两轮针对性修正和项目加载方式验证，ROOT 已正式采用：

```text
src/skills/attention-compression-protocol.md
```

该 skill 已进入 operational use。它当前有效，但仍保留已知的语义覆盖风险；后续只由重复的真实证据触发修正。

---

## 2. Current Structure

```text
p-root/
├── .vscode/
│   └── settings.json
├── README.md
├── project-instruction.md
├── foundation/
│   └── foundation.md
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

`src/code/` 当前仍为空。ROOT 没有中央 runtime、跨项目控制系统或自动 checkpoint 系统。

---

## 3. Current File Responsibilities

### `README.md`

面向人类的项目入口。负责解释 ROOT 为什么存在、负责什么以及主要导航。

它不承担 AI 行为指令或能力路由职责，默认不装载进 GPT Project Files。

### `project-instruction.md`

面向 AI 的项目入口与动态最小 router。

它负责：

- 简要说明 ROOT 的职责与边界；
- 指向长期原则和当前事实；
- 显式登记当前启用的 skill/code；
- 要求每轮输出加载 `attention-compression-protocol.md`。

当前没有 active code route。

### `foundation/foundation.md`

ROOT 的长期设计总纲。当前已包含人类/AI 双入口与 project-local routing 范式。

Foundation 不维护当前状态、版本或 active route。

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

减少 AI 输出造成的人类 attention 与 review burden，同时避免机械缩短带来的 semantic drift。

### Process

1. 建立 Quant / RSI control、manual compression 与 project-file compression 对照。
2. 发现文件存在或引用标识不能证明协议持续生效，因此加入 Activation 与最小 router。
3. 建立 English learning 对照，发现模型会把“有用、可教学”误判为“必要”，因此形成 v2 必要性判据。
4. 建立 AI job data workflow 对照，v2 四轮均缩短，总量约下降 20%，同时暴露字段覆盖遗漏风险。
5. 冻结测试结论，不继续因单次遗漏扩写协议。
6. 建立 README 人类入口、project-instruction AI 入口与动态 active route 范式。
7. 将协议正式命名并纳入 ROOT。

### Final Outcome

- `project-instruction.md`：正式 AI 入口与动态 router；
- `src/skills/attention-compression-protocol.md`：正式 operational skill；
- `tests/compression-protocol-test/compression-protocol-test-summary.md`：冻结测试汇总；
- README / Foundation：完成新项目范式对齐。

测试汇总冻结时将 v2 标记为 candidate baseline；此后人类依据“已经切实解决问题就优先投入使用”的原则，正式决定将其投入 operational use。两项记录分别描述不同时间点，不构成冲突。

---

## 5. GPT Project Files Baseline

ROOT 当前的 AI 项目文件组合为：

```text
foundation.md
current.md
project-instruction.md
attention-compression-protocol.md
```

默认不装载：

- `README.md`：人类入口；
- `history.md`：外部长期归档；
- `compression-protocol-test-summary.md`：仅在 review 测试依据时由人类提供。

---

## 6. Git State

当前主分支：

```text
main
```

本轮 implementation baseline 已提交并同步至 `origin/main`：

```text
e77d4f95a5a97c9f0a08babafe665fe6e3a57a0c
feat: add project routing, attention compression protocol, and test baseline
```

该 SHA 表示修改 Current 与 History 之前的完整实现状态。

承载本快照自身的 commit 不嵌入文件；需要时从 Git history 解析。

---

## 7. Current Boundaries

已经有证据支持：

- 显式 Activation 与动态 router 比单纯放置文件更可靠；
- v2 能明显抑制非必要展开；
- 结构化任务中已经观察到稳定的 attention reduction。

仍需保持警惕：

- 压缩可能遗漏影响后续决策的信息；
- 当前测试量不足以证明所有领域都能稳定缩短；
- 引用标识不是协议是否生效的可靠遥测。

这些边界已经足以指导实际使用，但不足以支持继续扩建协议或测试系统。

---

## 8. Next Stage

ROOT 进入实际使用阶段：

> **使用当前 baseline，并在后续项目重构中复用人类入口、AI router 与 project-local capability 的最小范式。**

默认不继续修改 Attention Compression Protocol。

只有真实使用中反复出现、明显影响正确性或人工成本的问题，才重新触发测试与窄幅修正。
