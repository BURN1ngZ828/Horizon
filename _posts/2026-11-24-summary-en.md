---
layout: default
title: "Horizon Summary: 2026-11-24 (EN)"
date: 2026-11-24
lang: en
---

> From 38 items, 13 important content pieces were selected

---

**Technology News**
1. [Ladybird releases first alpha for macOS and Linux](#item-tech-news-1) ⭐️ 8.0/10
2. [Zhipu releases GLM-5.4, its first loop transformer for coding](#item-tech-news-2) ⭐️ 8.0/10
3. [Baidu open-sources 280B ERNIE 5.5 Flash Preview under Apache 2.0](#item-tech-news-3) ⭐️ 8.0/10
4. [Nested Browser-in-a-Browser Demo Tied to trynix Draws Notice](#item-tech-news-4) ⭐️ 7.0/10
5. [Stalwart Claims Drop-In Replacement for Microsoft Exchange](#item-tech-news-5) ⭐️ 7.0/10
6. [NariQ releases 10 GB 3-bit Qwen3.8-27B GGUF, claims near-BF16 quality](#item-tech-news-6) ⭐️ 7.0/10
7. [Riemann Hypothesis &\#x27;AI Proof&\#x27; Challenged as Vacuous; Author Admits &\#x27;Garbage&\#x27; Code](#item-tech-news-7) ⭐️ 7.0/10
8. [EU business coalition urges probe of Apple&\#x27;s iPhone browser limits](#item-tech-news-8) ⭐️ 7.0/10
9. [Singapore&\#x27;s PM Says Country Won&\#x27;t Be Conduit for Evading US Chip Controls](#item-tech-news-9) ⭐️ 7.0/10
10. [Anthropic claims internal Claude found VP≠VNP, publishes Lean 4 proof](#item-tech-news-10) ⭐️ 7.0/10
11. [Novartis CEO: AI won&\#x27;t cure cancer, may cut R&amp;D by 4 years](#item-tech-news-11) ⭐️ 7.0/10

**Technology Blog**
1. [ERNIE 5.5 Flash Preview&\#x27;s vLLM Plugin and Kernel Optimizations](#item-tech-blog-1) ⭐️ 7.0/10

**Financial News**
1. [Fed’s Williams Says More Rate Action May Be Needed ‘Over Time’ to Curb Inflation](#item-finance-news-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Ladybird releases first alpha for macOS and Linux](https://ladybird.org/posts/alpha/) ⭐️ 8.0/10

Ladybird released its first alpha, with installable builds for macOS and Linux so users no longer need to compile it themselves. The independent browser implements most core components itself—HTML parsing, CSS, layout, JavaScript, and WebAssembly—while using HarfBuzz for text shaping, Skia for 2D graphics, ffmpeg for video, and SQLite for storage. The alpha is explicitly incomplete: some sites will not work and it will sometimes crash; a tester found WebAssembly ffmpeg and Pyodide tools working, but Datasette Lite failed on a missing service-worker API. Ladybird&\#x27;s October newsletter reported a gain of 75,650 web-platform-tests passes, with its best run finishing above Safari and below Firefox.

hackernews · janvdberg · Nov 23, 16:13 · [Discussion](https://news.ycombinator.com/item?id=50614249)

**「Background」** Ladybird began as part of the SerenityOS project and still reuses some of its code, while implementing its own HTML parsing, CSS, layout, JavaScript and WebAssembly components and relying on external projects including HarfBuzz, Skia, ffmpeg and SQLite. In October 2026 the project reported a large jump in web-platform-tests passes after directing AI coding agents at missing functionality, groundwork that preceded this first downloadable alpha for macOS and Linux.

**「Impact」** Users can evaluate the alpha on macOS and Linux without a build toolchain, but web apps that depend on service workers remain a compatibility risk—Datasette Lite failed on navigator.serviceWorker.startMessages. The browser includes an in-browser broken-site report flow and post-crash reports that users can inspect before sending.

**「Community discussion」** Commenters reported strong site compatibility: one said every site they tried rendered correctly but scrolling was slightly jerky, and another said Proxmox&\#x27;s NoVNC view was faster than in Firefox. Another commenter urged Ladybird to prioritize anti-fingerprinting measures and more granular permissions, presenting those as desired future design rather than existing behavior.

**Tags**: `#browsers`, `#Ladybird`, `#web engines`, `#open source`, `#privacy`

---

<a id="item-tech-news-2"></a>
### [Zhipu releases GLM-5.4, its first loop transformer for coding](https://z.ai/blog/glm-5.4) ⭐️ 8.0/10

Z.ai \(Zhipu AI\) has released GLM-5.4, its first model built on a looped-transformer architecture, in which a group of weight-shared layers runs for multiple iterations to deepen the network without increasing the parameter count. The coding-focused model is not available as open weights and cannot currently be reached through Z.ai&\#x27;s regular API plan; access requires a Coding Plan subscription, whose API keys work with the same OpenAI-compatible Responses API at https://api.z.ai/api/v1. Simon Willison tested it through that route and found its pelican SVGs similar in quality to GLM-5.3&\#x27;s, while noting a stark style shift from GLM-5.1 and 5.2.

hackernews · foohis · Nov 23, 10:06 · [Discussion](https://news.ycombinator.com/item?id=50609685)

**「What a loop transformer is」** A standard Transformer runs each layer once per forward pass. A looped Transformer instead reuses a group of weight-shared layers for several iterations, refining hidden states and gaining effective depth without adding parameters. Zhipu&\#x27;s GLM-5.4 follows Thinking Machines Lab&\#x27;s Inkling 2 Mini, introduced days earlier, which also runs middle layers multiple times per token.

**「Impact」** Developers who want to try GLM-5.4 must obtain a Coding Plan subscription key rather than use the regular API plan, and teams that need open weights cannot self-host it yet. The existing llm-zai plugin does not support the new model, so Willison shipped a temporary llm-glm plugin and said he will likely retire it once llm-zai catches up.

**「Community discussion」** Commenters praised Zhipu for publishing technical details, with one calling it a refreshing contrast to locked-down Western labs, and another explaining that looped transformers target inference memory-bandwidth costs by reusing layers instead of reloading new weights. A separate user reported that Chinese models&\#x27; &quot;marathon thinking&quot; sessions make even conceptually simple tasks much slower than frontier models, and speculated that this behavior may help benchmark scores.

**Tags**: `#LLM architecture`, `#looped transformers`, `#code generation`, `#GLM/Zhipu`, `#open models`

---

<a id="item-tech-news-3"></a>
### [Baidu open-sources 280B ERNIE 5.5 Flash Preview under Apache 2.0](https://x.com/Baidu_Inc/status/2125077484442190137) ⭐️ 8.0/10

Baidu announced on November 24 that it has open-sourced ERNIE 5.5 Flash Preview, a 280B-parameter mixture-of-experts model with 14B active parameters per token, 1M-token context, and Apache 2.0 weights on Hugging Face and ModelScope. Baidu says the preview is the first post-trained model based on ERNIE 5.5 Flash Base and can be deployed or fine-tuned with vLLM or SGLang. Circulating benchmark charts show 46.5 on Terminal-Bench 4.0 and 71.2 on DeepSWE v1.1, but Baidu has not said whether these results were independently verified.

telegram · zaihuapd · Nov 24, 07:32

**「Background」** A mixture-of-experts model routes each token through only part of its total parameter set, so a 280B-parameter model can activate 14B parameters per token; that distinction affects memory requirements and inference cost. This release is labeled a preview and is described as the first post-trained model built on ERNIE 5.5 Flash Base, so the supplied material does not establish final model behavior or independently verified benchmark results.

**「Impact」** Developers and organizations can download the weights under a permissive license and use vLLM or SGLang for self-hosted deployment and fine-tuning, but the preview label and unverified benchmark figures make independent evaluation necessary before production use.

**Tags**: `#open-source LLM`, `#Baidu ERNIE`, `#Mixture-of-Experts`, `#long context`, `#Apache 2.0`

---

<a id="item-tech-news-4"></a>
### [Nested Browser-in-a-Browser Demo Tied to trynix Draws Notice](https://fzakaria.com/2026/11/23/2035-came-early) ⭐️ 7.0/10

For developers following Nix-based browser experiments, a new blog post presents a nested browser-in-a-browser demo tied to trynix, which commenters identify as a downstream Nix fork. The available description frames it as a technical demonstration, not a shipped tool, and supplies no benchmark, release artifact, or concrete production use case. It drew strong Hacker News interest, but the evidence does not establish that the approach is practical or faster than alternatives.

hackernews · setheron · Nov 24, 06:30 · [Discussion](https://news.ycombinator.com/item?id=50624497)

**「Background」** Farid Zakaria released TryNix in early September 2026: a browser-based Nix package runner that boots an x86\_64 Linux kernel compiled to WebAssembly inside a tab and can run any of roughly 310,000 nixpkgs package versions, with output going to a serial console rather than a graphical desktop. The current post appears to extend that work into a browser nested inside a browser — the setup commenters are treating as a demonstration rather than a proven production tool.

**「Practical impact」** Developers can experiment with nixpkgs packages as a client-side Linux guest in a browser tab, with no server component, according to the trynix project. However, the discussion provides no evidence that this nested browser setup is production-ready, so teams should benchmark boot and workload performance before relying on it.

**「Community Discussion」** Commenters praised the demo as unexpectedly early and technically impressive, but the main disagreement was practical utility. One asked what a setup only one fork downstream from trynix would be used for and compared the enthusiasm to earlier V8 isolates and Pyodide experiments; another asked whether the nested approach is actually faster, as a talk had claimed.

<details><summary>References</summary>
<ul>
<li><a href="https://simonwillison.net/2026/Sep/10/trynix/">Any Nix package, live in your browser | Simon Willison’s Weblog</a></li>
<li><a href="https://dev.to/techaiwire/trynix-runs-any-nix-package-in-a-browser-tab-12i1">TryNix runs any Nix package in a browser tab - DEV Community</a></li>
<li><a href="https://fzakaria.com/2026/09/04/any-nix-package-live-in-your-browser">Any Nix package, live in your browser | Farid Zakaria ’s Blog</a></li>
<li><a href="https://trynix.dev/">trynix</a></li>
<li><a href="https://unkernel.dev/">︎ unkernel</a></li>

</ul>
</details>

**Tags**: `#browser-in-browser`, `#WebAssembly`, `#Nix`, `#systems experimentation`, `#technical demo`

---

<a id="item-tech-news-5"></a>
### [Stalwart Claims Drop-In Replacement for Microsoft Exchange](https://stalw.art/blog/microsoft-exchange-replacement/) ⭐️ 7.0/10

Stalwart announced that it can serve as a drop-in replacement for Microsoft Exchange, offering an open-source mail server to organizations that need Exchange-compatible email. The supplied announcement does not specify supported protocols, Outlook or MAPI compatibility, migration tooling, licensing, availability, or independent test results, so the replacement claim is a vendor statement rather than a demonstrated capability. The post drew substantial community discussion, with the main concerns centering on client compatibility and regulatory archiving.

hackernews · shaunpud · Nov 23, 22:32 · [Discussion](https://news.ycombinator.com/item?id=50620349)

**「Background」** Stalwart is an open-source mail and collaboration server written in Rust. Its 1.2.0 release adds Microsoft-compatible protocols — MAPI over HTTP, Exchange Web Services, ActiveSync, and Autodiscover — so Outlook, Apple Mail, and mobile devices can connect to it much as they would to an Exchange server. The release arrives as Microsoft has said EWS in Exchange Online will end in April 2027 and as the new Outlook for Windows works only through Microsoft&\#x27;s cloud, making third-party Exchange-compatible servers relevant to organizations that want self-hosting.

**「Migration planning caveat」** Administrators evaluating Stalwart as an Exchange replacement should verify client and protocol coverage before committing to a migration, because the surrounding Microsoft stack is changing independently of the mail server: Microsoft&\#x27;s published schedule has Exchange Web Services in Exchange Online starting to be disabled globally for all organizations in October 2026, so any EWS-dependent client or third-party application needs its own replacement path regardless of which back end an organization chooses.

**「Community Discussion」** Commenters challenged the drop-in framing on practical grounds: one asked how Outlook users would connect if Outlook stops supporting on-premises Exchange, another said Stalwart&\#x27;s regular and open-source plans lack the immutable 10-year archiving required under Germany&\#x27;s GoBD, and another argued that extending Microsoft&\#x27;s protocol stack ultimately works against the open email ecosystem. A separate commenter praised the release and noted that Kagi Mail was built on Stalwart.

<details><summary>References</summary>
<ul>
<li><a href="https://stalw.art/blog/microsoft-exchange-replacement/">Stalwart is now a drop-in replacement for Microsoft Exchange</a></li>
<li><a href="https://www.startuphub.ai/ai-news/technology/2026/stalwart-1-2-0-replaces-exchange-and-keeps-outlook-working">Stalwart 1.2.0 replaces Exchange and keeps Outlook…</a></li>
<li><a href="https://linuxiac.com/stalwart-1-2-offers-open-source-microsoft-exchange-replacement/">Stalwart 1.2 Offers Open-Source Microsoft Exchange Replacement</a></li>
<li><a href="https://learn.microsoft.com/en-us/exchange/clients-and-mobile-in-exchange-online/deprecation-of-ews-exchange-online">Deprecation of Exchange Web Services in Exchange Online</a></li>

</ul>
</details>

**Tags**: `#open-source email`, `#Microsoft Exchange`, `#mail server`, `#interoperability`, `#email infrastructure`

---

<a id="item-tech-news-6"></a>
### [NariQ releases 10 GB 3-bit Qwen3.8-27B GGUF, claims near-BF16 quality](https://huggingface.co/nari-labs/Qwen3.8-27B-NariQ-GGUF) ⭐️ 7.0/10

NariQ has published 3-bit-or-lower GGUF quantizations of Qwen3.8-27B, including 3-bit, 2.5-bit, and 2-bit variants, pitched as fitting in roughly 10 GB. The release claims near-BF16 quality across agentic, math, multilingual, and image benchmarks; in its own table, 3-bit and 2.5-bit scores track BF16 closely, while 2-bit drops sharply on DeepSWE \(28.6 vs 39.8\) and Terminal-Bench 2.1 \(52.4 vs 62.6\). Decode speed is described as comparable to other quants on an RTX PRO 6000, but running the files currently requires NariQ&\#x27;s custom llama.cpp fork.

hackernews · toebee · Nov 23, 13:42 · [Discussion](https://news.ycombinator.com/item?id=50611402)

**「Quantization basics and the NariQ fork」** GGUF is the file format llama.cpp uses for local inference, and quantization stores a model&\#x27;s weights at fewer bits each — measured in bits per weight \(bpw\) — trading file size and memory for some accuracy loss. Community quants of a 27B model have typically stayed at 4 bpw or above; NariQ&\#x27;s release targets 3.0, 2.5 and 2.0 bpw using a &quot;trellis-coded&quot; scheme, and the project&\#x27;s own llama.cpp fork is required to load those files rather than mainline llama.cpp. The base Qwen3.8-27B model itself ships under Apache 2.0 with a vision encoder and 262k context, which is why the release reports image-understanding and long-context benchmarks.

**「Impact」** Developers and self-hosters can test a 27B model in a roughly 10 GB footprint, but it is not a drop-in upstream llama.cpp quant because the custom fork must be built and Metal support is source-only; one commenter reports about 3.8 tok/s decoding on an 18 GB M3 Pro at 3.0 bpw, so fitting the file does not guarantee usable speed on low-memory Macs.

**「Community discussion」** Commenters treated the multi-task, held-out evaluation as a meaningful improvement over benchmark-only quantization claims, but several remained unconvinced that parity on these tests proves general quality: rao-v warned that QAT-style efforts can overfit benchmark-like data, Retro\_Dev asked what information is actually lost, and WithinReason argued the plots show most gains come from a harness difference. Hardware interest centered on whether the model can run on a 16 GB Mac and why Volta/sm\_70 GPUs are unsupported.

<details><summary>References</summary>
<ul>
<li><a href="https://huggingface.co/nari-labs/Qwen3.8-27B-NariQ-GGUF">nari - labs / Qwen 3 . 8 - 27 B - NariQ - GGUF · Hugging Face</a></li>
<li><a href="https://github.com/nari-labs/nari-llama.cpp">GitHub - nari - labs / nari -llama.cpp: llama.cpp fork that runs NariQ ...</a></li>
<li><a href="https://www.yottalabs.ai/post/how-to-run-qwen-3-8-27b-locally-ollama-gguf-single-gpu-2026">How to Run Qwen 3 . 8 27 B Locally: Ollama, GGUF , and... | Yotta Labs</a></li>

</ul>
</details>

**Tags**: `#quantization`, `#local LLMs`, `#GGUF`, `#llama.cpp`, `#agentic benchmarks`

---

<a id="item-tech-news-7"></a>
### [Riemann Hypothesis &\#x27;AI Proof&\#x27; Challenged as Vacuous; Author Admits &\#x27;Garbage&\#x27; Code](https://x.com/i/web/status/2124987173439209561) ⭐️ 7.0/10

A claimed Lean formalization of the Riemann hypothesis and its generalized version, attributed to Alpöge and Claude, is being challenged as vacuous after the project released 17 million lines of Lean across 175,000 files but no human-readable proof. The Lean and Mathlib community reportedly said the next day it had “sufficient confidence” that the code proved the proposition. Researchers then pointed out that key definitions were tautological and geometric conditions were effectively vacuous, suggesting the proof may only be spinning in place. Alpöge later reportedly conceded that “250,000 pages is a joke” and that the code was “full of garbage but compiles,” calling the criticism reasonable; the account has not been independently verified.

telegram · zaihuapd · Nov 24, 01:29

**「Background」** Lean is a proof assistant, and Mathlib is its community-maintained mathematics library; formal verification requires that the encoded statement and definitions actually express the intended theorem, not merely that the code compiles. The dispute follows Levent Alpöge&\#x27;s November 20, 2026 note claiming, with Claude, a proof of the Riemann hypothesis and the generalized version for Dirichlet L-functions, with the Lean development dated October 6 to November 16 \[tool-2-2\]\[tool-2-1\]. The Lean community blog had stated that the RiemannHypothesis statement in Mathlib was correct and vetted and that Alpöge&\#x27;s library compiled \[tool-2-3\].

**「Impact」** For Lean and Mathlib users, the case shows that a successful compile does not establish that a formal statement captures the intended theorem; reviewers would need to audit the definitions and theorem statement before treating a build as proof.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Riemann_hypothesis">Riemann hypothesis - Wikipedia</a></li>
<li><a href="https://www.youtube.com/watch?v=aDl7-MWFLVc">17 Million Lines Claim to Prove Riemann . We Ran Them. - YouTube</a></li>
<li><a href="https://leanprover-community.github.io/blog/posts/riemann-hypothesis/">Lean verification of the Riemann Hypothesis | Lean community blog</a></li>

</ul>
</details>

**Tags**: `#AI for mathematics`, `#Lean`, `#formal verification`, `#Riemann hypothesis`, `#AI-generated code`

---

<a id="item-tech-news-8"></a>
### [EU business coalition urges probe of Apple&\#x27;s iPhone browser limits](https://appleinsider.com/articles/26/11/23/eu-urges-to-challenge-apples-grip-on-iphone-browsers?utm_source=rss) ⭐️ 7.0/10

A coalition of European businesses and civil-society groups, including Mozilla and Shopify, has sent a letter asking the European Commission to open a case against Apple&\#x27;s iPhone browser restrictions. The signatories say they collectively represent roughly 45,000 to 55,000 EU organizations, with signatures open until December 3, 2026. Although Apple lets rival browsers use their own engines in the EU under the Digital Markets Act, the coalition argues that technical and legal requirements still prevent vendors from migrating existing EU users away from WebKit and leave businesses dependent on the App Store to reach users. The group estimates that moving half of native iOS apps to the web would save EU businesses €11 billion in annual development costs and €1.3 billion in App Store fees; those figures are the signatories&\#x27; own projections, and no EU enforcement action has been announced.

telegram · zaihuapd · Nov 24, 03:02

**「Background」** Under the EU&\#x27;s Digital Markets Act, Apple already allows competing browsers to use their own rendering engines on iPhones in the EU. The letter argues that this formal allowance has not made it practical to move existing users off WebKit or to reach iPhone customers without going through the App Store, which is the compliance gap it wants the Commission to investigate.

**「Impact」** For EU browser vendors, DMA-driven default-browser choice has not translated into engine choice: Mozilla says daily Firefox use on iOS has doubled in the EU since 2024, but its iOS users still rely on Apple’s WebKit, so Firefox cannot move existing users to its own engine. The letter’s signatories argue this keeps developers tied to App Store distribution; their estimate that moving half of native iOS apps to the web would save EU businesses €11 billion in development costs and €1.3 billion in App Store fees a year is an advocacy projection, not a measured result.

<details><summary>References</summary>
<ul>
<li><a href="https://www.macrumors.com/">MacRumors: Apple News and Rumors</a></li>
<li><a href="https://blog.mozilla.org/en/mozilla/internet-policy/apple-ios-browser-engine-rules/">Why there are still no non- WebKit browsers on iOS</a></li>
<li><a href="https://open-web-advocacy.org/blog/apples-browser-engine-ban-persists-even-under-the-dma/">Apple &#x27;s Browser Engine Ban Persists, Even Under the DMA</a></li>

</ul>
</details>

**Tags**: `#Apple`, `#EU DMA`, `#browser competition`, `#WebKit`, `#App Store`

---

<a id="item-tech-news-9"></a>
### [Singapore&\#x27;s PM Says Country Won&\#x27;t Be Conduit for Evading US Chip Controls](https://www.bloomberg.com/news/articles/2026-11-24/singapore-won-t-be-conduit-to-skirt-us-chip-curbs-wong-says) ⭐️ 7.0/10

Singapore Prime Minister Lawrence Wong said the country will not be used as a channel for companies to circumvent US chip export controls, and that authorities are investigating Megaspeed&\#x27;s purchases of Nvidia chips. The statement came a day after the US Commerce Department added Megaspeed and six other Southeast Asian firms to its trade blacklist, including related entities in Malaysia and Thailand. The Federal Register cited a &quot;significant risk&quot; that these firms would divert advanced computing products to unauthorized users. Reuters reported that Alibaba&\#x27;s Singapore subsidiary Apex Enterprise Solutions was also on the list; Alibaba said it has never transferred controlled advanced computing chips.

telegram · zaihuapd · Nov 24, 05:03

**「Background」** The remarks came a day after the US Commerce Department added Megaspeed and six other Southeast Asian firms to its trade blacklist, according to the source. The Federal Register said those firms posed a &quot;significant risk&quot; of diverting advanced computing products to unauthorized users, and the list included affiliates in Malaysia and Thailand; Reuters reported that Alibaba&\#x27;s Singapore subsidiary Apex Enterprise Solutions was also named, while Alibaba said it had never transferred controlled advanced computing chips.

**「Enforcement Exposure」** The blacklisting restricts US exports to the named firms and their Malaysian and Thai affiliates, so suppliers and partners handling Nvidia hardware in the region now need to verify end users and destinations before shipping. Alibaba&\#x27;s public denial shows listed companies are already contesting the designations, leaving the practical scope of the restrictions dependent on how the investigations and any licence decisions proceed.

**Tags**: `#export controls`, `#semiconductors`, `#Nvidia`, `#Singapore`, `#AI hardware`

---

<a id="item-tech-news-10"></a>
### [Anthropic claims internal Claude found VP≠VNP, publishes Lean 4 proof](https://github.com/anthropics/formal-math/blob/main/vp-vnp/README.md) ⭐️ 7.0/10

Anthropic on 24 November published a paper titled &quot;VP ≠ VNP over every field&quot; together with a Lean 4 formalization in its anthropics/formal-math repository, stating that the result was discovered by an internal research Claude model and that the paper and code were written by AI. Per the repository, the work proves a superpolynomial arithmetic-circuit lower bound for the Hamiltonian-cycle polynomial, which would make VP a proper subclass of VNP and settle Valiant&\#x27;s 1979 algebraic complexity conjecture — a claim about arithmetic circuits only, with no bearing on P versus NP. The formalization passed an audit against three standard axioms and a re-check by the independent kernel nanoda, with no \`sorry\` outside reserved files. However, no human mathematician has read it in full, Lean cannot confirm that the formalized statement matches the theorem claimed in prose, and appendix Q lists discrepancies between the two, so the result remains pending independent review.

telegram · zaihuapd · Nov 24, 06:02

**「Background」** VP and VNP are algebraic complexity classes introduced by Leslie Valiant in 1979 as arithmetic-circuit analogues of P and NP; VP ≠ VNP would mean that certain polynomials, such as the permanent, require superpolynomial-size arithmetic circuits. Lean 4 is a dependently typed proof assistant that can verify each proof step against its kernel, but it cannot by itself establish that the formal statement matches the intended mathematical claim.

**「Impact」** For complexity theorists and formal-verification practitioners, the Lean artifact certifies only that the checked statement follows from the stated axioms, not that it is the VP≠VNP claim itself; anyone relying on the result would first need to reconcile the appendix Q discrepancies and obtain human review of the mapping between the formal statement and the prose theorem.

**Tags**: `#AI for math`, `#complexity theory`, `#Lean 4`, `#formal verification`, `#Anthropic`

---

<a id="item-tech-news-11"></a>
### [Novartis CEO: AI won&\#x27;t cure cancer, may cut R&amp;D by 4 years](https://www.ft.com/content/1e5a9d70-221d-461d-ae03-dc235b1db340) ⭐️ 7.0/10

Novartis CEO Vas Narasimhan, who also sits on Anthropic&\#x27;s board, said AI will not cure cancer within five to 10 years, but could shorten average drug development from about 12 years to eight over roughly the next decade. At Novartis, he said, the clearest gains are in preclinical discovery, a roughly four-year stage that can be cut by up to two years. He expects success rates for entering human trials to rise from 8% to 12%, while animal testing and clinical trials cannot be skipped. His view contrasts with Anthropic&\#x27;s CEO, who has said cancer and other diseases could become relics of the past within a decade; Eli Lilly&\#x27;s CEO has also publicly expressed skepticism.

telegram · zaihuapd · Nov 24, 08:54

**「Context: how long drug development takes」** Drug candidates typically spend about four years in preclinical discovery before they reach human testing, and most programs still fail after that point — Novartis puts the success rate for candidates entering human trials at roughly 8%. The remarks land amid expansive claims from AI leaders about medicine: Anthropic&\#x27;s CEO has said diseases such as cancer could become &quot;relics of history&quot; within a decade, a prediction Eli Lilly&\#x27;s CEO has also publicly questioned.

**「Impact」** For pharmaceutical R&amp;D teams, Narasimhan&\#x27;s figures place AI&\#x27;s near-term value in earlier target and candidate discovery, not in removing the animal-testing and clinical-trial bottlenecks. Plans that assume AI can bypass those stages would overstate the likely timeline gain.

**Tags**: `#AI 药物研发`, `#制药研发周期`, `#AI 炒作`, `#行业观点`, `#生物科技`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [ERNIE 5.5 Flash Preview&\#x27;s vLLM Plugin and Kernel Optimizations](https://vllm.ai/blog/2026-11-24-ernie-5-5-flash-preview) ⭐️ 7.0/10

rss · vLLM Blog · Nov 24, 00:00

**「Background」** ERNIE 5.5 Flash Preview is a sparse mixture-of-experts model with 280B total and 14B active parameters, a 1M-token context, and agent-oriented reasoning and tool use. To make it practical on release day, Baidu&\#x27;s ERNIE team and vLLM packaged support as a plugin for vllm==0.32.0 rather than a fork.

**「Solution」** The integration combines a redesigned architecture with kernel fusion: 37 of 43 layers use compressed attention while six use MLA-DSA, routed experts run in MXFP4 W4A8 via quantization-aware training, and the KV cache is FP8. The teams report 1.55×–6.53× per-kernel speedups from folding fixed VHA mixing parameters into weights and quantizing FP8 in the same kernel, merging router GEMMs and routing steps, single-passing the roughly 200K-logit MultiMax transform with bitwise-identical output, and merging gated-attention projections. FlashIndexer adds a token-local head router trained by distillation from the full DSA indexer plus threshold pre-filtering, which the authors say yields a 40% \(1.4×\) indexing speedup at 1M context. DSpark, a three-layer draft model shipped with the weights, proposes up to seven tokens per step and reaches mean acceptance length above 4.0 on real coding and agent workloads after multi-stage training and on-policy distillation. The plugin registers architectures through vllm.general\_plugins as lazy module paths, so other models pay no import overhead and users can disable it with VLLM\_PLUGINS=&quot;&quot;; the performance figures are vendor-supplied, and the post does not detail benchmark hardware or methodology.

**「Takeaway」** The authors position day-0 model support as a thin, lazily loaded plugin over stock vLLM, with the real efficiency gains coming from carefully fused kernels plus a distilled lightweight indexer and draft model. The caveat is that most of the evidence is team-reported rather than independently benchmarked.

**Tags**: `#mixture-of-experts`, `#kernel-fusion`, `#speculative-decoding`, `#quantization-aware-training`, `#vllm-plugins`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Fed’s Williams Says More Rate Action May Be Needed ‘Over Time’ to Curb Inflation](https://www.cnbc.com/2026/11/23/john-williams-fed-inflation-rate-hikes.html) ⭐️ 7.0/10

New York Fed President John Williams said the Federal Reserve still has “more work to do” to return inflation to its 2% target and that further action can unfold “over time,” ahead of a Dec. 8-9 meeting where markets fully price a quarter-percentage-point rate increase from the current 3.75%-4% target range.

rss · CNBC Finance · Nov 23, 21:02

**「Background」** The Fed raised its benchmark rate by a quarter point in September 2026 — its first increase since 2023 — to a target range of 3.75%-4%, then held it there in October, leaving that range in place before the Dec. 8-9 meeting.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/09/16/fed-rate-decision-september-2026.html">Fed rate decision September 2026 : Rates rise to 3 . 75 %- 4 %</a></li>
<li><a href="https://tradingeconomics.com/united-states/interest-rate">United States Fed Funds Interest Rate</a></li>

</ul>
</details>

**Tags**: `#Federal Reserve`, `#monetary policy`, `#inflation`, `#interest rates`, `#FOMC`

---