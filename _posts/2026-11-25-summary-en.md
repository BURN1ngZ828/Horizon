---
layout: default
title: "Horizon Summary: 2026-11-25 (EN)"
date: 2026-11-25
lang: en
---

> From 33 items, 9 important content pieces were selected

---

**Technology News**
1. [Broadcom patches exploited critical vCenter auth bypass CVE-2026-123903](#item-tech-news-1) ⭐️ 8.0/10
2. [Apparent OpenAI preprint claims matrix multiplication exponent Θ\(n^2.25\)](#item-tech-news-2) ⭐️ 7.0/10
3. [Active campaign targets Check Point management servers via forged session cookies](#item-tech-news-3) ⭐️ 7.0/10
4. [Community Effort Runs Leaked GTA 6 Xbox Build on Windows](#item-tech-news-4) ⭐️ 7.0/10
5. [Ternary Bonsai 2.5 27B: early local inference reports](#item-tech-news-5) ⭐️ 7.0/10
6. [Simon Willison identifies three LLM inflection points in twelve months](#item-tech-news-6) ⭐️ 7.0/10
7. [GPT-6.2 Astra reportedly identifies 1808 Yale sketchbook creator in 22 minutes](#item-tech-news-7) ⭐️ 7.0/10

**Financial News**
1. [Fed’s Williams says more work needed to return inflation to 2%](#item-finance-news-1) ⭐️ 7.0/10
2. [SpaceX to Forgo $738 Million in Federal Broadband Subsidies, Offer Free Starlink Gear Instead](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Broadcom patches exploited critical vCenter auth bypass CVE-2026-123903](https://thehackernews.com/2026/11/vmware-vcenter-hit-by-another-critical.html) ⭐️ 8.0/10

Broadcom has released patches for 23 VMware vulnerabilities, including a critical authentication bypass in vCenter&\#x27;s directory service \(vmdir\) tracked as CVE-2026-123903 and rated 9.8. The flaw allows anyone who can access vCenter to bypass authentication and enter the system directly, according to the report. The item also reports that the vCenter flaw was exploited as a zero-day a few days before the patches were released.

telegram · zaihuapd · Nov 24, 14:50

**「Background」** vCenter is Broadcom&\#x27;s VMware management platform for virtualized data centers, and vmdir is the directory service that handles authentication for it. The reported flaw is an authentication bypass in that service, meaning an attacker who can reach vCenter over the network does not need valid credentials to get into the system.

**「Patch exposure」** Because CVE-2026-123903 requires only network access to vCenter and Broadcom lists no workaround, administrators should treat patching—not mitigation—as the primary fix. Any reachable vCenter management interface remains exposed until the update is applied.

<details><summary>References</summary>
<ul>
<li><a href="https://www.rescana.com/post/vmware-vcenter-cve-2026-123903-auth-bypass-and-esx-code-execution-patch-now">VMware vCenter Auth Bypass CVE-2026-123903 and ESX Code ...</a></li>

</ul>
</details>

**Tags**: `#vCenter`, `#VMware`, `#authentication bypass`, `#zero-day`, `#CVE-2026-123903`

---

<a id="item-tech-news-2"></a>
### [Apparent OpenAI preprint claims matrix multiplication exponent Θ\(n^2.25\)](https://github.com/openai/math/blob/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/paper.pdf) ⭐️ 7.0/10

A Hacker News post links to an apparent OpenAI math preprint titled “The matrix multiplication exponent is nine fourths,” which would make matrix multiplication Θ\(n^2.25\). The item supplies only the PDF link, with no abstract, proof details, or independent verification, so the claimed result should be treated as unconfirmed. Commenters disagree about its scope: one says it proves a lower bound of Ω\(n^2.25\) while an O\(n^2.25\) upper bound was already known, while another describes it as an exact exponent over every field.

hackernews · E-Reverance · Nov 25, 01:19 · [Discussion](https://news.ycombinator.com/item?id=50637220)

**「Background」** The matrix multiplication exponent ω is the asymptotic threshold: for any ε &gt; 0, n×n matrices can be multiplied in O\(n^\(ω+ε\)\) time, and most progress has come from lowering the upper bound rather than proving a matching lower bound. The linked preprint claims the exact value is nine fourths over every field, and a report on the preprint describes the claimed matching lower bound as the biggest shift in the bound since 1979.

**「Impact」** If the reported matching upper and lower bounds hold, there is no remaining asymptotic exponent left to chase: work would shift to the ε and constant factors in the stated O\(n^\(9/4+ε\)\) arithmetic-operation bound over ℂ, and to making such an algorithm usable — commenters note the known construction is far from practical. Until independent verification appears, algorithm designers should treat 9/4 as an unverified claim rather than a reason to change implementation choices.

**「Community discussion」** Commenters debated both the mathematics and the research culture: one framed the paper as resolving several Top-500 open problems, while others disputed whether it establishes an exact Θ\(n^2.25\) exponent or only a lower bound. Several questioned OpenAI’s and Anthropic’s incentives and disclosure, including speculation about unreleased models and whether such results are mainly for prestige.

<details><summary>References</summary>
<ul>
<li><a href="https://raw.githubusercontent.com/openai/math/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/paper.pdf">The matrix multiplication exponent is nine fourths</a></li>
<li><a href="https://cryptobriefing.com/openai-matrix-multiplication-exponent-9-4/">OpenAI preprint claims the matrix multiplication exponent is ...</a></li>
<li><a href="https://interestingengineering.com/culture/openai-exact-2-25-matrix-multiplication-exponent">OpenAI establishes exact 2.25 exponent for matrix multiplication</a></li>
<li><a href="https://gradientdamage.com/videos/l-bpl-matrix-multiplication-exponent-integer-multiplication-and-6-more/">L = BPL, Matrix Multiplication Exponent , Integer... | Gradient Damage</a></li>

</ul>
</details>

**Tags**: `#algorithms`, `#matrix multiplication`, `#computational complexity`, `#OpenAI`, `#Hacker News`

---

<a id="item-tech-news-3"></a>
### [Active campaign targets Check Point management servers via forged session cookies](https://www.greynoise.io/blog/check-point-security-management-servers-intrusion-campaign) ⭐️ 7.0/10

GreyNoise reports an active intrusion campaign against Check Point security management servers, centered on session-cookie forgery. Quoted report text in the discussion describes the actor scanning an HFS server, collecting \`sid\` values drawn from JavaScript&\#x27;s \`Math.random\(\)\` through repeated POSTs to the \`loginSrp1\` endpoint, reconstructing the internal state of the Node.js V8 PRNG, and recovering a session-cookie signing key to forge a signed admin cookie. The discussion does not establish how initial access was obtained; one commenter points to CVE-2026-16232 as the likely vector and asks whether every affected organization had its management server exposed to the internet.

hackernews · louiereederson · Nov 24, 16:32 · [Discussion](https://news.ycombinator.com/item?id=50630594)

**「Earlier Check Point flaw」** The campaign relies on CVE-2026-16232, a SmartConsole authentication-bypass vulnerability that Check Point publicly disclosed in July 2026 and said had already been exploited in the wild. Check Point&\#x27;s advisory states that the flaw affects a very small number of customers, while GreyNoise reports confirmed campaign activity from October 17 to November 2, 2026 against at least 22 organizations. The current incident is therefore an active exploitation campaign against an already-known vulnerability, not a newly disclosed flaw.

**「Impact」** The immediate operational concern is internet-exposed management interfaces: if a Check Point management server is reachable, the reported cookie-forging path can yield an admin session, so operators should restrict management-plane access and review Check Point&\#x27;s guidance. The supplied discussion provides no patch version or confirmation that updating alone addresses the PRNG-derived signing-key recovery.

**「Community discussion」** Commenters debate whether the root fix belongs in JavaScript&\#x27;s \`Math.random\(\)\` or in applications that misuse it, with one arguing that random number generators should be secure by default. Others question how the attacker first gained access—one cites CVE-2026-16232 and asks whether all victims exposed their management servers—and one warns that LLM-enabled attacks will widen the pool of attackers.

<details><summary>References</summary>
<ul>
<li><a href="https://www.greynoise.io/blog/check-point-security-management-servers-intrusion-campaign">An Active Intrusion Campaign Against Check Point Security ...</a></li>
<li><a href="https://www.bleepingcomputer.com/news/security/hackers-compromise-check-point-servers-in-22-organizations/">Hackers compromise Check Point Servers in 22 organizations</a></li>
<li><a href="https://support.checkpoint.com/results/sk/sk185169/">sk185169 - CVE - 2026 - 16232 - Authentication bypass with...</a></li>

</ul>
</details>

**Tags**: `#cybersecurity`, `#Check Point`, `#intrusion campaign`, `#PRNG`, `#session cookies`

---

<a id="item-tech-news-4"></a>
### [Community Effort Runs Leaked GTA 6 Xbox Build on Windows](https://twitter.com/raul_bs3/status/2125213756238291075) ⭐️ 7.0/10

A community compatibility and recompilation effort is reported to run the leaked Xbox build of GTA 6 on Windows, according to a tweet shared on Hacker News. Commenters describe two projects, xcl and VIctory, as taking a Wine-like approach; because modern Xbox hardware is close to a Windows PC and the leaked binary reportedly has no special DRM or obfuscation, the main remaining problems are compatibility and graphics. The build is unofficial and leaked, so this is not a Rockstar-sanctioned PC release, and the claim has not been independently verified in the supplied material.

hackernews · andrem · Nov 24, 13:19 · [Discussion](https://news.ycombinator.com/item?id=50627783)

**「Background」** The work targets a leaked Xbox build rather than an official PC release. The projects take a Wine-like compatibility approach, and a related effort, Xbox 2 Windows, describes static recompilation of selected machine code to C++ and selected shaders to desktop DXIL, while noting that full-game startup is unverified.

**「Legal exposure for recompilation efforts」** Projects in this space carry immediate takedown risk: Take-Two&\#x27;s DMCA notice removed Leonida, the fan recompilation led by a 15-year-old developer, and GitHub repos tied to the effort numbered in the thousands, according to The Verge and a GTA 6 PC port tracker. Forked or merged efforts such as the Victory/XCL-based recompilation that asks users to supply their own game files therefore face removal regardless of whether they distribute any copyrighted assets.

**「Community discussion」** One commenter \(Tiberium\) explains the path as a compatibility problem rather than a DRM break, while another \(pipes\) questions why a leaked console build is needed at all and warns that cloud-dependent game components could become a way to prevent similar recompilation or piracy. A separate commenter argues the project is unlikely to hurt GTA 6 commercially, citing its reported budget and revenue; this is an opinion, not a measured outcome.

<details><summary>References</summary>
<ul>
<li><a href="https://leonidapc.wiki/gta-6-pc-port/">GTA 6 PC Port Projects : Leonida, Xbox 2 Windows and More</a></li>
<li><a href="https://github.com/shadshuvo/GanduTheftAutoVi">GitHub - shadshuvo/GanduTheftAutoVi: GanduTheftAutoVi is...</a></li>
<li><a href="https://gta6.fyniti.co.uk/">GTA 6 PC Port Tracker: Does GTA VI Run on PC Yet? | Live Progress</a></li>
<li><a href="https://www.theverge.com/news/1041690/grand-theft-auto-6-pc-recompilation-project-leonida-takedown-take-two">GTA VI PC recompilation project shut down by Take - Two | The Verge</a></li>

</ul>
</details>

**Tags**: `#game recompilation`, `#Xbox compatibility`, `#reverse engineering`, `#open-source projects`, `#GTA 6`

---

<a id="item-tech-news-5"></a>
### [Ternary Bonsai 2.5 27B: early local inference reports](https://prismml.com/news/bonsai-2-5-27b) ⭐️ 7.0/10

Ternary Bonsai 2.5 27B is a new 27B local model being tested in a Q2 GGUF build for quantized inference and agentic coding. On a Mac Mini M5 Pro with 24 GB RAM and a 512 GB SSD, one commenter reported 22.3 tokens/s generation, 222.9 tokens/s prompt processing, a 2.12 s first token, and enough memory for 128k context. Another user running a self-created long-horizon benchmark saw the same 5-of-8 pass rate as Bonsai 2 but 296 steps instead of 358 and 76 minutes instead of 107. A claim that it matches Opus 4.6 on SWE-bench Verified, and the model&\#x27;s broader benchmark standing, remain unverified in the supplied material.

hackernews · b0m · Nov 24, 20:08 · [Discussion](https://news.ycombinator.com/item?id=50633922)

**「Earlier Bonsai release」** PrismML&\#x27;s Bonsai line is a ternary-quantized derivative of Qwen3.8 27B that keeps the base architecture but shrinks the model to roughly a 5.9 GB footprint. Ternary Bonsai 2.5 27B is an upgrade to the earlier Ternary Bonsai 2 27B, and PrismML says it retains that same footprint while targeting agentic coding and multi-turn tool use.

**「What it means for local agentic coding」** For developers running models on their own hardware, the practical gain is memory: a community tester reported about 22 tokens/s generation and a 2.12s first token on a 24GB Mac Mini, with 128k context fitting in memory easily — enough to attempt agentic or batch coding tasks locally rather than through an API. PrismML publishes the model as a GGUF build for vLLM serving, so teams already on that stack can adopt it without a new runtime. The caveat is quantization-dependent accuracy: PrismML says its conventional builds beat three IQ2 builds on Terminal-Bench 2.1 and DeepSWE and score highest on SWE-bench Verified, but IQ2\_S lands only 0.2 points behind, so which build you deploy changes measured results.

**「Community discussion」** Several commenters emphasize practical experience over benchmark scores: one found it &quot;useful&quot; versus version 2 and better than a Q4 Inkling 2 mini on agentic calls, while another asked whether the table&\#x27;s scores are actually worse than Qwen and whether the upside is memory and speed. A SWE-bench comparison to Opus 4.6 drew skepticism about benchmark overfitting and the representativeness of SWE-bench Verified.

<details><summary>References</summary>
<ul>
<li><a href="https://docs.prismml.com/models/bonsai-2-5-27b">Ternary Bonsai 2.5 27B - Bonsai - docs.prismml.com</a></li>
<li><a href="https://prismml.com/news/bonsai-2-5-27b">PrismML — Introducing Ternary Bonsai 2.5 27B: Powering ...</a></li>
<li><a href="https://www.eesel.ai/blog/ternary-bonsai-2-5">Ternary Bonsai 2.5 27B: benchmarks, size, speed and who it&#x27;s ...</a></li>
<li><a href="https://prismml.com/news/bonsai-2-5-27b">PrismML — Introducing Ternary Bonsai 2 . 5 27 B : Powering Agentic...</a></li>
<li><a href="https://huggingface.co/prism-ml/Ternary-Bonsai-2.5-27B-GGUF">prism-ml/ Ternary - Bonsai - 2 . 5 - 27 B -GGUF · Hugging Face</a></li>

</ul>
</details>

**Tags**: `#local LLMs`, `#model quantization`, `#agentic coding`, `#SWE-bench`, `#on-device inference`

---

<a id="item-tech-news-6"></a>
### [Simon Willison identifies three LLM inflection points in twelve months](https://simonwillison.net/2026/Nov/24/llm-inflection-points/) ⭐️ 7.0/10

In a November 24 retrospective drawn from his AI Engineer Code Summit keynote, Simon Willison argues that LLM and coding-agent capabilities crossed three inflection points in twelve months. He dates the first to Claude Opus 4.5, released a year earlier, which he says made Claude Code&\#x27;s default output generally correct for his daily coding work, with OpenAI&\#x27;s GPT-5.1 Instant, GPT-5.1 Thinking, GPT-5.1-Codex and GPT-5.1-Codex-Max having a similar effect on Codex; he quotes Anthropic&\#x27;s claim that Opus 4.5 handled ambiguity and multi-system bugs without hand-holding and says it held up. The second is the &quot;Fable class&quot; introduced by Claude Fable 5 in June—models that, given a goal and tools, can solve problems with brute force—a class he now assigns to Fable 5, 5.1, 5.2, Opus 5.5, GPT-6 Astra and possibly Gemini 4 Neon. The third is frontier models&\#x27; improved 3D modeling and game development with Blender and Three.js in September and October, including Opus 5.5&\#x27;s 12-hour playtesting and rebalancing of a strategy game; the post is a hands-on retrospective, not an independent benchmark, and the excerpt ends before his Fable 5.2 discussion.

rss · Simon Willison · Nov 24, 23:02

**「Preceding context」** Claude Code had been introduced alongside Claude 3.7 Sonnet on February 24, 2025, making the tool roughly nine months old when Claude Opus 4.5 arrived. Willison frames that November 2025 release as the point when the coding agent became reliably useful by default for his daily work, a judgment he is revisiting in this anniversary retrospective.

**「Impact」** Developers evaluating coding agents should treat default correctness on routine tasks as the adoption threshold: Willison says Opus 4.5 was the first model whose Claude Code output he did not need to correct often, and that GPT-5.1 Codex became reliably useful for many of his tasks. The supplied account gives no benchmark numbers, so teams still need their own hands-on tests before making a daily-driver switch.

**Tags**: `#LLM coding agents`, `#AI engineering`, `#model capabilities`, `#Claude Opus 4.5`, `#developer tooling`

---

<a id="item-tech-news-7"></a>
### [GPT-6.2 Astra reportedly identifies 1808 Yale sketchbook creator in 22 minutes](https://simonwillison.net/2026/Nov/24/astra-historical-mystery/) ⭐️ 7.0/10

History professor Mark Humphries reports that, with minimal prompting, GPT-6.2 Astra autonomously identified the creator of an anonymous 1808 sketchbook held at Yale&\#x27;s Beinecke Library in 22 minutes using public primary and secondary sources. According to the account, it found a diary reference to a visit by the vicomte de Chabot five days before a date in the sketchbook at a nearby river, then predicted that Chabot&\#x27;s travel journal—available only by order from Cleveland State University—would confirm the attribution. Humphries says the journal is itself a significant find for Canadian and fur-trade historians. The report is a single anecdotal case study and does not provide independent verification or the exact prompt.

rss · Simon Willison · Nov 24, 16:53

**「Background」** The case is a single anecdotal demonstration reported by history professor Mark Humphries on his Generative History Substack, not an independently replicated or peer-reviewed evaluation. The object at issue is an anonymous 1808 sketchbook held at Yale’s Beinecke Library; the post links to its digitized catalog record.

**「Impact」** Historians and archivists considering agentic search should treat the 22-minute attribution as a lead to verify rather than a settled finding: the confirming journal was available only by order from Cleveland State University, and the post gives no independent check of the chain of evidence.

**Tags**: `#AI research agents`, `#LLM applications`, `#autonomous agents`, `#historical research`, `#AI capabilities`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Fed’s Williams says more work needed to return inflation to 2%](https://www.cnbc.com/2026/11/23/john-williams-fed-inflation-rate-hikes.html) ⭐️ 7.0/10

New York Fed President John Williams said the Fed still has “work to do” to return inflation to its 2% target and that further actions can unfold “over time,” while markets fully price a quarter-point rate increase at the Dec. 8-9 meeting from the current 3.75%-4% range. He said he expects inflation to get closer to 2% in 2027 before hitting the goal the following year.

rss · CNBC Finance · Nov 24, 13:33

**「Background」** Fed officials have split over how quickly to raise rates, with Williams favoring a measured approach as inflation remains well above the 2% goal.

**Tags**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#inflation`, `#John Williams`

---

<a id="item-finance-news-2"></a>
### [SpaceX to Forgo $738 Million in Federal Broadband Subsidies, Offer Free Starlink Gear Instead](https://x.com/SawyerMerritt/status/2125314062997467640) ⭐️ 7.0/10

SpaceX has agreed to give up $738 million in US federal broadband subsidies under the NTIA&\#x27;s BEAD program and instead supply Starlink terminals free to eligible US households, with federal disbursement set at $0. Per the reported terms, SpaceX must guarantee at least 100 Mbps download and 20 Mbps upload, offer a low-cost monthly plan, commit to 10 years of service and meet the same performance testing as other BEAD recipients, while being exempted from most financial audit, procurement and administrative reporting; the account comes from a social-media post rather than an NTIA or SpaceX document, so the terms are not independently confirmed.

telegram · zaihuapd · Nov 25, 02:17

**「Background」** Starlink is SpaceX&\#x27;s satellite internet service, and BEAD is the federal broadband-expansion program administered by the National Telecommunications and Information Administration, which generally uses subsidy awards to fund network buildouts.

**「Impact」** Eligible US households in underserved areas would receive Starlink service without paying for the terminal, while SpaceX trades service and performance commitments for relief from most financial-audit and procurement-reporting rules.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Starlink">Starlink - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#SpaceX`, `#Starlink`, `#BEAD`, `#US broadband policy`, `#NTIA`

---