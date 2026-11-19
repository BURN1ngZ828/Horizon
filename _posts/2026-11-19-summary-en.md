---
layout: default
title: "Horizon Summary: 2026-11-19 (EN)"
date: 2026-11-19
lang: en
---

> From 46 items, 13 important content pieces were selected

---

**Technology News**
1. [Google launches Gemini 4 Neon for coding, research at $3/$15 per million tokens](#item-tech-news-1) ⭐️ 9.0/10
2. [Nginx 1.30.7 and 1.31.9 fix reported HTTP/2 RCE](#item-tech-news-2) ⭐️ 8.0/10
3. [Ruby discloses memory-corruption vulnerabilities in Regexp and String case conversion](#item-tech-news-3) ⭐️ 8.0/10
4. [Microsoft Announces Seven AI Models at Ignite 2026](#item-tech-news-4) ⭐️ 7.0/10
5. [Google DeepMind announces Genie 4 world model availability](#item-tech-news-5) ⭐️ 7.0/10
6. [LLM-Assisted Reverse Engineering Draws Practical Workflows and Agent Limits](#item-tech-news-6) ⭐️ 7.0/10
7. [Show HN: Interactive Voyager 1 teardown to a single memory chip](#item-tech-news-7) ⭐️ 7.0/10
8. [Tencent: WeChat Xiaowei testing reaches 30M daily users](#item-tech-news-8) ⭐️ 7.0/10
9. [Cuktech 10 Ultra firmware bug reported to risk low-voltage devices](#item-tech-news-9) ⭐️ 7.0/10
10. [PHP Plans CRITICAL Security Release for All Supported Versions](#item-tech-news-10) ⭐️ 7.0/10

**Financial News**
1. [Fed Minutes Signal More Rate Hikes, AI Inflation Risk](#item-finance-news-1) ⭐️ 8.0/10
2. [Fed’s Waller Says Half-Point December Rate Hike May Be Needed](#item-finance-news-2) ⭐️ 8.0/10
3. [Trump meets Putin and Xi separately ahead of trilateral APEC meeting](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Google launches Gemini 4 Neon for coding, research at $3/$15 per million tokens](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/) ⭐️ 9.0/10

Google has released Gemini 4 Neon, a new model in its Gemini 4 family aimed at fast end-to-end execution of complex software engineering, knowledge work, and research workflows. It is available to developers, enterprises, and Google AI Pro/Ultra subscribers at $3 per million input tokens \($0.15 cached\) and $15 per million output tokens, with a 1 million-token context window. Google reports that Neon ranks first on Artificial Analysis&\#x27;s coding-agent index at 58.6 and third overall on its intelligence index at 61 in the xhigh setting, and scores 65.2% on Terminal-Bench 4.1; Google also claims 32% lower cost per task than Carbon in the default high setting.

hackernews · yigitdemirag · Nov 18, 21:34 · [Discussion](https://news.ycombinator.com/item?id=50552424)

**「Background」** Gemini 4 Neon arrives as part of Google&\#x27;s Gemini 4 family, so its positioning depends on how it compares with sibling models rather than on a generational jump. Google&\#x27;s own cost comparison uses Carbon as the baseline for tasks at the default high setting, indicating that Neon is meant to be weighed against an existing family member as well as competing models.

**「Impact」** For teams choosing among Gemini 4 models, Neon is positioned for fast coding and research execution, while Carbon remains the long-horizon option; one commenter notes that Neon scores lower on CritPt research-reasoning evaluations despite its higher overall intelligence score.

**「Community discussion」** Commenters debated whether benchmark leadership translates into real-world quality, with one user arguing that the latest Gemini models still feel less capable than Opus 5.5 in general use. Others focused on lineup positioning, noting that Neon scores higher overall than Carbon but lower on research-scale CritPt, and one reported much faster OpenRouter throughput for Neon \(127 tokens per second versus 46 for Carbon\) while questioning whether Carbon is being throttled.

**Tags**: `#Google Gemini`, `#AI models`, `#frontier models`, `#model benchmarks`, `#AI industry`

---

<a id="item-tech-news-2"></a>
### [Nginx 1.30.7 and 1.31.9 fix reported HTTP/2 RCE](https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities) ⭐️ 8.0/10

The Nov. 18 nginx 1.30.7 and 1.31.9 releases fix 10 CVEs, including CVE-2026-123007, an HTTP/2 flow-control memory-corruption flaw that Xint says permits unauthenticated command execution inside an nginx worker. Xint&\#x27;s NGINX2Root disclosure says five nginx flaws plus a Linux kernel bug can be chained to go from an nginx visitor to host root. Rapid7 has published a proof-of-concept, with no in-the-wild exploitation reported; operators who cannot upgrade are advised to disable external HTTP/2.

hackernews · speedping · Nov 18, 15:19 · [Discussion](https://news.ycombinator.com/item?id=50547374)

**「Background」** NGINX has shipped HTTP/2 support since 2015, and the most serious flaw in this set, CVE-2026-123007, has reportedly existed in that HTTP/2 handling code since then. The disclosure bundles four other nginx RCE flaws with a Linux kernel SCTP bug that researchers say can escalate a compromised nginx worker to host root; CVSS scores have not yet been published.

**「Operational impact」** Operators running affected NGINX builds with HTTP/2 enabled face unauthenticated code execution in the worker process, and the NGINX2Root chain reported by LWN.net extended that to a host root shell, including when nginx ran in a Docker container. The concrete action is to upgrade to nginx 1.30.7 or 1.31.9, which the release notes say fix 10 CVEs, or disable external HTTP/2 where upgrading is not immediately possible; Rapid7&\#x27;s published PoC makes the window before patching more urgent.

**「Community discussion」** Commenters focused on disclosure timing, with one noting the fix appeared in the open-source repository about a week earlier and that a public warning to disable HTTP/2 could have been issued sooner. Another disputed the practical severity, saying exploitation requires about 128 Gb of HTTP/2 traffic and specific CPU instructions, while a third noted HTTP/2 is not enabled by default but is still used by about 12% of servers.

<details><summary>References</summary>
<ul>
<li><a href="https://www.getastra.com/blog/security-advisory/nginx2root/">nginx 2 root : Five nginx RCE Flaws and a Kernel Bug...</a></li>
<li><a href="https://www.ox.security/blog/nginx2root-five-critical-nginx-flaws-expose-web-servers-to-remote-code-execution/">NGINX 2 Root : 5 Critical NGINX RCE Vulnerabilities ... | OX Security</a></li>
<li><a href="https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities">Unauthenticated Remote Code Execution in NGINX ... | Wiz Blog</a></li>
<li><a href="https://lwn.net/Articles/1108362/">NGINX 2 Root: Remote Code Execution vulnerabilities in nginx [LWN.net]</a></li>

</ul>
</details>

**Tags**: `#nginx`, `#http2`, `#remote code execution`, `#vulnerability disclosure`, `#web security`

---

<a id="item-tech-news-3"></a>
### [Ruby discloses memory-corruption vulnerabilities in Regexp and String case conversion](https://www.ruby-lang.org/en/news/2026/11/18/multiple-vulnerabilities-in-regexp-and-string/) ⭐️ 8.0/10

The Ruby project published a security notice dated 2026-11-18 covering multiple vulnerabilities in its Regexp and String case-conversion code. The supplied material does not list affected Ruby versions, patched releases, or severity ratings, so the scope of the fix and who must upgrade remain unconfirmed here. Community analysis characterizes the flaws as C-level memory-corruption bugs triggered by character-encoding edge cases rather than logic errors, and one commenter posted a Shift\_JIS \`downcase\` reproducer said to misbehave on an unfixed build, though the reported output is truncated. Full exploitability and real-world impact are not established by the available evidence.

hackernews · runesoerensen · Nov 18, 23:52 · [Discussion](https://news.ycombinator.com/item?id=50554038)

**「Background」** Ruby&\#x27;s Regexp support is built on the C-based Onigmo engine, and external analysis of Ruby Onigmo regex vulnerabilities reports that such flaws can expose downstream applications—including unauthenticated remote code execution on GitLab—rather than only causing regex denial of service \(tool-1-1\). String case conversion is encoding-sensitive because some characters can change byte length when converted, so implementations must check buffer headroom for the converted result rather than assume a one-byte-in, one-byte-out transformation.

**「What Ruby users should do」** Ruby applications that pass attacker-controlled strings to case conversion should be treated as exposed until the patched release is applied, with non-UTF-8 inputs as the sharpest edge: the supplied comment demonstrates a Shift\_JIS string whose downcased bytesize is computed as roughly 4.29 GB, and a Windows-1252 upcase where ß expands to &quot;SS&quot; past a per-character buffer check. The practical action is to audit code paths that call String\#upcase/\#downcase on decoded external data \(form fields, headers, file names\) in legacy encodings, and to check the ruby-lang advisory for the versions that contain the fixes. The material provided does not establish which releases are patched or whether the bugs are remotely exploitable without a case-conversion call on crafted input.

**「Community discussion」** Commenters focused on mechanics: tptacek hypothesized that the Windows-1252 conversion path overflows because upcasing the German sharp s \(ß\) expands it to &quot;SS&quot;, adding a character while the buffer-headroom check advances one character at a time, and another commenter posted a Shift\_JIS \`downcase\` example against an unfixed version. rvz described the set as memory-unsafe-language exposure and noted the advisory credits Stephan Lipp \(Ada Logics\) and Anthropic for the report, arguing that non-disclosed AI-assisted bug discovery at scale is the bigger concern.

<details><summary>References</summary>
<ul>
<li><a href="https://raghubirmahato.com/blog/ruby-onigmo-regex-vulnerability-analysis">Ruby Onigmo Regex Vulnerability Analysis: RCE Risks Explaine</a></li>

</ul>
</details>

**Tags**: `#Ruby`, `#security vulnerabilities`, `#memory safety`, `#regexp`, `#string encoding`

---

<a id="item-tech-news-4"></a>
### [Microsoft Announces Seven AI Models at Ignite 2026](https://microsoft.ai/news/microsoft-ignite-2026/) ⭐️ 7.0/10

Microsoft announced seven new AI models at its Ignite 2026 event, positioning them around scalable price-performance. The supplied announcement does not name the models beyond MAI Code 2 mentioned in comments, and it provides no benchmarks, pricing, licensing terms, or availability dates, so the offering is announced rather than independently demonstrated.

hackernews · gmays · Nov 18, 16:08 · [Discussion](https://news.ycombinator.com/item?id=50548021)

**「Background」** Microsoft’s MAI family is the context for the Ignite 2026 launch: the company released seven MAI models on 17 November 2026, including MAI Code 2 and MAI Cyber 2 Flash. Microsoft claims MAI Code 2 reaches 98% of GPT-6.1 Sol’s coding quality at about 40% of the price, and that MAI Cyber 2 Flash beats GPT-6 Astra’s quality at less than 2% of the cost per task on the CyberGym-E2E benchmark; these are vendor claims, not independent results.

**「Procurement impact」** Because the announcement is framed around scalable price-performance and the supplied material contains no benchmarks or context-window figures, cost-sensitive, high-volume workloads such as coding assistance are the practical target, and buyers will have to validate quality themselves rather than rely on published comparisons. Microsoft has already been routing tens of thousands of weekly Excel and Outlook Copilot prompts to its in-house MAI models to reduce payments to OpenAI and Anthropic, so enterprise users may encounter MAI output inside Microsoft products without explicitly selecting a model.

**「Community Discussion」** Commenters debated Microsoft&\#x27;s competitive and open-weight strategy: one argued that Microsoft should release some models as open source or open weight to secure market share, warning of a “Windows Phone OS” repeat, while another dismissed the keynote as shallow and lacking innovation. A third reported positive hands-on use of MAI Code 2, saying it is roughly on par with Anthropic&\#x27;s Opus or OpenAI&\#x27;s Sol.

<details><summary>References</summary>
<ul>
<li><a href="https://microsoft.ai/news/microsoft-ignite-2026/">Seven new world-class models at scalable price-performance ...</a></li>
<li><a href="https://www.orcarouter.ai/blog/mai-code-2-ignite-seven-models">Seven MAI Models at Ignite 2026: Where MAI Code 2 Fits In</a></li>
<li><a href="https://emerging-tech-lab.com/press/microsoft-routes-excel-and-outlook-copilot-prompts-to-in-house-mai-models-to-cut">Microsoft Routes Excel and Outlook Copilot Prompts to In-House MAI ...</a></li>

</ul>
</details>

**Tags**: `#Microsoft`, `#AI models`, `#price-performance`, `#model competition`, `#MAI`

---

<a id="item-tech-news-5"></a>
### [Google DeepMind announces Genie 4 world model availability](https://blog.google/innovation-and-ai/models-and-research/google-deepmind/genie-4-now-available-project-genie/) ⭐️ 7.0/10

Google DeepMind announced that Genie 4, the next version of its generative interactive world model, is now available. The announcement post itself was not available for review, so specific capability, resolution, or performance details could not be verified from the primary source. A commenter quotes the post as restricting access to &quot;eligible Google AI Ultra subscribers&quot; and reports that, while signed in with a personal Gmail account, Ultra still lists Genie 3 rather than Genie 4 — leaving the tier and regional rollout unclear. The supplied material does not establish whether Genie 4 is broadly available or a limited-subscriber release.

hackernews · leumon · Nov 18, 18:49 · [Discussion](https://news.ycombinator.com/item?id=50550415)

**「Background」** Genie releases have been distributed through Google&\#x27;s paid AI subscription tiers rather than as open models, and at least one earlier version carried geographic restrictions — a commenter on this thread recalls a previous Genie being US-only. The current confusion over whether Ultra includes Genie 3 or Genie 4 is a continuation of that tier- and region-gated distribution model.

**「Impact」** For developers wanting to test Genie 4, the practical barrier reported in the discussion is subscription and geography rather than technical capability: one prospective user said their Google Workspace account could not obtain an Ultra subscription, and that a personal Gmail account showed only Genie 3 under Ultra. Anyone planning to build on the model should confirm eligibility for their specific account type and location before assuming access.

**「Community discussion」** Commenters focused on access friction and on what would make a generated world convincing, with one arguing a true world must allow a 360° look-around without details changing. Others speculated that the technology could eventually serve as a game engine — one asked whether Google would permit recreations of commercial titles like GTA — while a further commenter said the pricing and capability framing missed what they see as potentially devastating consequences of such technology.

**Tags**: `#Google DeepMind`, `#Genie 4`, `#AI product release`, `#world models`, `#game engines`

---

<a id="item-tech-news-6"></a>
### [LLM-Assisted Reverse Engineering Draws Practical Workflows and Agent Limits](https://www.slowchronicle.com/posts/llm-assisted-reverse-engineering) ⭐️ 7.0/10

A Slow Chronicle post on LLM-assisted reverse engineering prompted commenters to share concrete workflows and limits. One commenter used Gemini to reverse engineer a CCTV camera’s cloud connection plugin in about two hours, after writing a script to run the vendor’s desktop software in a separate network namespace and capture traffic with tcpdump; the plugin turned out to use a different server URL. Another commenter with little reverse-engineering experience reported successfully reverse engineering an abandoned audio effects plugin and a discontinued DSP instrument, while a practitioner said Claude’s “guessing loops” on harder targets require constant supervision and instructions to stop guessing.

hackernews · ioma8 · Nov 18, 22:29 · [Discussion](https://news.ycombinator.com/item?id=50553225)

**「Background」** LLM-assisted reverse engineering typically pairs a model-driven agent with established tools such as decompilers like Ghidra or IDA, using the agent to interpret output and propose next steps rather than replacing those tools. An arXiv paper indexed in June 2026 focused on one part of that workflow: automatic decompilers produce functionally correct but often unreadable C, and the paper used LLM agents guided by quantitative metrics to improve its readability. A later practitioner overview describes agents driving Ghidra and IDA and notes that licence terms and AI-provider usage policies can constrain what can legitimately be analyzed.

**「Impact」** Teams using LLM agents for reverse engineering should budget for supervision and experiment design: one commenter reports success after isolating the target and capturing only relevant traffic, but practitioners say agents fall into guessing loops on harder targets unless forced to run definitive tests.

**「Community Discussion」** Commenters split between reporting fast successes—such as Gemini on a CCTV plugin in about two hours—and warning that agents still need oversight; Retr0id called “guessing loops” the main annoyance with Claude on harder targets, while therepanic argued that outsourcing the process forfeits the skill-building and satisfaction of manual reverse engineering.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2606.06838">[2606.06838] LLM Agent-Assisted Reverse Engineering with ...</a></li>
<li><a href="https://dev.to/kausarraza/ai-reverse-engineering-in-2026-how-llm-agents-drive-ghidra-and-ida-and-where-they-fail-3270">AI Reverse Engineering in 2026: How LLM Agents Drive Ghidra ...</a></li>

</ul>
</details>

**Tags**: `#LLM-assisted reverse engineering`, `#reverse engineering`, `#AI coding agents`, `#software engineering`

---

<a id="item-tech-news-7"></a>
### [Show HN: Interactive Voyager 1 teardown to a single memory chip](https://rshekhar.com/voyager/) ⭐️ 7.0/10

A new Show HN interactive site by Raj Shekhar lets visitors dissect Voyager 1 down to individual hardware: it opens the radioisotope thermoelectric generator to its 24 plutonium spheres, navigates the data computer to a single memory chip and a command-computer bit, and explains the Golden Record cover. It also shows the current positions of both Voyagers, which Earth dish is listening live, and how Voyager 1 was repaired by radio, with a four-minute film accompanying the site. The project is an independent educational visualization, not an official NASA release, and the author provides direct links to the harder-to-find views.

hackernews · raj-shekhar · Nov 18, 16:18 · [Discussion](https://news.ycombinator.com/item?id=50548161)

**「Background」** Voyager 1 is now about one light-day from Earth, meaning a radio signal takes roughly 24 hours to travel one way. That delay is central to understanding the mission operations the site visualizes: commands and repairs, such as the radio fix documented in the project, had to be planned around long round-trip times and hardware that cannot be physically accessed.

**「Community discussion」** Commenters praised the visualization&\#x27;s ambition, with one calling it “awesome” and another saying they liked how Voyager is displayed even though it is missing some things. A recurring concern was provenance and depth: one commenter asked whether the site was “vibecoded” and how it was checked against authoritative sources, while another wanted the exact analog failure mode behind a CMOS memory chip that consistently reads stored values incorrectly.

**Tags**: `#Voyager 1`, `#interactive visualization`, `#computer hardware`, `#space systems`, `#technical deep-dive`

---

<a id="item-tech-news-8"></a>
### [Tencent: WeChat Xiaowei testing reaches 30M daily users](https://mp.weixin.qq.com/s/r3NthxJZQJgztyLADwNV4A) ⭐️ 7.0/10

Tencent said in its Q3 2026 earnings report that testing of WeChat&\#x27;s Xiaowei AI assistant has expanded to 30 million daily active users and that the assistant is being gradually integrated into WeChat chat, Moments, official accounts and Channels. The company says Xiaowei uses a cost-optimized custom WeLM model with low and declining inference costs, and that some inference tasks are expected to run on user devices in the future. The user and cost figures are Tencent&\#x27;s own; the source gives no independent measurement or general-availability date.

telegram · zaihuapd · Nov 18, 11:35

**「Background」** Xiaowei is Tencent’s in-app AI assistant for WeChat, and the company has been widening its test across core WeChat surfaces. The 30 million daily-active-user figure comes from Tencent’s third-quarter 2026 earnings disclosure, not from an independent measurement.

**「Impact」** For users included in the expanded test, Xiaowei is appearing across several core WeChat surfaces rather than in a separate app, while users outside the test pool have no stated date for broader access.

**Tags**: `#WeChat`, `#Tencent`, `#AI assistant`, `#LLM deployment`, `#on-device inference`

---

<a id="item-tech-news-9"></a>
### [Cuktech 10 Ultra firmware bug reported to risk low-voltage devices](https://www.bilibili.com/opus/1272074321303437312) ⭐️ 7.0/10

A hardware report alleges that Cuktech&\#x27;s 10 Ultra charger \(AD1204U\) can, in very rare cases, output up to 20V to low-voltage devices such as earphones and keyboards because an MCU firmware bug can leave the protocol chip unresponsive. Cuktech said it has identified and fixed the fault, pushing repair firmware over the air on the Monday before the report and recommending users update through the Mijia app over Bluetooth. The report cites a first damaged case in June 2026 and says devices rated for 20V, including phones and laptops, are unaffected; the damage allegation comes from a single outlet, while the fix and OTA timing are the vendor&\#x27;s account.

telegram · zaihuapd · Nov 19, 01:30

**「Background」** The Cuktech 10 Ultra \(AD1204U\) relies on a protocol chip to communicate with connected devices before supplying power. That matters because low-voltage accessories such as earbuds and keyboards are not designed to tolerate the 20V level the charger can otherwise output, so a protocol-chip failure can expose them to damaging voltage.

**「Impact」** Owners who connect low-voltage peripherals to the 10 Ultra should update the firmware before relying on it for those devices, since the remedy is an app-based Bluetooth OTA rather than an automatic charger update.

**Tags**: `#hardware`, `#firmware bug`, `#product safety`, `#chargers`, `#consumer electronics`

---

<a id="item-tech-news-10"></a>
### [PHP Plans CRITICAL Security Release for All Supported Versions](https://www.php.net/archive/2026.php) ⭐️ 7.0/10

The PHP security team has announced a security release for 19 November 2026, between 14:00 and 14:30 UTC, to fix a vulnerability affecting all supported PHP versions. The release carries the highest severity rating, CRITICAL, but PHP says the issue is triggered only under non-default configurations or uncommon environments. It is part of PHP&\#x27;s regular four-week release cycle; technical details and the fixed version numbers will be published with the release.

telegram · zaihuapd · Nov 19, 07:10

**「Context: PHP&\#x27;s security release cadence」** PHP ships security releases on a regular four-week cycle, and the security team grades each fixed issue by severity, with CRITICAL as the top level. This notice is an advance announcement: the affected code paths and the exact fixed version numbers are withheld until the release window on 19 November 2026, 14:00–14:30 UTC. The team also stated that the CRITICAL-rated issue requires non-default configuration or an uncommon environment to trigger.

**「Impact」** Administrators should plan to upgrade as soon as the fixed versions are available, but they cannot assess their own exposure from the announcement alone because the affected configurations and version numbers will not be disclosed until the release.

**Tags**: `#PHP`, `#security update`, `#vulnerability`, `#open source`, `#software maintenance`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Fed Minutes Signal More Rate Hikes, AI Inflation Risk](https://www.cnbc.com/2026/11/18/fed-minutes-october-2026.html) ⭐️ 8.0/10

Minutes from the Federal Reserve&\#x27;s October meeting released Wednesday showed that almost all participants judged further increases in the benchmark rate would likely be appropriate to bring inflation back to 2%, while the FOMC held the rate at 3.75%-4% on a 10-2 vote.

rss · CNBC Finance · Nov 18, 19:41

**「Background」** The Fed aims for 2% inflation; October CPI rose 0.4% and core CPI rose 0.3%, each 0.1 percentage point above expectations.

**Tags**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#inflation`, `#AI risk`

---

<a id="item-finance-news-2"></a>
### [Fed’s Waller Says Half-Point December Rate Hike May Be Needed](https://www.cnbc.com/2026/11/18/federal-reserve-governor-christopher-waller.html) ⭐️ 8.0/10

Federal Reserve Governor Christopher Waller said the central bank may need a half-percentage-point rate hike at the Dec. 8-9 Federal Open Market Committee meeting to &quot;shock people&quot; and bring down inflation, which he said is &quot;headed in the wrong direction.&quot; Waller, one of several policymakers who have spoken this week, also said the Fed should reverse the three quarter-point cuts made in 2025; futures markets tracked by CME Group&\#x27;s FedWatch gauge fully price a quarter-point hike in December, and it is Waller&\#x27;s own view, not an FOMC decision, that a larger move may be warranted.

rss · CNBC Finance · Nov 18, 15:13

**「Background」** The Fed had cut its benchmark rate three times in 2025, but inflation later reignited after U.S.-Israeli strikes on Iran in late February raised energy prices while tariffs lingered, leaving most inflation readings above 3%.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/18/federal-reserve-governor-christopher-waller.html">Fed’s Waller says central bank may need to ‘shock people’ with...</a></li>
<li><a href="https://www.kitco.com/news/off-the-wire/2026-11-18/waller-says-cnbc-fed-needs-get-more-aggressive-inflation-response">Waller says on CNBC the Fed needs to get more... | Kitco News</a></li>

</ul>
</details>

**Tags**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#inflation`, `#FOMC`

---

<a id="item-finance-news-3"></a>
### [Trump meets Putin and Xi separately ahead of trilateral APEC meeting](https://www.cnbc.com/2026/11/19/trump-xi-putin-china-apec-.html) ⭐️ 7.0/10

U.S. President Donald Trump met Vladimir Putin and Xi Jinping separately on Thursday, ahead of a scheduled trilateral meeting with the Russian and Chinese leaders at the Asia-Pacific Economic Cooperation summit in Shenzhen, according to pool notes and Chinese state media. At the summit, Xi said China would provide $20 million to support APEC cooperation, while Trump said he opposed regulating artificial intelligence because it would &quot;stifle&quot; the industry.

rss · CNBC Finance · Nov 19, 06:29

**「Background」** APEC is a 21-member forum whose economies account for more than half of global GDP and about 2.7 billion people, and this year&\#x27;s summit is being held in Shenzhen. The joint session would be the first face-to-face meeting of its kind between the three countries&\#x27; leaders, after Trump and Xi most recently met in September at the White House.

<details><summary>References</summary>
<ul>
<li><a href="https://www.theguardian.com/world/live/2026/nov/18/apec-summit-live-updates-xi-putin-trump-world-leaders-gather-in-china?page=with:block-6afbb2ed8f08a530bf2c3fef">Apec summit live: Xi welcomes Trump on China visit... | The Guardian</a></li>
<li><a href="https://www.aljazeera.com/news/liveblog/2026/11/19/apec-live-trump-xi-and-putin-to-meet-in-historic-three-way-china-summit">APEC Live: Trump , Xi and Putin to meet at historic trilateral China ...</a></li>
<li><a href="https://sputnikglobe.com/20261119/putinxitrump-meeting-tops-apec-summit-agenda-1125097471.html">Putin – Xi – Trump Meeting Tops APEC Summit Agenda</a></li>

</ul>
</details>

**Tags**: `#APEC`, `#US-China relations`, `#US-Russia relations`, `#geopolitics`, `#AI regulation`

---