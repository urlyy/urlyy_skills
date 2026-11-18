# urlyy_skills

这里收集了我选用的 20 个 AI Agent 技能，用于写作、理清需求、开发软件和制作图解。每个技能占一个根目录文件夹，入口是 `SKILL.md`，所需脚本、模板和参考资料都放在其中。

[English](README.en.md)

## 技能目录

| 技能 | 简介 | 使用场景 | 来源 |
| --- | --- | --- | --- |
| [sloptrim-zh](sloptrim-zh/SKILL.md) | 中文去 AI 味，保留事实与作者声音 | 润色文章、邮件、报告 | [链接](https://github.com/ismilewolf-eng/sloptrim-zh) |
| [ste-writing](ste-writing/SKILL.md) | 用简化技术英语改善表达 | 英文技术文档、README、错误消息 | [链接](https://github.com/woosal1337/blog/blob/main/videos/ep01-the-cure-for-ai-slop/ste-writing-skill.md) |
| [grill](grill/SKILL.md) | 通过分轮追问找出需求盲点 | 想法不清晰、方案压力测试 | [链接](https://github.com/nagi-studio/skills/tree/main/skills/pondering/grill) |
| [architect](architect/SKILL.md) | 比较技术栈并推荐方案 | 框架、数据库、部署选型 | [链接](https://github.com/nagi-studio/skills/tree/main/skills/rookie/architect) |
| [prove-it](prove-it/SKILL.md) | 用可验证证据证明交付 | 验收、重复错误、测试质量 | [链接](https://github.com/nagi-studio/skills/tree/main/skills/rookie/prove-it) |
| [to-spec](to-spec/SKILL.md) | 将已有讨论整理成规格说明 | 需求讨论结束，准备开发 | [链接](https://github.com/mattpocock/skills/tree/main/skills/engineering/to-spec) |
| [to-tickets](to-tickets/SKILL.md) | 拆分可验证的纵向任务与依赖 | 大型功能分解、任务排期 | [链接](https://github.com/mattpocock/skills/tree/main/skills/engineering/to-tickets) |
| [implement](implement/SKILL.md) | 依据规格或任务实现功能 | 需求明确后的编码执行 | [链接](https://github.com/mattpocock/skills/tree/main/skills/engineering/implement) |
| [implement-spec](implement-spec/SKILL.md) | 按规格说明和拆分好的任务编写代码 | 承接 to-spec 和 to-tickets | [链接](https://github.com/mattpocock/skills/tree/main/skills/engineering/implement-spec) |
| [tdd](tdd/SKILL.md) | 以测试驱动功能实现 | 先写失败测试再实现功能 | [链接](https://github.com/mattpocock/skills/tree/main/skills/engineering/tdd) |
| [diagnosing-bugs](diagnosing-bugs/SKILL.md) | 用复现与实验定位问题 | 疑难 bug、性能退化 | [链接](https://github.com/mattpocock/skills/tree/main/skills/engineering/diagnosing-bugs) |
| [code-review](code-review/SKILL.md) | 按项目规范和原始需求审查 | PR、分支或未提交变更评审 | [链接](https://github.com/mattpocock/skills/tree/main/skills/engineering/code-review) |
| [pr](pr/SKILL.md) | 编写便于评审的 PR 描述 | 提交合并请求前 | [链接](https://github.com/mattpocock/skills/tree/main/skills/engineering/pr) |
| [retro](retro/SKILL.md) | 总结编码过程中的经验 | 阶段结束、改进协作流程 | [链接](https://github.com/mattpocock/skills/tree/main/skills/engineering/retro) |
| [wait-what](wait-what/SKILL.md) | 换一种方式解释上一条回答 | 回答难懂或没有讲到重点 | [链接](https://github.com/mattpocock/skills/tree/main/skills/productivity/wait-what) |
| [handoff](handoff/SKILL.md) | 整理工作进展，方便下一次会话接着做 | 换会话或交给另一个代理 | [链接](https://github.com/mattpocock/skills/tree/main/skills/productivity/handoff) |
| [writing-for-agents](writing-for-agents/SKILL.md) | 编写清楚可执行的代理指令 | 维护技能、AGENTS.md 和 CLAUDE.md | [链接](https://github.com/mattpocock/skills/tree/main/skills/productivity/writing-for-agents) |
| [tune-agents-md](tune-agents-md/SKILL.md) | 起草、审阅或优化 AGENTS.md | 整理长期规则、授权边界和反复纠正的问题 | [参考视频](https://www.bilibili.com/video/BV13a4x6hEc1/) |
| [eli5](eli5/SKILL.md) | 用简短文字和 HTML 图示解释概念 | 学习陌生概念、给非专业人士讲解 | [链接](https://github.com/anthropics/claude-plugins-community/tree/main/eli5/skills/eli5) |
| [html-plan](html-plan/SKILL.md) | 生成可交互的 HTML 实施方案 | 开发前审阅设计和决策 | [链接](https://github.com/anthropics/claude-plugins-community/tree/main/html-plan/skills/html-plan) |

## 快速开始

1. 克隆仓库：`git clone https://github.com/urlyy/urlyy_skills.git`。
2. 选择需要的技能，将整个文件夹复制到你的 Agent 支持的技能目录。不要只复制 `SKILL.md`。安装目录与调用语法以所用客户端为准。
3. 也可以不安装，直接让 Agent 读取本地文件，例如：`请读取 grill/SKILL.md，按其中流程帮我澄清这个想法：……`。
4. 提供目标、输入材料、限制和验收条件。仅在客户端支持时使用 `/skill-name` 或 `$skill-name` 快捷调用。

### 使用例子

- 写作：`使用 sloptrim-zh 润色下面的报告，保留事实和不确定性，不新增结论。` 英文技术文档可使用 `ste-writing`。
- 需求：`使用 grill 帮我找出需求盲点，再用 architect 比较技术方案。`
- 开发：`用 to-spec 整理已讨论需求，再用 to-tickets 拆分任务；确认后使用 implement 或 implement-spec 实现。`
- 排错：`使用 diagnosing-bugs 排查这个错误，先建立稳定复现。`
- 验收：`使用 code-review 审查本次改动，再用 prove-it 展示验收证据。`
- 图解：`使用 eli5 解释数据库索引；使用 html-plan 展示下一步实施方案。`

`implement` 与 `implement-spec` 是两种相近的入口，通常选一个即可。上游部分流程包含提交代码、发布 issue、修改配置等操作，使用时应说明允许的范围。

### 会话结束后用哪个技能

会话里出了错，还不知道该改哪儿，就用 [retro](retro/SKILL.md)。它会复盘这次会话，按严重程度列出改进建议。想让 Agent 直接改技能、补测试或接入校验，就在提示词里说清楚可以改哪些地方。

> 用 `retro` 复盘当前会话，指出哪些地方做错了。有明确证据的，就在当前项目里改对应的技能或补回归测试，改完跑相关检查。

新功能做完后，想把以后的维护约定写进 `AGENTS.md`，就直接用 [tune-agents-md](tune-agents-md/SKILL.md)。

> 用 `tune-agents-md` 回看这次会话、需求和代码改动。把以后维护这个功能时还用得上的约定，写进离相关代码最近的 `AGENTS.md`。写清什么时候要做、怎么做、怎么验证。

## 依赖与运行环境

- `to-spec`、`to-tickets`、`implement-spec`、`code-review` 内置 `references/setup/`，保留上游配置流程和模板，缺少项目配置时按需读取。子依赖不使用 `SKILL.md`，不会新增独立技能。
- 每个技能独立携带所需子资源：实现流程内置 TDD 和审查指南，复盘内置写作指南，TDD 内置模块设计指南。无需另装其他技能，Agent 按需读取内部资料。
- Python 检测脚本需要 Python 3；`html-plan/runtime/pack.mjs` 需要 Node.js。外部任务跟踪系统需要相应连接或 CLI 与授权。
- `agents/openai.yaml` 等原有元数据按原样保留。客户端对字段、工具、子代理和调用策略的支持可能不同；尚未验证所有客户端的兼容性。

## 来源

本仓库选用了以下项目的技能，并参考了相关资料，感谢原作者：

- [sloptrim-zh](https://github.com/ismilewolf-eng/sloptrim-zh)
- [ste-writing](https://github.com/woosal1337/blog/blob/main/videos/ep01-the-cure-for-ai-slop/ste-writing-skill.md)
- [Nagi Studio Skills](https://github.com/nagi-studio/skills)
- [Matt Pocock Skills](https://github.com/mattpocock/skills)
- [Claude Plugins Community](https://github.com/anthropics/claude-plugins-community)（eli5、html-plan）
- [主题学习社 · 如何写好 Agents.md](https://www.bilibili.com/video/BV13a4x6hEc1/)（tune-agents-md 的参考视频）

各技能保留原有许可；根目录 MIT 许可适用于本仓库原创的技能、文档和维护内容。
