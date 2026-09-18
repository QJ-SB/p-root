# Small Compression Layer Protocol — Test Summary

**Freeze Date:** 2026-09-18  
**Scope:** 已完成的三组对照测试  
**Protocol State:** `skill.md` v2 frozen; no further edits in this phase

---

## 1. Purpose

验证一个独立的 pre-output compression protocol，是否能在不损失任务所需语义的前提下，降低人类阅读与审核成本。

本轮测试不验证归档后重开 session，也不建立自动化评测系统。

---

## 2. Test Architecture

### Control

使用相同领域项目的 `foundation.md` 与 `current.md`，不加载 compression protocol。

### Compression

在相同领域文件之外加入：

- `project-instruction.md`：最小 router；
- `skill.md`：持续生效的 pre-output protocol。

三个测试是在协议逐步修正的过程中完成的，因此不能把全部数字合并成一个严格的总分。

---

## 3. Frozen Results

| Test | Rounds | Protocol stage | Control response chars | Compression response chars | Result |
| --- | ---: | --- | ---: | ---: | --- |
| Quant / RSI | 3 | activation 与 router 尚未稳定 | 13,716 | 12,321 manual / 11,889 project-file | 约缩短 10%–13%，但首轮出现超出请求范围的展开 |
| English learning | 4 | router 已加入，v2 前 | 10,166 | 10,233 | 总量基本持平；第 2 轮过度教学抵消第 1 轮收益 |
| AI job data workflow | 4 | v2 | 17,991 | 14,326 | 缩短约 20%；四轮均更短，范围与不确定性控制明显稳定 |

### 3.1 Quant / RSI

三组输出在核心计算与代码结果上均正确。

Compression 版本整体更短，但两种 compression 变体都在第 1 轮主动扩展了额外 Wilder 计算，而 control 更严格地停在请求边界内。

这一组主要证明：

- 文件可见或出现引用标识，不等于协议已作为持续行为生效；
- 仅把 `skill.md` 放入项目文件，不足以证明 activation；
- 需要在 skill 内声明 Activation，并由项目级最小 router 明确路由。

### 3.2 English Learning

全部回答语义正确，但 compression 的稳定性不足：

- Round 1 明显更短，主线更清楚；
- Round 2 扩展到额外结构、决策树和低价值例句，单轮反而比 control 长约 49%；
- Round 3 略长；
- Round 4 基本持平。

这一组暴露的不是召回失败，而是选择标准过宽：模型把“有帮助、可教学、可补充”误判成“回答所必需”。

因此 v2 加入了明确判断：只有遗漏会实质损害正确理解、判断、行动、核验或安全的信息，才算必要信息；相关、有用、富有教学价值或更完整，本身不构成保留理由。

### 3.3 AI Job Data Workflow

这是 v2 的首个完整对照测试。

结果：

- 四轮 compression 输出全部短于 control；
- 总字符数约减少 20%；
- 未出现数据库、批处理、评分、多 agent 或自动化等范围升级；
- `not_stated`、歧义与冲突得到保留；
- 主语义线和核验路径保持清晰。

仍发现一个重要覆盖风险：compression schema 没有独立保留 `education_requirement`，导致样本中的强制学历要求只存在于原文，而没有进入结构化字段。这说明压缩已经明显改善，但仍可能把“影响后续决策的字段”误删。

另有一个轻微一致性问题：`source_url` 已单独存储，但 `raw_text` 没有完整包含 URL 行，与“保留完整原文”的表述不完全一致。

---

## 4. Cross-Test Findings

### Supported

1. `skill.md` 需要显式 Activation；项目文件中需要一个最小 router。
2. 引用标识不能作为协议是否被调用的可靠遥测。
3. v2 相比此前版本，已明显改善范围控制与稳定压缩。
4. 协议最有价值的不是机械缩短，而是减少非必要展开，同时保留任务所需的判断、核验与不确定性。

### Not Yet Supported

1. 不能据此声称所有领域都能稳定缩短固定比例。
2. 不能据此声称 compression 永远不会造成语义覆盖损失。
3. 不能把三组字符数合并成严格总分，因为协议版本和部署方式在测试间发生过变化。
4. 尚未测试归档后重开 session；本阶段也不把它列为必要验证项。

---

## 5. Frozen Decision

当前冻结 `skill.md` v2，不立即增加新规则。

理由：

- v2 已在第三组测试中表现出明显改善；
- `education_requirement` 的遗漏很重要，但现有 Compression Invariant 已经禁止删除影响决策的信息；
- 单次生成遗漏尚不足以证明协议文本仍缺少一条新规则。

因此，v2 当前状态定义为：

> **candidate baseline，尚未正式定版。**

下一步只做跨测试综合判断：选择直接把 v2 提升为 baseline，或基于重复证据进行一次窄幅修正。此前不继续扩建协议或测试系统。

---

## 6. Frozen Evidence

- Quant: `control-log.md`, `compression-log.md`, `compression(built-in)-log.md`
- English: `control-log(1).md`, `compression-log(1).md`
- AI job data workflow: `control-log(2).md`, `compression-log(2).md`
- Protocol under test: `skill.md` v2

原始日志保持不修改。本文件是本轮测试结论的唯一汇总，不替代原始证据。
