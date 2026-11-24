---
layout: default
title: "Horizon Summary: 2026-11-24 (ZH)"
date: 2026-11-24
lang: zh
---

> 从 38 条内容中筛选出 13 条重要资讯。

---

**科技新闻**
1. [Ladybird 浏览器发布首个 Alpha 版](#item-tech-news-1) ⭐️ 8.0/10
2. [GLM-5.4 发布：首款循环 Transformer，面向通用编程](#item-tech-news-2) ⭐️ 8.0/10
3. [百度开源文心 5.5 Flash Preview：280B MoE、Apache 2.0](#item-tech-news-3) ⭐️ 8.0/10
4. [嵌套浏览器实验《2035 Came Early》引讨论](#item-tech-news-4) ⭐️ 7.0/10
5. [Stalwart 宣称可替代 Microsoft Exchange](#item-tech-news-5) ⭐️ 7.0/10
6. [NariQ 发布 Qwen3.8-27B 的 3 位及以下 GGUF 量化](#item-tech-news-6) ⭐️ 7.0/10
7. [黎曼猜想 AI 证明被指空转，作者承认代码不可靠](#item-tech-news-7) ⭐️ 7.0/10
8. [4.5 万家企业组织联名促欧盟调查苹果 iPhone 浏览器限制](#item-tech-news-8) ⭐️ 7.0/10
9. [黄循财：新加坡不会成为规避美国芯片管制的通道](#item-tech-news-9) ⭐️ 7.0/10
10. [Anthropic 称 Claude 发现 VP≠VNP 并发布 Lean 4 形式化](#item-tech-news-10) ⭐️ 7.0/10
11. [诺华 CEO：AI 十年内治不好癌症，研发周期或从 12 年缩至 8 年](#item-tech-news-11) ⭐️ 7.0/10

**科技博客**
1. [vLLM 插件实现 ERNIE 5.5 Flash 首日支持](#item-tech-blog-1) ⭐️ 7.0/10

**财经新闻**
1. [纽约联储主席威廉姆斯称抗通胀仍有工作要做](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Ladybird 浏览器发布首个 Alpha 版](https://ladybird.org/posts/alpha/) ⭐️ 8.0/10

独立开发的 Ladybird 浏览器发布了首个 Alpha 版，macOS 和 Linux 用户现在可以直接下载安装，无需自行编译。它自行实现 HTML 解析、CSS、布局、JavaScript 和 WebAssembly 等核心组件，仅复用 HarfBuzz、Skia、ffmpeg 和 SQLite 等外部库。官方提醒 Alpha 阶段部分网站无法使用且浏览器偶尔会崩溃，用户可从浏览器内报告故障站点，并在崩溃后自行决定是否发送崩溃报告。早期试用显示多数网站渲染正常，ffmpeg 和 Pyodide 等 WebAssembly 工具可运行，但依赖 Service Worker 的 Datasette Lite 因调用缺失的 navigator.serviceWorker.startMessages 而失败；2026 年 10 月 Ladybird 在约 225 万项 web-platform-tests 子测试中通过 2,184,722 项，略低于 Firefox、高于 Safari。

hackernews · janvdberg · 11月23日 16:13 · [社区讨论](https://news.ycombinator.com/item?id=50614249)

**「背景」** Ladybird 最初是 SerenityOS 的浏览器项目，后来独立开发，目标是拥有自己的 HTML 解析、CSS 引擎、布局和 JavaScript 实现，而不是基于 Chromium、Gecko 或 WebKit。它仍复用 HarfBuzz、Skia、FFmpeg 和 SQLite 等外部组件。2026 年 2 月，项目开始借助 AI 编程工具把部分 LibJS 从 C++ 移植到 Rust；据其 10 月月报，这些工具还被用于集中补齐 Web Platform Tests 功能，使通过的子测试数快速上升。

**「影响」** 对需要评估浏览器兼容性的 Web 开发者，Ladybird Alpha 已可用于实际站点测试并通过内置入口报告故障；但 Service Worker 支持仍不完整，依赖该 API 的应用可能直接报错，因此暂不适合作为生产环境中的唯一测试或使用浏览器。

**「社区讨论」** 有评论者称其测试的多个网站均正确渲染，NoVNC 甚至比 Firefox 更流畅，但页面滚动略显卡顿；另一位评论者则呼吁 Ladybird 未来认真处理浏览器指纹识别，提供更细粒度的权限控制。还有用户询问在 Alpha 阶段使用时应采取哪些安全预防措施。

**标签**: `#browsers`, `#Ladybird`, `#web engines`, `#open source`, `#privacy`

---

<a id="item-tech-news-2"></a>
### [GLM-5.4 发布：首款循环 Transformer，面向通用编程](https://z.ai/blog/glm-5.4) ⭐️ 8.0/10

Z.ai（智谱 AI）发布 GLM-5.4，这是该公司首款采用循环 Transformer（Loop Transformer）架构的模型，目标是提升通用编程能力。该架构让一组共享权重的层在一次前向传播中运行多次，反复细化隐藏状态，从而在不增加参数量的情况下加深网络。GLM-5.4 目前未开放权重，也不能通过常规 API 套餐访问，需订阅 Coding Plan；但该套餐的密钥可在共享的 OpenAI 兼容 Responses API（https://api.z.ai/api/v1）上调用新模型。在 Simon Willison 的非正式 pelican 绘图测试中，GLM-5.4 与 GLM-5.3 在低、高、最高三档推理强度下观感相近，未体现明显提升。

hackernews · foohis · 11月23日 10:06 · [社区讨论](https://news.ycombinator.com/item?id=50609685)

**「背景」** 标准 Transformer 在一次前向传播中，每一层只计算一次；循环 Transformer 则让一组共享权重的层反复运行多轮，在参数量不变的情况下加深有效网络深度。GLM-5.4 之前，Thinking Machines Lab 在 11 月 20 日发布的 Inkling 2 Mini 也采用循环结构，让模型中间层对每个 token 运行三次；GLM-5.4 是 Z.ai 首个采用该架构的模型。

**「影响」** 对开发者而言，最直接的影响在接入路径：现有 OpenAI 兼容客户端可复用 Coding Plan 密钥调用 GLM-5.4，但 OpenRouter 和常规 API 套餐暂时不可用；由于未开放权重，也无法本地部署。

**「社区讨论」** 有 HN 评论者称赞 Zhipu 公开架构细节，认为循环 Transformer 是自然方向，并有人从逐层搬运权重的显存带宽瓶颈解释其动机。另一名用户则抱怨中国模型常进行冗长的“marathon thinking”，即使简单任务也反复自我怀疑、完成时间明显长于前沿模型，并猜测这是贴近基准成绩的代价。

**标签**: `#LLM architecture`, `#looped transformers`, `#code generation`, `#GLM/Zhipu`, `#open models`

---

<a id="item-tech-news-3"></a>
### [百度开源文心 5.5 Flash Preview：280B MoE、Apache 2.0](https://x.com/Baidu_Inc/status/2125077484442190137) ⭐️ 8.0/10

百度于 11 月 24 日通过官方 X 账号宣布开源文心 5.5 Flash Preview，模型权重以 Apache 2.0 协议在 Hugging Face 和 ModelScope 开放。该模型采用 MoE 架构，总参数 280B，每个 token 激活 14B，上下文长度 1M token，可用 vLLM 或 SGLang 部署并微调。百度称其是基于 ERNIE 5.5 Flash Base 训练的首个后训练模型。流传的基准图表显示 Terminal-Bench 4.0 得 46.5 分、DeepSWE v1.1 得 71.2 分，但百度未说明这些结果是否经过第三方独立验证。

telegram · zaihuapd · 11月24日 07:32

**「背景：MoE 架构与开源协议」** 文心 5.5 Flash Preview 采用混合专家（MoE）架构，280B 总参数指模型全部专家权重之和，而每个 token 仅激活其中 14B 参数，因此推理算力开销更接近小模型而非稠密 280B 模型。Apache 2.0 是允许商用、修改与再分发的宽松开源协议，权重同时在 Hugging Face 与 ModelScope 开放，并给出 vLLM、SGLang 两条部署路径，意味着使用者可直接自行托管与微调，而不必通过百度云 API 调用。该版本被定位为基于 ERNIE 5.5 Flash Base 训练的首个后训练模型，且仍属 Preview 阶段。

**「对开发者的影响」** 希望自托管或微调的团队可以直接使用 Apache 2.0 权重，并接入 vLLM、SGLang 工具链；但该模型仍是 Preview，且相关基准未说明第三方验证，生产选型前应做独立评测。MoE 每 token 仅激活 14B 参数，也不意味着部署只需容纳 14B 权重，资源规划仍需按 280B 总参数考虑。

**标签**: `#open-source LLM`, `#Baidu ERNIE`, `#Mixture-of-Experts`, `#long context`, `#Apache 2.0`

---

<a id="item-tech-news-4"></a>
### [嵌套浏览器实验《2035 Came Early》引讨论](https://fzakaria.com/2026/11/23/2035-came-early) ⭐️ 7.0/10

技术博客《2035 Came Early》在 Hacker News 引发讨论，评论者将其描述为一项把浏览器嵌入浏览器的嵌套实验，并提到它与 trynix 项目有关。多位评论者称赞该实验出现得比预期早、作为可能性演示很有价值，但同时质疑其生产可用性和性能。由于原文正文未提供，具体实现方式、依赖版本和可复现结果无法从现有材料确认。

hackernews · setheron · 11月24日 06:30 · [社区讨论](https://news.ycombinator.com/item?id=50624497)

**「背景：从 trynix 到浏览器套浏览器」** 这篇文章发布在 Farid Zakaria 的博客 fzakaria.com 上；他此前的项目 trynix 于 2026 年 9 月发布，通过 qemu-wasm 在浏览器标签页内启动一个编译为 WebAssembly 的 x86\_64 Linux 虚拟机，可直接运行 nixpkgs 中超过 31 万个包版本（tool-2-1、tool-2-2、tool-2-3）。作者当时说明 trynix 只提供串行控制台、没有图形界面（tool-2-3）。评论区所说的“嵌套浏览器”就是在这一基础上的新实验：评论者提到原 unkernel 讨论帖，并对把浏览器本身再放进浏览器中运行感到意外（tool-2-2 记录了 trynix 的发布时间与机制）。

**「实际影响」** 对需要在浏览器内运行 Linux/Nix 工具的开发者来说，trynix 宣称可在无服务器的情况下把 nixpkgs 软件作为 WebAssembly Linux 客户机启动，这意味着客户端侧环境可以少依赖后端。但 Hackaday 仅称其达到“接近原生速度的相当一部分”，评论者也质疑嵌套浏览器是否真的更快，因此在生产采用前应把性能与原生方案做基准对比。

**「社区讨论」** 评论中的主要分歧是实用价值：momojo 以 V8 isolates 和 Pyodide 为例，担心这类演示最终会因生产限制而难以落地，并追问 trynix 再往下分叉会变成什么；saagarjha 则追问嵌套浏览器是否真的因 Web 引擎的投入而更快。Cu3PO42 和 swiftcoder 肯定其作为技术演示的新颖性，认为它展示了此前难以实现的可能性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://simonwillison.net/2026/Sep/10/trynix/">Any Nix package, live in your browser | Simon Willison’s Weblog</a></li>
<li><a href="https://dev.to/techaiwire/trynix-runs-any-nix-package-in-a-browser-tab-12i1">TryNix runs any Nix package in a browser tab - DEV Community</a></li>
<li><a href="https://fzakaria.com/2026/09/04/any-nix-package-live-in-your-browser">Any Nix package, live in your browser | Farid Zakaria ’s Blog</a></li>
<li><a href="https://trynix.dev/">trynix</a></li>
<li><a href="https://hackaday.com/2026/11/17/linux-in-a-browser-tab/">Linux In A Browser Tab - Hackaday</a></li>

</ul>
</details>

**标签**: `#browser-in-browser`, `#WebAssembly`, `#Nix`, `#systems experimentation`, `#technical demo`

---

<a id="item-tech-news-5"></a>
### [Stalwart 宣称可替代 Microsoft Exchange](https://stalw.art/blog/microsoft-exchange-replacement/) ⭐️ 7.0/10

Stalwart 宣布其邮件服务器可作为 Microsoft Exchange 的“直接替代品”（drop-in replacement），但现有材料只有公告标题与社区反应，未给出支持版本、客户端兼容范围或独立验证结果。该声明面向希望迁移 Exchange 的企业邮件管理员和自建邮件服务用户。由于缺少技术细节，目前仍应把它视为项目方的能力宣称，而不是已证实可无缝替换所有 Exchange 部署。

hackernews · shaunpud · 11月23日 22:32 · [社区讨论](https://news.ycombinator.com/item?id=50620349)

**「背景」** Stalwart 是用 Rust 编写的开源邮件与协作服务器，在 1.2 版本之前不具备微软 Exchange 协议兼容能力；Exchange 环境下的 Outlook、Apple Mail 和移动设备通常依赖 MAPI over HTTP、Exchange Web Services（EWS）、ActiveSync 与 Autodiscover 等专有协议，而非单纯的 IMAP/SMTP。此次 1.2.0 正是补齐了这套协议栈，才使其能够像 Exchange 服务器一样接待这些客户端。外部报道还提到两个时间点：Exchange Online 中的 EWS 将于 2027 年 4 月完全停用，且新版 Windows Outlook 只能通过微软云工作，这构成自建 Exchange 兼容服务器受到关注的背景。

**「迁移影响」** 受德国 GoBD 等留档法规约束的组织不能把“可直接替代 Exchange”理解为合规上的开箱即用：有评论指出，Stalwart 的常规套餐和开源版本不含不可篡改、可供税务审计检索的十年邮件归档功能，迁移前需单独部署归档方案或选择包含该能力的商业方案。

**「社区讨论」** 评论者提出的实际顾虑包括：有评论者称 Outlook 将只支持云端 Exchange，因此质疑企业若仍依赖 Outlook，如何连接到 Stalwart；也有人指出德国 GoBD 要求邮件不可篡改归档并保存最长 10 年，而 Stalwart 的常规计划或开源版本未包含该功能。另有评论认为，MAPI 等兼容支持虽方便管理员，却可能加深围绕 Microsoft 邮件协议的锁定，不利于仍存在的开放邮件生态。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://stalw.art/blog/microsoft-exchange-replacement/">Stalwart is now a drop-in replacement for Microsoft Exchange</a></li>
<li><a href="https://www.startuphub.ai/ai-news/technology/2026/stalwart-1-2-0-replaces-exchange-and-keeps-outlook-working">Stalwart 1.2.0 replaces Exchange and keeps Outlook…</a></li>
<li><a href="https://linuxiac.com/stalwart-1-2-offers-open-source-microsoft-exchange-replacement/">Stalwart 1.2 Offers Open-Source Microsoft Exchange Replacement</a></li>

</ul>
</details>

**标签**: `#open-source email`, `#Microsoft Exchange`, `#mail server`, `#interoperability`, `#email infrastructure`

---

<a id="item-tech-news-6"></a>
### [NariQ 发布 Qwen3.8-27B 的 3 位及以下 GGUF 量化](https://huggingface.co/nari-labs/Qwen3.8-27B-NariQ-GGUF) ⭐️ 7.0/10

NariQ 发布了 Qwen3.8-27B 的 3 位及以下 GGUF 量化文件，称约 10 GB 的版本在智能体、数学、多语言和图像理解任务上接近 BF16 质量，并自称是首个在长程智能体任务上保持 BF16 水平的 3 位及以下量化。其公布的基准显示，3 位和 2.5 位版本在 DeepSWE、Terminal-Bench 2.1、AIME 25+26 等任务上与 BF16 基本持平或略高，而 2 位版本明显下降，例如 DeepSWE 从 39.8 降至 28.6、Terminal-Bench 从 62.6 降至 52.4、AIME 从 97.7 降至 86.0。目前运行这些文件需要 NariQ 的 llama.cpp 分支；作者称在 RTX PRO 6000 上解码速度与其他量化相当。

hackernews · toebee · 11月23日 13:42 · [社区讨论](https://news.ycombinator.com/item?id=50611402)

**「背景」** NariQ 的 3.0、2.5 和 2.0 bpw 权重采用 Nari Labs 的 trellis-coded 量化，目前需通过其 nari-llama.cpp 分支运行。低比特 GGUF 的核心取舍在于：把 27B 级模型压到约 10 GB 时，是否还能保住长程代理、数学与多语言任务的表现；NariQ 因此将 3-bit 以下结果与 BF16 对照，并公开了这条自定义推理路径。

**「影响」** 对希望用单张消费级或工作站显卡本地部署 27B 模型的用户，约 10 GB 的文件显著降低了内存门槛，但必须改用 NariQ 的 llama.cpp 分支，且 2 位版本在长程智能体和数学任务上已出现约 10 个百分点的下滑；若目标是接近 BF16 的效果，应优先考虑 3 位或 2.5 位文件。这些基准尚未经过独立复测。

**「社区讨论」** 评论者对基准能否代表真实使用存在分歧：rao-v 表示此类高计算量量化容易过拟合基准类数据，但认可该项目在多种长程任务上做了留出集检查；WithinReason 则认为从图表看大部分提升来自测试框架差异，而非模型本身。Retro\_Dev 追问文件变小时究竟丢失了什么信息，jedbrooke 则提到在 18 GB M3 Pro 上 3.0 bpw 文件解码约 3.8 tok/s（2.0 bpw 为 4.9 tok/s），远慢于 CUDA，并询问能否塞进 16 GB Mac。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/nari-labs/nari-llama.cpp">GitHub - nari - labs / nari -llama.cpp: llama.cpp fork that runs NariQ ...</a></li>

</ul>
</details>

**标签**: `#quantization`, `#local LLMs`, `#GGUF`, `#llama.cpp`, `#agentic benchmarks`

---

<a id="item-tech-news-7"></a>
### [黎曼猜想 AI 证明被指空转，作者承认代码不可靠](https://x.com/i/web/status/2124987173439209561) ⭐️ 7.0/10

据一则 Telegram 摘要，Alpöge 与 Claude 宣称证明了黎曼猜想及其广义版本，却只公开了约 1700 万行 Lean 代码和 17.5 万个文件，没有提供人类可读的证明。Lean 与 Mathlib 社区次日表示对该代码证明这一命题“有充分信心”，但随后有研究者指关键定义被写成恒真、几何条件形同虚设，证明可能只是空转。23 日 Alpöge 承认“25 万页是玩笑”，称代码“满是垃圾但能编译”，并称批评完全合理。这些说法来自该摘要，尚未见独立验证。

telegram · zaihuapd · 11月24日 01:29

**「背景」** Lean 是可机械检查证明的交互式定理证明器，但它只核对代码是否与写入的定义和公理相符，无法判断这些定义是否忠实表达黎曼猜想；若关键定义退化成恒真命题，证明就会“空转”。Mathlib 社区博客称，黎曼猜想的 Lean 陈述 \`RiemannHypothesis\` 已由 Lean 与数论专家审核，且 Alpöge 的库可以正确编译，这使争议集中在定义和证明内容，而非语法错误。

**「对形式化验证的影响」** 对 Lean 与 Mathlib 用户而言，这一事件突显出“能编译”不等于证明有效：审查 AI 生成的正式化时，需要先检查关键定义是否恒真、定理陈述是否空转，而不能只以编译通过或社区初步信心作为验收依据。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://leanprover-community.github.io/blog/posts/riemann-hypothesis/">Lean verification of the Riemann Hypothesis | Lean community blog</a></li>

</ul>
</details>

**标签**: `#AI for mathematics`, `#Lean`, `#formal verification`, `#Riemann hypothesis`, `#AI-generated code`

---

<a id="item-tech-news-8"></a>
### [4.5 万家企业组织联名促欧盟调查苹果 iPhone 浏览器限制](https://appleinsider.com/articles/26/11/23/eu-urges-to-challenge-apples-grip-on-iphone-browsers?utm_source=rss) ⭐️ 7.0/10

包括 Mozilla 和 Shopify 在内的企业及民间组织已联名致信欧盟委员会，要求对苹果在 iPhone 上的浏览器限制正式立案；信方称，署名方合计代表约 4.5 万至 5.5 万家欧盟企业组织，联署将持续到 2026 年 12 月 3 日。信方认为，苹果虽已按《数字市场法》允许欧盟竞品浏览器使用自有引擎，但现有技术和法律要求仍使厂商难以把用户迁出 WebKit，企业也仍依赖 App Store 触达用户。联名方自行估算，若半数原生 iOS 应用转向 Web，欧盟企业每年可节省 110 亿欧元开发成本和 13 亿欧元 App Store 费用；目前尚无欧盟立案或裁决。

telegram · zaihuapd · 11月24日 03:02

**「背景」** 《数字市场法》是欧盟要求大型平台开放竞争的规则，苹果在欧盟的浏览器政策受其约束。苹果此前已按该法允许竞品浏览器使用自有引擎，但联名方称，现有技术与法律要求仍使企业和用户难以把既有欧盟用户迁出 WebKit。

**「实际影响」** 对欧盟 iOS 用户和浏览器厂商来说，默认浏览器选择增多并没有带来真正独立的引擎：Mozilla 表示，DMA 生效后 Firefox 在 iOS 的日活翻倍，但 iPhone 版仍基于 WebKit；Open Web Advocacy 也指出，iOS 上仍没有非 WebKit 浏览器。这意味着，除非欧盟委员会据此立案并推动改变执行，开发者仍需按 WebKit 的兼容约束开发和适配，浏览器厂商也无法把现有欧盟用户迁到自有引擎。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.mozilla.org/en/mozilla/internet-policy/apple-ios-browser-engine-rules/">Why there are still no non- WebKit browsers on iOS</a></li>
<li><a href="https://open-web-advocacy.org/blog/apples-browser-engine-ban-persists-even-under-the-dma/">Apple &#x27;s Browser Engine Ban Persists, Even Under the DMA</a></li>

</ul>
</details>

**标签**: `#Apple`, `#EU DMA`, `#browser competition`, `#WebKit`, `#App Store`

---

<a id="item-tech-news-9"></a>
### [黄循财：新加坡不会成为规避美国芯片管制的通道](https://www.bloomberg.com/news/articles/2026-11-24/singapore-won-t-be-conduit-to-skirt-us-chip-curbs-wong-says) ⭐️ 7.0/10

新加坡总理黄循财表示，新加坡不会成为企业规避美国芯片出口管制的通道，当局正调查 Megaspeed 采购英伟达芯片的交易。此前一天，美国商务部将 Megaspeed 及另外 6 家东南亚企业列入贸易黑名单；《联邦公报》称这些企业存在将先进计算产品转移给未获授权用户的“重大风险”，名单还包括其在马来西亚和泰国的关联实体。路透社报道，阿里巴巴新加坡子公司 Apex Enterprise Solutions 也在名单中；阿里巴巴表示从未转移受管制的先进计算芯片。

telegram · zaihuapd · 11月24日 05:03

**「背景」** 此次表态发生在美方执法行动之后：美国商务部在前一天将 Megaspeed 及另外 6 家东南亚企业列入贸易黑名单，理由是其存在向未获授权用户转移先进计算产品的“重大风险”。新加坡当局对 Megaspeed 采购英伟达芯片交易的调查，正是在这一美方黑名单与区域转口审查背景下展开。

**「影响」** 被列入黑名单的企业将直接面临美国出口限制；对在新加坡和东南亚运营的芯片采购、转口企业而言，新加坡当局的调查与总理表态意味着相关交易将受到更严格的合规审查。

**标签**: `#export controls`, `#semiconductors`, `#Nvidia`, `#Singapore`, `#AI hardware`

---

<a id="item-tech-news-10"></a>
### [Anthropic 称 Claude 发现 VP≠VNP 并发布 Lean 4 形式化](https://github.com/anthropics/formal-math/blob/main/vp-vnp/README.md) ⭐️ 7.0/10

Anthropic 于 11 月 24 日公开论文《VP ≠ VNP over every field》及 Lean 4 形式化仓库，称结果由其内部研究用 Claude 模型发现，论文与代码均由 AI 撰写。论文给出哈密顿圈多项式的超多项式算术电路下界，据此推出 VP 是 VNP 的真子类；若成立，即解决 Valiant 1979 年的代数复杂度猜想，但该结果仅针对算术电路，不涉及 P 与 NP。仓库称已通过三条标准公理审计和独立内核 nanoda 复核，除预留文件外未出现 sorry；不过尚无人类数学家完成通读，Lean 无法确认形式化陈述与论文声称的命题一致，附录 Q 还列出若干出入，仍需独立审阅。

telegram · zaihuapd · 11月24日 06:02

**「背景」** VP 与 VNP 是 Leslie Valiant 于 1979 年提出的代数复杂度类，分别刻画可用多项式规模算术电路计算的多项式，以及具有简洁组合描述的多项式；VP≠VNP 是该框架下类比 P≠NP 的核心猜想。

**「影响与待办」** 对复杂度理论研究者而言，当前可直接开展的工作是独立核对 Lean 4 形式化陈述是否与论文定理一致，并审查附录 Q 列出的出入；在这些审阅完成前，不宜把该仓库视为 Valiant 猜想的已确认证明。

**标签**: `#AI for math`, `#complexity theory`, `#Lean 4`, `#formal verification`, `#Anthropic`

---

<a id="item-tech-news-11"></a>
### [诺华 CEO：AI 十年内治不好癌症，研发周期或从 12 年缩至 8 年](https://www.ft.com/content/1e5a9d70-221d-461d-ae03-dc235b1db340) ⭐️ 7.0/10

诺华 CEO 万思瀚（Vas Narasimhan，同时担任 Anthropic 董事）表示，AI 不会在 5 到 10 年内治愈癌症；仅把平均约 12 年的药物研发周期压缩到 8 年，就需要大约十年时间。他给出的现实依据是 AI 的提速主要发生在进入人体试验之前的早期发现阶段：这一步通常耗时约 4 年，最多可缩短 2 年，而动物实验和临床试验无法跳过。他还预计，进入人体试验的成功率能从 8% 提高到 12%，但这属于高管预期而非已测得的成果。上述判断与 Anthropic CEO 关于癌症等疾病将在十年内成为「历史遗迹」的说法相左，礼来 CEO 也公开表达怀疑；万思瀚认为科技界习惯用「工程思维」看待医学，而人类对人体内机制只了解约 5%。

telegram · zaihuapd · 11月24日 08:54

**「背景」** 药物研发通常要经过早期发现、动物实验和多期人体临床试验；诺华给出的平均周期约为 12 年，进入人体试验的成功率目前约为 8%。万思瀚同时担任 Anthropic 董事，而 Anthropic CEO 此前公开预测癌症等疾病将在十年内成为“历史遗迹”，这使两人的判断形成直接对照。

**「影响」** 对制药研发团队而言，这一判断意味着 AI 的近期价值集中在临床前发现环节，项目排期与资源投入若按「临床阶段大幅提速」来规划，可能与实际收益不符；同时 8% 到 12% 的成功率提升仍是预期值，需在真实管线数据中验证。

**标签**: `#AI 药物研发`, `#制药研发周期`, `#AI 炒作`, `#行业观点`, `#生物科技`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [vLLM 插件实现 ERNIE 5.5 Flash 首日支持](https://vllm.ai/blog/2026-11-24-ernie-5-5-flash-preview) ⭐️ 7.0/10

rss · vLLM Blog · 11月24日 00:00

**「背景」** 百度 ERNIE 5.5 Flash Preview 是总参数 280B、每 token 激活 14B 的稀疏 MoE 模型，支持 1M 上下文与工具调用；要让它在发布当天运行在官方 vLLM 上，同时不维护 fork，是这次集成的核心约束。

**「方案」** 作者称，团队通过 vLLM-ERNIE 插件支持 vllm==0.32.0：插件经 vllm.general\_plugins 入口注册模型与解析器，并以模块路径延迟导入，只有 config.json 命中 ERNIE 架构才加载，其他模型无额外开销，还可用 VLLM\_PLUGINS=&quot;&quot; 关闭。模型侧针对 37 层 HCA 与 6 层 MLA-DSA 等新结构做专用融合内核：加载时把 VHA 固定混合参数折叠成单个矩阵，并把下游所需 FP8 量化并入同一内核；合并多路由器 GEMM 与路由链；把约 20 万 logits 的 MultiMax 分段变换改为单次读写、结果按位一致。作者报告这些融合比逐算子实现快 1.55×–6.53×。FlashIndexer 用动态头路由和阈值预筛选降低 DSA 索引成本，在 1M 上下文报告 1.4× 加速。训练侧采用 W4A8 QAT 对齐伪量化与推理数值，并用多阶段 DSpark 训练 3 层草稿模型，每步最多提议 7 个 token，在编码和 Agent 负载上平均接受长度超过 4.0。

**「启示」** 文章的核心论点是：把模型专属代码和内核放进 vLLM 插件，可以在不 fork 的情况下实现 Day-0 支持，并把模型架构与内核协同设计转化为端到端推理收益；不过其加速数据多由模型与 serving 团队自报，缺少基准方法细节，仍需独立验证。

**标签**: `#mixture-of-experts`, `#kernel-fusion`, `#speculative-decoding`, `#quantization-aware-training`, `#vllm-plugins`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [纽约联储主席威廉姆斯称抗通胀仍有工作要做](https://www.cnbc.com/2026/11/23/john-williams-fed-inflation-rate-hikes.html) ⭐️ 7.0/10

纽约联储主席约翰·威廉姆斯 11 月 23 日表示，要让通胀回到美联储 2%的目标“还有更多工作要做”，并称相关行动可能“随着时间推移”展开；在 12 月 8-9 日议息会议前，市场已完全计入从当前 3.75%-4%的目标区间加息 25 个基点的预期。

rss · CNBC Finance · 11月23日 21:02

**「背景」** 美联储在 2026 年 9 月将基准利率上调 25 个基点至 3.75%-4%，为 2023 年以来首次加息，10 月会议则维持利率不变；下一次议息会议定于 12 月 8 日至 9 日。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/09/16/fed-rate-decision-september-2026.html">Fed rate decision September 2026 : Rates rise to 3 . 75 %- 4 %</a></li>
<li><a href="https://tradingeconomics.com/united-states/interest-rate">United States Fed Funds Interest Rate</a></li>

</ul>
</details>

**标签**: `#Federal Reserve`, `#monetary policy`, `#inflation`, `#interest rates`, `#FOMC`

---