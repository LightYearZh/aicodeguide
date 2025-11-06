<div align="center">
  <img src="https://i.imgur.com/v0Tx6am.png" alt="AI 编码指南" />
  <p align="center">
    作者 <a href="https://x.com/aut0mata">Vilson Vieira</a> 和
       <a href="https://x.com/esrtweet">Eric S. Raymond</a>
  </p>
  <a href="https://discord.gg/NrDfXmtvw3">
     <img src="https://i.imgur.com/uqKVFHj.png" alt="加入我们的 Discord" height="48" />
  </a>
</div>
<br/>

> 您想知道的有关使用 AI 帮助您编码和/或为您编码的所有信息。

<div align="center" style="font-size: 30px">
  <a href="#vibe">太长不看，直接告诉我如何进行“氛围编程” 😎！</a>
</div>
<br /><br />

## 引言

我们与计算机交互并为其编写代码的方式正在发生变化。这是一种深刻的变化：体现在我们使用的工具、我们编码和思考软件产品和系统的方式上。

而且它变化得超快！每周都有新的 LLM 模型发布。新的工具、新的编辑器、新的“氛围编程”实践、新的协议、MCP、A2A、SLOP……要跟上所有这些真的很难。所有东西都分散在不同的地方、网站、代码仓库、YouTube 视频等。

这就是我们决定编写本指南的原因。这是我们谦虚的尝试，旨在将所有内容整合在一起，以一种无障碍、易于理解的形式，向您呈现围绕 **AI 编码** 或 **AI 辅助代码生成** 的实践和工具。

- **如果您是程序员但尚未使用 AI 代码助手**，本指南适合您：它介绍了最新的工具和良好实践，以充分利用它们来帮助您的日常工作。无论是让 AI 成为您的副驾驶，还是成为 AI 代理的副驾驶。

- **如果您以前从未编码过，但对这种新的“氛围编程”感兴趣，想用它来构建自己的 SaaS 和其他软件产品**，本指南绝对适合您：我们将尽力消除晦涩难懂之处，只为您保留开始旅程所必需的内容，同时对什么是真正重要的，什么是“纯属炒作”保持批判性思考。

酷，让我们开始吧！

📚 资源：

- [我们所知的编程的终结](https://www.oreilly.com/radar/the-end-of-programming-as-we-know-it) by Tim O'Reilly
- [如何为开发的未来和 AI 做准备](https://www.youtube.com/watch?v=BP54GqVK3JA) by Santiago
- [初级开发人员的复仇](https://sourcegraph.com/blog/revenge-of-the-junior-developer) by Steve Yegge
- [亲爱的学生：是的，AI 来了，除非你采取行动，否则你就完蛋了...](https://ghuntley.com/screwed/) by Geoffrey Huntley
- [如何构建一个代理](https://ampcode.com/how-to-build-an-agent) by Thorsten Ball
- [使用 LLM 进行编码](https://simonwillison.net/2025/Mar/11/using-llms-for-code/) by Simon Willison
- [70% 的问题：关于 AI 辅助编码的残酷事实](https://addyo.substack.com/p/the-70-problem-hard-truths-about) by Addy Osmani
- [成为一名 AI 增强工程师](https://maryrosecook.com/blog/post/become-an-ai-augmented-engineer) by Mary Rose Cook
- [养育一个代理播客](https://ampcode.com/podcast) by Amp 团队
- [软件正在（再次）改变](https://www.youtube.com/watch?v=LCEmiRjPEtQ) by Andrej Karpathy

## AI 编码？氛围编程？

所有这些术语都非常相似。但基本上，AI 编码是关于使用 AI 模型（特别是如今的 LLM）以及围绕它的所有工具来帮助您编写软件。它也被称为“AI 代码生成”或简称“code gen”，这是一个可以追溯到 1950 年代我们使用 Lisp 生成代码的迷人研究和工程领域。现在我们有 LLM 作为驱动代码生成的主要引擎，并且也开始出现一些关于神经符号混合方法的线索。AI 编码也是一种实践：如果您正在使用 Cursor 并通过 tab-tab-tab 来获得补全，您就在“AI 编码”；如果您完全使用 Cursor 的代理模式，您也在“AI 编码”。总而言之：它是使用 AI 模型帮助您生成代码的任何方式。通常这个群体里的人已经知道如何编码。

氛围编程是 AI 编码的升级版 :-) 在这里，您不太关心生成的代码，您只是给出一个提示，并期望 AI 为您编写所有代码。这个术语是 [Karpathy 在 2025 年创造的](https://x.com/karpathy/status/1886192184808149383)，并且正变得非常流行。在我看来，它正在帮助那些以前从未想过编码的人实现编码的民主化！

所以，总而言之，无论您是使用 AI 来讨论您的软件想法，还是帮助您编写现有代码库的一部分，或者您完全在进行氛围编程，您都在使用 AI 来帮助您生成代码。让我们称之为 AI 编码，然后继续。

## 我该如何使用它？

您可以通过多种不同方式使用 AI 编码，但总的来说：

- AI 是您的副驾驶：您使用 AI 模型来增强自己，提高您的生产力。无论是启动 ChatGPT 帮助您头脑风暴 SaaS 的想法；还是使用 Cursor 自动完成您的文档字符串。这里有很多好处，特别是在创造性探索和自动化您工作中的无聊部分方面。

- AI 是主驾驶：在这里您是副驾驶。这就是“氛围编程”发生的地方。您打开 Cursor Agent 的 YOLO 模式，并相信代理们为您生成代码所做的一切。这是一种非常强大的自动化方式，但需要一些关于如何设计系统、驾驭代理以及在您不了解的混乱代码中解决错误的良好实践。

您应该学习并实践这两种方式！

但随着项目复杂性的增加，应更多地倾向于副驾驶模式，远离纯粹的 YOLO 氛围编程。另一个（或六个月后的您自己）需要维护代码的可能性越大，这一点就越重要。

# 🗺️ 路线图

## 我该如何开始？

- 如果您不知道如何编码并想尝试一下，我们建议从一些基于 Web 的工具开始，如 [Bolt](https://bolt.new)、[Replit](https://replit.com)、[v0](https://v0.dev) 或 [Lovable](https://lovable.dev)。

- 如果您已经知道如何编码，请安装 [Cursor](https://cursor.com/) 或 [Windsurf](https://windsurf.com/)。您可以从免费计划开始，然后升级到每月 20 美元的计划。Cursor 非常好用且便宜，因为您将有大量的 token 可用于最新的 LLM 模型。VSCode 最近也推出了自己的[代理模式](https://code.visualstudio.com/blogs/2025/02/24/introducing-copilot-agent-mode)。它与 Github Copilot 配对，并使用代理工作流来进行更改和编辑文件。其他编辑器也在迅速增加代理功能，所以请查看您最喜欢的编辑器的网站以获取更多信息。这些代理功能通常只在 Beta 或 Insider 版本中启用。

- 如果您想要一个更开源的替代方案，可以试试 [OpenHands](https://github.com/All-Hands-AI/OpenHands)。您将它作为一个暴露 webapp 的 Docker 容器来运行。您需要创建一个 [Anthropic API 账户](https://console.anthropic.com/) 来获取 API 密钥，或者使用 [OpenRouter](https://openrouter.ai/) 上可用的某些 LLM。

- 如果您已经知道如何编码并且像我们一样是终端狂人，请查看 [aider](https://aider.chat/)、[Claude Code](https://docs.anthropic.com/en/docs/agents-and-tools/claude-code/overview) 或 [OpenAI Codex](https://github.com/openai/codex)。对于这些，您需要为 Anthropic Claude、OpenAI GPT 或 OpenRouter 设置 API 密钥。

- 如果您已经知道如何编码，既喜欢终端又喜欢 VSCode 的风格，并且真的想体验让子代理为您并行运行的强大功能，并且不关心成本只关心完成任务，可以试试 [Amp](https://ampcode.com)。

> 建议：我们真的建议在 OpenRouter 创建一个账户。这真的很容易，您将可以访问最新的 LLM 模型，甚至是它们的免费版本。例如，我们现在首选的 LLM 模型是 Gemini 2.5 Pro，并且可以通过 OpenRouter 免费运行它（有每日信用额度，但对于使用 aider 和 OpenHands 进行实验来说，这仍然是一个有趣的选择）。

> 重要提示：Claude Code 现在非常昂贵！您每天可以轻松花费 50 美元。所以要小心，监控您的使用情况。这就是为什么建议从 Cursor 开始，这样您就不必担心这个问题。

📚 资源：

- [使用 Replit 进行氛围编程 101](https://www.deeplearning.ai/short-courses/vibe-coding-101-with-replit/)
- [Cursor AI 初学者教程 [2025 版]](https://www.youtube.com/watch?v=3289vhOUdKA)

## 我该如何为编码提问？也就是我该如何进行氛围编程？<a id='vibe'></a>

在您安装并使用这些工具一段时间后，您会注意到它们会产生幻觉，进入试图修复一个可能错误的无限循环等。知道如何很好地提问很重要。一些技巧：

- 不要在一次提示中问所有事情。仅仅提示“嘿，给我建一个我的宠物店的应用程序”对软件工程师没有帮助，对 AI 更没有帮助 :-) 理解您的项目，首先与 LLM 进行头脑风暴，创建一个 PRD（产品需求文档），制定一个计划并将其分解为任务。您将在下面找到一个如何使用 ChatGPT 为您创建一个的秘诀。
- 给出细节。如果您知道您想要什么，就说出来。如果您知道您想要哪种编程语言、哪种技术栈、什么样的受众，就把它添加到您的提示中。
- Markdown 或任何其他轻量级的基于文本的格式，如 asciidoc，对于 LLM 来说应该是可以解释的。最终文本将被编码为 token。然而，为了强调您提示的特定部分，建议使用一些符号，如 [XML 标签](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/use-xml-tags)。
- 将您的项目分解为任务和子任务。
- 针对不同目标尝试不同模型。
- 尝试不同模型来确认和验证其他模型的输出。
- LLM 是“应声虫”，所以要运用批判性思维。

在我们其余的例子中，我们将使用与 Markdown 关联的 .md 文件扩展名。如果您更喜欢 asciidoc（它对结构化文档的支持稍好），请使用它并在这些说明中用“.adoc”替换。LLM 不在乎，它们会处理您扔给它们的 Markdown、asciidoc 或任何其他纯文本格式。

这里有一个通常效果很好的方法/程序/策略/工作流：

1. 使用 `ChatGPT 4.5`、`4o` 或 `o3` 并使用以下提示：

```
您是一名高级软件工程师。我们将一起构建一个项目的 PRD。

非常重要：
- 一次只问一个问题
- 每个问题都应基于之前的答案
- 深入探讨所需的每个重要细节

想法：
<在此处粘贴您的想法>
```

2. 您将进入一个几分钟的问答循环。尽量用尽可能多的细节回答。完成后（或者当您决定足够了），发送此提示以指导模型将其编译为 PRD：

```
将这些发现编译成一个 PRD。使用 markdown 格式。它应包含以下部分：

- 项目概述
- 核心需求
- 核心功能
- 核心组件
- 应用/用户流程
- 技术栈
- 实施计划
```

3. 将此文件复制并保存到您项目文件夹内的 `docs/specs.md` 中
4. 现在让我们为您的项目创建任务列表。询问以下内容：
```
根据生成的 PRD，创建一个详细的、分步的计划来构建这个项目。
然后将其分解为相互依赖的小任务。
根据这些任务，将它们分解为更小的子任务。
确保步骤足够小，可以在一个步骤中实现，但又足够大，可以成功完成项目。
使用软件开发和项目管理的最佳实践，不要有大的复杂性跳跃。将任务连接到其他任务，创建一个依赖列表。不应该有孤立的任务。

非常重要：
- 使用 markdown 或 asciidoc
- 每个任务和子任务都应该是一个清单项
- 为每个任务提供足够的上下文，以便开发人员能够实现它
- 每个任务都应该有一个数字 ID
- 每个任务都应该列出依赖的任务 ID
```
5. 将此保存为项目文件夹内的 `docs/todo.md`

[这是一个例子](https://chatgpt.com/share/67f8e8c6-c92c-8007-8fe0-76bdc73f9812)
一个使用 ChatGPT 4o 为一个简单的 CLI 工具进行的头脑风暴/规划会议，用它作为您的灵感。

现在为您的项目创建一个本地文件夹，记得在文件夹内安装并运行 `git init` 以将其置于版本控制之下。

这应该会给您提供构建项目所需的 PRD 和任务列表！有了这些，您就可以打开您的 Cursor（或其他 AI 代码编辑器），将它指向这些文件并询问：

```
您是一名高级软件工程师。研究 @docs/specs.md 并实现 @docs/todo.md 中仍然缺失的内容。每次实现一个任务，并尊重任务和子任务的依赖关系。完成一个任务后，在列表中勾选它，然后继续下一个。
```

在 Cursor Agent 第一次执行命令时启用 YOLO 模式，然后在提示中不断接受或询问 `continue`。

在使用 Cursor 的情况下，有时 LLM 会达到某些限制并要求重试。只需这样做并继续。是的，您正在进行氛围编程 :-)

在这里，您会找到一个基于此工作流在 10 分钟内构建的 CLI 工具的 Git 仓库：https://github.com/automata/localbiz

> 重要提示：虽然“氛围编程”非常酷，但了解您正在做什么也同样非常有趣 :-) 回顾代理生成的代码也会在您遇到错误时（它们会的！）帮助您很多，并提高您的代码审查技能（不仅是 AI 制作的，还有您自己和其他开发人员制作的）。

📚 资源：

- [您正在错误地使用 Cursor AI...](https://ghuntley.com/stdlib/) by Geoffrey Huntley:
在这里 Geoff 介绍了他使用 Cursor 规则标准库的想法
- [从设计文档到代码：Groundhog AI 编码助手（以及新的 Cursor 氛围编程元）](https://ghuntley.com/specs/) by Geoffrey Huntley:
前一篇文章的第 2 部分，其中 Geoff 建议使用 LLM 自动构建规范（PRD）和 Cursor 规则
- [我目前的 LLM 代码生成工作流](https://harper.blog/2025/02/16/my-llm-codegen-workflow-atm/) by Harper Reed
- [一个 LLM 代码生成英雄的旅程](https://harper.blog/2025/04/17/an-llm-codegen-heros-journey/) by Harper Reed
- [Claude Code：代理编码的最佳实践](https://www.anthropic.com/engineering/claude-code-best-practices) by Anthropic: 这是针对他们的 Claude Code 工具的，但它有关于基于任何 LLM 模型的 AI 编码工作流的有趣技巧
- [提示工程](https://www.kaggle.com/whitepaper-prompt-engineering) by Lee Boonstra from Google: 这是一份 70 页的文档，其中包含有关如何进行提示工程的有趣技巧，其中有一节是关于代码生成的
- [提示工程指南](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering) by Anthropic
- [GPT 4.1 提示指南](https://cookbook.openai.com/examples/gpt4-1_prompting_guide) by OpenAI
- [RepoPrompt](https://repoprompt.com/) 是一个帮助从您的项目中收集上下文的工具。值得观看一个 [RepoPrompt 工作流](https://www.youtube.com/watch?v=fm3VreCt-5E) 的概述视频，以学习如何轻松利用这些工具在您的氛围编程提示中提供更多上下文。
- [并非所有 AI 辅助编程都是氛围编程（但氛围编程很酷）](https://simonwillison.net/2025/Mar/19/vibe-coding/) by Simon Willison

## 我应该使用哪个 LLM 模型？

LLM 经过训练和微调以实现不同目标，这里有一个您可能有的目标/用途以及使用哪个模型的综合列表：

| 目标 | 模型 |
|----------------------|---------------------------------------------------------------|
| 头脑风暴 | GPT 5, 4o, o3, Grok |
| 编码 | Claude Sonnet 4, Gemini 2.5 Pro, Grok, GPT 5, o3, o4-mini |

鉴于 LLM 每天都在变化，这个表格很快就会过时。请查看以下排行榜以获得更准确的比较：

- [OpenRouter 的模型](https://openrouter.ai/models?categories=programming&fmt=table): 将类别设置为 `programming` 并只过滤支持 `tools` 的模型通常是选择用于 AI 辅助编码模型的好方法
- [Models.dev](https://models.dev): 一个 AI 模型的开源数据库
- [代理排行榜](https://huggingface.co/spaces/galileo-ai/agent-leaderboard)

## 当可怕的“速率限制”消息出现时该怎么办

切换到不同的模型。

这种情况至少有两个不同的原因。您可能会发出一个超出模型输入/输出 token 限制的繁重请求。或者，如果它运行的服务器集群今天状态不佳，您可能会被限流以减少负载。您收到的错误消息通常对此并不透明。您可以在[这里](https://platform.openai.com/docs/guides/rate-limits)找到更详细的解释。

不同的模型有非常不同的 token 限制。例如，在我写这篇文章的 2025 年 4 月下旬，gpt-4.1-mini 比 gpt-4.1 慷慨得多。口袋里准备好几个 API 密钥（这很便宜，因为您是按需付费），并访问描述速率限制的页面。
这里是 [Anthropic 的](https://console.anthropic.com/settings/limits) 例子。

## 我如何设置项目范围的规则？

您可以通过将规则或约定“注入”到 LLM 的上下文中来定义它们。每个编辑器都有一些方法可以做到这一点：

- 在 Cursor 中，只需在 `.cursor/rules/` 文件夹内创建 markdown 文件。Cursor 将确保在与 LLM 的所有通信中应用这些规则。
- 在 Aider 中，创建包含您想要使用的[规则/约定](https://aider.chat/docs/usage/conventions.html)的 markdown 文件（如 `rules.md`），并在您的 `.aider.conf.yml` 文件中添加以下内容：`read: rules.md`。

此外，许多工具支持在您的主目录中配置文件/约定文件，以应用于您的所有项目。例如，在 Aider 中，您基本上可以在一个名为 `~/.global_conventions.md` 的文件中添加全局约定，然后将其添加到 `.aider.conf.yml` 中，`read: [~/.global_conventions.md, rules.md]`。

您可以将 PRD 的一部分作为规则添加，例如技术栈或关于代码格式和风格的一些指南。

规则非常强大，您甚至可以使用 AI 本身为 您创建规则！[查看 Geoff 关于此的方法](https://ghuntley.com/specs/)。

📚 资源：

- [Cursor 规则文档](https://docs.cursor.com/context/rules-for-ai)
- [Windsurf 规则文档](https://windsurf.com/editor/directory)
- [Aider 约定文档](https://aider.chat/docs/usage/conventions.html)
- [Aider 约定集合](https://github.com/Aider-AI/conventions): 一个社区贡献的约定文件集合，用于 Aider。
- [很棒的 Cursor 规则](https://github.com/PatrickJS/awesome-cursorrules): 一个精选的
  很棒的 .cursorrules 文件列表，用于增强您的 Cursor AI 体验。

## 我如何避免幻觉？什么是 PRD？

PRD。什么？！他们说解决工程问题的最好方法是创建一个新的首字母缩写词，这里也不例外 :-) 开个玩笑... PRD 是产品需求文档（Product Requirements Document）的缩写。基本上，它只是一堆描述您的软件项目需求和其他细节的文档（或只有一个文档）。

事实证明，如果您让您的亲爱的 LLM 自由发挥，没有太多关于做什么的上下文，它会很快产生非常疯狂的幻觉。您需要驯服这头野兽，而 PRD 是一个很好的方法。

我最喜欢 PRD 的地方在于它们对任何人都有帮助，从从未编码过的人到高级软件工程师或产品经理。

您不需要任何背景就可以开始一个 PRD，您只需要您的应用程序的想法，就是这样。

查看<a href="#vibe">这里</a>如何使用 LLM 为您创建一个。

## 保留提示日志

记录您发送的每个提示，并（这很重要）穿插您对当时想法和遇到的任何意外的评论。这个提示日志是您设计意图的记录；对于任何没有参与过项目的人来说，它都将是无价之宝，包括六个月后忘记了自己当时想法的您。

这个文件还没有命名约定，您可以使用像 `vibecode.adoc` 或 `history.md` 这样的东西。

有些工具，比如 [aider](https://aider.chat/)，会记录您与 LLM 的所有来回聊天记录。
所以一个选择是设置以下环境变量，并将所有这些历史文件置于版本控制之下：

```bash
# 历史文件：

## 指定聊天输入历史文件（默认：.aider.input.history）
#AIDER_INPUT_HISTORY_FILE=.aider.input.history

## 指定聊天历史文件（默认：.aider.chat.history.md）
#AIDER_CHAT_HISTORY_FILE=.aider.chat.history.md

## 将与 LLM 的对话记录到此文件（例如，.aider.llm.history）
#AIDER_LLM_HISTORY_FILE=.aider.llm.history
```

有了这些文件，您就可以在进行过程中用自己的想法对它们进行评论。
当您将来重新审视您的项目时，您（和其他人）可以学到很多关于您的项目的东西，并且
您可能会开始注意到可以在下一次会话中使用的模式和技巧。

## 我该如何开始我的项目？

### Web 应用（前端）

现代 Web 开发非常令人不知所措。有大量的 JavaScript/TypeScript 框架、CSS 框架等，所以开始并考虑使用哪一个真的很难。在过去几周构建前端之后，我最终使用了这些：

- Next.js，这样您就可以部署到 Vercel 并拥抱他们的生态系统（可能会很快变得昂贵）
- Vanilla React 并使用 React Router，这样您就可以部署到任何地方
- Remix，这样您就可以有很好的路由支持并且仍然可以部署到任何地方
- FastHTML，如果您喜欢 Python 并且更关心暴露核心后端功能（例如一些数据分析或 AI/ML 模型管道）而不是非常漂亮的 UI

像 Lovable 这样的基于 Web 的 AI 编码平台使用 React，而 v0 使用 Next.js。

您可以使用的一个技巧是在 Lovable 开始您的项目（您可以在他们的免费计划中每天获得最多 5 条消息），将其设置为将您的项目输出到 GitHub，然后只需在您的本地机器上克隆它，并使用 Cursor 继续对其进行 AI 编码。然后您可以将其部署到像 Render、Fly.io、CloudFlare 等地方。没有任何附加条件。特别是如果您在后端有特定/更复杂的例程，这会很有趣。

如果您也在编写后端代码，请确保在您的 Git 仓库的根文件夹中有一个用于后端的文件夹和另一个用于前端的文件夹；或者为后端和前端设置不同的仓库，然后将它们添加到 Cursor 的同一个工作区中（这样您就可以在您的前端代理中引用后端的文件，反之亦然）。

为了避免过早地将前端集成到后端，请指示 AI 代理使用模拟/虚拟数据，这样您就可以在实现后端后稍后更新它。

另一个有趣的技巧是使用好的 MCP 工具将您的编码代理与 playwright 或 browser-use 集成。这样您就可以避免从 Web 浏览器到您的 AI 代理的复制粘贴错误循环，因为 AI 将控制浏览器并自行抓取屏幕截图和错误消息。

如果您想在您的 Web 应用中使用 3D 内容并且您正在使用 React，那么使用 React Three Fiber 而不是尝试直接使用 three.js 库会很有趣。R3F 使处理状态变得更容易，因为它将所有 three.js 对象包装为 React 组件。

### 后端

像 Lovable 这样的 Web 工具在后端方面做得不好。所以您可能需要使用 Cursor/Windsurf/aider 或任何其他非基于 Web 的工具。

使用 Python 和 FastAPI 是一个很好的选择。如果您更喜欢使用与前端相同的语言（猜测大多数时候会是 JavaScript 或 TypeScript），您可以使用 Nodejs 和 Express。

后端是端到端测试的绝佳目标，因此请考虑指导代理为每个新功能及其子任务编写测试并运行它们。

完成后端后，您可以将其文档（特别是关于 HTTP 端点的）作为在前端工作的代理的输入。这样，您就可以将前端从使用模拟/虚拟数据转移到使用来自后端的真实数据。

### 游戏

对于小型游戏，在单个 .js 文件中使用原生 JS，并使用 threejs 进行 3D 游戏或 pixijs 进行 2D 游戏。

游戏的关键在于好的资产，所以可以考虑使用像 Tripo AI 和 Anything World 这样的服务来生成 3D 资产并对其进行绑定/动画处理。

## 我该如何处理错误和 bug？

关于编码和软件，您必须知道一件事：它们会失败。无论您如何尝试阻止，它都会发生。所以让我们首先接受这一点，并与错误和 bug 成为朋友。

这里的第一个策略是模仿软件工程师的做法：查看解释器/编译器给您的错误消息并尝试理解它。将错误复制并粘贴回 LLM 并要求它修复它。另一个好主意是添加像 [BrowserTools](https://browsertools.agentdesk.ai/) 这样非常适合调试的 MCP 工具。

## 什么是 MCP、SLOP 和 A2A，我如何从中受益？

MCP 是模型上下文协议（Model Context Protocol）的缩写。它由 Anthropic 开发，但正开始被其他 LLM（如 OpenAI 的 GPT 和 Google 的 Gemini）考虑。这是一个强大的概念，并且与另一个概念紧密相连：函数/工具调用。

工具调用是 LLM 调用工具或函数来执行某些操作的一种方式。这是一种用新信息更新 LLM（在过去的数据上训练的）知识窗口的方式，同时将其与外部工具和端点集成。例如，如果您想在网上搜索一些信息，您可以指示 LLM 使用一个可以做到这一点的工具（例如 `嘿，如果您需要在网上搜索什么，请使用这个工具：search(term)`）。然后，LLM 将调用该工具，获取输出，并在为您生成新预测时使用它，而不是花费许多 token、迭代步骤和解析工作量。

MCP 通过为此创建一个标准来扩展这个想法。这样我们就可以创建一个 MCP 服务器，它将向 LLM 公开一些资源（例如数据库）或工具（例如一个将计算某些东西并返回结果的特定软件）。

等等，但这不就是一个 API 吗？我不能用 REST API 服务器/客户端和 LLM 提示中的一些解析来模仿同样的事情吗？有点像，这就是 SLOP（简单语言开放协议）所提议的。然而，拥有像 MCP 这样的标准可以更容易地确保 LLM 将原生支持它，而无需在客户端进行额外的解析和技巧。

A2A（代理到代理协议）在这个领域还很新。它由 Google 创建，以“补充”MCP，专注于多代理通信，而 MCP 则专注于 LLM-工具通信。

> 重要提示：有很多好的 MCP 服务器，像 Cursor 这样的编辑器也支持它们。目前，只有 Anthropic Claude LLM 支持它们，所以当您想要使用 MCP 工具时，请确保使用 Claude。

Anthropic 在这里维护一个更新的 MCP 服务器列表：
https://github.com/modelcontextprotocol/servers 

📚 资源：

- [MCP](https://modelcontextprotocol.io/)
- [SLOP](https://github.com/agnt-gg/slop)
- [介绍 SLOP](https://russell.ballestrini.net/introducing-slop/)
- [MCP vs SLOP](https://mcpslop.com/)
- [A2A](https://google.github.io/A2A/)

## 从头开始还是使用样板？

通常 LLM 从头开始做得更好。但您也可以从一个样板开始（基本上是一个入门工具包：一个包含启动一个特定技术栈工作项目所需的最小源文件和配置的初始骨架的文件夹），并在上下文窗口中添加规则，以确保它会尊重您的入门工具包。

另一个好主意是使用 Cursor 自己的索引功能来索引您的项目（您刚刚用入门工具包创建的），或者使用像 [repomix](https://repomix.com/) 或 [files-to-prompt](https://github.com/simonw/files-to-prompt) 这样的工具。

## 绿地/全新状态/新项目 vs 现有代码库

如果您有一个现有的代码库，一个好主意是使用 [repomix](https://repomix.com/) 或 [files-to-prompt](https://github.com/simonw/files-to-prompt) 将其打包到上下文窗口中。

另一个很棒的技巧是在任务级别而不是项目级别提示更改。例如，专注于您想要实现的一个功能，并要求 Cursor Agent 实现它。为该特定功能提供一个迷你 PRD。想象一下，您正在指导一个初级开发人员在一个特定的 GH 工单上工作 :-)

📚 资源：

- [Karpathy 关于他使用 AI 辅助编码方式的推文](https://x.com/karpathy/status/1915581920022585597)
- [如何在 Cursor 中处理大型代码库](https://docs.cursor.com/guides/advanced/large-codebases)

## 结构良好的提示，用于结构良好的设计

目前（2025 年 4 月），LLM 已经擅长生成可工作的代码，但它们在生成结构良好的代码方面还不是很好——也就是说，具有适当的分层和关注点分离。良好的结构对于可读性和可维护性很重要，并能降低您的缺陷率。

仔细考虑您的设计，然后以一种能够产生良好结构的顺序进行提示工程。例如，在以数据库为中心的应用程序中，一个好主意是首先指定您的记录类型，然后引导您的 LLM 构建一个封装对它们访问的管理类或模块。只有在那之后，您才应该开始提示业务逻辑。

更一般地说，当您提示时，要考虑将引擎代码与策略代码分开，并按顺序发出您的提示，以引导 LLM 这样做。

您应该在您的项目规则中包含一条，告诉 LLM 不要违反分层——如果它需要一个新的引擎方法，它应该向一个干净的封装层添加一些东西，而不是让低级实现细节与业务逻辑纠缠在一起。

另一个有趣的实践是从您的项目核心开始，花时间确保主要功能以您想要的方式实现和组织。您甚至可以编写类和函数的骨架，然后让 LLM 填补空白。只有在您拥有一个良好的基础并且有良好的测试之后，您才能转向这个核心库的消费者，比如将其作为 CLI 或 REST API 暴露给未来的 Web 应用。

## 我应该使用 TDD 或任何其他类型的测试吗？

是的，测试比以往任何时候都更重要。在 2025 年的当前技术水平下，LLM 擅长生成干净和正确的代码，但它们有时会产生幻觉——更重要的是，它们可能无法理解规范并生成正确的代码来做错误的事情。

即使我们获得了完全等同于人类的人工通用智能，这种情况也不太可能改变——毕竟，人类也会误解规范！语言的模糊性是为什么即使在未来，测试仍将继续重要的原因。

使用 TDD 创建您想要的结果的骨架，可以真正帮助引导 LLM 实现您正在测试的目标代码。指示您的 LLM 创建测试并运行它们也是一个很好的实践：它将能够将破坏给定测试的可能错误添加到其上下文中并对其采取行动，试图使测试通过。

测试对于与 LLM 一起发展您的代码库至关重要，只有在所有当前测试都通过时才能继续前进。

与 LLM 一起工作时，基于属性的测试非常有趣。测试整个值域/范围，而不仅仅是您指定的特定值，将有助于确保代理生成的代码即使在后续更改最终触及您没有预先想到的边缘情况时仍然有效。每种语言都有很好的基于属性的测试库，比如 Python 的 [hypothesis](https://hypothesis.readthedocs.io/en/latest/) 或 JavaScript/TypeScript 的 [fast-check](https://fast-check.dev/)。

在尝试编写或修复测试时，始终检查 LLM 生成的代码也很重要：有时它们甚至会尝试生成一些硬编码的输出来使测试通过 :-)

## 如何确保安全？

对于非 AI 辅助编码所建议的完全相同的规则和最佳实践在这里同样有效。研究更多关于它们的信息并应用到您的代码中。这里有一个初步的安全检查清单：

- 不要相信 AI 生成的代码。始终验证。请记住，AI 不会对您运行的代码负责，您才会！
- 不要将任何 API 密钥或其他机密信息存储为硬编码字符串，尤其是在前端代码中。将它们作为受保护的环境变量存储在后端（例如 Vercel 等平台提供此选项）
- 查询 API 端点时，始终使用 HTTPS
- 创建 HTML 表单时，始终进行输入验证和清理
- 不要在 `localStorage`、`sessionStorage` 或 cookie 中存储敏感数据
- 在您的包需求中运行验证器和安全漏洞扫描器

## 如何在 Claude Code 中使用任何 LLM？

您只是想在您的 Claude Code CLI 中尝试 Kimi K2 或其他 LLM 吗？您可以使用 claude-code-router 让 Claude Code CLI 使用一个在您机器上本地运行的“代理”来将其路由到 OpenRouter 上可用的任何模型！下面的说明适用于 Kimi K2，但您可以将其调整为任何您想要的其他 LLM。

首先在 OpenRouter 创建一个账户并获取您的 API 密钥。

确保您已经安装了 Claude Code CLI：

```
npm install -g @anthropic-ai/claude-code
```

然后安装 claude-code-router：

```
npm install -g @musistudio/claude-code-router
```

将以下行添加到您的 `~/.claude-code-router/config.json` 文件中，将 `OPENROUTER_API_KEY` 替换为您的 OpenRouter API 密钥：

```
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

现在只需通过路由器运行 Claude Code：

```
ccr code
```

您应该会看到 Claude Code `API Base URL: http://127.0.0.1:3456`，这意味着它正在使用由 claude-code-router 创建的本地代理。就是这样！

如果您只对 Kimi K2 或 Moonshot 的其他模型感兴趣，一个替代方案是使用 Moonshot 自己提供的模型：
https://github.com/LLM-Red-Team/kimi-cc/blob/main/README_EN.md

## 如何创建我自己的 AI 编码代理？

我们正在编写一些关于如何在我们构建自己的工具时做到这一点的教程，所以请保持关注。最好的入门是
Thorsten 的[这个实用教程](https://ampcode.com/how-to-build-an-agent)，您可以在其中逐步用 Go 构建一个使用最少量工具（`list_files`、`read_file`、`edit_file`）的简单代理。

如果您想更深入，Gerred 的[这个开源系列书籍](https://gerred.github.io/building-an-agentic-system)绝对是一个很好的开始。

# ✨ 特定工具和代理的提示和技巧

## Claude Code

- [Claude Code 指南](https://github.com/zebbern/claude-code-guide): 涵盖了所有可发现的 Claude Code 命令，包括许多在基本教程中没有广泛知晓或记录的功能

# 🛠️ 工具

在这里，我们保留了一份关于使用 AI 进行编码的主要工具的更新列表。我们测试了其中的大部分，您会在我们测试它们期间找到我们诚实的意见。

## 编辑器 / IDE

- [Cursor](https://cursor.com)
- [Windsurf](https://windsurf.com)
- [Cline](https://cline.bot/)
- [OpenHands](https://github.com/All-Hands-AI/OpenHands)
- [Devin](https://devin.ai)
- [VSCode + GitHub Copilot](https://code.visualstudio.com/docs/copilot/setup)
- [Amp](https://ampcode.com)
- [Kiro](https://kiro.dev)

## CLI

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

## 有用的工具

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

# 🤗 值得关注的人

一些在实现 AI 编码模型/工具或在自己的项目中使用它的非常有趣的人。

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

本指南的灵感来自 Maxime Labonne 的伟大课程 [llm-course](https://github.com/mlabonne/llm-course)。

特别感谢：

- [Gabriela Thumé](https://github.com/gabithume) 为一切 ❤️
- [Albert Espín](https://github.com/albert-espin) 提供深思熟虑的反馈和首次纠错
- [Geoffrey Huntley](https://x.com/GeoffreyHuntley) 指引我了解基于属性的测试，以及他所有关于自主代理的伟大教程和实验
- ChatGPT 4o 生成了您在顶部看到的横幅，灵感来自令人难以置信的艺术家 [Deathburger](https://citadel9.com/)

# ⭐ 贡献

如果您想贡献更正、反馈或一些缺失的工具或参考资料，请随时开启一个新的 PR、一个新的 issue 或与 [Eric](https://x.com/esrtweet) 或 [Vilson](https://x.com/aut0mata) 联系。

如果您喜欢本指南，请考虑给它一个星 ⭐ 并关注它以获取新的更新！

# ⚖️ 许可证

MIT
