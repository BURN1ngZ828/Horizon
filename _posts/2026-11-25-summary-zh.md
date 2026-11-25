---
layout: default
title: "Horizon Summary: 2026-11-25 (ZH)"
date: 2026-11-25
lang: zh
---

> 从 33 条内容中筛选出 9 条重要资讯。

---

**科技新闻**
1. [vCenter 曝 9.8 分鉴权绕过漏洞，补丁前疑遭零日利用](#item-tech-news-1) ⭐️ 8.0/10
2. [OpenAI math 仓库预印本声称矩阵乘法复杂度为 Θ\(n^2.25\)](#item-tech-news-2) ⭐️ 7.0/10
3. [GreyNoise 披露针对 Check Point 安全管理服务器的入侵活动](#item-tech-news-3) ⭐️ 7.0/10
4. [社区项目尝试在 Windows 运行泄露的《GTA 6》Xbox 版](#item-tech-news-4) ⭐️ 7.0/10
5. [三元量化模型 Bonsai 2.5 27B 引发本地推理实测讨论](#item-tech-news-5) ⭐️ 7.0/10
6. [Simon Willison 回顾 LLM 与编程智能体的三个拐点](#item-tech-news-6) ⭐️ 7.0/10
7. [GPT-6.2 Astra 用 22 分钟识别 1808 年匿名素描本作者](#item-tech-news-7) ⭐️ 7.0/10

**财经新闻**
1. [纽约联储威廉姆斯：美联储仍需行动使通胀回到 2%](#item-finance-news-1) ⭐️ 7.0/10
2. [SpaceX 放弃 7.38 亿美元联邦宽带补贴，改为免费提供星链设备](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [vCenter 曝 9.8 分鉴权绕过漏洞，补丁前疑遭零日利用](https://thehackernews.com/2026/11/vmware-vcenter-hit-by-another-critical.html) ⭐️ 8.0/10

Broadcom 为 VMware 产品线发布了覆盖 23 个漏洞的补丁，其中核心是 vCenter 目录服务（vmdir）的鉴权绕过漏洞 CVE-2026-123903，CVSS 评分为 9.8。该漏洞无需认证，只要能够访问 vCenter，就可绕过认证进入系统。报道指出，该漏洞在补丁发布前几天已被作为零日漏洞利用；这一利用情况来自报道，尚缺厂商独立确认。

telegram · zaihuapd · 11月24日 14:50

**「背景」** vCenter 是集中管理 ESXi 主机、虚拟机及相关权限的控制平面；此次漏洞位于其目录服务 vmdir，该组件承担身份目录与认证相关功能。报道还提到，在 Broadcom 发布补丁前几天，这一鉴权绕过已被作为零日利用，因此对暴露在外的 vCenter 管理面而言，修复时间窗口尤为关键。

**「处置影响」** 对运维团队而言，只要 vCenter 可从网络访问，攻击者就可能绕过认证，而 Broadcom 未列出可用的变通方案，因此应优先部署本轮补丁并收紧 vCenter 的网络暴露。同一批修复还覆盖 ESX、Workstation、Fusion 和 Avi Load Balancer，相关环境需要一并核对受影响版本。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.rescana.com/post/vmware-vcenter-cve-2026-123903-auth-bypass-and-esx-code-execution-patch-now">VMware vCenter Auth Bypass CVE-2026-123903 and ESX Code ...</a></li>
<li><a href="https://aviatrix.ai/threat-research-center/vmware-vcenter-critical-auth-bypass-cve-2026-123903-armory-castle/">VMware vCenter CVE-2026-123903: Critical 9.8 Auth Bypass ...</a></li>

</ul>
</details>

**标签**: `#vCenter`, `#VMware`, `#authentication bypass`, `#zero-day`, `#CVE-2026-123903`

---

<a id="item-tech-news-2"></a>
### [OpenAI math 仓库预印本声称矩阵乘法复杂度为 Θ\(n^2.25\)](https://github.com/openai/math/blob/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/paper.pdf) ⭐️ 7.0/10

Hacker News 上出现了一个指向 OpenAI math 仓库的预印本链接，其标题声称矩阵乘法的复杂度为 Θ\(n^2.25\)。但当前材料只有标题和 PDF 链接，没有摘要、证明细节或独立验证，且链接路径标注的日期为 2026 年 11 月，因此这仍是一项待核实的声明，而非已确立的结果。对算法与复杂度理论读者而言，若该证明成立，将直接涉及矩阵乘法的精确指数；在获得论文内容和外部复核前，不宜把评论中的“9/4”“解决 Top 500 问题”等说法当作事实。

hackernews · E-Reverance · 11月25日 01:19 · [社区讨论](https://news.ycombinator.com/item?id=50637220)

**「背景：矩阵乘法指数的长期格局」** 矩阵乘法指数 ω 是使两个 n×n 矩阵能在 O\(n^ω\) 时间内相乘的指数下确界：输出本身就有 n² 个元素，因此 ω≥2 是平凡下界，而自 Strassen 1969 年的算法之后，上界被反复改进，下界却长期停留在 2。该论文摘要称其证明「平方矩阵乘法的指数在每个域上均为 9/4」，也就是用一个相匹配的下界把 ω 确定为 9/4；CryptoBriefing 的报道称，这会是 1979 年以来该指数界最大的一次变动。

**「对算法研究的影响」** 对算法研究者而言，若该证明通过独立审阅，一般矩阵乘法的渐进指数将被钉在 9/4：继续寻找更低的通用指数不再有意义，研究重点会转向常数因子、实际可实现的算法以及特殊矩阵结构。但当前仍是预印本，评论中对上下界的表述也存在分歧；在独立验证前，开发者不应据此调整生产实现。

**「社区讨论」** 评论中最具体的技术分歧是结果的含义：有评论者指出标题应写作 Θ\(n^2.25\) 而非 O\(n^2.25\)，并称论文证明的是下界 Ω\(n^2.25\)，而 2.25 的上界此前已知；另一条评论则称相关论文给出所有域上的精确指数 9/4，并把它与多个 Top 500 公开问题联系起来，但这些说法均未在提供材料中验证。另有评论把 OpenAI、Anthropic 的近期数学成果与贝尔实验室作比较，质疑其公共价值，或猜测成果来自未公开模型，这些属于观点和推测。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://raw.githubusercontent.com/openai/math/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/paper.pdf">The matrix multiplication exponent is nine fourths</a></li>
<li><a href="https://cryptobriefing.com/openai-matrix-multiplication-exponent-9-4/">OpenAI preprint claims the matrix multiplication exponent is ...</a></li>
<li><a href="https://interestingengineering.com/culture/openai-exact-2-25-matrix-multiplication-exponent">OpenAI establishes exact 2.25 exponent for matrix multiplication</a></li>
<li><a href="https://gradientdamage.com/videos/l-bpl-matrix-multiplication-exponent-integer-multiplication-and-6-more/">L = BPL, Matrix Multiplication Exponent , Integer... | Gradient Damage</a></li>

</ul>
</details>

**标签**: `#algorithms`, `#matrix multiplication`, `#computational complexity`, `#OpenAI`, `#Hacker News`

---

<a id="item-tech-news-3"></a>
### [GreyNoise 披露针对 Check Point 安全管理服务器的入侵活动](https://www.greynoise.io/blog/check-point-security-management-servers-intrusion-campaign) ⭐️ 7.0/10

GreyNoise 报告了一起针对 Check Point 安全管理服务器的活跃入侵活动：攻击者反复请求登录端点，并收集 JavaScript Math.random\(\) 的输出，以此重建 Node.js V8 伪随机数生成器的内部状态，进而恢复会话 cookie 的签名密钥，再伪造管理员会话 cookie。评论中引述的报告细节称，相关扫描与利用从 2026 年 10 月 2 日开始；被针对的是 HFS 服务器的 loginSrp1 端点，每次 POST 都会返回一个含 sid 值的新签名会话 cookie。报告将 CVE-2026-16232 列为可能的初始入口，但评论者指出，报告并未说明攻击者最初如何进入这些系统，也未说明受影响的 Check Point 客户是否都把管理服务器暴露在互联网上。

hackernews · louiereederson · 11月24日 16:32 · [社区讨论](https://news.ycombinator.com/item?id=50630594)

**「背景：已披露的 SmartConsole 认证绕过漏洞」** 这轮攻击利用的是 Check Point 于 2026 年 7 月公开的 CVE-2026-16232：该漏洞可通过应用令牌绕过 SmartConsole 登录认证，且当时已观察到在野利用。Check Point 随后确认该漏洞正被利用，但称受影响的客户数量“非常少”；因此当前活动属于这一已披露漏洞的后续利用，而非全新的未公开漏洞。

**「影响」** 对运行 Check Point 安全管理服务器的组织而言，直接后果是：只要管理界面可从互联网访问，攻击者在拿到 cookie 签名密钥后，无需口令即可伪造管理员会话。因此需要把管理面收敛到受控网络，并按厂商指引修补或排查失陷迹象；在初始入口尚未确认的情况下，仅封堵 CVE-2026-16232 是否足够仍无定论。

**「社区讨论」** 有评论者认为，根本问题在于 Math.random\(\) 这类非密码学安全的随机数；他质疑，为什么要逐个修补误用它的应用，却不直接让随机数生成器本身更安全。另有评论者预测，LLM 会降低攻击门槛，使更多犯罪者能够自动化攻击在线服务乃至关键基础设施。这属于个人判断，而非已证实的事实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.bleepingcomputer.com/news/security/hackers-compromise-check-point-servers-in-22-organizations/">Hackers compromise Check Point Servers in 22 organizations</a></li>
<li><a href="https://support.checkpoint.com/results/sk/sk185169/">sk185169 - CVE - 2026 - 16232 - Authentication bypass with...</a></li>

</ul>
</details>

**标签**: `#cybersecurity`, `#Check Point`, `#intrusion campaign`, `#PRNG`, `#session cookies`

---

<a id="item-tech-news-4"></a>
### [社区项目尝试在 Windows 运行泄露的《GTA 6》Xbox 版](https://twitter.com/raul_bs3/status/2125213756238291075) ⭐️ 7.0/10

一条提交到 Hacker News 的推文声称，《GTA 6》可以在 Windows 上运行。据评论介绍，xcl 和 VIctory 等项目采用类似 Wine 的兼容或重编译路线；由于现代 Xbox 架构接近 Windows PC，且该二进制没有特殊 DRM 或混淆，主要难点集中在兼容层和图形表现。泄露内容据称由 Cyberleek 先发布资源、后发布游戏二进制；这并非 Rockstar 官方 PC 版，因此当前展示仍属非官方、未经验证的社区成果，并涉及法律风险。

hackernews · andrem · 11月24日 13:19 · [社区讨论](https://news.ycombinator.com/item?id=50627783)

**「背景」** 背景是，现代 Xbox 主机与 Windows PC 的架构接近，社区因此尝试用 Wine 式兼容层或静态重编译，让 Xbox 版《GTA 6》在 Windows 上运行；相关项目包括 XCL、VIctory、Xbox 2 Windows 和 Leonida。其中 Xbox 2 Windows 的项目说明称，它研究把选定机器码转为 C++、把选定着色器转为桌面 DXIL，但完整游戏启动仍未验证。

**「法律风险与下架后果」** 对想尝试的玩家和开发者来说，最直接的影响来自发行商的法律行动：The Verge 报道称，Take-Two 的 DMCA 通知已让粉丝重编译项目 Leonida 下架，另有追踪页面称该通知波及 3,007 个 GitHub 仓库。这类项目需要用户自备泄漏版 Xbox 构建的文件，因此在官方 PC 版问世前，参与者面临的是仓库随时被删除、缺少稳定兼容性支持的风险，而非可持续的替代方案。

**「社区讨论」** 评论中，Tiberium 认为现代 Xbox 与 Windows PC 足够接近，二进制又无特殊 DRM 或混淆，因此真正要解决的是兼容性与图形问题；pipes 则质疑为何必须依赖泄露的 Xbox 构建，并担心未来游戏会把关键组件放到云端以阻止反编译和移植。另有评论认为，即便出现这类非官方运行方案，也不会实质削弱《GTA 6》的商业成功。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://gta6recomp.com/repo">Repositories &amp; Groups — GTA 6 Recomp</a></li>
<li><a href="https://leonidapc.wiki/gta-6-pc-port/">GTA 6 PC Port Projects : Leonida, Xbox 2 Windows and More</a></li>
<li><a href="https://gta6.fyniti.co.uk/">GTA 6 PC Port Tracker: Does GTA VI Run on PC Yet? | Live Progress</a></li>
<li><a href="https://www.theverge.com/news/1041690/grand-theft-auto-6-pc-recompilation-project-leonida-takedown-take-two">GTA VI PC recompilation project shut down by Take - Two | The Verge</a></li>

</ul>
</details>

**标签**: `#game recompilation`, `#Xbox compatibility`, `#reverse engineering`, `#open-source projects`, `#GTA 6`

---

<a id="item-tech-news-5"></a>
### [三元量化模型 Bonsai 2.5 27B 引发本地推理实测讨论](https://prismml.com/news/bonsai-2-5-27b) ⭐️ 7.0/10

27B 的三元量化本地模型 Ternary Bonsai 2.5 27B 已发布，主打在消费级内存内做快速量化推理。有用户报告其 Q2 GGUF 版本在 24GB 内存的 Mac Mini M5 Pro 上生成速度约 22–25 tokens/s、首 token 约 2.12 秒，并能把 128k 上下文放进内存。另有评论称该模型在 SWE-bench Verified 上的成绩接近 Opus 4.6，但这只是个人观察，而且本次未取得厂商公告原文，基准分数与实机表现仍需独立验证。

hackernews · b0m · 11月24日 20:08 · [社区讨论](https://news.ycombinator.com/item?id=50633922)

**「背景」** Ternary Bonsai 2.5 27B 属于 PrismML 的三值（ternary）量化模型家族，是此前 Bonsai 2 27B 的升级版；官方文档称其架构直接沿用 Qwen3.8 27B 这一混合注意力因果语言模型，并未改动，同时保留上一版约 5.9 GB 的模型体积。三值量化的意义在于把 27B 参数的模型压缩到消费级设备可运行的内存占用，这也是社区评论集中在 Mac 本地推理速度和长上下文可用性的原因。

**「对本地部署者的实际影响」** 对在消费级硬件上跑本地模型的开发者来说，最直接的变化是内存占用：有用户报告在 24GB 内存的 Mac Mini 上可轻松容纳 128k 上下文，生成速度约 22–25 token/s，这使得同一台机器上做批量或代理式编码任务变得可行。模型以 GGUF 形式在 Hugging Face 发布并可通过 vLLM 部署，方便团队在自有 2-bit 量化基线上复测 Terminal-Bench 2.1 与 SWE-bench Verified；但上述速度仅为单用户轶事，量化版本相对其他 IQ2 构建的领先幅度来自厂商自述，需自行验证。

**「社区讨论」** 多位用户报告了可用的实机体验：有人称其速度与 Q4 量化的 Inkling 2 mini 相当（prefill 约 300 tok/s、生成约 30 tok/s），并认为 agentic 调用表现稳定、优于旧版 Bonsai 2；也有人用自建长任务基准测得通过数不变（8 项中 5 项）但步数减少 17%、耗时减少 29%。同时有评论质疑基准榜上该模型的分数其实低于 Qwen，并怀疑存在“刷榜”成分，提醒需区分榜单成绩与实际能力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://docs.prismml.com/models/bonsai-2-5-27b">Ternary Bonsai 2.5 27B - Bonsai - docs.prismml.com</a></li>
<li><a href="https://prismml.com/news/bonsai-2-5-27b">PrismML — Introducing Ternary Bonsai 2.5 27B: Powering ...</a></li>
<li><a href="https://prismml.com/news/bonsai-2-5-27b">PrismML — Introducing Ternary Bonsai 2 . 5 27 B : Powering Agentic...</a></li>
<li><a href="https://huggingface.co/prism-ml/Ternary-Bonsai-2.5-27B-GGUF">prism-ml/ Ternary - Bonsai - 2 . 5 - 27 B -GGUF · Hugging Face</a></li>

</ul>
</details>

**标签**: `#local LLMs`, `#model quantization`, `#agentic coding`, `#SWE-bench`, `#on-device inference`

---

<a id="item-tech-news-6"></a>
### [Simon Willison 回顾 LLM 与编程智能体的三个拐点](https://simonwillison.net/2026/Nov/24/llm-inflection-points/) ⭐️ 7.0/10

Simon Willison 在 11 月 24 日的回顾文章中，把过去 12 个月 LLM 与编程智能体的进展归纳为三个拐点，而非宣布新模型发布。他指出，2025 年 11 月的 Claude Opus 4.5 与 OpenAI GPT-5.1/Codex 让编程智能体对日常任务通常直接给出可用结果，其中 Opus 4.5 发布至今已一年。他把 2026 年 6-7 月的 Claude Fable 5 及其后续版本称为“Fable 类模型”，特征是给定目标和工具后能自行推进复杂问题，并把 Opus 5.5、GPT-6 Astra 和可能 Gemini 4 Neon 纳入这一档。第三个拐点是 2026 年 9-10 月前后模型在 3D 建模与游戏开发上的跃升，Opus 5.5 曾进行 12 小时试玩并重新平衡一款 RTS；文章在讨论 Fable 5.2 是否也是拐点时截断。

rss · Simon Willison · 11月24日 23:02

**「背景」** Claude Code 于 2025 年 2 月 24 日随 Claude 3.7 Sonnet 一同发布，因此到 2025 年 11 月 24 日 Claude Opus 4.5 问世时，这款编程代理只有九个月历史。同一时期，OpenAI 也发布了 GPT-5.1 Instant、GPT-5.1 Thinking、GPT-5.1-Codex 和 GPT-5.1-Codex-Max，使两家厂商的编程代理几乎同时具备了新的可用性基线。

**「影响」** 对使用编程智能体的开发者而言，这篇回顾给出的可操作判断是：评估工具时应重点看默认结果是否需要频繁纠正，而不是只看演示效果；面对复杂任务，则应看模型在获得必要工具后能否自行推进。

**标签**: `#LLM coding agents`, `#AI engineering`, `#model capabilities`, `#Claude Opus 4.5`, `#developer tooling`

---

<a id="item-tech-news-7"></a>
### [GPT-6.2 Astra 用 22 分钟识别 1808 年匿名素描本作者](https://simonwillison.net/2026/Nov/24/astra-historical-mystery/) ⭐️ 7.0/10

历史学教授 Mark Humphries 报告，GPT-6.2 Astra 在仅需少量提示的情况下，用 22 分钟自主识别出耶鲁大学 Beinecke 图书馆所藏一本 1808 年匿名素描本的创作者。它使用公开的一手和二手资料，在纸质档案中找到一条关于 vicomte de Chabot 到访的日记线索，日期比素描本中提到的附近河流日期早五天，并推测 Chabot 的旅行日记——只能向克利夫兰州立大学订购——可确认作者身份；据称查验结果支持了该假设。该案例由 Simon Willison 转述，属于单次轶事性演示，不能证明此类自主研究代理的普遍可靠性，关键档案的获取也仍依赖人工订购。

rss · Simon Willison · 11月24日 16:53

**「背景」** 耶鲁大学拜内克图书馆收藏的这本 1808 年素描册已数字化，但作者身份不明。Astra 的识别路径依赖一条档案线索：日记中提到沙博子爵（vicomte de Chabot）在素描册所记日期前五天访问附近河流，而沙博的旅行日记只能向克利夫兰州立大学订购，Astra 据此提出该日记可用来验证素描册出自沙博之手。

**「影响」** 对历史研究者和构建研究代理的开发者而言，这个案例把实际瓶颈放在两处：一是对代理提出的档案线索和作者归属做人工复核，二是获取需要向克利夫兰州立大学订购的 Chabot 日记。Humphries 也认为，历史学不像数学那样追求单一普遍真理，因此即便代理能完成这类检索，历史写作与解释仍需人的判断。

**标签**: `#AI research agents`, `#LLM applications`, `#autonomous agents`, `#historical research`, `#AI capabilities`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [纽约联储威廉姆斯：美联储仍需行动使通胀回到 2%](https://www.cnbc.com/2026/11/23/john-williams-fed-inflation-rate-hikes.html) ⭐️ 7.0/10

纽约联储主席威廉姆斯表示，美联储仍有工作要做才能把通胀降回 2%，并称进一步行动可以随着时间推进；市场已完全计入 12 月会议将基准利率目标区间从 3.75%-4%上调 25 个基点的预期。

rss · CNBC Finance · 11月24日 13:33

**「背景」** 美联储的通胀目标是 2%，当前基准利率目标区间为 3.75%-4%，通胀仍远高于目标；负责决策的联邦公开市场委员会将于 12 月 8-9 日开会，官员们对加息快慢存在分歧。

**标签**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#inflation`, `#John Williams`

---

<a id="item-finance-news-2"></a>
### [SpaceX 放弃 7.38 亿美元联邦宽带补贴，改为免费提供星链设备](https://x.com/SawyerMerritt/status/2125314062997467640) ⭐️ 7.0/10

SpaceX 已同意放弃 7.38 亿美元美国联邦宽带补贴，改为在 NTIA 的 BEAD 计划下签署「零支出协议」，向符合条件的美国家庭免费提供星链终端，联邦拨付金额为 0 美元。按条款，SpaceX 须保证最低 100 Mbps 下载、20 Mbps 上传，提供低价月费套餐，承诺服务 10 年并接受与其他 BEAD 受资助方相同的交付时间表和性能测试，同时豁免大部分财务审计、采购和行政报告义务。

telegram · zaihuapd · 11月25日 02:17

**「背景」** BEAD（宽带公平、接入与部署计划）是美国国家电信与信息管理局（NTIA）管理的联邦宽带建设补贴项目，受资助方通常须接受财务审计、采购和行政报告等监督。SpaceX 原本在该计划下享有 7.38 亿美元补贴额度，此次以放弃这笔资金换取大部分合规义务豁免；阿拉斯加也出现过类似安排，SpaceX 可放弃 2360 万美元、涉及 1.57 万个星链已覆盖站点。

**「影响」** 对符合条件的美国服务不足地区家庭，免费终端降低了接入星链的前期成本，但月费仍需自付；据 PhoneArena 报道，星链已把六项套餐月费上调 5 至 10 美元，实际负担仍取决于低价套餐的定价。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://alaskanews.com/c/alaska-news/new-deal-would-let-spacex-skip-its-236-million-alaska-grant-and-much-of-the-oversight">New deal would let SpaceX skip its $23.6 million ... | Alaska News</a></li>
<li><a href="https://www.phonearena.com/news/starlink-price-increase-monopoly_id181266">Starlink slammed for leaving users worse off, but critics... - PhoneArena</a></li>

</ul>
</details>

**标签**: `#SpaceX`, `#Starlink`, `#BEAD`, `#US broadband policy`, `#NTIA`

---