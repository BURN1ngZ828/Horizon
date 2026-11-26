---
layout: default
title: "Horizon Summary: 2026-11-26 (ZH)"
date: 2026-11-26
lang: zh
---

> 从 38 条内容中筛选出 15 条重要资讯。

---

**科技新闻**
1. [1Password 披露员工 GitHub 账户被入侵并推送恶意代码](#item-tech-news-1) ⭐️ 8.0/10
2. [Anthropic 的 GRH Lean 形式化出现精简版本](#item-tech-news-2) ⭐️ 8.0/10
3. [FCC 批准 SpaceX 部署百万颗 Starmind 数据中心卫星](#item-tech-news-3) ⭐️ 8.0/10
4. [Neuralink 称 LINK 渐冻症关键试验获 FDA 批准](#item-tech-news-4) ⭐️ 8.0/10
5. [英伟达据报暂停东南亚四国 AI 服务器出货](#item-tech-news-5) ⭐️ 8.0/10
6. [Aaronson 博文回应矩阵乘法指数 9/4 主张，正文未提供](#item-tech-news-6) ⭐️ 7.0/10
7. [Ubuntu 补丁响应慢引发 Debian 迁移讨论](#item-tech-news-7) ⭐️ 7.0/10
8. [Lean 审查 Clojure 核心的缺陷发现受质疑](#item-tech-news-8) ⭐️ 7.0/10
9. [预印本宣称多项式 Hirsch 猜想不成立](#item-tech-news-9) ⭐️ 7.0/10
10. [SemiAnalysis 发布 GDPx：首日最高分仅 12%](#item-tech-news-10) ⭐️ 7.0/10
11. [三星与 SK 海力士据报采用长江存储 Xtacking 技术](#item-tech-news-11) ⭐️ 7.0/10
12. [华为拟公布 HBM 新芯片研究，称数据引脚密度翻倍](#item-tech-news-12) ⭐️ 7.0/10
13. [三部门发布新一代通信网建设方案](#item-tech-news-13) ⭐️ 7.0/10

**财经新闻**
1. [美商务部被曝施压英特尔交出 10%股权](#item-finance-news-1) ⭐️ 9.0/10
2. [美国拟依据 301 条款对 14 个贸易伙伴加征新关税](#item-finance-news-2) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [1Password 披露员工 GitHub 账户被入侵并推送恶意代码](https://1password.com/blog/update-on-nov-2026-security-incident) ⭐️ 8.0/10

1Password 确认发生安全事件：攻击者入侵一名员工的企业 GitHub 账户，访问源代码并向后台服务推送恶意代码，导致部分客户账户信息被下载，包括姓名、邮箱地址、账户标识以及账户创建和最近登录时间；公司称客户保险库及其内容未受影响。调查始于 11 月 19 日，1Password 未披露受影响用户数量，已停用涉事账户、轮换或撤销可能暴露的内部凭证，并加强邀请和恢复邮件验证码。现有客户无需更改账户，但公司提醒警惕钓鱼。

hackernews · lxhrstn · 11月25日 17:18 · [社区讨论](https://news.ycombinator.com/item?id=50644817)

**「事件背景」** 1Password 于 11 月 19 日开始调查员工企业 GitHub 账户被入侵的迹象，随后确认攻击者通过该账户访问源代码并向后台服务推送恶意代码；本次公开更新是在调查推进后对事件范围和处置措施的说明。对 SaaS 密码管理器而言，后台部署链路被攻破与用户保险库加密属于不同层面的风险，公司称客户保险库及其中内容未受影响。

**「对用户与部署控制的影响」** 按 1Password 的说明，受影响的只是姓名、邮箱地址、账户标识以及账户创建和最近登录时间等管理数据，客户加密保险库及其中的内容未被访问，因此用户无需更改密码或轮换密钥；但这些信息足以支撑针对性的钓鱼攻击，公司也已为此提醒用户保持警惕。此次攻击的路径是通过入侵员工的 GitHub 账户获得源代码，并向后台服务推送恶意代码，这意味着只要能写入生产部署的开发者身份失守，攻击者无需破解保险库加密，也能触达后端数据，因此分支保护和部署审批是这类 SaaS 场景首先要检查的控制点。

**「社区讨论」** 评论者把此事视为 SaaS 供应链的典型风险：tptacek 认为员工设备被攻陷后攻击者能向 GitHub 推送代码，一旦代码被部署就可能控制生产环境，并称 1Password 的最坏情况因客户侧加密而得到一定缓解。ctidd 质疑公告未说明是否缺少分支保护或对推送主分支的限制，ChrisHardie 和 fn-mote 则分别表达了对恶意代码进入生产服务、以及公告未明确“加密保险库未被下载”的披露缺口的不安。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://1password.com/blog/update-on-nov-2026-security-incident">Update on a security incident involving 1Password’s backend ...</a></li>
<li><a href="https://thehackernews.com/2026/11/1password-hacked-customer-data-and.html">1Password Hacked, Customer Data and Source Code Stolen in ...</a></li>

</ul>
</details>

**标签**: `#1Password`, `#security incident`, `#SaaS security`, `#supply chain security`, `#password managers`

---

<a id="item-tech-news-2"></a>
### [Anthropic 的 GRH Lean 形式化出现精简版本](https://github.com/lsernau/grh-lean) ⭐️ 8.0/10

一个与 Anthropic 的 GRH 工作相关的 Lean 形式化仓库 grh-lean 以大幅缩短的版本引发讨论，社区评论称代码量从约 1700 万行降到约 7.6 万行，并带有“已知数学/新数学”的划分和可读文档。该仓库目前以 GitHub 项目和讨论线索的形式出现，尚无来源内容或独立验证可确认其证明有效性与来源；评论者已质疑 Main.lean 是否直接导入 mathlib 的 RiemannHypothesis。对 Lean 用户和形式化数学研究者来说，这是一个可审阅的证明材料，但还不是已确认完成的 GRH 验证结果。

hackernews · nb-t · 11月25日 21:48 · [社区讨论](https://news.ycombinator.com/item?id=50648050)

**「背景」** GRH（广义黎曼猜想）是黎曼猜想的一类推广，Lean 则是把数学证明写成可被机器逐条核验的代码的交互式定理证明器。此前 Anthropic 相关 GRH 工作的 Lean 形式化约有 1700 万行，这也是此次“更短版本”被拿来比较的直接背景。在 Lean 中，证明是否针对标准陈述取决于导入的定义和定理，因此审阅者会追查新仓库与 Mathlib 中 GRH 陈述的连接。

**「影响」** 对准备复用该形式化的 Lean 用户而言，应先核对 Main.lean 的导入链是否连接到 mathlib 的 RiemannHypothesis，并检查“已知数学/新数学”边界与来源说明，再决定能否把它当作 GRH 验证依据。

**「社区讨论」** 评论者称赞规模缩减和可读性提升，认为“已知数学/新数学”的划分与文档有助于理解；但也有人质疑 Main.lean 未直接导入 mathlib，无法确认它是否真的引用了 mathlib 的 RiemannHypothesis，并追问这是否改变了陶哲轩此前关于巨大证明缺乏洞见的批评。

<details><summary>参考链接</summary>
<ul>
<li>Anthropic has achieved a remarkable 99.56% reduction in the formalization of the Riemann Hypothesis in Lean : r/singularity - Reddit</li>

</ul>
</details>

**标签**: `#Lean`, `#formal verification`, `#GRH`, `#AI-assisted mathematics`, `#proof engineering`

---

<a id="item-tech-news-3"></a>
### [FCC 批准 SpaceX 部署百万颗 Starmind 数据中心卫星](https://www.geekwire.com/2026/fcc-clears-spacex-million-satellites-starmind-data-center/) ⭐️ 8.0/10

据 GeekWire 报道，美国联邦通信委员会（FCC）批准 SpaceX 最多部署 100 万颗卫星，用于构建 Starmind 在轨数据处理网络，运行高度为 500 至 1002 公里。FCC 称这是美国首次批准太空数据中心星座，授权附带通信备份、定期提交进展和轨道碎片减缓详细方案等条件。首颗卫星须不晚于 2033 年投入运行，整个星座须在 2040 年前全部运行；FCC 在审批中还驳回了亚马逊、Viasat 和美国天文学会的反对意见。报道未提供卫星设计或在轨处理能力的技术细节，也未给出独立验证。

telegram · zaihuapd · 11月26日 04:45

**「背景」** Starmind 是 SpaceX 拟建的在轨数据处理网络，卫星在轨道上处理数据，而不只是承担通信中继。美国商业卫星星座须获得 FCC 的频谱与部署许可，许可通常附带部署时间表和轨道碎片减缓条件；因此，这次批准是星座建设和运营前的一个监管节点。

**「影响」** 对 SpaceX 而言，授权设定了 2033 年和 2040 年的阶段性节点，意味着 Starmind 星座必须按阶段推进；同时，FCC 驳回亚马逊、Viasat 和美国天文学会的反对，使这些机构无法通过本次审批程序阻止项目。SpaceX 还需持续满足通信备份、进展报告和碎片减缓条件。

**标签**: `#SpaceX`, `#FCC`, `#space data centers`, `#satellite constellations`, `#orbital computing`

---

<a id="item-tech-news-4"></a>
### [Neuralink 称 LINK 渐冻症关键试验获 FDA 批准](https://www.bloomberg.com/news/articles/2026-11-25/neuralink-gets-clearance-for-brain-implant-trial-in-als-patients?srnd=phx-technology) ⭐️ 8.0/10

Neuralink 宣布已获 FDA 批准，将在美国启动 LINK 植入式脑机接口针对渐冻症（ALS）患者的关键临床试验；该试验旨在把大脑信号直接转化为计算机控制指令。Bloomberg 的报道称，这是美国首个获批的此类关键试验。Neuralink 此前通过早期研究已在全球为超过 30 名瘫痪患者植入设备，此次关键试验的数据将作为未来申请医疗器械上市许可的核心依据。目前尚无该试验的疗效或安全性结果，获批启动并不等于已证明临床获益。

telegram · zaihuapd · 11月26日 07:15

**「背景」** 关键性试验是医疗器械在美国申请上市许可前验证安全性与有效性的核心环节，其数据通常直接构成上市审评的主要依据。脑机接口此前多以研究性植入的形式在少量患者中开展，尚无此类植入设备完成关键性试验并进入商业化审批。Neuralink 早前通过早期研究已在全球为超过 30 名瘫痪患者植入设备，此次获批意味着相关工作从安全性验证阶段转入面向上市的临床评价阶段。

**「影响」** 对 Neuralink 而言，这项关键试验产生的数据将成为其向 FDA 申请 LINK 上市许可的核心依据；在结果公布和监管审评完成前，LINK 仍是研究性设备，不能视为已获批上市。

**标签**: `#Neuralink`, `#brain-computer interface`, `#FDA clinical trial`, `#ALS`, `#neurotechnology`

---

<a id="item-tech-news-5"></a>
### [英伟达据报暂停东南亚四国 AI 服务器出货](https://www.ft.com/content/7838a715-07d4-4605-aa60-21f5af2b2370) ⭐️ 8.0/10

据《金融时报》报道，英伟达已要求主要制造伙伴暂停向马来西亚、新加坡、泰国和印度尼西亚发运 AI 服务器；戴尔、美超微等组装厂商已通知当地买家相关订单无法出厂。三名知情人士称，这一冻结与美国新一轮出口管制有关，但是否为临时措施尚不清楚。美国商务部上周发布的新规要求区域云服务商在 90 天内取得出口许可，并核实客户不包含受限制的中国实体；这四国此前是中国 AI 公司获取英伟达最先进处理器的中转地，相关芯片不得直接出口中国大陆。

telegram · zaihuapd · 11月26日 07:38

**「背景」** 美国已禁止英伟达最先进 AI 芯片直接出口中国大陆，马来西亚、新加坡、泰国和印尼因而成为相关芯片及服务器的采购与转运节点。AI 服务器通常由戴尔、美超微等厂商把英伟达芯片组装成整机，所以出口限制会同时作用于芯片和整机出货环节；来源称美国商务部上周的新规要求区域云服务商在 90 天内取得出口许可，并核实客户不含受限中国实体。

**「影响」** 对马来西亚、新加坡、泰国和印度尼西亚的云服务商与数据中心运营商来说，新规给出的 90 天窗口要求它们取得出口许可，并核实客户中不含受限的中国实体；戴尔、美超微也已通知买家，相关订单无法出厂。由于发货冻结何时解除尚不清楚，相关扩容计划需按交付延迟重新安排，并先完成合规核查。

<details><summary>参考链接</summary>
<ul>
<li>Washington&#x27;s AI chip crackdown spells trouble for a multibillion dollar cloud business helping to power Southeast Asia&#x27;s data center boom. The new rulebook applies to data centers in plac</li>
<li>US to curb China&#x27;s access to AI chips as Trump heads to Asia | Reuters</li>

</ul>
</details>

**标签**: `#Nvidia`, `#AI servers`, `#export controls`, `#Southeast Asia`, `#supply chain`

---

<a id="item-tech-news-6"></a>
### [Aaronson 博文回应矩阵乘法指数 9/4 主张，正文未提供](https://scottaaronson.blog/?p=10379) ⭐️ 7.0/10

Scott Aaronson 发布了一篇以夸张的重复感叹句为标题的博文，回应一项被描述为重大的进展，并链接到题为《矩阵乘法指数为 9/4》的 PDF；但条目没有提供博文正文，因此无法核实该成果的作者、证明细节或是否已被独立确认。对关注计算复杂度、AI 数学能力和密码学影响的人来说，目前可确认的只是一篇博文和一条论文链接，而不是已核实的技术结果。Hacker News 上的讨论随后转向 AI 在数学、密码学和生存风险方面的含义，但这些属于评论者观点，不是对所述成果的验证。

hackernews · Kotlopou · 11月25日 19:11 · [社区讨论](https://news.ycombinator.com/item?id=50646108)

**「背景」** 矩阵乘法指数 ω 描述两个 n×n 矩阵相乘所需时间随 n 增长的最优渐近指数；长期目标是把上界压到 2 附近，任何接近 2 的改进都牵动复杂性理论。斯科特·阿伦森是量子计算与计算复杂性学者，其博客 Shtetl-Optimized 常评论这类进展（tool-1-1）。这次 HN 讨论围绕一项声称把该指数做到 9/4 的结果展开；有评论称这个界“相当基础”，并提到阿伦森表示理解相关证明可能需要数年，但现有材料缺少帖子正文，无法核实证明细节或验证状态（tool-1-2）。

**「实际影响」** 该预印本给出的 ω=9/4 是“形式算术电路”模型下、对任意域成立的渐近上界与匹配下界，而不是对现有矩阵乘法实现的可测加速；因此在 111 页论证被独立核验前，数值线性代数库的选型与密码学参数都没有据此调整的依据。对于复杂度研究者，可直接检验的对象是上下界是否真正匹配、以及证明所依赖的电路模型假设是否成立。

**「社区讨论」** 评论者 jsLavaGoat 认为，AI 擅长公理化数学，并不足以证明它也能“解决”其他领域或构成生存威胁；nickysielicki 则依据大型实验室难以长期保密、且当前缺乏证据，判断实验室尚未掌握密码学的根本性突破。这些均为个人判断，未获条目内容证实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://scottaaronson.blog/?p=10379">Shtetl-Optimized » Blog Archive » HOLY SHIT HOLY SHIT HOLY...</a></li>
<li><a href="https://news.ycombinator.com/item?id=50646108">Holy shit holy shit holy shit holy shit : The magnitude... | Hacker News</a></li>
<li><a href="https://dev.to/axrisi/openais-claim-that-the-matrix-multiplication-exponent-is-exactly-94-and-what-has-been-checked-398j">OpenAI&#x27;s claim that the matrix multiplication exponent is ...</a></li>
<li><a href="https://interestingengineering.com/culture/openai-exact-2-25-matrix-multiplication-exponent">OpenAI establishes exact 2.25 exponent for matrix multiplication</a></li>

</ul>
</details>

**标签**: `#AI for mathematics`, `#matrix multiplication`, `#computational complexity`, `#cryptography`, `#AI risk`

---

<a id="item-tech-news-7"></a>
### [Ubuntu 补丁响应慢引发 Debian 迁移讨论](https://www.openwall.com/lists/oss-security/2026/11/25/9) ⭐️ 7.0/10

Hacker News 讨论围绕 Ubuntu 安全更新响应慢的抱怨展开，一名评论者称其所在公司已因此把所有服务器镜像从 Ubuntu 迁到 Debian，并认为一个广泛使用的发行版在 2026 年仍出现这种延迟不可接受。另一名评论者提醒，主要发行版会花大量时间做回归测试，并用 Debian 的一个缺陷报告说明测试不足同样会带来问题。所给材料没有给出具体 CVE、延迟天数或 Ubuntu 的正式回应，也没有独立测量能确认慢了多少，因此这目前主要是用户经验和观点，而非已核实的能力指标。

hackernews · gslin · 11月25日 20:38 · [社区讨论](https://news.ycombinator.com/item?id=50647181)

**「背景」** Ubuntu 等发行版通常由安全团队把上游修复回移到已发布的软件包版本，因此补丁能否及时到达用户，取决于该团队的响应速度和回归测试流程。稳定内核维护者曾警告，随意挑选补丁可能漏掉已知或未知问题，发行版因而需要在修复速度与回归风险之间权衡。

**「影响」** 对使用 Ubuntu 服务器镜像的团队来说，这场讨论的可操作后果是把补丁响应速度与回归测试质量一起纳入选型评估；若跟随评论者的做法迁往 Debian，也需要重新验证镜像和更新流程，因为评论者指出 Debian 同样可能发生回归问题。

**「社区讨论」** 评论中的分歧在于如何看待延迟：一方认为 Ubuntu 的安全响应已慢到值得迁移，另一方强调回归测试的价值，并提醒 Debian 的 QA 资源有限也可能出错。还有评论者引用稳定内核维护者 2025 年的说法，主张必须跟进完整的 stable/LTS 更新，只挑选个别补丁不能解决所有已知和未知问题；另有人询问相关漏洞的修复是否已进入 Ubuntu Livepatch。

**标签**: `#Ubuntu`, `#Linux distributions`, `#security response`, `#open source`, `#Debian`

---

<a id="item-tech-news-8"></a>
### [Lean 审查 Clojure 核心的缺陷发现受质疑](https://s.conao3.com/blog/2026/e4f733) ⭐️ 7.0/10

一篇博客文章报告称，作者用 Lean 对 Clojure 核心进行审查，并发现此前未报告的缺陷。由于现有材料没有提供原文，缺陷数量、复现条件以及 Lean 模型的覆盖范围都无法核实。这些发现目前只能视为一组待复核的审查结果，还不能视为已经确认的 Clojure 运行时问题。

hackernews · encyclopedism · 11月25日 14:56 · [社区讨论](https://news.ycombinator.com/item?id=50642939)

**「背景」** Lean 是带有依赖类型的定理证明器兼编程语言，通常用于把程序性质写成可机器检查的证明；Clojure 的 core 是该语言的标准库，提供基础数据结构、序列和字符串等操作。用 Lean 审计 core，前提是先把这些函数的预期行为与边界条件形式化，再让证明检查器验证实现是否满足；这与传统上使用 Rocq（原 Coq）等证明助手做程序验证属于同一类工作。

**「影响」** 对 Clojure 用户以及依赖其核心函数的项目而言，当前应把这些发现视为待复核的缺陷线索：回到原报告核对复现用例，并区分真正的实现错误与类型不匹配或参数强制转换造成的误报。若未经确认就据此修改代码，可能把正常语义当作缺陷处理。

**「社区讨论」** 评论者 rvprasad 认为清单中至少两例是误报：byte-array 的 .indexOf 收到 Long 类型的 2，以及 get 在字符串上对键做整数强制转换，都属于用法或既定语义问题；yababa\_y 则称在 SBCL、Clozure 和 ACL2 中也发现数十个问题，并给出审计仓库链接。vitorsr 对以 Clojure 承载关键业务的 Nubank 使用场景下核心函数出现这类问题表示意外，networked 则追问 Lean 与 Rocq 在验证程序正确性上的适用差异。

**标签**: `#Clojure`, `#Lean`, `#formal verification`, `#programming languages`, `#software testing`

---

<a id="item-tech-news-9"></a>
### [预印本宣称多项式 Hirsch 猜想不成立](https://github.com/openai/math/blob/main/preprints/Superpolynomial-graph-diameter-of-simple-polytopes-November-24-2026/paper.pdf) ⭐️ 7.0/10

OpenAI 的 GitHub 数学仓库（openai/math）中一份标注为 2026 年 11 月 24 日版本的预印本论文，标题宣称多项式 Hirsch 猜想（polynomial Hirsch conjecture）为假；该链接于 11 月 25 日在 Hacker News 上被讨论。若结论成立，其直接含义是不存在多项式时间的单纯形法，即单纯形法无法保证在多边形数量的步数内到达线性规划的最优顶点。目前可获取的只有论文 PDF 本身，条目未提供摘要、证明结构或验证情况，因此这仍是一份未经同行评审确认的预印本声明，而非已确立的结果。

hackernews · acossta · 11月25日 17:34 · [社区讨论](https://news.ycombinator.com/item?id=50644980)

**「背景：从 Hirsch 猜想到多项式版本」** 多项式 Hirsch 猜想是经典 Hirsch 猜想的放宽版本。后者由 Warren M. Hirsch 于 1957 年在单纯形方法的背景下提出，断言 d 维、n 个面的多面体上任意两顶点之间的图距离不超过 n−d；多项式版本则只要求存在某个常数 k，使直径上界形如 n^k，原猜想相当于 k=1 的特例。Francisco Santos 于 2010 年构造反例推翻了原始 Hirsch 猜想，但据维基百科条目，该反例并不构成对多项式 Hirsch 猜想的否定，后者此前一直被视为开放问题——此次预印本针对的正是这一更弱的版本。

**「影响」** 对线性规划使用者而言，这一声明的实际后果是：不能指望单纯形法获得多项式时间的最坏情况保证，此类保证只能来自内点法等其它算法路径。不过评论者同时指出，单纯形法在实践中依然高效，该结果针对的是最坏情况的理论上界，不改变现有求解器的性能表现。

**「社区讨论」** 评论者 GIFtheory 提供了背景：原始 Hirsch 猜想曾试图解释单纯形法为何在实践中表现异常好，但在提出 50 多年后于 2010 年被证伪，因此他把这次结果看作“收尾工作”而非颠覆性突破。另有评论者用“可行解构成的多维多面体、顶点与棱”的直观比喻向普通读者解释问题设定，也有人调侃如今数学突破是以 GitHub 补丁说明的形式出现的。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Hirsch_conjecture">Hirsch conjecture - Wikipedia</a></li>
<li><a href="https://gilkalai.wordpress.com/2010/05/10/francisco-santos-disproves-the-hirsch-conjecture/">Francisco Santos Disproves the Hirsch Conjecture | Combinatorics...</a></li>
<li><a href="https://arxiv.org/pdf/1006.2814">A counterexample to the Hirsch conjecture</a></li>

</ul>
</details>

**标签**: `#theoretical computer science`, `#linear programming`, `#polytope theory`, `#complexity theory`, `#Hirsch conjecture`

---

<a id="item-tech-news-10"></a>
### [SemiAnalysis 发布 GDPx：首日最高分仅 12%](https://newsletter.semianalysis.com/p/evaluating-recent-model-releases) ⭐️ 7.0/10

SemiAnalysis 本月早些时候发布 GDPx 基准，称其用于衡量对前沿智能最有价值的领域；该基准覆盖芯片设计、网络安全、生物、金融、法律、量化交易、递归自我改进、硬件设计、材料科学、对齐和软件工程 11 个领域，并与 14 家数据合作方制作了 206 项任务。作者批评 GDPVal、Agent&\#x27;s Last Exam 按 GDP 占比或 O\*NET 分类选取领域，并称 GDPx 发布日最高分 Opus 5.5 仅 12%，而许多基准首日头名可超过 50%。自 11 月 1 日上线后，Anthropic、OpenAI、Google 的 Gemini 4 系列以及 Alibaba、Moonshot 均有新模型发布，但这篇摘录未给出完整排行榜和具体得分。

rss · Semianalysis · 11月26日 00:05

**「背景」** GDPx 由 SemiAnalysis 于 2026 年 11 月 1 日发布，其设计出发点是：现有综合性智能体基准（如 OpenAI 的 GDPVal 和 Agent&\#x27;s Last Exam）按 GDP 占比或 O\*NET 职业分类挑选领域，而前沿模型的能力增长在不同经济领域之间分布并不均匀。此前多数智能体基准只覆盖编码、法律等单一领域，因此 SemiAnalysis 认为，要追踪前沿模型进展，就应聚焦模型真正会发挥最大作用的领域。基于这一思路，GDPx 刻意排除政府、房地产等行业，改以芯片设计、网络安全、生物、金融、法律、量化交易、递归自我改进、硬件设计、材料科学、对齐和软件工程等领域构建任务。

**「影响」** 对使用榜单比较前沿模型的团队而言，原始 GDPx 总分会受安全分类器影响：作者称 Fable 5.2 与 GPT-6.2 Astra 在网络安全、生物和对齐三个领域被压低，因此另给出剔除这三项、并对法律和金融采用部分评分的榜单。直接按单一排名选型可能低估这些模型，至少应同时核对两种评分口径。

**标签**: `#AI benchmarks`, `#frontier models`, `#agentic AI`, `#model evaluation`, `#AI economics`

---

<a id="item-tech-news-11"></a>
### [三星与 SK 海力士据报采用长江存储 Xtacking 技术](https://tech.ifeng.com/c/8yLRPKxQy4L) ⭐️ 7.0/10

据凤凰网报道，三星电子和 SK 海力士已通过交叉许可协议，同意在 3D NAND 闪存中采用长江存储 Xtacking 堆叠技术的部分内容；三家公司均拒绝置评，因此这一安排尚未得到官方确认。Xtacking 将存储单元与控制电路（CMOS）分别制作在两片晶圆上，再通过键合工艺合二为一，使两部分能够独立生产和优化。报道援引 Omdia 高级分析师的说法称，这种模式允许厂商自行生产存储阵列，并把逻辑电路交给晶圆代工厂，从而采用更先进的制程。

telegram · zaihuapd · 11月25日 14:33

**「背景」** 3D NAND 通过垂直堆叠存储单元提高密度，外围 CMOS 电路则负责控制读写；两者如何布置会影响芯片面积、制程选择和制造分工。按报道介绍，Xtacking 将存储阵列与 CMOS 分别制作在两片晶圆上再键合，使两部分可以独立生产和优化，这也是外界讨论其键合工艺优势的技术前提。

**「影响」** 若该交叉许可最终落地，三星和 SK 海力士可将 3D NAND 的存储阵列与 CMOS 逻辑电路分开制造，并按 Omdia 分析师的说法把逻辑部分交给晶圆代工厂使用更先进制程，从而改变其先进 NAND 的制造分工和代工合作方式。由于三方均拒绝置评，许可覆盖的具体技术范围、是否以及何时用于量产仍未确认，相关厂商短期内不宜按已量产采用来规划兼容性或供应安排。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.trendforce.com/news/2026/11/25/news-sk-hynix-reportedly-joins-samsung-in-licensing-ymtcs-xtacking-technology-as-nand-race-heats-up/">[News] SK hynix Reportedly Joins Samsung in Licensing YMTC’s ...</a></li>
<li><a href="https://www.techpowerup.com/355199/samsung-and-sk-hynix-to-license-ymtcs-xtacking-technology">Samsung and SK hynix to License YMTC&#x27;s Xtacking Technology</a></li>

</ul>
</details>

**标签**: `#3D NAND`, `#Xtacking`, `#YMTC`, `#Samsung/SK Hynix`, `#semiconductor manufacturing`

---

<a id="item-tech-news-12"></a>
### [华为拟公布 HBM 新芯片研究，称数据引脚密度翻倍](https://www.bloomberg.com/news/articles/2026-11-26/huawei-teases-next-gen-ai-memory-chip-to-take-on-samsung-hynix) ⭐️ 7.0/10

华为计划公布一款新型高带宽内存（HBM）芯片的研究细节：其论文标题称，该芯片的数据引脚密度是三星电子和 SK 海力士当前量产产品的两倍，理论上可显著提升内存带宽。华为将在 2027 年 2 月于旧金山举行的一场会议上发表这篇论文。目前公开信息仅来自论文标题和会议安排，尚不能证明该芯片已流片、量产或经过独立测试；华为同时正推动 HBM 在中国本土生产，而该部件受美国制裁限制。

telegram · zaihuapd · 11月26日 05:30

**「背景」** HBM 通过将多层 DRAM 芯片垂直堆叠，并以超宽数据通路连接处理器，在带宽、密度和能耗之间取得平衡。其可用带宽不仅取决于堆叠层数和单引脚速率，也取决于数据引脚的数量与密度，因此“数据引脚密度翻倍”指向的是内存与计算芯片之间数据通道的扩展能力。

**「影响」** 对关注 AI 硬件的开发者和采购方而言，这项披露目前只是会议论文计划，不能据此安排基于华为 HBM 的系统设计或产能规划；需要等待论文、样品或量产信息，才能判断其与三星、SK 海力士产品的实际带宽和兼容性差距。

<details><summary>参考链接</summary>
<ul>
<li>Scaling the Memory Wall: The Rise and Roadmap of HBM</li>

</ul>
</details>

**标签**: `#Huawei`, `#HBM`, `#AI hardware`, `#semiconductors`, `#export controls`

---

<a id="item-tech-news-13"></a>
### [三部门发布新一代通信网建设方案](https://www.news.cn/politics/20261126/9fe827a2d98741acb60f62d36ba89cf7/c.html) ⭐️ 7.0/10

经国务院同意，工业和信息化部、国家网信办、国家发展改革委于 11 月 26 日对外发布《新一代通信网建设实施方案》。方案提出到 2030 年建成覆盖完善、性能领先的新一代通信网，适时开展 6G 网络建设，低轨卫星互联网系统基本建成，并推动工业互联网、车联网等融合网络规模化发展。方案还要求积极推进 5G-A 网络规模覆盖，加快 6G、卫星互联网、算网融合等标准研制，并深化脑机接口、具身智能、智能网联汽车与新一代通信网的融合发展。

telegram · zaihuapd · 11月26日 06:30

**「背景」** 5G-A（5G-Advanced）是 5G 向 6G 过渡的中间阶段，运营商通常先在现网上升级这一代能力，再等待 6G 标准与产业成熟后启动新一代网络建设。因此这份方案把「5G-A 网络规模覆盖」列为近期任务，而把 6G 表述为「适时开展」，两者处于先后衔接的不同节奏上。

**「产业影响」** 对运营商、设备商和卫星互联网企业来说，5G-A 规模覆盖、6G 与卫星互联网标准研制被列为明确任务，网络规划和研发路线需要围绕 2030 年节点推进；方案未给出投资规模或分阶段时间表。

**标签**: `#6G`, `#telecom policy`, `#satellite internet`, `#5G-A`, `#China tech`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美商务部被曝施压英特尔交出 10%股权](https://www.wired.com/story/inside-trumps-demands-to-another-chips-ceo/) ⭐️ 9.0/10

法庭文件显示，2025 年 8 月美国商务部律师在与英特尔首席财务官通话时向英特尔董事会施压，要求其交出 10%股权，并称这不是一场谈判；数日后董事会照做。特朗普随后称美国政府未付费即“完全拥有并控制”这 10%股份，报道称其现值约 110 亿美元。

telegram · zaihuapd · 11月25日 13:25

**「背景」** 这批股份与英特尔此前依据美国《芯片与科学法案》获得的约 89 亿美元联邦补贴（用于支持美国本土半导体制造）有关：政府以放行这笔资金为条件，取得了约 9.9% 的股权。此后股东提起衍生诉讼，质疑政府持股对公司治理的影响。

**「影响」** 据《福布斯》报道，美国政府已在约 30 家公司持有股份，英特尔只是其中之一；这显示其他被视为战略关键的制造和芯片企业也可能面临类似的政府入股要求，而这些公司现有股东的持股会被稀释。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.dandodiary.com/2026/03/articles/shareholders-derivative-litigation/intel-derivative-suit-tests-governance-implications-of-government-equity-stakes/">Intel Derivative Suit Tests Governance Implications of ...</a></li>
<li><a href="https://www.gate.com/news/detail/intel-lawsuit-reveals-trumps-alleged-10-stake-demand-for-chips-act-funds-25863723">Intel Lawsuit Reveals Trump&#x27;s Alleged 10% Stake Demand for ...</a></li>
<li><a href="https://www.forbes.com/sites/frankholmes/2026/08/03/the-us-government-now-owns-stakes-in-30-companies-intel-is-just-the-beginning/">The U.S. Government Now Owns Stakes In 30 Companies. Intel Is ...</a></li>

</ul>
</details>

**标签**: `#Intel`, `#US Commerce Department`, `#semiconductor industry`, `#government equity stake`, `#industrial policy`

---

<a id="item-finance-news-2"></a>
### [美国拟依据 301 条款对 14 个贸易伙伴加征新关税](https://www.cnbc.com/2026/11/25/us-tariffs-trump-section-301.html) ⭐️ 8.0/10

美国政府拟依据 1974 年《贸易法》第 301 条，对中国、欧盟、日本、印度等 14 个贸易伙伴加征针对制造业结构性产能过剩的新关税，税率按国别设定而非统一税率。新关税除中国外不与现有关税叠加；中国将在 2018 年已加征的 25%基础上再加征 20%，若中国未遵守 2025 年 10 月在韩国釜山达成的贸易休战协议，对华税率可能升至 40%。

telegram · zaihuapd · 11月25日 13:59

**「背景」** 第 301 条源自 1974 年《贸易法》，允许美国在认定他国存在不公平贸易做法后单边加征关税；本轮措施是在为期八个月的结构性产能过剩调查结束后提出的（tool-1-2）。美国贸易代表办公室同步公布了对 14 项调查的认定，例如拟对欧盟商品按 15%的税率征税（tool-1-3）。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.foxbusiness.com/fox-news-global-economy/trump-admin-raise-tariffs-china-eu-other-trading-partners">Trump administration proposes sweeping Section 301 tariffs on China ...</a></li>
<li><a href="https://ustr.gov/about/policy-offices/press-office/press-releases/2026/november/ustr-makes-determinations-and-proposes-actions-14-section-301-investigations-relating-structural">USTR Makes Determinations and Proposes Actions in 14 Section 301 ...</a></li>

</ul>
</details>

**标签**: `#US tariffs`, `#Section 301`, `#US-China trade`, `#EU-Japan-India trade`, `#trade policy`

---