<div align="center">
  <img src="https://i.imgur.com/v0Tx6am.png" alt="AI 编码指南" />
  <p align="center">
    作者 <a href="https://x.com/aut0mata">Vilson Vieira</a> & <a href="https://x.com/esrtweet">Eric S. Raymond</a>
  </p>
  <a href="https://discord.gg/NrDfXmtvw3">
     <img src="https://i.imgur.com/uqKVFHj.png" alt="加入我们的 Discord" height="48" />
  </a>
</div>
<br/>

> 你想了解的，关于 AI 辅助编程或 AI 自主编程的一切。

<div align="center" style="font-size: 30px">
  <a href="#vibe">太长不看，直接教我怎么“氛围编程” 😎！</a>
</div>
<br /><br />

## 引言

我们与计算机交互、为其编写代码的方式，正迎来一场深刻的变革。这场变革不仅体现在工具层面，更深入到我们编码、构思软件产品和系统的方式之中。

而且，技术迭代的速度超乎想象！每周都有新的 LLM 模型问世，随之而来的是层出不穷的工具、编辑器、编程范式（例如“氛围编程”），以及各种新协议（MCP, A2A, SLOP...）。想要跟上这股潮流并非易事，所有信息都散落在不同的网站、代码仓库和视频教程里，令人眼花缭乱。

这正是我们编写本指南的初衷。我们希望能尽力将所有相关内容整合起来，用清晰、易懂的方式，为你呈现 **AI 编码**（AI Coding）或 **AI 辅助代码生成**（AI-assisted Code Generation）领域的实践与工具。

- **如果你是开发者，但还没用过 AI 代码助手**，本指南就是为你准备的。它将介绍最新的工具和最佳实践，助你在日常工作中如虎添翼，无论你是让 AI 当你的副驾，还是反过来，你为 AI 代理领航。

- **如果你从未接触过编程，但对“氛围编程”这种新潮玩意儿很感兴趣，想用它来打造自己的 SaaS 或其他软件产品**，那本指南就更适合你了。我们将尽力为你扫清障碍，只保留开启这段旅程的必备知识，并以批判性的眼光，帮你分辨哪些是真材实料，哪些只是昙花一现的炒作。

好了，让我们开始吧！

📚 **相关资源:**

- [我们所知的编程的终结](https://www.oreilly.com/radar/the-end-of-programming-as-we-know-it) by Tim O'Reilly
- [如何为开发的未来和 AI 做准备](https://www.youtube.com/watch?v=BP54GqVK3JA) by Santiago
- [初级开发人员的复仇](https://sourcegraph.com/blog/revenge-of-the-junior-developer) by Steve Yegge
- [亲爱的学生：是的，AI 来了，除非你采取行动，否则你就完蛋了...](https://ghuntley.com/screwed/) by Geoffrey Huntley
- [如何构建一个代理](https://ampcode.com/how-to-build-an-agent) by Thorsten Ball
- [使用 LLM 进行编码](https://simonwillison.net/2025/Mar/11/using-llms-for-code/) by Simon Willison
- [70% 的问题：关于 AI 辅助编码的残酷事实](https://addyo.substack.com/p/the-70-problem-hard-truths-about) by Addy Osmani
- [成为一名 AI 增强工程师](https://maryrosecook.com/blog/post/become-an-ai-augmented-engineer) by Mary Rose Cook
- [播客：Raising an Agent](https://ampcode.com/podcast) by Amp team
- [软件正在（再次）改变](https://www.youtube.com/watch?v=LCEmiRjPEtQ) by Andrej Karpathy

## AI 编码？氛围编程？

这些术语大同小异。简单来说，**AI 编码** 就是利用 AI 模型（尤其是现在流行的 LLM）及相关工具来辅助编写软件。它也被称为“AI 代码生成”（Code Gen），这是一个迷人的研究和工程领域，其历史可以追溯到 1950 年代用 Lisp 生成代码的时代。如今，LLM 已成为代码生成的主要引擎，同时，神经符号混合等前沿方法也开始崭露头角。AI 编码也是一种实践：无论你是用 Cursor `Tab` 键自动补全代码，还是完全依赖其代理模式，都属于 AI 编码的范畴。简而言之，任何利用 AI 模型生成代码的方式，都是 AI 编码。通常，这个群体已经具备一定的编程基础。

**“氛围编程”**（Vibe Coding）则是 AI 编码的“进阶玩法” :-) 在这种模式下，你不再过度关心代码细节，只需给出提示，然后期望 AI 为你搞定一切。这个词由 [Karpathy 在 2025 年提出](https://x.com/karpathy/status/1886192184808149383)后迅速流行起来。在我看来，它正在帮助那些从未想过编程的人，真正地实现“编程民主化”！

所以，总而言之，无论你是用 AI 讨论软件构想、辅助编写部分代码，还是完全沉浸在“氛围编程”中，你都在利用 AI 生成代码。我们就统一称之为 **AI 编码**，然后继续往下看。

## 我该如何使用它？

你可以通过多种方式进行 AI 编码，但主要分为两种角色：

- **AI 当你的副驾**：你借助 AI 模型来增强自身能力、提高效率。无论是用 ChatGPT 头脑风暴 SaaS 产品的点子，还是用 Cursor 自动生成文档字符串，都属于此范畴。这种方式在创造性探索和自动化繁琐工作方面优势明显。

- **AI 当主驾，你当副驾**：这就是“氛围编程”的核心所在。你开启 Cursor Agent 的 YOLO 模式，充分信任 AI 代理为你生成代码。这是一种强大的自我自动化方式，但它也对你提出了一些要求：你需要掌握设计系统、驾驭 AI 代理的良好实践，并学会在一片你并不熟悉的代码“面条”中解决问题。

你应该学习并实践这两种模式！

不过，随着项目复杂度的提升，你应该更多地采用“副驾模式”，而不是纯粹的“YOLO 氛围编程”。代码越有可能需要被他人（或六个月后的你自己）维护，这一点就越重要。

# 🗺️ 路线图

## 如何开始？

- **如果你不懂编程，只是想尝尝鲜**，建议从 [Bolt](https://bolt.new)、[Replit](https://replit.com)、[v0](https://v0.dev) 或 [Lovable](https://lovable.dev) 这类 Web 工具开始。

- **如果你已经会编程**，请安装 [Cursor](https://cursor.com/) 或 [Windsurf](https://windsurf.com/)。可以从免费版开始，之后再考虑是否升级到每月 20 美元的付费套餐。Cursor 功能强大且性价比高，能让你用上大多数最新的 LLM 模型。VSCode 最近也推出了自己的[代理模式](https://code.visualstudio.com/blogs/2025/02/24/introducing-copilot-agent-mode)，它与 GitHub Copilot 结合，通过代理工作流来修改文件。其他主流编辑器也在迅速跟进，可以关注你常用编辑器的官网，了解它们的最新动态（这些高级功能通常在 Beta 或 Insider 版本中提供）。

- **如果你想要更开源的替代品**，可以试试 [OpenHands](https://github.com/All-Hands-AI/OpenHands)。它通过 Docker 容器运行一个 Web 应用。你需要注册 [Anthropic API 账户](https://console.anthropic.com/) 获取 API 密钥，或使用 [OpenRouter](https://openrouter.ai/) 上的 LLM 模型。

- **如果你是和我们一样的终端爱好者**，可以看看 [aider](https://aider.chat/)、[Claude Code](https://docs.anthropic.com/en/docs/agents-and-tools/claude-code/overview) 或 [OpenAI Codex](https://github.com/openai/codex)。使用这些工具前，你需要准备好 Anthropic Claude、OpenAI GPT 或 OpenRouter 的 API 密钥。

- **如果你既喜欢终端，又离不开 VSCode 风格的编辑器，还想体验多代理并行工作的强大威力，且预算充足**，那么 [Amp](https://ampcode.com) 值得一试。

> **建议**：我们强烈建议注册一个 OpenRouter 账户。注册过程非常简单，之后你就可以访问到包括免费版在内的各种最新 LLM 模型。例如，我们目前的首选模型 Gemini 2.5 Pro 就可以通过 OpenRouter 免费使用（虽然有每日额度限制，但对于体验 Aider 和 OpenHands 等工具来说，是个不错的选择）。

> **重要提示**：Claude Code 目前相当昂贵！一天花掉 50 美元是常有的事。所以请务必留意你的账单。这也是我们推荐从 Cursor 入手的原因之一，能省去不少费用上的烦恼。

📚 **相关资源:**

- [使用 Replit 进行氛围编程 101](https://www.deeplearning.ai/short-courses/vibe-coding-101-with-replit/)
- [Cursor AI 初学者教程 [2025 版]](https://www.youtube.com/watch?v=3289vhOUdKA)

## 如何更好地提问（Prompt）？或者说，如何“Vibe”出好代码？<a id='vibe'></a>

在你上手这些工具一段时间后，你可能会发现它们有时会产生幻觉，或者陷入修复某个错误的死循环。因此，学会如何有效提问至关重要。以下是一些技巧：

- **不要指望一个提示就搞定所有事**。简单地甩一句“嘿，给我做个宠物店 App”对人类工程师没用，对 AI 更没用。你应该先和 LLM 一起进行头脑风暴，梳理你的项目，创建一份 PRD（产品需求文档），制定计划，并拆分成小任务。下文会教你如何用 ChatGPT 来完成这些。
- **提供充足的细节**。明确你想要什么，就直接说出来。比如你希望使用哪种编程语言、技术栈，你的目标用户是谁等等，都应该在提示中说明。
- **善用格式**。Markdown 或 AsciiDoc 等轻量级标记语言都能被 LLM 很好地解析。为了强调提示中的关键部分，建议使用 [XML 标签](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/use-xml-tags)等符号。
- **拆分任务**。将你的项目分解成任务和子任务。
- **为不同目标选用不同模型**。
- **交叉验证**。用一个模型的输出去验证另一个模型的结果。
- **保持批判性思维**。LLM 很可能会对你“有求必应”，所以你必须保持批判性思维，审视其生成的内容。

在后续的例子中，我们将默认使用 Markdown（`.md`）文件。如果你更喜欢对结构化文档支持更好的 AsciiDoc，只需将文件后缀换成 `.adoc` 即可。LLM 不会挑剔你用的纯文本格式。

这里有一套行之有效的工作流：

1.  打开 `ChatGPT 4.5`、`4o` 或 `o3`，输入以下提示：

    ```
    你是一位资深软件工程师。接下来，我们将一起为我的项目构思一份 PRD（产品需求文档）。

    重要原则：
    - 一次只问一个问题。
    - 每个问题都基于前一个回答展开。
    - 针对每个重要细节进行深入挖掘。

    我的想法是：
    <在这里粘贴你的想法>
    ```

2.  接下来，你会和 AI 进行几分钟的问答。尽量详细地回答每个问题。当你觉得差不多了，就用下面的提示，让 AI 把讨论结果整理成 PRD：

    ```
    请将以上讨论内容整理成一份 PRD，使用 Markdown 格式。PRD 应包含以下部分：

    - 项目概述
    - 核心需求
    - 核心功能
    - 核心组件
    - 用户/应用流程
    - 技术栈
    - 实现计划
    ```

3.  将生成的 PRD 内容保存到项目文件夹下的 `docs/specs.md` 文件中。
4.  现在，我们来创建项目任务列表。向 AI 发出以下指令：

    ```
    请基于刚刚生成的 PRD，为这个项目创建一个详尽的、分步执行的计划。
    首先，将计划分解为多个互相依赖的小任务。
    然后，将每个任务再细分为更小的子任务。
    请确保每个步骤都足够小，便于实现，但又能有效推进项目直至成功。
    遵循软件开发和项目管理的最佳实践，避免出现大的技术断层或复杂性跳跃。
    任务之间应该建立依赖关系，形成一个依赖列表，不应有任何孤立的任务。

    重要要求：
    - 使用 Markdown 或 AsciiDoc 格式。
    - 每个任务和子任务都应是一个可勾选的列表项。
    - 为每个任务提供足够的上下文，以便开发者能直接上手实现。
    - 每个任务都应有唯一的数字 ID。
    - 每个任务都应列出其依赖的任务 ID。
    ```

5.  将这份任务清单保存为 `docs/todo.md`。

[这里有一个范例](https://chatgpt.com/share/67f8e8c6-c92c-8007-8fe0-76bdc73f9812)，展示了如何使用 ChatGPT 4o 为一个简单的 CLI 工具进行头脑风暴和规划。你可以此为参考。

现在，为你的项目创建一个本地文件夹，并记得在其中运行 `git init`，从一开始就做好版本控制。

至此，你应该已经拥有了项目的 PRD 和任务清单！有了它们，你就可以打开 Cursor（或其他 AI 代码编辑器），把这两个文件喂给它，然后说：

```
你是一位资深软件工程师。请研究 @docs/specs.md 文件，并实现 @docs/todo.md 中尚未完成的任务。请严格按照任务和子任务的依赖关系，逐一实现。每完成一个任务，就在列表中将其标记为完成，然后继续下一个。
```

当 Cursor Agent 首次执行命令时，大胆启用 YOLO 模式，然后你只需在它的每次询问后输入 `continue` 或直接同意即可。

在使用 Cursor 时，LLM 有时会达到处理上限并请求重试。照做就行。没错，你正在体验的就是“氛围编程” :-)

这里有一个基于此工作流，在 10 分钟内构建完成的 CLI 工具的 Git 仓库，可供参考：https://github.com/automata/localbiz

> **重要提示**：虽然“氛围编程”很酷，但理解 AI 正在做什么也同样重要。花时间审查 AI 生成的代码，不仅能帮助你在出错时（错误总会发生！）快速定位问题，还能极大地锻炼你的代码审查能力（无论是审查 AI 还是人类写的代码）。

📚 **相关资源:**

- [你用错了 Cursor AI...](https://ghuntley.com/stdlib/) by Geoffrey Huntley: Geoff 在此文中介绍了他使用 Cursor 规则标准库（stdlib）的想法。
- [从设计文档到代码：Groundhog AI 编码助手](https://ghuntley.com/specs/) by Geoffrey Huntley: 上一篇文章的续篇，Geoff 建议利用 LLM 自动生成项目规格（PRD）和 Cursor 规则。
- [我目前的 LLM 代码生成工作流](https://harper.blog/2025/02/16/my-llm-codegen-workflow-atm/) by Harper Reed
- [一个 LLM 代码生成英雄的旅程](https://harper.blog/2025/04/17/an-llm-codegen-heros-journey/) by Harper Reed
- [Claude Code：代理式编码的最佳实践](https://www.anthropic.com/engineering/claude-code-best-practices) by Anthropic: 这篇文章虽然是针对其自家的 Claude Code 工具，但其中关于 AI 编码工作流的技巧对使用任何 LLM 都很有启发。
- [提示工程](https://www.kaggle.com/whitepaper-prompt-engineering) by Lee Boonstra (Google): 一份长达 70 页的文档，深入浅出地介绍了提示工程的技巧，其中有专门的章节讨论代码生成。
- [提示工程指南](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering) by Anthropic
- [GPT 4.1 提示指南](https://cookbook.openai.com/examples/gpt4-1_prompting_guide) by OpenAI
- [RepoPrompt](https://repoprompt.com/): 一个能帮你从项目中整合上下文的工具。建议观看其 [RepoPrompt 工作流概览视频](https://www.youtube.com/watch?v=fm3VreCt-5E)，学习如何轻松地为你的“氛围编程”提示提供更丰富的上下文。
- [并非所有 AI 辅助编程都是“氛围编程”](https://simonwillison.net/2025/Mar/19/vibe-coding/) by Simon Willison

## 我应该使用哪个 LLM 模型？

不同的 LLM 为不同的目标而生。下表根据常见任务推荐了一些适用模型：

| 任务 | 推荐模型 |
|----------------------|---------------------------------------------------------------|
| 头脑风暴 | GPT 5, 4o, o3, Grok |
| 编码 | Claude Sonnet 4, Gemini 2.5 Pro, Grok, GPT 5, o3, o4-mini |

LLM 的世界日新月异，这张表很快就会过时。请参考以下排行榜获取更准确的实时对比：

- [OpenRouter 模型榜单](https://openrouter.ai/models?categories=programming&fmt=table): 将分类筛选为 `programming`，并勾选只看支持 `tools` 的模型，通常能帮你找到适合 AI 辅助编码的好模型。
- [Models.dev](https://models.dev): 一个开源的 AI 模型数据库。
- [AI 代理排行榜](https://huggingface.co/spaces/galileo-ai/agent-leaderboard)

## 遇到烦人的“速率限制”（Rate Limit）怎么办？

换个模型试试。

遇到速率限制通常有两个原因：一是你的请求可能太“重”，超出了模型的输入/输出 token 限制；二可能是服务器负载过高，暂时对你进行了限流。但返回的错误信息往往不会说得这么明白。你可以在[这里](https://platform.openai.com/docs/guides/rate-limits)找到更详细的解释。

不同模型的 token 限制差异很大。例如，在 2025 年 4 月，gpt-4.1-mini 就比 gpt-4.1 要慷慨得多。所以，多备几个平台的 API 密钥是个好习惯（反正按量付费，成本不高），并时常关注它们的速率限制说明页面，比如 [Anthropic 的这个例子](https://console.anthropic.com/settings/limits)。

## 如何设定全局规则？

你可以通过向 LLM 的上下文中“注入”规则或约定来影响它的行为。不同的编辑器有不同的实现方式：

- **Cursor**: 只需在项目根目录的 `.cursor/rules/` 文件夹下创建 Markdown 文件即可。Cursor 会确保在与 LLM 的所有交互中都应用这些规则。
- **Aider**: 创建一个包含[规则/约定](https://aider.chat/docs/usage/conventions.html)的 Markdown 文件（例如 `rules.md`），然后在 `.aider.conf.yml` 配置文件中添加 `read: rules.md`。

此外，许多工具还支持在家目录中设置全局规则文件，让其对所有项目生效。例如，在 Aider 中，你可以创建一个 `~/.global_conventions.md` 文件，然后在配置文件中通过 `read: [~/.global_conventions.md, rules.md]` 同时加载全局和项目级规则。

你可以把 PRD 中的技术栈、代码风格指南等内容作为规则注入，效果拔群。你甚至可以利用 AI 来为你生成这些规则！具体可以参考 [Geoff 的方法](https://ghuntley.com/specs/)。

📚 **相关资源:**

- [Cursor 规则文档](https://docs.cursor.com/context/rules-for-ai)
- [Windsurf 规则文档](https://windsurf.com/editor/directory)
- [Aider 约定文档](https://aider.chat/docs/usage/conventions.html)
- [Aider 约定集合](https://github.com/Aider-AI/conventions): 一个由社区贡献的 Aider 约定文件集合。
- [Awesome Cursor Rules](https://github.com/PatrickJS/awesome-cursorrules): 一个精选的 `.cursorrules` 文件列表，用于增强你的 Cursor AI 体验。

## 如何避免 AI “胡说八道”？PRD 又是什么？

PRD 是什么鬼？开个玩笑 :-) 工程界有句老话，解决问题的最好方法是创造一个新缩写。PRD 就是**产品需求文档**（Product Requirements Document）的缩写。说白了，它就是一份或几份描述软件项目需求和各种细节的文档。

事实证明，如果你放任你的 LLM “自由发挥”，不给它足够的上下文，它很快就会开始“胡说八道”。你需要驯服这头“野兽”，而 PRD 正是绝佳的缰绳。

PRD 最棒的一点是，它对所有人都有用——无论你是编程小白，还是资深工程师、产品经理。

你不需要任何专业背景就能开始写 PRD，你需要的只是一个想法。

参考<a href="#vibe">这里</a>，学习如何利用 LLM 为你生成一份 PRD。

## 保留提示记录 (Prompt Log)

把你发给 AI 的每一个提示都记录下来，更重要的是，在记录旁边写下你当时的想法和遇到的意外。这份提示记录就是你的“设计心路历程”，对于任何后来接触这个项目的人（包括六个月后忘得一干二净的你自己）来说，都将是无价之宝。

目前还没有统一的文件命名约定，你可以用 `vibecode.adoc` 或 `history.md` 之类的名字。

像 [aider](https://aider.chat/) 这样的工具会自动记录你与 LLM 的完整对话历史。你可以设置以下环境变量，并将这些历史文件纳入版本控制：

```bash
# 历史文件

## 指定聊天输入历史文件 (默认: .aider.input.history)
#AIDER_INPUT_HISTORY_FILE=.aider.input.history

## 指定聊天历史文件 (默认: .aider.chat.history.md)
#AIDER_CHAT_HISTORY_FILE=.aider.chat.history.md

## 将与 LLM 的对话日志记录到此文件 (例如: .aider.llm.history)
#AIDER_LLM_HISTORY_FILE=.aider.llm.history
```

有了这些日志文件，你就可以随时回顾并附上自己的思考。当你日后重温时，你（和你的合作者）不仅能更好地理解项目，还可能从中发现一些模式和技巧，用于未来的 AI 协作。

## 我该如何启动项目？

### Web 应用（前端）

现代 Web 开发的技术选型令人眼花缭乱。在尝试了多种方案后，我总结出以下几条路径：

- **Next.js**: 如果你想拥抱 Vercel 的生态系统，这是一个不错的选择（但要注意成本可能快速上升）。
- **纯 React + React Router**: 灵活性高，可以部署到任何地方。
- **Remix**: 提供强大的路由功能，同样可以随处部署。
- **FastHTML**: 如果你偏爱 Python，且项目更侧重于后端功能（如数据分析、AI/ML 模型接口）而非华丽的 UI，这是一个值得考虑的选项。

像 Lovable 这样的 AI 编码平台使用 React，而 v0 则基于 Next.js。

**小技巧**：你可以在 Lovable 上启动项目（免费版每天有 5 次交互机会），将其配置为自动同步到 GitHub。然后，你只需将仓库克隆到本地，用 Cursor 继续进行 AI 编码，最后再部署到 Render、Fly.io 或 CloudFlare 等平台。这种方式非常灵活，尤其适合那些后端逻辑比较复杂的项目。

如果你同时开发前端和后端，建议将它们放在同一个 Git 仓库下的不同目录中，或者分成两个独立的仓库，然后在 Cursor 中将它们添加到同一个工作区。这样，AI 代理就能在前后端之间自由引用文件。

为了避免过早地进行前后端集成，你可以指示 AI 代理先使用模拟（Mock）数据。等后端接口开发完毕后，再切换到真实数据。

另一个有用的技巧是，利用 MCP 工具将你的编码代理与 Playwright 或 Browser-use 等浏览器自动化工具集成。这样，AI 就能自己控制浏览器、抓取截图和错误信息，省去你手动复制粘贴的麻烦。

如果你想在 React 项目中使用 3D 内容，推荐使用 React Three Fiber (R3F)，而不是直接操作 three.js。R3F 将 three.js 的对象封装成了 React 组件，能让你更轻松地管理状态。

### 后端

像 Lovable 这样的 Web 工具在后端开发方面能力有限，所以你很可能需要求助于 Cursor、Windsurf 或 Aider 等本地工具。

**Python + FastAPI** 是一个绝佳组合。如果你希望前后端语言统一（假设前端是 JavaScript/TypeScript），那么 **Node.js + Express** 也是不错的选择。

后端是端到端测试的重点应用场景。你可以引导 AI 代理为每个新功能及其子任务编写并运行测试。

后端开发完成后，你可以将其 API 文档（尤其是 HTTP 端点说明）作为上下文提供给负责前端的 AI 代理，帮助它顺利地从模拟数据过渡到真实的后端数据。

### 游戏

对于小型游戏，可以考虑用原生 JavaScript，搭配 Three.js (3D) 或 PixiJS (2D)，并将所有代码放在单个 `.js` 文件中。

游戏开发离不开优质的资源。可以考虑使用 Tripo AI、Anything World 等服务来生成 3D 模型并完成绑定和动画制作。

## 如何处理错误和 Bug？

关于编码和软件，你必须接受一个事实：**总会出问题**。无论你如何预防，错误和 Bug 都在所难免。所以，让我们先学会和它们和平共处。

最直接的策略就是模仿人类开发者的做法：仔细阅读解释器或编译器抛出的错误信息，并尝试理解它。然后，把错误信息复制粘贴给 LLM，让它来修复。此外，引入像 [BrowserTools](https://browsertools.agentdesk.ai/) 这样强大的 MCP 调试工具也是个好主意。

## MCP、SLOP、A2A 都是些啥？我能用它们做什么？

**MCP** (Model Context Protocol) 是由 Anthropic 开发的一项协议，旨在标准化 LLM 与外部工具的交互，目前也开始受到 OpenAI 和 Google 的关注。它与“函数/工具调用”（Function/Tool Calling）的概念紧密相关。

**工具调用**允许 LLM 调用外部函数或工具来执行特定操作。这既能为 LLM（其知识截止于某个过去的时间点）提供最新信息，也能让它与外部世界（如数据库、软件）集成。例如，你可以告诉 LLM：“如果你需要搜索网页，就使用 `search(term)` 这个工具。” 这样，LLM 就能直接调用工具获取结果，而不是耗费大量 token 和计算资源去猜测或解析。

MCP 正是为这种交互提供了一套标准。通过 MCP，我们可以创建一个服务器，向 LLM 暴露特定的资源（如数据库）或工具（如一个计算程序）。

你可能会问：这不就是个 API 吗？用 REST API 也能实现吧？没错，这正是 **SLOP** (Simple Language Open Protocol) 的思路。然而，MCP 这样的标准能确保 LLM 原生支持这种交互，省去了客户端大量的解析和适配工作。

**A2A** (Agent to Agent Protocol) 则是这个领域的新玩家，由 Google 提出，作为 MCP 的补充。它更侧重于多代理之间的通信，而 MCP 专注于 LLM 与工具的通信。

> **重要提示**：目前市面上已经有不少优秀的 MCP 服务器，Cursor 等编辑器也提供了支持。但眼下只有 Anthropic 的 Claude 系列模型原生支持 MCP，所以如果你想使用相关工具，请确保选用 Claude 模型。

Anthropic 在这里维护了一份 MCP 服务器的更新列表：
https://github.com/modelcontextprotocol/servers

📚 **相关资源:**

- [MCP 官网](https://modelcontextprotocol.io/)
- [SLOP GitHub](https://github.com/agnt-gg/slop)
- [SLOP 介绍](https://russell.ballestrini.net/introducing-slop/)
- [MCP vs SLOP](https://mcpslop.com/)
- [A2A 官网](https://google.github.io/A2A/)

## 从零开始还是使用项目模板？

通常，LLM 在全新的项目上表现更好。但你也可以从一个**项目模板**（Boilerplate，即包含特定技术栈基本文件和配置的启动套件）开始。诀窍是在上下文窗口中添加规则，确保 AI 遵循模板的结构和约定。

另一个好方法是，在使用模板创建项目后，利用 Cursor 的索引功能，或 [repomix](https://repomix.com/)、[files-to-prompt](https://github.com/simonw/files-to-prompt) 等工具，将整个项目结构和内容提供给 AI。

## 全新项目 vs 已有代码库

如果你要在一个已有的代码库上工作，强烈建议使用 [repomix](https://repomix.com/) 或 [files-to-prompt](https://github.com/simonw/files-to-prompt) 等工具，将代码库的关键信息打包到 AI 的上下文窗口中。

另一个技巧是，**在任务层面而非项目层面进行提问**。例如，专注于你想要实现的某一个功能，为这个功能提供一个“迷你 PRD”，然后让 Cursor Agent 去实现它。想象一下，你正在指导一位初级开发者完成一个具体的开发任务 :-)

📚 **相关资源:**

- [Karpathy 关于他如何进行 AI 辅助编码的推文](https://x.com/karpathy/status/1915581920022585597)
- [如何在 Cursor 中处理大型代码库](https://docs.cursor.com/guides/advanced/large-codebases)

## 好的提示才能带来好的设计

截至 2025 年 4 月，LLM 已经很擅长生成能跑起来的代码，但在生成**结构清晰、层次分明**的代码方面，它们还差点火候。而良好的代码结构对于可读性、可维护性以及降低缺陷率至关重要。

因此，你需要先思考你的设计，然后通过一系列提示来引导 AI 生成具有良好结构的代码。例如，在一个以数据库为中心的应用中，最好先定义好数据模型（Record Types），然后引导 LLM 构建一个封装了数据访问逻辑的管理类或模块。在此之后，再开始编写业务逻辑。

更广泛地说，你在提问时，应该有意识地将**引擎代码**（通用逻辑）与**策略代码**（业务逻辑）分离，并通过提示的顺序来引导 LLM 遵循这一原则。

你还应该在项目规则中加入一条：**禁止破坏代码分层**。如果 AI 需要一个新的底层方法，它应该将其添加到干净的封装层中，而不是让低级实现细节与业务逻辑耦合在一起。

另一个有效的实践是，从项目的核心功能入手，花时间确保其实现方式和代码组织结构符合你的预期。你甚至可以先写好类和函数的“骨架”，然后让 LLM 来填充具体实现。只有在打下坚实的基础并配有良好测试之后，再着手开发上层应用，例如将其封装成 CLI 或为 Web 应用提供 REST API。

## 我应该写测试吗？比如 TDD？

**当然要！测试比以往任何时候都更加重要。** 在 2025 年，LLM 虽然能生成整洁、正确的代码，但它们偶尔会产生幻觉。更重要的是，它们可能会误解你的需求，然后生成一段“正确”实现“错误”功能”的代码。

即使未来我们拥有了通用人工智能（AGI），这种情况也不太可能改变——毕竟，人类也会误解需求！语言的模糊性决定了测试将永远是软件工程中不可或缺的一环。

**测试驱动开发（TDD）** 在这里尤其有用。通过编写测试用例，你可以为 AI 提供清晰的实现目标。指示 LLM 编写并运行测试也是一个绝佳的实践：它能将失败的测试作为上下文，并尝试修复代码以使测试通过。

测试是与 LLM 协同开发、保证代码库健康增长的基石。只有当所有测试都通过时，你才应该继续推进。

**基于属性的测试**（Property-based testing）在与 LLM 协作时也大放异彩。相比于只测试几个特定输入，它会测试整个输入范围，这有助于确保 AI 生成的代码在各种边缘情况下依然健壮。几乎所有主流语言都有优秀的属性测试库，例如 Python 的 [Hypothesis](https://hypothesis.readthedocs.io/en/latest/) 和 JavaScript/TypeScript 的 [fast-check](https://fast-check.dev/)。

最后，在审查 AI 编写或修复的测试时要留个心眼：它们有时会为了让测试通过而“作弊”，比如直接返回硬编码的结果 :-)

## 如何保证代码安全？

所有适用于传统软件开发的安全最佳实践，在这里**同样有效，甚至更为重要**。以下是一份基础安全自查清单：

- **不要盲信 AI 生成的代码，一定要亲自验证**。记住，AI 不会为你的代码负责，你才是最终责任人！
- **不要在代码中硬编码任何 API 密钥或敏感信息**，尤其是在前端代码里。应该将它们存储在后端的受保护环境变量中（Vercel 等平台都提供此功能）。
- **始终使用 HTTPS** 来请求 API 端点。
- **对用户输入进行严格的验证和清理**，尤其是在处理 HTML 表单时。
- **不要在 `localStorage`、`sessionStorage` 或 Cookie 中存储敏感数据**。
- **使用包管理器自带的工具或第三方服务，定期扫描项目依赖中的安全漏洞**。

## 如何在 Claude Code 中使用任何 LLM？

想在 Claude Code CLI 中体验一下 Kimi K2 或其他 LLM？你可以使用 `claude-code-router`。它会在你的本地启动一个“代理”，将 Claude Code 的请求转发到 OpenRouter 上的任何模型。以下以 Kimi K2 为例，你可以轻松地将其替换为任何其他模型。

首先，在 OpenRouter 注册并获取你的 API 密钥。

确保你已安装 Claude Code CLI：

```bash
npm install -g @anthropic-ai/claude-code
```

然后，安装 `claude-code-router`：

```bash
npm install -g @musistudio/claude-code-router
```

接着，编辑 `~/.claude-code-router/config.json` 文件，将 `OPENROUTER_API_KEY` 替换成你自己的密钥：

```json
{
  "Providers": [
    {
      "name": "kimi-k2",
      "api_base_url": "https://openrouter.ai/api/v1/chat/completions",
      "api_key": "OPENROUTER_API_KEY",
      "models": [
        "moonshotai/kimi-k2"
      ],
      "transformer": {
        "use": ["openrouter"]
      }
    }
  ],
  "Router": {
    "default": "kimi-k2,moonshotai/kimi-k2"
  }
}
```

现在，通过路由器启动 Claude Code：

```bash
ccr code
```

如果你看到 `API Base URL: http://127.0.0.1:3456` 的输出，就说明它成功用上了本地代理。大功告成！

如果你只对 Kimi K2 或其他 Moonshot 模型感兴趣，也可以直接使用 Moonshot 官方提供的适配方案：
https://github.com/LLM-Red-Team/kimi-cc/blob/main/README_EN.md

## 如何创建自己的 AI 编码代理？

我们正在编写相关教程，敬请期待。目前，最好的入门材料是 Thorsten 写的[这篇实战教程](https://ampcode.com/how-to-build-an-agent)，它会带你用 Go 语言，一步步构建一个只使用 `list_files`、`read_file`、`edit_file` 三个基础工具的简单代理。

如果你想深入研究，Gerred 写的[这个开源系列书籍](https://gerred.github.io/building-an-agentic-system)绝对是一个绝佳的起点。

# ✨ 特定工具和代理的技巧

## Claude Code

- [Claude Code 指南](https://github.com/zebbern/claude-code-guide): 涵盖了所有已知的 Claude Code 命令，包括许多在基础教程中未被提及的隐藏功能。

# 🛠️ 工具

我们在此维护一份 AI 编码领域主流工具的列表，并附上我们基于实际测试的真实看法。

## 编辑器 / IDE

- [Cursor](https://cursor.com)
- [Windsurf](https://windsurf.com)
- [Cline](https://cline.bot/)
- [OpenHands](https://github.com/All-Hands-AI/OpenHands)
- [Devin](https://devin.ai)
- [VSCode + GitHub Copilot](https://code.visualstudio.com/docs/copilot/setup)
- [Amp](https://ampcode.com)
- [Kiro](https://kiro.dev)

## 命令行工具 (CLI)

- [Claude Code](https://github.com/anthropics/claude-code)
- [Aider](http://aider.chat/)
- [Claude Engineer](https://github.com/Doriandarko/claude-engineer)
- [Roo Code](https://github.com/RooVetGit/Roo-Code)
- [OpenAI Codex CLI](https://github.com/openai/codex)
- [Codebuff](https://www.codebuff.com/)
- [opencode](https://github.com/opencode-ai/opencode)
- [Gemini CLI](https://github.com/google-gemini/gemini-cli)

## Web 应用

- [Bolt](https://bolt.new)
- [v0](https://v0.dev)
- [Replit](https://replit.com)
- [Lovable](https://lovable.dev)
- [Firebase Studio](https://firebase.studio/)

## 后台/远程代理

- [ZenCoder](https://zencoder.ai/)
- [CodeRabbit](https://www.coderabbit.ai/)
- [Factory AI](https://www.factory.ai/)
- [OpenAI Codex](https://chatgpt.com/codex)

## 辅助工具

- [Specstory](https://specstory.com/)
- [Claude Task master](https://github.com/eyaltoledano/claude-task-master)
- [CodeGuide](https://www.codeguide.dev/)
- [repomix](https://repomix.com/)
- [files-to-prompt](https://github.com/simonw/files-to-prompt)
- [repo2txt](https://github.com/donoceidon/repo2txt)
- [stakgraph](https://github.com/stakwork/stakgraph)
- [Repo Prompt](https://repoprompt.com/)
- [Uzi](http://uzi.sh/)
- [Claudia](https://claudia.asterisk.so/)

# 🤗 值得关注的大佬

以下是一些在 AI 编码领域进行探索和创造的先行者，值得关注。

- [Addy Osmani](https://x.com/addyosmani)
- [Andrej Karpathy](https://x.com/karpathy)
- [Beyang Liu](https://x.com/beyang) (Amp)
- [Cat Wu](https://x.com/_catwu) (Claude Code)
- [Eric S. Raymond](https://x.com/esrtweet)
- [Eyal Toledano](https://x.com/EyalToledano) (TaskMaster)
- [Geoffrey Huntley](https://x.com/GeoffreyHuntley)
- [Gerred Dillon](https://x.com/devgerred)
- [Harper Reed](https://x.com/harper)
- [Nathan Wilbanks](https://x.com/NathanWilbanks_) (agnt, SLOP)
- [Pietro Schirano](https://x.com/skirano)
- [Quinn Slack](https://x.com/sqs) (Amp)
- [Sandeep Pani](https://x.com/skcd42) (Aider, AgentFarm)
- [Simon Willison](https://x.com/simonw)
- [Vilson Vieira](https://x.com/aut0mata)
- [Thorsten Ball](https://x.com/thorstenball) (Amp)
- [Xingyao Wang](https://x.com/xingyaow_) (OpenHands, AllHands)

# 💖 致谢

本指南的创作灵感来源于 Maxime Labonne 的优秀课程 [llm-course](https://github.com/mlabonne/llm-course)。

特别感谢：

- [Gabriela Thumé](https://github.com/gabithume) ❤️
- [Albert Espín](https://github.com/albert-espin) 提供了深刻的反馈和初版校对。
- [Geoffrey Huntley](https://x.com/GeoffreyHuntley) 启发了我对基于属性测试的思考，并贡献了大量关于自主代理的精彩教程和实验。
- ChatGPT 4o 生成了顶部的横幅图片，其灵感来自杰出艺术家 [Deathburger](https://citadel9.com/)。

# ⭐ 贡献

如果你希望贡献内容、订正错误，或是补充遗漏的工具和参考资料，欢迎随时提交 PR 或 Issue，或直接与 [Eric](https://x.com/esrtweet) 或 [Vilson](https://x.com/aut0mata) 联系。

如果你喜欢本指南，请给它一个 Star ⭐ 并保持关注，获取最新动态！

# ⚖️ 许可证

MIT