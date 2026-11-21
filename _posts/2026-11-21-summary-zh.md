---
layout: default
title: "Horizon Summary: 2026-11-21 (ZH)"
date: 2026-11-21
lang: zh
---

> 从 41 条内容中筛选出 14 条重要资讯。

---

**科技新闻**
1. [Inkling 2 Mini 开放权重循环 Transformer 模型](#item-tech-news-1) ⭐️ 8.0/10
2. [Navier–Stokes 有限时间爆破的 GitHub 声明引发讨论](#item-tech-news-2) ⭐️ 8.0/10
3. [KVM CVE-2026-99312 允许 AMD 虚拟机读取宿主内存](#item-tech-news-3) ⭐️ 8.0/10
4. [陶哲轩撰文讨论无外力欧拉/纳维-斯托克斯奇点与广义黎曼猜想](#item-tech-news-4) ⭐️ 7.0/10
5. [Aaronson 博客讨论随机鹦鹉与 Lean 黎曼猜想证明](#item-tech-news-5) ⭐️ 7.0/10
6. [GRH 拟议证明草稿提前公布](#item-tech-news-6) ⭐️ 7.0/10
7. [Levent Alpöge 称与 Claude 证明黎曼猜想，尚无验证](#item-tech-news-7) ⭐️ 7.0/10
8. [苹果被曝研发自主 AI 智能体](#item-tech-news-8) ⭐️ 7.0/10
9. [台积电据报暂停对华 16nm 以下订单](#item-tech-news-9) ⭐️ 7.0/10
10. [微软发布 USB4 RDMA 预览，多台 PC 合跑本地大模型](#item-tech-news-10) ⭐️ 7.0/10

**科技博客**
1. [为什么输出缓存收效有限](#item-tech-blog-1) ⭐️ 6.0/10

**财经新闻**
1. [沃什避免前瞻指引，美联储官员却更频繁谈论加息](#item-finance-news-1) ⭐️ 7.0/10
2. [美国企业转向净发行股票，规模达市值的 3.1%](#item-finance-news-2) ⭐️ 7.0/10
3. [北京就租房合同示范文本征求意见：正常损耗不得扣减押金](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Inkling 2 Mini 开放权重循环 Transformer 模型](https://thinkingmachines.ai/news/inkling-2-mini/) ⭐️ 8.0/10

Thinking Machines 发布开放权重的 Inkling 2 Mini，其特点是采用循环 Transformer 架构，并明确面向本地部署。社区已在 llama.cpp/GGUF 上测试：Ryzen 395 配合 Vulkan 解码约 27 token/s，M1 Pro 32GB 在 q4 下约 10 token/s，但有人报告复杂任务表现不稳定。据社区转述的发布方说明，该模型训练全程使用 nvfp4，尺寸设计参考了本地用户需求；关于其性能可与 Qwen3.8-27B 相提并论的说法仍属早期且未经独立验证。

hackernews · jasondavies · 11月20日 20:12 · [社区讨论](https://news.ycombinator.com/item?id=50581260)

**「背景」** 在 Inkling 2 Mini 之前，Thinking Machines Lab 已用 Inkling 指代面向文本、图像和音频的高效多模态模型，并支持在 Tinker 上微调。此次新模型沿用该系列名称，核心做法是循环执行中间层，让每个 token 获得更多推理计算，从而用更少 token 得到答案。

**「对本地部署的影响」** 对本地用户而言，Inkling 2 Mini 已提供可配合 llama.cpp/Ollama 使用的 GGUF 量化版本，官方博客还称支持 transformers、llama.cpp 与 MLX，因此可在消费级 PC 和 Mac 上直接部署。不过早期社区测试显示性能因硬件和补丁而异（如 Ryzen 395 上约 27 tokens/s、M1 Pro 32GB 上约 10 tokens/s），且可能需要合入尚未合并的 llama.cpp PR 或打补丁才能获得更好速度，这些数字并非独立基准。

**「社区讨论」** 社区的实际体验并不一致：hedgehog 在 Ryzen 395 配合 llama.cpp Vulkan 上测到约 27 token/s，dgacmu 在 M1 Pro 32GB 上约 10 token/s，且其“识别硬币类型和年份”测试在约 1.2 万 token 后仍失败。montroser 认为若基准在真实场景中成立，这一成绩“好得离谱”，lilytweed 则提出循环架构开放权重后的安全与可解释性问题。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://thinkingmachines.ai/news/inkling-2-mini/">Introducing Inkling 2 Mini - Thinking Machines Lab</a></li>
<li><a href="https://thinkingmachines.ai/inkling/">Inkling - Thinking Machines Lab</a></li>
<li><a href="https://unsloth.ai/docs/models/inkling-2-mini">Inkling 2 Mini - Run Locally Guide | Unsloth Documentation</a></li>
<li><a href="https://huggingface.co/blog/inkling2mini">Welcome Inkling 2 Mini, Cutting-edge Performance for your ...</a></li>

</ul>
</details>

**标签**: `#open-weight models`, `#looped transformers`, `#local inference`, `#llama.cpp`, `#AI model release`

---

<a id="item-tech-news-2"></a>
### [Navier–Stokes 有限时间爆破的 GitHub 声明引发讨论](https://github.com/tristanbuckmaster/navier-stokes/) ⭐️ 8.0/10

2026 年 11 月 20 日，Hacker News 上出现一个指向 GitHub 仓库的条目，标题为“Finite-time blow-up for the Navier–Stokes equations”，声称给出 Navier–Stokes 方程的有限时间爆破结果。给定材料目前只包含该仓库链接，没有论文正文、证明细节或独立验证，因此应将其视为未经确认的研究声明，而非已确立的数学结论。

hackernews · trotro · 11月20日 15:34 · [社区讨论](https://news.ycombinator.com/item?id=50576232)

**「背景」** 纳维–斯托克斯方程解的存在性与光滑性是千禧年大奖难题之一；其中“无外力”（unforced）版本不允许在方程中人为加入外部力，而“受迫”（forced）构造则通过精心选择外力来制造爆破，因此无外力版本更接近原始问题。社区评论提到，OpenAI 此前公布过带外力的爆破构造；此次仓库所指向的工作则声称在无外力条件下、从光滑初值出发得到有限时间爆破。

**「优先权与验证负担」** 这项声称的实际后果首先落在验证与优先权认定上：Clay 数学研究所为 Navier–Stokes 存在性与光滑性的四类情形各设 100 万美元奖金，授予首个给出解答者，而该仓库所涉的无外力情形正是其中之一（另两类为带光滑外力情形）。由于已有 OpenAI 于 2026 年 9 月 8 日公布、并附带 Lean 形式化的带外力版本解答，研究者和评奖方需要在独立审稿或形式化复核完成前，把这份仓库声称视为未经核实的结论，并据此判断两者的先后与归属。

**「社区讨论」** 评论者重点区分了问题的版本：有人称该仓库处理的是无外力情形，并认为这比需要精心设计外力的构造更接近真实流体；也有人把它与同日流传的广义黎曼猜想及 OpenAI 相关结果相提并论，但这些比较均来自评论、未获条目内容证实。还有读者询问能否用数值模拟实时展示爆破过程，以便直观理解方程在何处偏离现实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_priority_controversy">Navier–Stokes priority controversy - Wikipedia</a></li>
<li><a href="https://magica.com/news/alpoge-buckmaster-navier-stokes-unforced-blowup-claim">Alpöge and Buckmaster’s unverified Navier–Stokes claim | Magica</a></li>
<li><a href="https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_existence_and_smoothness">Navier–Stokes existence and smoothness - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_priority_controversy">Navier–Stokes priority controversy - Wikipedia</a></li>
<li><a href="https://openai.com/index/navier-stokes-solution/">On the Navier–Stokes Millennium Prize Problem | OpenAI</a></li>

</ul>
</details>

**标签**: `#Navier–Stokes equations`, `#mathematics`, `#fluid dynamics`, `#research result`, `#Hacker News`

---

<a id="item-tech-news-3"></a>
### [KVM CVE-2026-99312 允许 AMD 虚拟机读取宿主内存](https://thehackernews.com/2026/11/new-linux-kvm-flaw-cve-2026-99312-lets.html) ⭐️ 8.0/10

Linux 内核 KVM 被披露存在 CVE-2026-99312 漏洞：在启用嵌套虚拟化的 AMD 主机上，虚拟机可读取宿主内存；研究人员在 DigitalOcean 环境中从虚拟机内读取到约 127 GB 宿主内存。上游修复已于 11 月 18 日随稳定内核 7.3.5 等版本发布，但 Debian、Ubuntu 等发行版内核尚未包含该修复。补丁到位前，受影响主机可关闭嵌套虚拟化作为缓解措施。

telegram · zaihuapd · 11月20日 14:23

**「背景」** KVM 是内置于 Linux 内核的虚拟机监控器；嵌套虚拟化允许虚拟机内部再运行虚拟机，因此也使客户机获得管理嵌套虚拟机的路径。Terra Security 的分析称，CVE-2026-99312 源于 KVM 中的一个陈旧指针缺陷，该缺陷由一次安全修复引入，并已存在近四年；这也解释了为何受影响范围限于启用嵌套虚拟化的 AMD 主机。

**「影响」** 对使用 AMD 主机且开启嵌套虚拟化的云平台和运维团队，最直接的处置是先核对发行版内核是否已包含修复，并在补丁可用前关闭嵌套虚拟化；这能阻断该读取路径，但会使依赖嵌套虚拟机的开发测试或多级虚拟化负载无法运行。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.terra.security/blog/kvm-guest-to-host-escape">KVM Guest-to- Host Escape | Terra Security Research</a></li>
<li><a href="https://www.digitalocean.com/blog/cve-2026-99312-kvm-patch">Virtualization , Responsible Disclosure, and CVE - 2026 - 99312</a></li>

</ul>
</details>

**标签**: `#KVM`, `#Linux kernel`, `#CVE`, `#virtualization security`, `#AMD`

---

<a id="item-tech-news-4"></a>
### [陶哲轩撰文讨论无外力欧拉/纳维-斯托克斯奇点与广义黎曼猜想](https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/) ⭐️ 7.0/10

陶哲轩（Terry Tao）于 2026 年 11 月 20 日在其个人博客发表题为《Unforced Euler Singularity, Unforced Navier-Stokes Singularity, and the Generalized Riemann Hypothesis》的文章，把无外力（unforced）条件下的欧拉方程奇点、纳维-斯托克斯方程奇点与广义黎曼猜想放入同一篇讨论。由于本次抓取到的条目没有正文，文章的具体定理陈述、证明完成度与结论强度无法在此确认，可核实的只是标题所标示的这三个主题及其相互关联。围绕该文的讨论很快从数学内容转向形式化验证：有评论者引用 Lean 社区的 Zulip 讨论称，两个相互独立的内核都接受了相关结果，因此认为内核本身被漏洞利用的可能性较低。这些说法来自社区评论，并非对文章内容的独立确认。

hackernews · archon1410 · 11月20日 17:21 · [社区讨论](https://news.ycombinator.com/item?id=50578358)

**「背景」** 纳维–斯托克斯方程的光滑解是否会在有限时间内产生奇点，是流体力学与偏微分方程中的核心未解问题；欧拉方程作为无粘情形，常被用来研究同一类爆破机制。Tao 在 2026 年 10 月 4 日的文章中已讨论过不可压缩流体中的经典解与奇点形成，本次 11 月 20 日的文章则把无强迫项的欧拉/纳维–斯托克斯奇点与广义黎曼猜想放在同一框架下讨论。

**「影响」** 对关注形式化与 AI 辅助数学的读者，这项讨论的实际落点是：证明助手“构建通过”只说明内核接受了所写下的形式化语句，并不自动说明该语句忠实表达了想要证明的数学命题。有评论者正是以“15 万行乃至上千万行 Lean 代码如何确认证明的是目标命题、而不是一句 1+1=2”提出这一担忧，因此在采信任何形式化结果前，需要核对形式化陈述本身是否与原命题一致。

**「社区讨论」** 评论中较有价值的争论集中在验证的可靠性上：一位评论者质疑大规模 Lean 代码库通过构建是否等于证明了正确的东西，另一位则引用 Lean Zulip 的讨论，称两个独立内核均接受结果，从而降低了内核缺陷导致误判的风险。另有评论者把话题引向更远的问题——现有工具擅长在既有抽象（如 Langlands 纲领这类框架）之上做生成与验证，但新抽象本身如何被创造出来仍未解决。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://terrytao.wordpress.com/2026/10/04/on-classical-solutions-and-singularity-formation-in-incompressible-fluids/">On classical solutions and singularity formation in ...</a></li>

</ul>
</details>

**标签**: `#mathematics`, `#Lean theorem prover`, `#formal verification`, `#AI-assisted theorem proving`, `#Navier-Stokes`

---

<a id="item-tech-news-5"></a>
### [Aaronson 博客讨论随机鹦鹉与 Lean 黎曼猜想证明](https://scottaaronson.blog/?p=10344) ⭐️ 7.0/10

Scott Aaronson 的博客文章讨论了一项说法：LLM 式“随机鹦鹉”系统生成了一个看似黎曼猜想的证明，问题在于它能否借 Lean 通过形式化检查。现有材料没有给出可复核的证明细节，因此这仍是对不确定主张的分析，而不是已确认的数学突破。讨论的核心是 AI 定理证明与形式验证如何区分“生成看似证明的文本”和“证明真正通过检查器”。

hackernews · stratos123 · 11月20日 20:03 · [社区讨论](https://news.ycombinator.com/item?id=50581084)

**「背景」** “随机鹦鹉”是 2021 年流行起来的贬义说法，用来批评大语言模型只会复述训练数据、并不真正理解语言；Aaronson 的帖子借用它，是因为社交媒体上出现了“这些随机鹦鹉刚刚证明了黎曼猜想”的说法。黎曼猜想长期没有公认证明，而这类由 AI 生成的候选证明还必须经过 Lean 等形式化工具逐步核查、并让人能够读懂，相关讨论的焦点正是这种证明是否可信、是否可审查。

**「影响」** 对使用 Lean 的定理证明研究者和评审者而言，可检验的产物应是能独立重放的完整证明脚本；在细节公布前，这项说法无法作为可复用或可评审的结果。

**「社区讨论」** 有评论者把 Lean 与随机预测器的组合概括为“暴力定理求解器”，并认为 AlphaGo 在精神上与此类似；也有人追问，如此多的 Lean 代码是否还能被任何人整体理解。还有评论者引用“我们仍应修补漏洞”一语，认为这种谨慎态度不限于当前语境。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://scottaaronson.blog/?p=10344">Shtetl-Optimized » Blog Archive » The stochastic parrots have ...</a></li>
<li><a href="https://daily.steinslab.io/en/posts/vol-155-2026-11-21/">Anthropic Mathematician Proves GRH in 15 Million Lines of ...</a></li>

</ul>
</details>

**标签**: `#AI theorem proving`, `#LLMs`, `#Lean`, `#formal verification`, `#scientific discovery`

---

<a id="item-tech-news-6"></a>
### [GRH 拟议证明草稿提前公布](https://simonwillison.net/2026/Nov/20/ravi-vakil/) ⭐️ 7.0/10

数学家 Ravi Vakil 宣布，Alessandro Masullo 已提出广义黎曼猜想（GRH）的证明草案，并决定在完整审稿完成前公开当前草稿。Vakil 表示，Brian Conrad 已密切审查该工作数月并给出大量反馈，这些反馈正在被纳入，目前“看起来不错”；他强调该工作完全由人类完成，没有使用 AI。Vakil 原计划让 Masullo 到斯坦福打磨一年、再征求足够多人意见后公布，但现在认为最好先发布现有草稿。该证明仍处于拟议和待审状态，尚不能视为已确立的数学结果。

rss · Simon Willison · 11月20日 19:21

**「背景」** 黎曼猜想是数学界悬而未决 167 年的核心问题，而广义黎曼猜想（GRH）是它更强、更难的推广形式，一旦成立可推出大量关于素数分布的结论。据 Scientific American 报道，此次围绕黎曼猜想的声明实际上出现了“双方对垒”的局面：Vakil 发布的是 Masullo 的人类证明，同期还有一份由 AI 给出的证明声明，两份都尚未被接受。这也解释了 Vakil 为何特意强调该证明“全部由人类完成，没有使用 AI”。

**「影响」** 对研究数论的数学家而言，目前可获得的是待审草稿而非已确认定理，任何依赖 GRH 的论证仍需等待完整审查；Conrad 的反馈正在被纳入，也意味着草稿内容可能继续修改。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.scientificamerican.com/article/dueling-claims-of-riemann-hypothesis-proofs-emerge/">Dueling claims of Riemann hypothesis proofs ... | Scientific American</a></li>
<li><a href="https://techcrunch.com/2026/11/20/ai-claimed-a-solution-to-the-167-year-old-riemann-hypothesis-and-a-human-did-too/">AI claimed a solution to the 167-year-old Riemann Hypothesis — and...</a></li>

</ul>
</details>

**标签**: `#mathematics`, `#Generalized Riemann Hypothesis`, `#research announcement`, `#proof verification`

---

<a id="item-tech-news-7"></a>
### [Levent Alpöge 称与 Claude 证明黎曼猜想，尚无验证](https://simonwillison.net/2026/Nov/20/levent-alpoge/) ⭐️ 7.0/10

Levent Alpöge 在一份 PDF 声明中表示，他与 Claude 合作发现了黎曼猜想的证明，并称该方法可延伸至广义黎曼猜想，预计投入更多时间还能处理扩展黎曼猜想；他还称相关论证已在无额外假设的情况下形式化。该说法目前只是其个人声明，所引内容没有给出证明、形式化代码或独立验证，因此不能视为已确认的数学突破。Simon Willison 的条目仅转载了这段引文并附上原文链接。

rss · Simon Willison · 11月20日 16:30

**「背景」** 黎曼猜想由波恩哈德·黎曼于 1859 年提出，问的是黎曼 ζ 函数的所有非平凡零点是否都落在复平面的临界线 Re\(s\)=1/2 上，一百六十多年来始终无人证明（此前也未有人声称证明成功）。据《科学美国人》报道，Alpöge 将这份与 Claude 合作的证明以 Lean 语言发布；Lean 是证明助手，会逐条机器检查论证是否正确，编码本身可能出错，但专家核验这份证明是否被正确形式化、以及证明本身是否成立，应该用不了太久。Alpöge 的身份是 Anthropic 的数学家。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.scientificamerican.com/article/anthropic-mathematician-claims-to-prove-riemann-hypothesis-most-famous-problem-in-all-of-math/">Anthropic mathematician claims to prove Riemann hypothesis , most...</a></li>
<li><a href="https://www.clarin.com/us-news/who-is-levent-alpoge-the-anthropic-mathematician-who-claims-solved-the-riemann-hypothesis-with-claude_0_2WdGvYKBVM.html">Who is Levent Alpöge ? The Anthropic mathematician who claims he...</a></li>
<li><a href="https://www.nacionale.com/en/articles/has-riemann-hypothesis-been-proved-levent-alpoge-claude-anthropic-claim-lean">Riemann hypothesis proof claimed with Claude , unverified</a></li>

</ul>
</details>

**标签**: `#AI-assisted mathematics`, `#Riemann Hypothesis`, `#Claude`, `#AI for science`, `#unverified claim`

---

<a id="item-tech-news-8"></a>
### [苹果被曝研发自主 AI 智能体](https://www.bloomberg.com/news/articles/2026-11-19/apple-is-working-on-ai-agent-for-device-control-apps-browsing-and-coding) ⭐️ 7.0/10

彭博根据苹果本周新增的招聘信息报道，苹果正招募高级工程经理，主导“主动式 AI 智能体”开发；该智能体可代用户写代码、浏览网页和操控应用，最早 2027 年末推出，项目仍处早期。报道同时称，macOS 27.3 新增警告页，第三方智能体获取 Mac 控制权限的步骤由 4 步增至 14 步。Meta Muse、OpenAI 等已推出同类智能体，但苹果这一项目尚属媒体报道，未获苹果确认，也没有已发布产品可供验证。

telegram · zaihuapd · 11月20日 08:59

**「背景」** 主动式 AI 智能体指能自主规划并跨应用执行多步任务的系统，例如代用户浏览网页、编写代码或操作界面，而不只是回答问题；这类能力通常依赖屏幕读取、输入模拟和应用接口等系统级权限。此前同类智能体主要由 OpenAI、Meta 等第三方厂商推进，平台方如何授权并约束它们，已成为 macOS 等桌面系统面临的新问题。

**「对开发者的影响」** 对第三方 AI 智能体开发者而言，macOS 27.3 把获取 Mac 控制权限的步骤从 4 步增至 14 步并加入警告页，接入时需重新设计授权引导和权限说明，用户授予控制权的摩擦也随之上升。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.moneycontrol.com/news/business/apple-is-building-its-own-ai-agent-and-making-it-harder-for-rivals-to-control-macs-14085248.html">Apple is building its own AI agent and making it harder for ...</a></li>

</ul>
</details>

**标签**: `#Apple`, `#AI agents`, `#macOS`, `#platform security`, `#Bloomberg report`

---

<a id="item-tech-news-9"></a>
### [台积电据报暂停对华 16nm 以下订单](https://appleinsider.com/articles/26/11/20/apple-supplier-tsmc-cuts-off-china-chip-orders-amid-tighter-export-controls) ⭐️ 7.0/10

据该 Telegram 条目转述 AppleInsider 的报道，台积电已通知客户暂停承接中国公司的 16nm 及以下先进制程订单；该消息来自简短转述，尚无台积电或美国监管机构的直接声明可供核实。按收紧后的美国半导体出口新规，除非事先取得美国出口许可或豁免，否则台积电不得向这些中国客户供货。报道称，此前台积电可自行评估客户设计是否符合豁免条件，现在客户须提前申请；美国获批名单包括苹果、AMD 和英伟达，尚无中国公司。若暂停持续，相关中国企业将只能使用 28nm、40nm 等较旧制程，并无法使用 AI 数据中心所需的高带宽内存。

telegram · zaihuapd · 11月21日 02:01

**「背景」** 16nm 及以下属于较先进制程，28nm、40nm 则是更成熟节点；在出口管制框架下，能否列入许可或豁免名单，直接决定客户可否继续在先进节点下单。

**「影响」** 对中国芯片设计公司而言，若无法获得豁免，先进节点订单和 AI 数据中心相关内存供应将受直接限制，需提前申请美国许可或转向成熟制程。

**标签**: `#semiconductors`, `#export-controls`, `#TSMC`, `#China`, `#AI-hardware`

---

<a id="item-tech-news-10"></a>
### [微软发布 USB4 RDMA 预览，多台 PC 合跑本地大模型](https://videocardz.com/newz/microsoft-brings-rdma-over-usb4-to-windows-allowing-multiple-pcs-to-run-one-local-ai-model) ⭐️ 7.0/10

微软发布了面向 Windows 开发者的 RDMA over USB4 预览版，让多台 PC 通过普通 USB4 连接共享内存和 GPU 算力，共同运行同一个本地 AI 模型，无需专用网卡或交换机。微软在三台搭载 AMD Ryzen AI Max+ 395 的机器上，以 4-bit 量化运行 Qwen3-235B-A22B，演示吞吐约为 18.5 token/s。该预览将通过 Windows Insider 推送；目前仍属早期开发者预览，实际部署条件和适用范围尚未披露。

telegram · zaihuapd · 11月21日 06:13

**「背景」** RDMA（远程直接内存访问）通常用于数据中心，让一台机器绕过常规网络协议栈直接读写另一台机器的内存，常见实现依赖 InfiniBand 或 RoCE 等专用网络。USB4 是高速点对点互连标准，并非原生为 RDMA 设计的网络架构；微软的开发者预览把 RDMA 跑在 USB4 上，目的是让普通 Windows 11 PC 无需专用网卡或交换机也能组成共享内存与 GPU 的推理集群。

**「影响」** 对需要在本地运行超出单机内存或显存容量的大模型的 Windows 开发者，这提供了一条复用现有 USB4 端口扩展内存与 GPU 算力的路径；但它是开发者预览，测试者需通过 Windows Insider 获取，且 18.5 token/s 仅是该三机演示的数据，不能当作通用性能保证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://club.dns-shop.ru/digest/189601-windows-11-nauchili-obedinyat-pamyat-i-gpu-pk-cherez-usb4-dlya-lok/">Windows 11 научили объединять память и GPU ПК через...</a></li>

</ul>
</details>

**标签**: `#RDMA`, `#USB4`, `#local AI inference`, `#Windows`, `#distributed computing`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [为什么输出缓存收效有限](https://seangoedecke.com/why-output-caching-doesnt-work/) ⭐️ 6.0/10

rss · Sean Goedecke · 11月21日 00:00

**「背景」** 作者指出，LLM 推理成本优化通常依赖缓存输入（KV cache），以免每轮都重新计算完整对话历史；一个自然的问题是，是否也应缓存或压缩模型输出中的重复内容。Agent 经常被要求复述代码、证据或样例，而输出 token 又明显比输入 token 更贵，因此这看似是值得优化的浪费。

**「方案」** 作者设想通过提示或微调，让模型输出“src/script.py:12-15”这类引用，或引用自身对话历史中的片段，再由运行框架展开，从而避免直接复述。但他认为，这只能优化用户可见的输出，而模型内部思维链通常不必重复已有信息；按他个人 agent 历史的不严谨估计，可见输出仅占约 6%，推理 token 约 50%，工具调用约 44%。因此受 Amdahl 定律约束，即便乐观地省掉可见输出三分之二的 token，也只能减少约 4% 的总输出 token。要真正降低输出成本，应减少不可见的 94%，这主要取决于模型智能：更强的模型需要的推理和工具调用更少，可能单 token 贵 5 倍，但总 token 少 6 倍，整体反而更便宜。作者也承认，自己对前沿模型思维链是否重复只有中等信心，工具调用内部是否重复仍有待验证。

**「启示」** 输出缓存的根本局限在于，它瞄准的是占比很小的可见重复，而非占据绝大多数的推理与工具调用 token；降低 LLM 输出成本的关键，更可能是用更聪明的模型和更好的运行框架减少“看不见”的工作量。

**标签**: `#LLM inference economics`, `#output caching`, `#Amdahl&\#x27;s law`, `#token costs`, `#AI agents`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [沃什避免前瞻指引，美联储官员却更频繁谈论加息](https://www.cnbc.com/2026/11/20/warsh-fed-forward-guidance-rate-hikes.html) ⭐️ 7.0/10

美联储主席凯文·沃什上任六个月来一直避免就利率走向提供前瞻指引，但其同僚正更频繁地公开谈论加息，多数官员支持近期加息。CME Group 的 FedWatch 显示，交易员预计美联储 12 月至少加息 25 个基点的概率为 100%。

rss · CNBC Finance · 11月20日 21:10

**「背景」** 沃什于 2026 年 6 月上任后，把美联储会后声明压缩至 132 词并取消“前瞻指引”，即央行通过公开表态预示未来利率路径的做法。美联储自 2000 年代初起就在声明中用这一工具，在真正调整利率前向市场传递信号。

**「市场影响」** 据芝商所 FedWatch 的隐含概率，交易员认为 12 月至少加息 25 个基点的可能性为 100%；这意味着信用卡、浮动利率贷款等与短期利率挂钩的借贷成本，可能会比此前预期更早上升。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.financialexpress.com/market/global-market-pulse/why-fed-chair-warsh-scrapped-forward-guidance-in-a-132-word-pivot/4272071/">Why Fed Chair Warsh scrapped forward guidance in a 132-word ...</a></li>
<li><a href="https://www.federalreserve.gov/faqs/what-is-forward-guidance-how-is-it-used-in-the-federal-reserve-monetary-policy.htm">What is forward guidance, and how is it used in the Federal ...</a></li>

</ul>
</details>

**标签**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#FOMC communication`, `#Kevin Warsh`

---

<a id="item-finance-news-2"></a>
### [美国企业转向净发行股票，规模达市值的 3.1%](https://www.cnbc.com/2026/11/20/equity-issuance-bull-market-problem.html) ⭐️ 7.0/10

据 CNBC 报道，美国企业已从股票回购转向净发行股票；Acadian Asset Management 的分析显示，截至上周晚些时候，净发行量相当于美国股市总市值的 3.1%，为持续四年的牛市增加了股票供给。

rss · CNBC Finance · 11月20日 14:15

**「背景」** 过去多年，企业回购会减少流通股数量，在盈利不变时抬高每股收益并支撑股价；如今净发行增加股票供给，Acadian 将其视为市场的潜在逆风。

**标签**: `#equity issuance`, `#share buybacks`, `#IPO market`, `#AI infrastructure financing`, `#US stock market`

---

<a id="item-finance-news-3"></a>
### [北京就租房合同示范文本征求意见：正常损耗不得扣减押金](https://mp.weixin.qq.com/s/PmGxh5knIyxiBRhpRoJnoQ) ⭐️ 7.0/10

北京市住建委与市场监管局起草的《北京市住房租赁合同（示范文本）（修订征求意见稿）》自 11 月 20 日起公开征求意见，拟明确承租人正常使用造成的房屋正常损耗不承担赔偿责任，出租人不得以此为由扣减押金；征求意见稿还要求从事转租经营的租赁企业将租金和押金付至监管账户，细化押金托管与租金监管要求，并新增保密和个人信息保护条款。该文件目前为公开征求意见的示范文本草案，尚未成为最终生效规则。

telegram · zaihuapd · 11月20日 13:46

**「背景」** 住房租赁合同示范文本是住建部门发布、供房东与租客签约时参照的合同范本，此次北京是在现行文本基础上修订，细化了押金托管（即押金交由第三方账户监管）与租金监管要求，并再次公开征求意见。

**「影响」** 若最终落地，北京的租客在退租时面对“正常损耗”扣款将有明确依据，出租人以此扣减押金的理由受限，从事转租的租赁企业则须把收付的租金和押金纳入监管账户。

**标签**: `#housing rental`, `#Beijing policy`, `#tenant protections`, `#deposit regulation`, `#public consultation`

---