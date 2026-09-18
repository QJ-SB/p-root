# ***ROOT Foundation***

## `1. Mission`

ROOT 用于设计、验证、维护和重构一套适用于 AI 协作项目的通用项目范式。

它试图解决的核心问题不是 AI 产出不足，而是：

> **AI 产出能力快速增长后，人类 attention、理解能力和 review bandwidth 成为新的瓶颈。**

因此，ROOT 的目标不是建立更复杂的工程系统，而是建立一套：

* 足够小
* 足够稳定
* 足够通用
* 易于理解
* 易于维护
* 能持续产出

的 AI 协作项目结构与工作方式。

ROOT 本身也必须遵守这套原则。

---

## `2. Core Philosophy`

### 2.1 Output Before Optimization

项目首先应该解决现实问题，而不是首先完善自身。

当一个项目已经拥有可以稳定工作的 Minimal Vertical Slice 后，默认行为应该是：

> **停止建设，开始使用。**

只有真实使用中暴露出的明确问题，才重新触发优化。

不因为“未来可能需要”提前建设。

---

### 2.2 Minimal Vertical Slice

项目应尽快形成一个能够贯通核心工作流的最小垂直切片。

它不需要：

* 功能完整
* 覆盖所有场景
* 消除全部 ambiguity
* 拥有完善自动化
* 拥有完整测试体系

它只需要能够稳定完成项目最核心的职责。

Minimal Vertical Slice 一旦成立，项目即进入实际使用阶段。

---

### 2.3 Single Responsibility

一个项目原则上只承担一个主要职责。

不同项目之间应尽量保持独立：

* 不依赖彼此内部状态
* 不直接认识彼此
* 不形成复杂跨项目耦合

复杂任务可以由人类根据需要组合多个项目完成。

ROOT 不作为其他项目的中央控制器或运行时系统。

人类是项目之间的信息选择者、传递者和最终协调者。

---

### 2.4 Attention Budget

所有新增结构都存在人类成本。

任何新增：

* 文件
* 协议
* 状态
* checkpoint
* router
* validation
* automation
* 文档层级

都必须考虑：

> **它节省的人类 attention，是否大于它带来的理解、审核和维护成本。**

如果不能明显成立，则默认不增加。

---

### 2.5 Resolution Discipline

项目只管理到完成自身职责所需要的最低有效解析度。

不是所有 ambiguity 都需要被消灭。

如果 AI 可以在运行时可靠判断，则不应为了获得形式上的确定性，把这些判断继续升级成人类需要维护的：

* protocol
* rule
* schema
* state machine
* routing logic

核心原则：

> **Specify only what must not drift. Leave the rest to intelligence.**

只规定不能漂移的东西，其余交给智能。

---

### 2.6 Evidence-Driven Expansion

项目扩张必须由真实证据驱动。

新增结构、功能或规则的合理来源通常包括：

* 同类问题反复发生
* 已明显影响稳定性
* 已明显增加人工成本
* 已阻碍项目核心产出

单次异常、理论风险或未来假设，通常不足以触发架构升级。

项目默认采用消极膨胀原则：

> **没有足够证据，就不扩张。**

---

## `3. Canonical Truth`

同一件事情应尽量只存在一个 authoritative source。

避免同时存在多个表达同一状态的文件，例如：

* current state
* latest state
* session checkpoint
* handoff
* architecture latest
* architecture final

如果多个文件描述同一个当前事实，人类就需要额外判断哪个才是真的。

因此 ROOT 默认要求：

> **One canonical truth per concern.**

当前项目的真实结构、状态、能力和版本，以：

`context/snap/current.md`

为唯一最新事实来源。

Foundation 不重复维护当前目录树、当前实现状态或当前版本信息。

---

## `4. Context and Archive`

项目上下文只承担两个职责：

### Current Snapshot

`context/snap/current.md`

记录项目当前真实状态，包括：

* 当前结构
* 当前能力
* 当前核心文件或实现
* 当前阶段
* 已完成事项
* 尚未完成事项
* 下一步

它采用覆盖更新。

原则上只保留一个当前快照。

---

### Rolling Archive

`context/archive/history.md`

保存项目历史。

每次需要归档时，只进行：

> **压缩 → 加时间戳 → rolling append**

Archive 不承担当前状态说明职责。

如果需要知道项目现在是什么状态，应直接查看 Current Snapshot。

默认不因每个 session 创建新的 checkpoint 或 archive 文件。

---

## `5. Project Structure Principle`

ROOT 使用一套稳定的一级项目骨架。

具体项目可以根据职责，在现有一级目录内部形成自己的子结构。

一级结构默认保持稳定，不因为单个项目的特殊需求轻易扩张。

只有当真实项目实践反复证明当前一级结构无法合理承载需求时，才考虑修改通用骨架。

ROOT 当前实际目录结构以：

`context/snap/current.md`

中的记录为唯一 authoritative source。

通用骨架的核心职责包括：

* `foundation/`：项目长期设计理念与稳定原则
* `context/`：当前状态与历史归档
* `src/`：项目核心能力
* `tests/`：验证与测试空间
* `data/`：项目数据空间

具体目录结构不在 Foundation 中重复维护。

---

### 5.1 Human and AI Project Entry

项目默认区分两个入口：

* `README.md`：面向人类，帮助快速理解项目目的、定位和主要导航
* `project-instruction.md`：面向 AI，简要介绍项目并承担初始路由职责

`README.md` 不承担 AI 行为指令或能力路由职责，默认不需要装载进 GPT Project Files 或同类 AI 项目文件环境。

`project-instruction.md` 位于项目根目录。它只负责告诉 AI：

* 项目是什么、边界在哪里
* 哪个文件负责长期原则
* 哪个文件负责当前事实
* 当前任务应路由到哪个 skill 或 code

它不复制 Foundation、Current、skill 或 code 的具体内容，也不建立第二份项目状态。

---

### 5.2 Project-Local Routing

`project-instruction.md` 是项目内部的最小 router，不是中央运行时系统。

项目规模较小时，当前任务所需的 `foundation.md`、`current.md`、skill 和 code 可以直接装载进 AI 项目文件环境，由 `project-instruction.md` 指向相应文件。

只有真实使用证明文件数量或加载成本已经造成问题时，才考虑更细的索引、分层加载或外部工具。不得为潜在膨胀提前建设复杂路由系统。

Router 只建立选择关系：

* 需要稳定原则时，读取 Foundation
* 需要当前事实时，读取 Current Snapshot
* 需要专门行为能力时，读取匹配的 `src/skills/` 文件
* 需要执行能力时，检查并使用匹配的 `src/code/` 文件

文件被路由或装载不等于代码已经执行。代码执行仍需要可用的运行环境、明确的任务授权和必要验证。

如果被路由的文件不可用，AI 不应假定其内容或虚构其能力。

---

## `6. Source and Data Principles`

### src

`src/` 存放项目真正工作的核心能力。

通常可以包括：

* `skills/`
* `code/`

具体子结构由项目职责决定。

项目正常运行所依赖的核心 skill、代码和脚本原则上应进入版本管理。

临时生成物、缓存和可重新构建的 runtime 不应因为存在于 `src/` 就自动进入 Git。

---

### tests

`tests/` 是验证空间，而不是强制流程。

项目可以没有复杂测试体系。

测试只应在它真实提高可靠性或降低人工验证成本时出现。

长期有效的 regression、behavior 或代码测试可以保留。

一次性测试材料应及时清理或忽略。

---

### data

`data/` 用于项目运行产生或依赖的数据。

它允许根据项目职责形成自己的内部结构。

数据通常不作为项目架构本身的一部分，因此是否进入 Git 应根据：

* 体积
* 可复现性
* 敏感性
* 项目实际需求

决定。

---

## `7. Expansion Rules`

默认遵循：

> **能删就不加。**
> **能合并就不拆。**
> **能让 AI 判断就不写规则。**
> **能开始产出就停止造系统。**

新增结构前，应优先问：

1. 这是已经发生的问题，还是想象中的问题？
2. 它是否真正影响核心产出？
3. AI 是否可以直接处理？
4. 是否可以通过修改已有文件解决？
5. 新结构是否会制造新的 review burden？

如果没有明确理由，则不新增。

---

## `8. ROOT's Own Responsibility`

ROOT 只负责：

* 维护项目范式
* 设计项目骨架
* 重构和简化已有项目
* 从真实项目实践中提炼通用原则
* 验证这些原则是否真的减少复杂度和人工负担

ROOT 不负责：

* 统一运行其他项目
* 保存所有项目状态
* 自动协调所有项目
* 成为跨项目 dependency
* 为每种未来情况提前设计解决方案

ROOT 必须避免自己成长为它原本试图解决的问题。

---

## `9. Success Criterion`

ROOT 的成功不以：

* 文件数量
* 功能数量
* 自动化程度
* 架构复杂程度

衡量。

它的主要成功标准是：

> **在项目持续工作的前提下，让人需要理解、维护和审核的东西尽可能少。**

最终目标不是建立最完整的系统。

而是建立：

> **能够工作的最小系统。**
