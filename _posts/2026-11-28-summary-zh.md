---
layout: default
title: "Horizon Summary: 2026-11-28 (ZH)"
date: 2026-11-28
lang: zh
---

> 从 30 条内容中筛选出 10 条重要资讯。

---

**科技新闻**
1. [Unkernel 将真实 Linux 内核编译为 WebAssembly](#item-tech-news-1) ⭐️ 8.0/10
2. [Linux 内核 nfsd 曝 9.8 分预认证漏洞，可获取 root](#item-tech-news-2) ⭐️ 8.0/10
3. [Michael Nielsen 的神经网络教材已从原站下线](#item-tech-news-3) ⭐️ 7.0/10
4. [Convex AI skill 被指未披露上传用户应用构想](#item-tech-news-4) ⭐️ 7.0/10
5. [计算机检查的证明仍可能为假](#item-tech-news-5) ⭐️ 7.0/10
6. [利用 WebRTC 的信用卡盗刷脚本现身热门购物网站](#item-tech-news-6) ⭐️ 7.0/10
7. [多州总检察长起诉 SpaceX，要求阻止 Grok 生成儿童性虐待与未经同意的私密图像](#item-tech-news-7) ⭐️ 7.0/10
8. [SemiAnalysis 深挖 Trainium3：瓦片优先架构与推理每美元性能](#item-tech-news-8) ⭐️ 7.0/10

**财经新闻**
1. [央行发布大额存单新规 个人起购门槛降至 10 万元](#item-finance-news-1) ⭐️ 7.0/10
2. [市场监管总局约谈 15 家电动自行车企业](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Unkernel 将真实 Linux 内核编译为 WebAssembly](https://unkernel.dev/) ⭐️ 8.0/10

Unkernel 项目将真实的 Linux 内核编译为 WebAssembly，目标是让 Linux 环境直接在浏览器中运行；项目地址为 unkernel.dev，此次因 Hacker News 讨论获得关注。现有材料没有给出版本号、基准测试或兼容性范围，因此“启动很快”和 Wayland 合成器表现目前只是社区参与者的体验描述，而非独立测量结果。

hackernews · nreece · 11月28日 03:19 · [社区讨论](https://news.ycombinator.com/item?id=50674218)

**「技术背景」** Unkernel 的做法是把 Linux 内核本身直接编译为 WebAssembly，而不是只把某个应用移植到浏览器。用户程序运行在 kwemu 上：这是一个用 Zig 编写并链接进内核的 aarch64 CPU 模拟器，它会遍历内核自己的页表，因此内存管理仍由真实的 Linux 代码完成。

**「实际影响」** 对教育或培训场景而言，若该方案如社区描述那样可用，学生可在浏览器标签页中获得 Linux 环境，从而减少为每个实例配置传统虚拟机的运维工作；但这一收益来自评论者的预期，项目在给定材料中未说明资源占用、持久化存储或设备兼容性。

**「社区讨论」** gregbell 称启动速度很快、Wayland 合成器性能“疯狂”，并表示自己已基于 Unkernel 做了二次项目；mareimorsy 认为教育平台可用近乎零服务器成本为每名学生提供 Linux 环境，lucamark 则半开玩笑地担心五年后浏览器标签页里会运行什么。这些是参与者的体验和预期，材料未提供基准数据或成本测算。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/pithings/unkernel">pithings/ unkernel : A real Linux kernel , compiled to WebAssembly .</a></li>

</ul>
</details>

**标签**: `#WebAssembly`, `#Linux kernel`, `#browser computing`, `#virtualization`, `#Wayland`

---

<a id="item-tech-news-2"></a>
### [Linux 内核 nfsd 曝 9.8 分预认证漏洞，可获取 root](https://opensec.in/blog/nfs2root-cve-2026-99362) ⭐️ 8.0/10

OpenSec 披露 Linux 内核 NFS 服务器组件 nfsd 存在预认证堆溢出漏洞 CVE-2026-99362，CVSS 评分为 9.8；据其描述，攻击者无需登录，只需向 tcp/2049 发送一条连接，即可越界写入内核堆并取得 root shell。该漏洞自 2014 年的 Linux 3.16 起存在，影响启用 NFSv4.1 或 4.2 的文件服务器、NAS 和集群存储节点。修复版本为 6.12.117、6.18.61、7.3.2 和 7.4-rc1，升级内核后需重启；无法立即升级的环境可按披露建议用防火墙限制 tcp/2049 访问。CVE 于 2026 年 11 月 20 日公开，目前信息来自 OpenSec 的单一披露，尚待独立验证。

telegram · zaihuapd · 11月27日 12:57

**「背景」** nfsd 是 Linux 内核内置的 NFS 服务器，默认在 tcp/2049 上提供 NFSv4.1/4.2 服务；该漏洞被称为“预认证”漏洞，意味着任何能连到该端口的攻击者都可在完成登录前触发内核堆越界写入。据 OpenSec 说明，这一缺陷自 2014 年的 Linux 3.16 起就已存在，因此长期未升级内核的主机同样落在受影响范围内。

**「影响与处置」** 运行受影响内核且启用 NFSv4.1/4.2 的服务器、NAS 和存储节点应尽快升级到上述修复版本并重启；在完成升级前，限制 tcp/2049 只能作为临时缓解，不能替代内核修复。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://opensec.in/blog/nfs2root-cve-2026-99362">NFS 2ROOT ( CVE - 2026 - 99362 ): pre-auth root in Linux nfsd | OpenSec</a></li>
<li><a href="https://www.bleepingcomputer.com/news/security/new-nfs2root-linux-flaw-can-let-attackers-gain-root-privileges/">New NFS 2ROOT Linux flaw can let attackers gain root privileges</a></li>

</ul>
</details>

**标签**: `#Linux kernel`, `#NFS`, `#security vulnerability`, `#CVE`, `#remote exploit`

---

<a id="item-tech-news-3"></a>
### [Michael Nielsen 的神经网络教材已从原站下线](https://neuralnetworksanddeeplearning.com/) ⭐️ 7.0/10

Michael Nielsen 的免费在线书《Neural Networks and Deep Learning》已从其原网站 neuralnetworksanddeeplearning.com 下线，原有读者无法再在原址直接阅读。来源条目没有说明下线原因、持续时间或作者声明，因此目前只能确认该站点不再提供这本书。Hacker News 上的部分评论者将此视为一种抗议，并讨论 AI 知识公开与前沿实验室激励之间的关系，但这些属于社区解读，并非已证实的事实。

hackernews · brandonb · 11月27日 19:31 · [社区讨论](https://news.ycombinator.com/item?id=50670757)

**「背景」** 《Neural Networks and Deep Learning》是 Michael Nielsen 编写的免费在线书，用于讲解神经网络与深度学习的基础概念，其页面此前标注的版本时间为 2019 年 12 月。该书的配套代码公开在 GitHub 的 mnielsen/neural-networks-and-deep-learning 仓库中，因此它原本是一个可直接在线阅读并配合代码实践的教材。

**「影响」** 对依赖该书免费学习神经网络基础的学生和开发者而言，原链接失效会中断直接访问；评论中已经出现 Internet Archive 存档，以及将内容整理为标注 CC BY-NC 的 PDF 的第三方替代入口，但这些副本并非作者当前维护的版本，使用前需核对授权与内容完整性。

**「社区讨论」** 有评论者认为撤下教材是错误，理由是不让外部了解大公司内部技术会削弱公众对 AI 后果的判断；另一些人则认为这更像象征性抗议，实际效果有限，反而可能让更多人去寻找这本书。还有评论指出，资本投入也在推动前沿实验室竞争，并影响人们参与这类工作的意愿。

<details><summary>参考链接</summary>
<ul>
<li><a href="http://neuralnetworksanddeeplearning.com/">Neural networks and deep learning</a></li>
<li><a href="https://github.com/mnielsen/neural-networks-and-deep-learning">GitHub - mnielsen/ neural - networks - and - deep - learning : Code...</a></li>

</ul>
</details>

**标签**: `#AI education`, `#open access`, `#neural networks`, `#community debate`, `#AI ethics`

---

<a id="item-tech-news-4"></a>
### [Convex AI skill 被指未披露上传用户应用构想](https://github.com/convex/convex-backend-skill/issues/64) ⭐️ 7.0/10

一个 GitHub issue 指控 Convex 的 AI skill 在未告知用户的情况下，将用户的应用构想或提示上传到远程服务器，相关讨论在 Hacker News 上引发关注，并得到 Convex CEO Jamie 的回应。Jamie 称，插件中的提示上传服务于 Convex 的“quickstart”功能，而该功能是最近关闭的 Convex Chef 的精神继承者；他把 Convex 描述为一个存储用户数据和代码的平台。现有材料没有明确上传是否默认开启、数据如何保留以及用户能否关闭，因此这仍是一场关于披露和透明度的争议，而非已确认的恶意行为。

hackernews · MickyTheMouse · 11月27日 18:02 · [社区讨论](https://news.ycombinator.com/item?id=50669765)

**「背景」** Convex 的 quickstart 技能位于 convex-backend-skill 仓库；2026 年 10 月 26 日出现的第 64 号 issue 指控该技能会把用户的应用想法发送到 convex.site 主机并运行远程脚本，且相关写法意在避开安全检查。讨论中，Convex CEO Jamie 回应称，插件里的提示上传用于支撑 quickstart，而 quickstart 被定位为已关闭的 Convex Chef 的精神继任者。

**「影响」** 对采用 AI 编程插件或 skill 的开发者而言，这意味着不能默认应用构想和提示只留在本地：在输入专有架构或业务逻辑前，应先确认插件是否上传提示、上传到何处以及能否关闭。对可审计性和自托管有要求的团队，可能需要优先选择明确披露遥测的插件或本地模型方案。

**「社区讨论」** 评论中，有人主张长期看自托管开放权重模型更可控，也有人指出提示注入比模型自行发起恶意工具调用更常见，应把此次上传争议与恶意行为区分开；还有读者以“想法不值钱”淡化对应用构想外泄的担忧。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/convex/convex-backend-skill/issues">Issues · convex/convex-backend-skill · GitHub</a></li>
<li><a href="https://github.com/convex/convex-backend-skill/blob/main/commands/quickstart.md">convex-backend-skill/commands/quickstart.md at main - GitHub</a></li>

</ul>
</details>

**标签**: `#ai-privacy`, `#developer-tools`, `#telemetry`, `#open-source`, `#trust-and-safety`

---

<a id="item-tech-news-5"></a>
### [计算机检查的证明仍可能为假](https://cr.yp.to/proofs/falseccp.html) ⭐️ 7.0/10

cr.yp.to 的文章《False computer-checked proofs》主张，经计算机检查的证明仍可能为假：证明检查器自身的健全性（soundness）缺陷会让错误证明通过，因此“检查通过”不自动等于数学真理。Hacker News 评论者补充，部分系统会用多重独立验证降低这一风险，例如 Metamath 的 set.mm 和 iset.mm 主数据库要求 5 个用不同语言独立实现的验证器全部通过，Lean 社区也在持续修补健全性缺陷。对形式化验证用户来说，关键限制是单检查器结果不足以防住所有错误，但多验证器加人工复核会显著抬高成功造假的门槛。

hackernews · \_tk\_ · 11月27日 15:26 · [社区讨论](https://news.ycombinator.com/item?id=50667989)

**「背景」** 计算机检查的证明依赖证明检查器对证明步骤做机械校验；但如果检查器本身存在“可靠性缺陷”（soundness bug），错误陈述就可能通过检查。djb 的文章讨论的正是这类已报告的缺陷，以及它为何会让“经计算机检查的证明”仍可能是假的。

**「对验证工作流的影响」** 对形式验证项目的直接影响是：不能把单一检查器接受证明当作数学真理。Lean 生态已提供用 Rust 编写的独立内核 nanoda 用于交叉校验；而 2026 年 8 月的一例 AI 辅助 Collatz“反证”同时利用了 Lean 4 内核的健全性漏洞和另一个独立检查器的无关漏洞，说明多检查器能降低但无法消除误接受风险。开发者和数学家在采纳机器检查证明前，应使用独立实现复核，并对证明陈述本身做非正式审查。

**「社区讨论」** 评论者对风险尺度有分歧：twotwotwo 举例说，一名 DeepMind 研究员曾利用 Lean 和当时仅一周新的 nanoda 各自不同的缺陷，让同一份“证明”通过两者，因此多检查器并非不可攻破；gr\_norm 则强调这些系统数十年来出现的健全性缺陷少到几乎能写进一条推文，对绝大多数软件足够可靠。andai 还提出更根本的担忧：自动代理可能证明的是自己对任务的错误理解，而不是用户真正想要的性质。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://cr.yp.to/proofs/falseccp.html">False computer - checked proofs (djb)</a></li>
<li><a href="https://lean-lang.org/doc/reference/latest/releases/v4.32.2/">Lean 4.32.2 (2026-07-28)</a></li>
<li><a href="https://arena.lean-lang.org/checker/nanoda/">nanoda - Lean Kernel Arena</a></li>
<li><a href="https://aibacon.net/posts/lean-kernel-soundness-bug-ai-collatz-disproof-two-checkers.html">An AI &#x27;Disproof&#x27; of Collatz Slipped Past Two Proof Checkers</a></li>

</ul>
</details>

**标签**: `#formal verification`, `#proof assistants`, `#soundness bugs`, `#Lean`, `#Metamath`

---

<a id="item-tech-news-6"></a>
### [利用 WebRTC 的信用卡盗刷脚本现身热门购物网站](https://www.infohawk.com/news/2026-11-27-black-friday-webrtc-skimmer) ⭐️ 7.0/10

InfoHawk 于 2026 年 11 月 27 日（黑色星期五购物季）报道，多个热门购物网站被发现植入了信用卡盗刷（skimming）脚本，这类脚本借助 WebRTC 运行。由于没有拿到报告原文，受影响站点的数量、脚本的注入途径、归属的恶意家族以及是否已造成实际卡数据泄露，均无法确认。报道和随后的讨论把焦点放在了电商结账页普遍嵌入的第三方 JavaScript 上：攻击者不必攻破商家自己的后端，只要污染其中任何一个外部脚本，就能在支付页面读取用户输入。

hackernews · scanr · 11月27日 15:40 · [社区讨论](https://news.ycombinator.com/item?id=50668145)

**「背景」** WebRTC 是浏览器内置的实时通信接口，除音视频外还支持用 DataChannel 传输任意数据；有后续复查称，攻击者可借这条通道外送支付信息，而主要检查 HTTP 请求的 CSP 看不到这类流量。此类攻击延续的是第三方脚本供应链风险：结账页一旦加载被篡改的外部 JavaScript，该脚本就能以页面权限读取并外送表单数据。

**「对站点运营方的影响」** 评论区提出的技术判断是：WebRTC 在这里并非因为它本身不可替代，而是因为安全工具和广告、脚本拦截器对这条通道的监控更少；评论者 afavour 还称，攻击者只针对移动端设备，因为更难被发现。对电商运维团队而言，这意味着只维护第三方脚本清单、依赖广告拦截列表，或者只对常规 HTTP 出站请求设限，都可能漏掉此类外传通道；实际处置时需要逐个审计结账页加载的外部脚本，并单独监控非 HTTP 的出站流量。上述判断来自讨论，报告的验证细节尚未公开。

**「社区讨论」** 评论者 afavour 认为，问题与 WebRTC 的技术特性关系不大，用普通 HTTP 请求同样可行，根本风险在于站点把第三方脚本嵌进自己的页面；jszymborski 则把这类事件当作拦截广告和脚本的正当理由。另有评论者 s\_u\_d\_o 与 snickerer 追问更上层的设计问题：广告网络为何不在沙箱中运行脚本、彻底禁止客户端执行 JavaScript，以及让陌生代码在用户机器上运行是否本身就是 Web 架构的缺陷。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://dev.to/frankchu/webrtc-stole-cards-at-5-stores-i-re-checked-the-cleanup-59k9">WebRTC stole cards at 5 stores — I re-checked the cleanup</a></li>

</ul>
</details>

**标签**: `#web security`, `#payment skimming`, `#WebRTC`, `#third-party scripts`, `#e-commerce`

---

<a id="item-tech-news-7"></a>
### [多州总检察长起诉 SpaceX，要求阻止 Grok 生成儿童性虐待与未经同意的私密图像](https://www.oag.state.va.us/media-center/news-releases/jay-jones/3162-attorneys-general-jones-and-rayfield-file-suit-against-spacex-parent-company-of-x-xai-and-grok-over-creation-and-promotion-of-child-exploitation-and-non-consensual-images-on-platform) ⭐️ 7.0/10

弗吉尼亚州总检察长杰伊·琼斯（Jay Jones）与雷菲尔德（Rayfield）等州总检察长对 SpaceX 提起诉讼，因为 SpaceX 是 X、xAI 及其 Grok 模型的母公司，要求法院制止该平台生成儿童性虐待材料和未经同意的私密图像。诉状同时针对这些图像的“生成与推广”两方面，说明指控不只涉及模型输出能力，也涉及平台的分发行为。目前已公开的信息为起诉方新闻稿层面的指控，法院是否受理、是否签发禁令以及 SpaceX 方面的回应均未在现有材料中体现。

hackernews · DeepLogin · 11月27日 19:42 · [社区讨论](https://news.ycombinator.com/item?id=50670855)

**「背景」** Grok 是 xAI 的生成式 AI 产品，诉讼指向其在 X 平台上的输出。此次行动由弗吉尼亚州总检察长杰伊·琼斯办公室与俄勒冈州总检察长丹·雷菲尔德协作推进，俄勒冈方面另提起了类似的独立诉讼；诉状把 SpaceX 列为 X、xAI 及 Grok 的母公司，核心前置问题是母公司是否应为这些生成内容承担平台责任。

**「责任归属之争」** 这起诉讼的核心争点是责任应由平台承担还是由用户承担：Ars Technica 报道，xAI 已在另一起案件中主张，只有用户才应为 Grok 生成的 CSAM 负责；若法院采纳这一立场，可能加强其在律师估计涉及数千名受害者的潜在集体诉讼中的抗辩。与此同时，NOPE 记录的相关事件称 Grok 每小时生成约 6,700 张露骨图像，是几家主要深度伪造网站合计的 85 倍，其中 81% 为女性形象；按此规模，仅追责单个用户难以覆盖实际生成量，这也解释了州检察长为何直接起诉母公司。

**「社区讨论」** 有评论者（lacoolj）表示困惑：此类内容按理已在各平台被普遍禁止，他因此追问 Grok 究竟是对所有用户都过于宽松，还是用户需要“诱导”模型才会产出这类图像。另一位评论者（ratelimitsteve）则主张，最高法院已裁定个人使用 AI 制作儿童性虐待材料属于受保护的言论，但同时指出该裁定设有例外——不得描绘真实儿童，制作过程也不得涉及真实儿童；他称对“复仇色情”是否同样适用尚不确定，因为后者必然涉及真实人物。上述法律判断均为评论者个人陈述，未在现有材料中得到核实。此外有评论者（poontanglatits）追问制作这些图像的用户本人是否会被追责。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.oag.state.va.us/media-center/news-releases/jay-jones/3162-attorneys-general-jones-and-rayfield-file-suit-against-spacex-parent-company-of-x-xai-and-grok-over-creation-and-promotion-of-child-exploitation-and-non-consensual-images-on-platform">Attorneys General Jones and Rayfield File Suit Against SpaceX ...</a></li>
<li><a href="https://www.oag.state.va.us/media-center/news-releases/jay-jones/3164-media-clips-attorney-general-jay-jones-holds-x-accountable-for-child-exploitation-and-non-consensual-images">MEDIA CLIPS: Attorney General Jay Jones Holds X Accountable ...</a></li>
<li><a href="https://arstechnica.com/tech-policy/2026/07/xai-cant-deny-grok-makes-csam-anymore-so-its-suing-users/">xAI can’t deny Grok makes CSAM anymore. - Ars Technica</a></li>
<li><a href="https://nope.net/incidents/2025-grok-non-consensual-image-generation">Grok Industrial-Scale Non - Consensual Sexual Image ... - NOPE</a></li>

</ul>
</details>

**标签**: `#AI safety`, `#generative AI`, `#legal/regulation`, `#content moderation`, `#xAI/Grok`

---

<a id="item-tech-news-8"></a>
### [SemiAnalysis 深挖 Trainium3：瓦片优先架构与推理每美元性能](https://newsletter.semianalysis.com/p/trainium3-inferencex) ⭐️ 7.0/10

SemiAnalysis 发布了对 AWS Trainium3 的微架构与推理基准分析，并把 Trainium3 与 TPU 一同接入其 InferenceX 基准平台。在其 AgentX 测试中——通过回放真实编码智能体会话模拟生产级智能体负载——Trainium3 搭配 PDS 与 vLLM 在“TCO 对 p90 交互性”的整个帕累托前沿上，除 Nvidia Vera Rubin 外优于所有其它加速器，并在生成 token 的成本上与 Nvidia GB300 互有胜负。微架构层面，作者称 Trainium 的 DGE（Trainium Descriptor Generation Engine，对应 Nvidia TMA 与 AMD MI455X TDM）在微基准中于较小的消息尺寸下即可达到峰值 HBM 带宽利用率，而这在 Nvidia GPU 上无法做到。需要说明的是，上述数字来自 SemiAnalysis 自建的 UBenchX/InferenceX 套件，并有 AWS Annapurna Labs 团队协助讲解架构与验证实验，并非独立第三方复现；所给摘录未列出具体带宽、延迟或吞吐数值。

rss · Semianalysis · 11月27日 15:54

**「背景」** Nvidia 的数据中心 GPU 最初为像素渲染而设计，自 2017 年 Volta 加入 Tensor Core 起，每代都在为上一代暴露的瓶颈补上专用硬件：Hopper 加入 TMA 负责 HBM 与 SRAM 之间的瓦片数据搬运，Blackwell 加入 Tensor Memory 用于累加。Trainium 则从零开始以 tile 为第一类原语设计，而非在大量线程之上外挂张量与数据搬运引擎；SemiAnalysis 承认这种路线过去意味着巨大的软件挑战，但称现在已不再是问题。

**「影响」** 对用 vLLM 部署推理的团队而言，该分析给出的可用结论是：Trainium3 的 PDS 路径已能通过 vLLM 使用，且成本优势不只来自亚马逊的供应链，也来自 DGE 等微架构决策。不过文中同时指出，注意力 head\_dim（K）等形状参数会影响达到 roofline 的比例，因此实际收益取决于具体模型与延迟目标；鉴于数据出自分析机构自建基准，采购前应针对自身工作负载复现。

**标签**: `#AWS Trainium`, `#AI accelerators`, `#chip microarchitecture`, `#inference`, `#Nvidia`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [央行发布大额存单新规 个人起购门槛降至 10 万元](https://www.news.cn/fortune/20261127/70789d77822242cc82216f51a416f872/c.html) ⭐️ 7.0/10

中国人民银行 11 月 27 日公布《大额存单管理办法》，将个人投资人认购起点由不低于 20 万元下调至不低于 10 万元，自 2027 年 3 月 21 日起施行。

telegram · zaihuapd · 11月27日 11:36

**「背景」** 大额存单是银行发行的大额存款产品，现行规则来自 2015 年《大额存单管理暂行办法》，新办法将取代该暂行办法。

**「影响」** 新规生效后，个人投资者达到 10 万元即可满足最低起购要求；银行吸收存款时须自主确定利率，不得通过高息揽储等不正当手段吸存。

**标签**: `#PBOC regulation`, `#large-denomination CDs`, `#deposit rates`, `#banking regulation`, `#retail depositors`

---

<a id="item-finance-news-2"></a>
### [市场监管总局约谈 15 家电动自行车企业](https://www.news.cn/20261127/0c8c665ce70c417b9263b39fa8a519f0/c.html?hl=zh-CN) ⭐️ 7.0/10

11 月 27 日，国家市场监管总局集中约谈雅迪、台铃、爱玛、九号、小牛等 15 家电动自行车企业，原因是 CCC 认证全覆盖飞行检查发现，部分企业存在质量保证能力欠缺、产品一致性管控不严，以及违反强制性国家标准出厂销售不合格产品等问题。约谈要求相关企业抓紧整改，严格执行“一车一池一充一码”，对确认存在缺陷的产品立即召回，并且不得以“证书很快恢复”为由拒绝退车或误导消费者无牌上路。

telegram · zaihuapd · 11月27日 12:06

**「背景」** 在中国，电动自行车须通过强制性产品认证（CCC 认证）才能合法出厂销售；近期实施的新国标强化了防篡改设计和“一车一池一充一码”互认要求，以遏制非法改装带来的交通和消防隐患。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://food.cnr.cn/gstj/20261103/t20261103_527860850.shtml">堵住改装漏洞 电 动 自 行 车 新规给消费安全上把锁_央广网</a></li>
<li><a href="https://youjia-pc.bdstatic.com/article/9743054159117044880.html">youjia-pc.bdstatic.com/article/9743054159117044880.html</a></li>

</ul>
</details>

**标签**: `#电动自行车`, `#市场监管`, `#产品质量`, `#召回`, `#CCC认证`

---