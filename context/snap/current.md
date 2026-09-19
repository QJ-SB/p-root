# ROOT — Current Snapshot

**Snapshot Date:** 2026-09-19  
**Stage:** Operational Use  
**Status:** Project routing, Attention Compression Protocol, and Human Layer baseline operational

---

## 1. Current Position

ROOT 的最小项目骨架保持稳定，并已完成第二轮由真实需求驱动的能力扩展。

现有 AI 侧 baseline 保持不变：

```text
src/skills/attention-compression-protocol.md
```

该 skill 继续作为当前唯一启用的 project-local skill，用于降低 AI 输出造成的人类 attention 与 review burden。

本轮新增 Human Layer，用于承载人类自身的跨项目 AI 协作 meta-skills：

```text
foundation/human-layer-skills.md
```

该文件只供人类阅读和维护，不进入 GPT Project Files，不参与 AI routing，也不作为 AI 行为指令。ROOT 只记录这一层的存在、职责与边界。

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

`src/code/` 当前仍为空。ROOT 没有中央 runtime、跨项目控制系统或自动 checkpoint 系统。

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

ROOT 的长期设计总纲。当前已包含：

- 人类/AI 双入口与 project-local routing 范式；
- Human Layer 的长期定位与边界；
- Human Layer 具体内容的 canonical source 指向。

Foundation 不维护 Human Layer meta-skill 正文，也不维护当前状态、版本或 active route。

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

将已经在真实 AI 协作中反复出现的人类侧经验凝结为一个轻量 Human Layer，同时避免继续把人类判断习惯错误地下沉为 AI skill 或固定 workflow。

### Process

1. 从“保持人类对关键决策的实际所有权”出发，讨论 delegation、attention、communication granularity 与 consequence 的关系。
2. 冻结第一条 meta-skill：`Maintain human decision ownership by calibrating delegation and attention.`
3. 从 externalization、observability 与 drift control 的真实协作经验出发，区分通用认知原则与高控制 execution pattern。
4. 冻结第二条 meta-skill：`Externalize critical state to keep AI execution observable and controllable.`
5. 创建 `foundation/human-layer-skills.md`，仅保存已冻结的 Human Layer meta-skills。
6. 最小更新 Foundation 与 README；检查 `project-instruction.md` 和 Attention Compression Protocol 后均保持不变。
7. 完成 implementation freeze review，并将本轮结果 rolling append 到 History。

### Final Outcome

本轮新增并冻结：

```text
foundation/human-layer-skills.md
```

同时最小更新：

```text
foundation/foundation.md
README.md
```

明确边界：

- Human Layer 属于人类侧；
- `human-layer-skills.md` 不进入 GPT Project Files；
- 不参与 AI routing；
- 不加入 Active Routes；
- 不修改 Attention Compression Protocol；
- 不新增测试体系。

本轮 implementation baseline 已完成内容冻结。

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

上一轮 implementation baseline：

```text
e77d4f95a5a97c9f0a08babafe665fe6e3a57a0c
feat: add project routing, attention compression protocol, and test baseline
```

本轮 Human Layer implementation baseline 已提交并同步至 `origin/main`：

```text
0b196dc728408f28944fb78e25daa7ba38efc61c
feat: add human layer collaboration skills
```

该 SHA 表示本轮 Human Layer implementation 的完整实现状态：

```text
foundation/human-layer-skills.md
foundation/foundation.md
README.md
```

`context/archive/history.md` 与 `context/snap/current.md` 不属于该 implementation commit，将作为后续 context-only commit 提交。

承载本快照自身的 commit 不嵌入文件；需要时从 Git history 解析。

---

## 7. Current Boundaries

已经成立的当前边界：

- Human Layer 与 AI Layer 分离；
- Human Layer 具体 meta-skills 只由 `foundation/human-layer-skills.md` 维护；
- AI 只需要知道 Human Layer 的存在、职责与边界，不默认读取或执行其中内容；
- `project-instruction.md` 的 Active Routes 保持只面向 AI capability；
- Attention Compression Protocol 继续只负责 AI 输出前的信息选择与表达压缩；
- Human Layer 不自动升级为固定 prompt template、审批流程或 state machine。

仍需保持警惕：

- Human Layer 如果继续无证据扩张，可能重新制造人类 review burden；
- externalization 与 stepwise control 应按任务 consequence 动态使用，不能机械 ritualize；
- Attention Compression Protocol 仍存在已知的语义覆盖风险。

这些边界已经足以指导实际使用，不支持继续因理论可能性扩建 Human Layer、AI protocol 或测试系统。

---

## 8. Next Stage

ROOT 继续处于实际使用阶段：

> **使用当前 AI Layer 与 Human Layer baseline，在真实项目协作中验证它们是否持续降低 drift、ambiguity 与人类 review burden。**

默认不继续修改：

- `foundation/human-layer-skills.md`
- `src/skills/attention-compression-protocol.md`

只有真实使用中反复出现、明显影响正确性、可控性或人工成本的问题，才重新触发窄幅修正或新增能力。
