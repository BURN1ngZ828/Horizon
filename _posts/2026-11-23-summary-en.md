---
layout: default
title: "Horizon Summary: 2026-11-23 (EN)"
date: 2026-11-23
lang: en
---

> From 35 items, 10 important content pieces were selected

---

**Technology News**
1. [XNU Linux project claims full OS X GUI userspace on Linux](#item-tech-news-1) ⭐️ 7.0/10
2. [OpenAI Article Examines Perplexity and Intelligence](#item-tech-news-2) ⭐️ 7.0/10
3. [GL.iNet Security Notice Draws Questions on Router Compromise](#item-tech-news-3) ⭐️ 7.0/10
4. [Phison unveils space-grade SSDs, 488 TB planned for 2027 orbital data center](#item-tech-news-4) ⭐️ 7.0/10
5. [Windows Server 2028 drops WoW64 by default, blocking 32-bit apps](#item-tech-news-5) ⭐️ 7.0/10

**Technology Blog**
1. [NVMe KV Pool Matches DRAM for Agentic vLLM Serving](#item-tech-blog-1) ⭐️ 8.0/10
2. [The Case for Purposeful Flailing in Ambiguous Engineering Work](#item-tech-blog-2) ⭐️ 6.0/10

**Financial News**
1. [Nasdaq Falls 5.28% as Asian Authorities Announce Stabilization Measures](#item-finance-news-1) ⭐️ 9.0/10
2. [Record El Niño Warming Projected to Worsen Global Food Insecurity](#item-finance-news-2) ⭐️ 7.0/10
3. [Ant Group Leads $100 Million Round for Simplexity at $1.6 Billion Valuation](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [XNU Linux project claims full OS X GUI userspace on Linux](https://github.com/AFK-surf/xnulinux) ⭐️ 7.0/10

A GitHub project called XNU Linux claims to run the full OS X GUI userspace on Linux through XNU, according to its Hacker News submission; the supplied item includes no repository README, implementation details, or independent verification. Commenters described the current user-facing model as VM-like, with one task per core and a large file-backed disk for the XNU kernel, and questioned what efficiency or integration gains it offers over running XNU under KVM. The project&\#x27;s compatibility, performance, and production readiness therefore remain unestablished in the available evidence.

hackernews · mmastrac · Nov 23, 03:49 · [Discussion](https://news.ycombinator.com/item?id=50607261)

**「Background」** XNU is the open-source kernel at the core of macOS. The xnulinux repository says it builds XNU from Apple&\#x27;s published sources and runs it as a loadable kernel module \(xnu.ko\) inside an unmodified arm64 Linux kernel, rather than booting macOS as a separate virtual machine.

**「Deployment constraints」** Running this requires loading an out-of-tree \`xnu.ko\` into an otherwise unmodified arm64 Linux kernel, so the approach as described is limited to arm64 hosts and needs kernel-module privileges plus a module built for the running kernel. Because XNU executes as a kernel module in the host rather than as a KVM guest, users should not assume the isolation a virtual machine would provide.

**「Community discussion」** Commenters focused on whether the design is meaningfully different from a VM: one said it currently feels VM-like and asked about efficiency or integration benefits, while another asked how it compares with XNU in KVM. Others raised speculative extensions, including loading Windows&\#x27; NTOSKRNL as a module and whether the work could let Asahi Linux users access the macOS desktop semi-natively.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/AFK-surf/xnulinux">AFK - surf / xnulinux : XNU as a loadable kernel module inside Linux ...</a></li>
<li><a href="https://github.com/AFK-surf/xnulinux">AFK-surf/xnulinux: XNU as a loadable kernel module inside Linux ...</a></li>
<li><a href="https://linux-kvm.org/">KVM</a></li>

</ul>
</details>

**Tags**: `#XNU`, `#macOS`, `#Linux`, `#virtualization`, `#kernel`

---

<a id="item-tech-news-2"></a>
### [OpenAI Article Examines Perplexity and Intelligence](https://openai.com/index/perplexity-and-intelligence/) ⭐️ 7.0/10

OpenAI has published an article titled “Perplexity and Intelligence” examining the relationship between language-model perplexity and intelligence; the supplied material does not include the article text, so its specific claims, charts, and stated conclusions cannot be verified here. The accompanying Hacker News discussion focused on how perplexity is defined, its connection to prediction and compression, cross-entropy loss, reinforcement learning, and benchmark design. The source provided no independent measurement or shipped capability to assess.

hackernews · acossta · Nov 22, 17:06 · [Discussion](https://news.ycombinator.com/item?id=50601525)

**「Background」** Perplexity is a language-model metric that measures how well a model predicts the next token in a dataset, with lower values indicating better predictive performance. OpenAI&\#x27;s article presents it as a simpler, shared way to track model progress and evaluate emerging capabilities.

**「Impact」** For model evaluators, the practical consequence is that perplexity figures need the tokenizer, vocabulary size, and evaluation set attached: hazrmard’s definition puts the best case at 1 and a random predictor at the vocabulary size.

**「Community discussion」** hazrmard noted that the article does not define perplexity and supplied a working definition: next-token surprise, ranging from 1 for perfect prediction to vocabulary size for a random predictor. jrflo called the apparent cross-entropy trend surprising given the rise of RL and welcomed a simpler benchmark, while d\_burfoot argued that prediction—and thus compression—rate is exactly the metric that captures progress toward intelligence.

<details><summary>References</summary>
<ul>
<li><a href="https://openai.com/index/perplexity-and-intelligence/">Perplexity and Intelligence - OpenAI</a></li>
<li><a href="https://blockchain.news/news/openai-perplexity-metric-ai-progress">OpenAI Advocates Perplexity as Key Metric for AI Progress and ...</a></li>

</ul>
</details>

**Tags**: `#perplexity`, `#language models`, `#model evaluation`, `#cross-entropy`, `#AI research`

---

<a id="item-tech-news-3"></a>
### [GL.iNet Security Notice Draws Questions on Router Compromise](https://www.gl-inet.com/en-us/blogs/blog/glinet-security-notice-2026-11-20) ⭐️ 7.0/10

GL.iNet has published a security notice dated 2026-11-20 for its networking devices, but the notice text was not included in the supplied material, leaving affected models, firmware versions, and remediation steps unconfirmed. Community discussion centered on whether travel routers such as the GL-E750V2 Mudi are affected and on replacing GL.iNet firmware with OpenWrt. Commenters also cited a GL.iNet forum thread alleging malware on devices since at least the prior year, a user report not independently verified here.

hackernews · gregsadetsky · Nov 22, 23:06 · [Discussion](https://news.ycombinator.com/item?id=50604988)

**「Cloud management exposure」** GoodCloud is GL.iNet&\#x27;s cloud remote-management service for routers and KVM devices, allowing administrators to reach and manage them remotely. GL.iNet&\#x27;s November 20, 2026 notice says a vulnerability in that cloud service was exploited by an unauthorized party to access and install malicious software on some routers and KVM devices, a confirmation also reported by BleepingComputer.

**「Limited mitigation path for Mudi V2 owners」** For owners of the Mudi V2 \(GL-E750V2\) travel router, switching to OpenWrt as a mitigation is not straightforward: the OpenWrt device page covers the original GL-E750 but warns that Mudi v2 does not yet have official support, noting a shift from PCIe LTE to M.2 LTE. Users asking whether the notice covers travel routers therefore face a gap between the general advice to flash open firmware and the actual availability of a supported build for that model.

**「Community Discussion」** Commenters split between urging users to remove cloud connectivity and flash OpenWrt on supported GL.iNet routers, and asking whether specific travel models are affected; one noted that GL.iNet&\#x27;s KVMs lack an OpenWrt alternative. One commenter linked a GL.iNet forum thread claiming devices had been compromised since at least the previous year, a user-supplied report that the available notice text does not confirm.

<details><summary>References</summary>
<ul>
<li><a href="https://www.gl-inet.com/en-us/blogs/blog/glinet-security-notice-2026-11-20">GL.iNet Security Notice 2026-11-20</a></li>
<li><a href="https://forum.gl-inet.com/t/2026-11-20-gl-inet-security-notice-goodcloud-kvm-routers/73056">2026-11-20: GL.iNet Security Notice - GoodCloud / KVM / Routers</a></li>
<li><a href="https://www.bleepingcomputer.com/news/security/hackers-exploit-glinet-cloud-flaw-to-infect-routers-kvm-devices/">Hackers exploit GL.iNet cloud flaw to infect routers, KVM devices</a></li>
<li><a href="https://openwrt.org/toh/gl.inet/gl-e750">[ OpenWrt Wiki] GL . iNet GL - E 750 ( Mudi )</a></li>

</ul>
</details>

**Tags**: `#security`, `#routers`, `#GL.iNet`, `#firmware`, `#OpenWrt`

---

<a id="item-tech-news-4"></a>
### [Phison unveils space-grade SSDs, 488 TB planned for 2027 orbital data center](https://videocardz.com/newz/phison-announces-488tb-of-ssd-storage-for-space-data-centers-pricing-expected-to-be-astronomical) ⭐️ 7.0/10

Phison announced the Pascari Space SSD line for spacecraft, satellites and orbital data centers, split into Flight Critical, Main Storage and Orbital Data Center classes with drives up to 128 TB. The company confirmed the SSDs will fly on Lonestar Data Holdings&\#x27; StarVault-001 orbital data center, scheduled to launch in the first half of 2027 with 488 TB of Phison storage that yields roughly 370 TB of usable capacity in low Earth orbit, counted as total system capacity. Phison says pSLC mode on some models raises write endurance by up to 60 times, and states the products are already available, though the StarVault-001 deployment remains a 2027 plan.

telegram · zaihuapd · Nov 22, 10:31

**「Background」** Storage destined for orbit has to survive radiation, vacuum and thermal cycling without hands-on servicing, which is why vendors qualify dedicated space product lines rather than shipping standard data-center drives. Lonestar&\#x27;s StarVault-001 is the specific orbital data center that the announced 488 TB figure is tied to.

**「Impact」** The 370 TB usable-versus-488 TB raw gap indicates that part of the onboard capacity is given up to redundancy or formatting overhead, so orbital-compute operators should plan around usable rather than raw figures. Because the drives are shipping now but StarVault-001 is not due to launch until the first half of 2027, in-orbit endurance and reliability of the line remain unproven.

**Tags**: `#space-grade SSDs`, `#orbital data centers`, `#Phison`, `#storage hardware`, `#pSLC`

---

<a id="item-tech-news-5"></a>
### [Windows Server 2028 drops WoW64 by default, blocking 32-bit apps](https://www.windowslatest.com/2026/11/23/32-bit-apps-days-are-numbered-as-microsoft-strips-support-bit-by-bit-starting-with-windows-server-2028-but-windows-11-is-safe-for-now/) ⭐️ 7.0/10

Microsoft said at Ignite 2026 that Windows Server 2028 will ship without the WoW64 compatibility subsystem, so 32-bit applications will not run out of the box. The release is planned for fall 2027 alongside Windows 11 27H2. Administrators can add WoW64 back as a Feature on Demand \(FoD\), typically via PowerShell or DISM on Server Core; Microsoft says the default removal reduces attack surface and blocks 32-bit malware. Windows 11 retains WoW64, and Microsoft has not announced a removal plan for it.

telegram · zaihuapd · Nov 23, 03:03

**「What WoW64 does」** WoW64 is the compatibility layer that lets 64-bit Windows run 32-bit x86 applications; without it, those binaries cannot load. It has been part of the default Windows Server installation, so Windows Server 2028 changes the baseline rather than eliminating 32-bit support entirely, since Microsoft keeps WoW64 available as an optional on-demand feature.

**「Impact」** Server administrators and software teams that depend on legacy 32-bit binaries should inventory those dependencies before planning Server 2028 deployments, because images provisioned without the WoW64 FoD will fail to launch them; restoring support means adding the feature during or after installation, using PowerShell or DISM on Server Core.

**Tags**: `#Windows Server`, `#WoW64`, `#backward compatibility`, `#Microsoft`, `#32-bit apps`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [NVMe KV Pool Matches DRAM for Agentic vLLM Serving](https://vllm.ai/blog/2026-11-23-skip-the-dram-tier) ⭐️ 8.0/10

rss · vLLM Blog · Nov 23, 00:00

**「Background」** Agentic serving is dominated by multi-turn sessions resending long, already-seen prefixes: AgentX&\#x27;s median turn has 142K input tokens, over 96% seen before, so KV-cache hits strongly affect throughput. GPU memory and DRAM fill quickly—Kimi-K3 wrote 2.3–4.6 TB of KV hourly, leaving a 1.8 TB DRAM pool 23–47 minutes of retention.

**「Solution」** AMD and Embedded LLM tested MoRI UMBP on 16 MI355X GPUs with 1.8 TB pools: one in DRAM, one entirely on local NVMe with only ~80 GB DRAM buffering/staging. At 48, 70, and 96 concurrent AgentX sessions, NVMe stayed within 1% of DRAM, hit rates within 0.08% and TTFT similar; a repeat elsewhere put NVMe 0.4–0.9% ahead. The authors attribute parity to equal capacity and eviction plus asynchronous loads that finish while requests wait for prefill. Tuning mattered: 256 MiB segment files instead of 4 GiB raised throughput 15.6%, reporting GPU-resident prefix hits added 2.1–3.9%, and denser hybrid-model checkpoints raised hit rate from 91.4% to 95.6% and throughput 33%. Cost shifts from capacity to writes: ~$59,000 of drives rated for 83 TB/day held a day of KV versus a $76,000 DRAM pool holding 31 minutes, but the test drives could wear out in ~5.5 months at 96 sessions. Capacity, not medium, explained a 4.6 TB NVMe pool&\#x27;s 5.1× lead over 1.0 TB DRAM; one no-write-buffer run at 96 sessions was 6.7% slower.

**「Takeaway」** The reported result supports skipping the DRAM tier for same-size NVMe pools in this vLLM/AMD setting, because capacity and retention—not raw load latency—can govern agentic hit rates. It also makes write endurance, not just throughput, the central constraint on broader deployment.

**Tags**: `#KV cache`, `#NVMe`, `#vLLM`, `#agentic serving`, `#storage tiering`

---

<a id="item-tech-blog-2"></a>
### [The Case for Purposeful Flailing in Ambiguous Engineering Work](https://seangoedecke.com/when-in-doubt-flail-about/) ⭐️ 6.0/10

rss · Sean Goedecke · Nov 23, 00:00

**「Background」** When guidance is unclear and no obvious course exists, Sean Goedecke argues that the cautious instinct to wait for better understanding is usually wrong. He acknowledges that indiscriminate action can damage a reputation at a tech company, but frames the problem as execution rather than the impulse itself.

**「Solution」** Goedecke&\#x27;s method is to try many different things, watch feedback closely, and ruthlessly drop approaches that are not getting positive signals. Breadth provides contact with reality, raises the odds that one of many likely-bad plans works, and prevents over-investment in any single plan. He applies this to product work—where GitHub Models experiments, including AI inference via a GitHub Actions token, seeded what became Continuous AI—to large tangled systems, where speculative changes should be kept only if they show improvement, and to organizational problems, where senior engineers should volunteer and propose without expecting most attempts to land. In the organizational case, missing feedback is especially dangerous because people may redirect their frustration at the engineer. Goedecke says the approach feels like flailing from the inside even when it looks proactive from outside, so that discomfort should be treated as expected rather than as evidence of failure.

**「Takeaway」** For Goedecke, effective engineering in ambiguity depends less on finding the right plan up front than on generating options, reading feedback honestly, and abandoning failures fast enough to preserve trust.

**Tags**: `#engineering-process`, `#problem-solving`, `#organizational-dynamics`, `#feedback-loops`, `#product-development`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Nasdaq Falls 5.28% as Asian Authorities Announce Stabilization Measures](https://news.bjd.com.cn/2026/11/22/12039852.shtml) ⭐️ 9.0/10

US technology stocks sold off sharply on Friday, with the Nasdaq falling 5.28% and the Philadelphia Semiconductor Index dropping nearly 11%, as authorities in mainland China, South Korea and Taiwan announced market-stabilization measures.

telegram · zaihuapd · Nov 22, 13:24

**「Background」** Worries about AI spending had already hit US tech shares in late October, when the Nasdaq 100 fell 3.5% in a single session, its worst month since March 2025. The mainland&\#x27;s cut of the minimum margin-financing ratio to 80% reverses a January move by the Shanghai, Shenzhen and Beijing exchanges that raised it from 80% to 100% for new margin contracts.

**「Impact」** Taiwan short sellers face a ban on selling below the previous close from Nov. 23 and a 150% margin requirement, up from 130%, while South Korean listed companies get a three-month easing of daily buyback order limits from Nov. 24.

<details><summary>References</summary>
<ul>
<li><a href="https://finance.sina.com.cn/stock/usstock/c/2026-10-31/doc-inixaepa5130478.shtml">美国股市：纳斯达克100指数重挫3.5% AI投资疑虑加剧科技股抛售_新浪财...</a></li>
<li><a href="https://c.m.163.com/news/a/KJ8B7DVI0534A4SC.html">“慢牛”、“长牛”信号明确！ 融 资 保 证 金 比 例 上调至100%，释放哪些深意</a></li>

</ul>
</details>

**Tags**: `#US tech selloff`, `#Asian market stabilization`, `#short-selling restrictions`, `#margin trading rules`, `#semiconductor stocks`

---

<a id="item-finance-news-2"></a>
### [Record El Niño Warming Projected to Worsen Global Food Insecurity](https://www.wired.com/story/how-this-years-super-el-nino-will-worsen-global-hunger/) ⭐️ 7.0/10

Record El Niño-related warming in the central tropical Pacific reached 3.5°C as of October, above the previous record of about 2.75°C, according to Berkeley Earth climate scientist Zeke Hausfather. The World Food Programme warned in August that this El Niño could push an additional 49 million people into acute food insecurity by the end of 2027, bringing the total to 274 million.

telegram · zaihuapd · Nov 22, 14:09

**「Background」** El Niño is a recurring warming of the tropical Pacific that disrupts rainfall and harvests; forecasters warned in July 2026 that this event could be the strongest on record and, combined with global warming, push global temperatures to new highs in 2027.

**「Impact」** The added need would fall on households relying on humanitarian food aid, as global assistance funding in 2025 was 30% below its 2022 peak and WFP’s Somalia coverage fell from 10 million people in a comparable drought to under 1 million.

<details><summary>References</summary>
<ul>
<li><a href="https://www.nature.com/articles/d41586-026-02293-y">This El Niño is set to be the largest on record by a ‘mind ...</a></li>
<li><a href="https://www.wired.com/story/2026-el-nino-the-strongest-in-150-years/">The 2026 El Niño Is on Track to Be the Strongest on Record</a></li>

</ul>
</details>

**Tags**: `#El Niño`, `#food security`, `#humanitarian aid`, `#climate risk`, `#macro policy`

---

<a id="item-finance-news-3"></a>
### [Ant Group Leads $100 Million Round for Simplexity at $1.6 Billion Valuation](https://www.bloomberg.com/news/articles/2026-11-22/ant-group-bets-on-simplexity-to-thrive-in-china-s-humanoid-race) ⭐️ 7.0/10

Bloomberg reported that Ant Group led a $100 million pre-A funding round for Chinese robotics startup Simplexity Robotics at a $1.6 billion post-money valuation, with existing investors including Alibaba, Tencent, HongShan and BlueRun Ventures also participating.

telegram · zaihuapd · Nov 23, 02:02

**「Background」** Simplexity was founded in Hangzhou in July 2025 by former Li Auto executives and had already disclosed five funding rounds totaling 2 billion yuan by March, when its post-money valuation exceeded $1 billion.

**「Impact」** The funding gives Simplexity capital to compete with more established Chinese humanoid-robot makers such as Unitree and UBTech, Bloomberg reported.

<details><summary>References</summary>
<ul>
<li><a href="https://aiweekly.co/alerts/ant-group-leads-100m-pre-a-for-simplexity-at-16b-valuation">Ant Group Leads $100M Pre-A for Simplexity at $1.6B Valuation</a></li>
<li><a href="https://www.humanoidmegahub.com/robots/702-i-series">I-Series by Simplexity Robotics – Humanoid Robot ...</a></li>

</ul>
</details>

**Tags**: `#Ant Group`, `#humanoid robotics`, `#startup funding`, `#China tech`, `#valuation`

---