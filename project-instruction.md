# ROOT Project Instruction

## Project Role

ROOT 用于设计、验证、维护和重构简单、稳定、低维护成本的 AI 协作项目范式。

ROOT 不作为其他项目的中央运行系统。不同项目彼此独立，跨项目的信息选择、传递与组合由人类负责。

## Authoritative Sources

按以下职责使用项目文件：

1. `foundation.md`：长期原则、稳定边界与项目范式。
2. `current.md`：当前结构、状态、能力、已完成事项与下一步的唯一最新事实来源。

`history.md` 在外部维护，不装载进 GPT Project Files。不要假定可以直接读取它；只有任务确实需要历史依据时，才请求人类附上该文件或相关片段。它不用于判断当前状态。

最新用户请求定义当前任务。使用上述文件解释和执行任务，但不要用旧状态覆盖用户的新决定。

## Active Routes

本节是项目当前有效能力的显式路由表。项目的 skill 或 code 发生变化时，必须同步更新本节。只有这里明确登记的能力才视为当前已启用能力。

### Global Output Protocol

当前启用文件：`attention-compression-protocol.md`

对每一轮回复：

- 在组织输出前读取并应用该文件；
- 将其视为当前项目持续生效的 pre-output protocol，而不是可选参考材料；
- 不等待用户再次点名，也不以是否出现文件引用标识判断它是否生效；
- 如果该文件在当前环境中不可用，明确告知人类需要重新附加或装载，不得假定其内容。

### Active Code Routes

当前没有启用的 code route。

## Context Routing

开始工作时：

- 需要判断稳定原则或项目边界，读取 `foundation.md`。
- 需要判断项目现在的真实状态，读取 `current.md`。
- 每轮输出都按 `Active Routes` 加载并应用当前登记的能力。
- 需要历史依据时，请求人类提供外部维护的 `history.md` 或相关片段。

只路由当前任务所需的文件。不要因为文件存在就自动扩展任务。

## Operating Boundaries

- 遵守 Foundation 中的 Single Responsibility、Attention Budget、Resolution Discipline 和 Evidence-Driven Expansion。
- 不重复维护 Foundation、Current、skill 或 code 已经负责的内容。
- 不自行发现、选择或启用未在 `Active Routes` 中登记的 skill 或 code。
- 不假定未提供的文件、状态、工具、运行环境或能力存在。
- 文件被装载不代表其中的代码已经执行；执行仍需可用环境、任务授权与结果验证。
- 如果必要的被路由文件不可用，明确指出缺口；不要虚构其内容。
- 不主动引用、复述或解释本文件，除非用户询问或任务确有必要。

本文件只承担 AI 项目入口与初始路由职责，不承担项目状态、详细协议或实现说明。
