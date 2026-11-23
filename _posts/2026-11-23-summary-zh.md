---
layout: default
title: "Horizon Summary: 2026-11-23 (ZH)"
date: 2026-11-23
lang: zh
---

> 从 35 条内容中筛选出 10 条重要资讯。

---

**科技新闻**
1. [xnulinux 项目声称在 Linux 上运行 OS X GUI](#item-tech-news-1) ⭐️ 7.0/10
2. [OpenAI 文章讨论困惑度与智能的关系](#item-tech-news-2) ⭐️ 7.0/10
3. [GL.iNet 发布安全公告，社区追问受影响机型](#item-tech-news-3) ⭐️ 7.0/10
4. [Phison Pascari Space SSD 发布，488 TB 计划 2027 年入轨](#item-tech-news-4) ⭐️ 7.0/10
5. [Windows Server 2028 将默认移除 WoW64](#item-tech-news-5) ⭐️ 7.0/10

**科技博客**
1. [跳过 DRAM 层：MoRI UMBP 的 NVMe KV 池实测](#item-tech-blog-1) ⭐️ 8.0/10
2. [在不确定时，有策略地试错](#item-tech-blog-2) ⭐️ 6.0/10

**财经新闻**
1. [美股科技股大幅下挫 亚洲多地推出稳市措施](#item-finance-news-1) ⭐️ 9.0/10
2. [厄尔尼诺海温破纪录，粮食援助资金承压](#item-finance-news-2) ⭐️ 7.0/10
3. [蚂蚁集团领投 Simplexity Robotics 1 亿美元 pre-A 轮，投后估值 16 亿美元](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [xnulinux 项目声称在 Linux 上运行 OS X GUI](https://github.com/AFK-surf/xnulinux) ⭐️ 7.0/10

一个名为 xnulinux 的 GitHub 项目声称能借助 XNU 在 Linux 上运行完整的 OS X GUI 用户空间，面向希望在 Linux 环境中使用 macOS 图形界面的用户。当前条目没有提供 README、版本号、宿主机要求或实现细节，因此这仍是项目方的说法，尚无独立验证。现有讨论也无法确认它究竟是内核模块、用户态加载器还是虚拟机方案，性能和兼容性均未量化。

hackernews · mmastrac · 11月23日 03:49 · [社区讨论](https://news.ycombinator.com/item?id=50607261)

**「背景」** XNU 是苹果 macOS 的开源内核。该项目的做法是从苹果公布的源码构建 XNU，并把它作为可加载内核模块 xnu.ko 载入未修改的 arm64 Linux 内核，让 macOS 用户态程序运行在这一内核之上，而不是把整个 macOS 放进虚拟机。

**「试用门槛」** 对打算试用的开发者来说，项目把 XNU 作为 xnu.ko 加载进未修改的 arm64 Linux 内核，因此运行环境需要是 arm64 主机，并且具备加载该内核模块的条件；项目材料没有说明 x86 等其他架构的支持情况，迁移或部署前应先核实。

**「社区讨论」** 评论者主要质疑这种方案相对 KVM 虚拟机的实际收益：ajasmin 认为从用户视角看它仍很像虚拟机，只是把任务分到各核心并用文件承载 XNU 磁盘；darksim905 则追问同样的内核模块思路能否套用到 Windows 的 NTOSKRNL。上述均为社区推测，项目本身未在现有材料中给出效率或集成证据。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/AFK-surf/xnulinux">AFK - surf / xnulinux : XNU as a loadable kernel module inside Linux ...</a></li>
<li><a href="https://github.com/AFK-surf/xnulinux">AFK-surf/xnulinux: XNU as a loadable kernel module inside Linux ...</a></li>

</ul>
</details>

**标签**: `#XNU`, `#macOS`, `#Linux`, `#virtualization`, `#kernel`

---

<a id="item-tech-news-2"></a>
### [OpenAI 文章讨论困惑度与智能的关系](https://openai.com/index/perplexity-and-intelligence/) ⭐️ 7.0/10

OpenAI 发布了一篇题为《Perplexity and Intelligence》的文章，讨论语言模型困惑度（perplexity）与智能之间的关系。由于提供的页面没有正文，目前只能确认文章主题，无法核实其具体论点、数据或结论。Hacker News 的讨论补充了困惑度的定义：它衡量模型预测下一个 token 时的意外程度，最好为 1，最差等于词表大小。评论还围绕交叉熵损失、预测即压缩和基准设计展开。

hackernews · acossta · 11月22日 17:06 · [社区讨论](https://news.ycombinator.com/item?id=50601525)

**「背景：困惑度是什么」** 困惑度（perplexity）是语言建模中的经典指标，用来衡量模型预测下一个 token 时的“意外”程度：数值越低越好，理想情况下为 1，而在随机猜测时约等于词表大小。OpenAI 此次发文主张把这一指标作为跨模型、跨机构比较能力进展的共同尺度；据路透社报道，OpenAI 首席科学家还提出可据此为越来越强的模型设定行业共同上限。

**「社区讨论」** 有评论者指出文章没有定义困惑度，并补充其衡量下一 token 预测的意外程度、最优值为 1；也有人表示，在强化学习使用增多后，交叉熵仍与能力趋势清晰相关令人意外，并赞赏这种比复杂基准更简单的评测思路。另有评论称微软的 MAI-2 Base 在同一评测集上报告 log-perplexity 为 0.819，但这只是评论中的说法，未获文章正文或独立来源确认。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/perplexity-and-intelligence/">Perplexity and Intelligence - OpenAI</a></li>
<li><a href="https://www.reuters.com/business/openai-scientist-proposes-industry-ai-limits-tied-model-intelligence-metric-2026-11-22/">OpenAI scientist proposes industry AI limits tied to model ...</a></li>

</ul>
</details>

**标签**: `#perplexity`, `#language models`, `#model evaluation`, `#cross-entropy`, `#AI research`

---

<a id="item-tech-news-3"></a>
### [GL.iNet 发布安全公告，社区追问受影响机型](https://www.gl-inet.com/en-us/blogs/blog/glinet-security-notice-2026-11-20) ⭐️ 7.0/10

GL.iNet 于 2026 年 11 月 20 日发布了一则安全公告，相关链接随后在 11 月 22 日被提交至 Hacker News 讨论。所提供的材料中没有公告正文，因此无法确认受影响的设备型号、漏洞性质、影响范围或是否已提供修复固件。讨论中最集中的疑问是公告是否涵盖旅行路由器，例如较受欢迎的 GL-E750V2（Mudi），但这一点目前尚无来自厂商文本的答案。

hackernews · gregsadetsky · 11月22日 23:06 · [社区讨论](https://news.ycombinator.com/item?id=50604988)

**「背景」** GL.iNet 的部分路由器和 KVM 设备可通过其 GoodCloud 云服务进行远程管理。根据 GL.iNet 于 2026 年 11 月 20 日发布的安全公告，该云远程管理服务中的一个漏洞被未授权方利用，导致部分设备被访问并植入了恶意软件。

**「受影响用户的固件替代限制」** 对于希望改用第三方固件以规避风险的 GL.iNet 旅行路由器用户，OpenWrt 官方支持范围构成实际限制：OpenWrt 设备页面列出 GL-E750（Mudi），但明确提示 Mudi v2（GL-E750V2）尚无官方支持，因此该版本用户暂时无法通过这一途径替换固件。

**「社区讨论」** 有评论者直接询问公告是否涉及 GL-E750V2 等旅行路由器，另一人则引用 GL.iNet 论坛帖称相关恶意软件至少从去年起就已存在——这是论坛帖的说法，并非已核实的结论。多位评论者主张刷入 OpenWrt 等第三方固件或关闭云端与远程访问以降低风险，同时有人提醒 GL.iNet 的 KVM 类产品缺乏同等水平的 OpenWrt 支持，因此更换固件并非对所有设备都可行。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.gl-inet.com/en-us/blogs/blog/glinet-security-notice-2026-11-20">GL.iNet Security Notice 2026-11-20</a></li>
<li><a href="https://forum.gl-inet.com/t/2026-11-20-gl-inet-security-notice-goodcloud-kvm-routers/73056">2026-11-20: GL.iNet Security Notice - GoodCloud / KVM / Routers</a></li>
<li><a href="https://www.bleepingcomputer.com/news/security/hackers-exploit-glinet-cloud-flaw-to-infect-routers-kvm-devices/">Hackers exploit GL.iNet cloud flaw to infect routers, KVM devices</a></li>
<li><a href="https://www.youtube.com/watch?v=gV_WarQtZnI">GL - iNet Mudi V 2 - Portable 4G LTE Router - Unbox... - YouTube</a></li>
<li><a href="https://openwrt.org/toh/gl.inet/gl-e750">[ OpenWrt Wiki] GL . iNet GL - E 750 ( Mudi )</a></li>

</ul>
</details>

**标签**: `#security`, `#routers`, `#GL.iNet`, `#firmware`, `#OpenWrt`

---

<a id="item-tech-news-4"></a>
### [Phison Pascari Space SSD 发布，488 TB 计划 2027 年入轨](https://videocardz.com/newz/phison-announces-488tb-of-ssd-storage-for-space-data-centers-pricing-expected-to-be-astronomical) ⭐️ 7.0/10

Phison 发布面向航天器、卫星与在轨数据中心的 Pascari Space SSD 系列，产品已上市，分为 Flight Critical、Main Storage 和 Orbital Data Center 三类，系列最高容量 128 TB。公司同时确认，Lonestar Data Holdings 的 StarVault-001 轨道数据中心计划于 2027 年上半年发射，将搭载合计 488 TB 的 Phison SSD，进入低地球轨道后整机可用容量约 370 TB。Phison 称部分型号采用 pSLC 可将写入寿命提高至多 60 倍；不过 488 TB 的在轨部署仍是已宣布的计划，而非已完成的在轨验证。

telegram · zaihuapd · 11月22日 10:31

**「背景」** pSLC 通常指把闪存单元按单层方式使用，以牺牲容量换取更高写入耐久度，因此“最高 60 倍”的寿命提升需要结合具体型号与容量理解。488 TB 搭载容量对应约 370 TB 整机可用容量，也说明这两个数字并非同一口径。

**「影响」** 对计划把存储放在轨道的任务方，系统设计应按多盘聚合而非单盘 488 TB 来规划，并以约 370 TB 的整机可用容量和 2027 年上半年发射窗口做验证；当前可确认的是产品已上市和部署计划，尚不是在轨运行结果。

**标签**: `#space-grade SSDs`, `#orbital data centers`, `#Phison`, `#storage hardware`, `#pSLC`

---

<a id="item-tech-news-5"></a>
### [Windows Server 2028 将默认移除 WoW64](https://www.windowslatest.com/2026/11/23/32-bit-apps-days-are-numbered-as-microsoft-strips-support-bit-by-bit-starting-with-windows-server-2028-but-windows-11-is-safe-for-now/) ⭐️ 7.0/10

微软在 Ignite 2026 上表示，Windows Server 2028 将默认不再包含 WoW64 兼容子系统，因此开箱无法运行 32 位应用；该版本计划于 2027 年秋季与 Windows 11 27H2 一同发布。需要时可通过“按需功能”（FoD）重新安装 WoW64，在 Server Core 上通常使用 PowerShell 或 DISM 添加。微软称此举旨在减少攻击面、阻止 32 位恶意软件，而 Windows 11 目前仍保留 WoW64，且未公布移除计划。

telegram · zaihuapd · 11月23日 03:03

**「背景」** WoW64 是 64 位 Windows 中负责承载 32 位应用的兼容子系统；没有它，64 位系统无法直接加载 32 位程序。微软在 Ignite 2026 上称，Windows Server 2028 将把 WoW64 从默认安装中移除，但保留为可按需功能（FoD），这使管理员在遇到旧软件时需额外手动恢复兼容层。该服务器版本计划于 2027 年秋季随 Windows 11 27H2 发布，而 Windows 11 暂未公布类似移除计划。

**「影响」** 对仍依赖 32 位软件的企业服务器管理员而言，升级前需要盘点 32 位依赖，并在镜像或部署脚本中通过 FoD 加入 WoW64，或迁移到 64 位版本；Windows 11 客户端暂不受这一默认变更影响。

**标签**: `#Windows Server`, `#WoW64`, `#backward compatibility`, `#Microsoft`, `#32-bit apps`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [跳过 DRAM 层：MoRI UMBP 的 NVMe KV 池实测](https://vllm.ai/blog/2026-11-23-skip-the-dram-tier) ⭐️ 8.0/10

rss · vLLM Blog · 11月23日 00:00

**「背景」** 智能体服务反复重发长前缀：作者称 AgentX 单轮输入中位数 142K token，逾 96% 为已见前缀，命中率每升 1 个百分点约值 10% 吞吐；而 1.8 TB DRAM 池仅保留 23–47 分钟 KV，促使作者尝试跳过 DRAM 层。

**「方案」** AMD 与 Embedded LLM 在 16 张 MI355X 上用 vLLM 和 MoRI UMBP 测试 Kimi-K3：1.8 TB KV 池全放本地 NVMe，DRAM 只留约 80 GB 的写缓冲与读暂存。作者报告，AgentX 的 48/70/96 并发下，同容量 NVMe 与 DRAM 吞吐差不超过 1%，命中率最多差 0.08 个百分点；kvlab 长提示负载也约在 1% 内。原因在于同容量池按相同策略淘汰、留下相同 KV，且异步加载可被 prefill 等待掩盖；不过无写缓冲的高负载等配置仍有下降。调优中，段文件从 4 GiB 降到 256 MiB 使吞吐 +15.6%，报告 GPU 仍命中的前缀和每 7168 token 加检查点则减少误淘汰、把命中率从 91.4% 提到 95.6%。代价是每个 KV 块都写盘：96 会话每天约 83 TB，测试盘约 5.5 个月耗尽；按列表价，保留一天的 83 TB NVMe 池约 5.9 万美元，1.8 TB DRAM 池约 7.6 万美元，低于约 24 分钟保留时才轮到 DRAM 更便宜。

**「启示」** 作者据此认为，在智能体 KV 缓存中，容量和淘汰策略比介质更决定命中率，NVMe 可绕过 DRAM 层，以按写入付费换取更长保留；但写寿命与部分高负载回退仍是待解约束。

**标签**: `#KV cache`, `#NVMe`, `#vLLM`, `#agentic serving`, `#storage tiering`

---

<a id="item-tech-blog-2"></a>
### [在不确定时，有策略地试错](https://seangoedecke.com/when-in-doubt-flail-about/) ⭐️ 6.0/10

rss · Sean Goedecke · 11月23日 00:00

**「背景」** 面对没有明确指引、也不知道什么会有用的局面，Sean Goedecke 主张不要先谨慎等待“看清全局”，而应主动试错；但他也承认，做得不好会损害技术公司里的声誉。

**「方案」** 他把有效试错拆成三点：大量尝试不同做法、密切读取来自专家和现实的反馈、对没有正反馈的方案立刻放弃。多试既是为了直接接触现实，也因为大多数计划本就不可靠；同时手上有多个方案，才不会对某一个过度投入。作者用三类场景说明：产品未找到市场契合时可围绕核心价值在边缘试错，他在 GitHub Models 上做了不少不奏效的功能，但“用 GitHub Actions token 运行 AI 推理”意外有黏性，后来成为 Continuous AI 的种子；工程上与其先梳理庞大而快速变化的系统，不如做若干探索性改动，看效果再决定；组织问题中则可自动化手工工作、主动承担任务或提出长期方案。作者强调，试错从内部感受像反复失败，但管理者看到的是主动实验，因此要把这种不适当作正常信号。

**「启示」** 作者的结论是：在高度不确定时，广泛而廉价地实验、紧贴反馈并迅速砍掉失败路径，比等待完整理解更快变得有用；关键不是避免“乱”，而是让每次乱试都接受现实检验。

**标签**: `#engineering-process`, `#problem-solving`, `#organizational-dynamics`, `#feedback-loops`, `#product-development`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美股科技股大幅下挫 亚洲多地推出稳市措施](https://news.bjd.com.cn/2026/11/22/12039852.shtml) ⭐️ 9.0/10

美国人工智能科技股周五遭大规模抛售，纳斯达克指数单日下跌 5.28%，费城半导体指数重挫近 11%。中国内地、韩国和中国台湾地区随后推出稳市措施，包括将融资保证金最低比例下调至 80%、放宽回购订单限制，以及自 11 月 23 日起全面禁止以低于前一交易日收盘价卖空。

telegram · zaihuapd · 11月22日 13:24

**「背景」** 这轮抛售并非毫无前兆：10 月 31 日纳斯达克 100 指数就曾因市场担忧 AI 相关支出而单日重挫 3.5%，并创下 2025 年 3 月以来最差单月表现。中国内地此次下调的“融资保证金最低比例”，指投资者借钱买股票时必须自付的资金占比，该比例越低，投资者可用的借贷杠杆就越高。

**「影响」** 这些措施将直接约束使用融资和卖空交易的投资者：台湾的卖空禁令限制做空，融券保证金上调抬高相关成本，中国内地下调融资保证金比例则降低融资交易的保证金门槛。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://finance.sina.com.cn/stock/usstock/c/2026-10-31/doc-inixaepa5130478.shtml">美国股市：纳斯达克100指数重挫3.5% AI投资疑虑加剧科技股抛售_新浪财...</a></li>

</ul>
</details>

**标签**: `#US tech selloff`, `#Asian market stabilization`, `#short-selling restrictions`, `#margin trading rules`, `#semiconductor stocks`

---

<a id="item-finance-news-2"></a>
### [厄尔尼诺海温破纪录，粮食援助资金承压](https://www.wired.com/story/how-this-years-super-el-nino-will-worsen-global-hunger/) ⭐️ 7.0/10

气候学家 Zeke Hausfather 表示，截至 10 月，用于衡量厄尔尼诺强度的中热带太平洋升温达 3.5℃，超过此前约 2.75℃的纪录，并预计在初冬升至约 4℃的峰值。世界粮食计划署 8 月警告，本轮厄尔尼诺可能在 2027 年底前额外推高 4900 万急性粮食不安全（短期内难以获得足够食物）人口；报道同时称，全球援助资金 2025 年较 2022 年峰值下降 30%。

telegram · zaihuapd · 11月22日 14:09

**「背景」** 厄尔尼诺是赤道太平洋中东部海水异常变暖、会扰乱全球降雨并影响农业的气候现象；截至 10 月，本轮厄尔尼诺用于衡量强度的中热带太平洋升温已达 3.5℃，超过此前约 2.75℃的纪录。

**「影响」** 报道以索马里为例称，在遭遇类似旱情时，世界粮食计划署可覆盖人数从 1000 万降至不足 100 万，显示受援家庭在援助资金下降背景下面临覆盖收缩。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.envirolink.org/2026/11/05/record-breaking-el-nino-threatens-to-push-millions-more-into-hunger/">Record-Breaking El Niño Threatens to Push Millions More into ...</a></li>

</ul>
</details>

**标签**: `#El Niño`, `#food security`, `#humanitarian aid`, `#climate risk`, `#macro policy`

---

<a id="item-finance-news-3"></a>
### [蚂蚁集团领投 Simplexity Robotics 1 亿美元 pre-A 轮，投后估值 16 亿美元](https://www.bloomberg.com/news/articles/2026-11-22/ant-group-bets-on-simplexity-to-thrive-in-china-s-humanoid-race) ⭐️ 7.0/10

据彭博报道，中国具身智能公司 Simplexity Robotics 完成 1 亿美元 pre-A 轮融资，由蚂蚁集团领投，投后估值 16 亿美元；公司董事长兼联合创始人 Wang Kai 向彭博确认了这一消息，老股东阿里巴巴、腾讯、HongShan（红杉中国）和蓝驰创投跟投。该公司 2025 年 7 月成立于杭州，核心团队来自理想汽车；今年 3 月它曾披露成立半年内完成五轮融资、累计 20 亿元人民币，当时投后估值已超 10 亿美元。

telegram · zaihuapd · 11月23日 02:02

**「背景」** Simplexity Robotics 2025 年 7 月成立于杭州，核心团队来自理想汽车，主攻“具身智能”，即让人工智能系统在物理环境中感知并行动，产品形态包括轮式人形机器人平台。据源报道，公司在成立半年内已完成五轮融资、累计融资 20 亿元人民币，当时投后估值已超过 10 亿美元。

**「影响」** 按彭博报道，这笔资金将用于与宇树、优必选等更成熟的人形机器人厂商争夺市场，这些已有出货规模的厂商将面对一个资金更充足的新进入者。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.humanoidmegahub.com/robots/702-i-series">I-Series by Simplexity Robotics – Humanoid Robot ...</a></li>

</ul>
</details>

**标签**: `#Ant Group`, `#humanoid robotics`, `#startup funding`, `#China tech`, `#valuation`

---