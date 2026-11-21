---
layout: default
title: "Horizon Summary: 2026-11-21 (EN)"
date: 2026-11-21
lang: en
---

> From 41 items, 14 important content pieces were selected

---

**Technology News**
1. [Thinking Machines releases Inkling 2 Mini, an open-weight looped transformer](#item-tech-news-1) ⭐️ 8.0/10
2. [GitHub repo claims finite-time blow-up for unforced Navier–Stokes equations](#item-tech-news-2) ⭐️ 8.0/10
3. [KVM CVE-2026-99312 exposes AMD host memory via nested virtualization](#item-tech-news-3) ⭐️ 8.0/10
4. [Tao post links unforced Euler/Navier-Stokes singularities to generalized Riemann Hypothesis](#item-tech-news-4) ⭐️ 7.0/10
5. [Aaronson post examines claimed LLM-assisted Riemann Hypothesis proof in Lean](#item-tech-news-5) ⭐️ 7.0/10
6. [Ravi Vakil announces early draft of proposed Riemann Hypothesis proof](#item-tech-news-6) ⭐️ 7.0/10
7. [Levent Alpöge Claims Claude-Assisted Riemann Hypothesis Proof](#item-tech-news-7) ⭐️ 7.0/10
8. [Apple reportedly developing proactive AI agent for late 2027](#item-tech-news-8) ⭐️ 7.0/10
9. [TSMC Reportedly Pauses 16nm-and-Below Orders From Chinese Firms](#item-tech-news-9) ⭐️ 7.0/10
10. [Microsoft previews RDMA over USB4 for pooled local AI inference on Windows](#item-tech-news-10) ⭐️ 7.0/10

**Technology Blog**
1. [Why Caching LLM Output Repetition Saves Little](#item-tech-blog-1) ⭐️ 6.0/10

**Financial News**
1. [Fed Officials Push for Rate Hikes as Warsh Avoids Forward Guidance](#item-finance-news-1) ⭐️ 7.0/10
2. [U.S. companies shift from buybacks to net share issuance](#item-finance-news-2) ⭐️ 7.0/10
3. [Beijing Opens Comment on Draft Lease Rules Barring Normal Wear Deposit Deductions](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Thinking Machines releases Inkling 2 Mini, an open-weight looped transformer](https://thinkingmachines.ai/news/inkling-2-mini/) ⭐️ 8.0/10

Thinking Machines has released Inkling 2 Mini, an open-weight model built on a looped transformer architecture and sized for local use, with GGUF builds circulating for llama.cpp and Ollama. Early testers report decoding around 27 tokens/s on a Ryzen 395 with llama.cpp&\#x27;s Vulkan backend and roughly 10 tokens/s on a 32GB M1 Pro at q4 quantization while other applications were running. Those throughput figures, along with favorable coding results, come from individual user tests rather than the release itself, so the model&\#x27;s benchmark standing remains unverified.

hackernews · jasondavies · Nov 20, 20:12 · [Discussion](https://news.ycombinator.com/item?id=50581260)

**「Background」** A looped transformer reuses its middle layers repeatedly for each token, spending more compute per token rather than adding parameters; Thinking Machines describes this as how Inkling 2 Mini reasons more per token and reaches answers in fewer tokens. The model belongs to Thinking Machines Lab&\#x27;s Inkling family of efficient multimodal models, which the company also offers for fine-tuning and inference on its Tinker platform.

**「Impact」** Local users can run Inkling 2 Mini through llama.cpp and MLX, and an Unsloth GGUF is available for Ollama/llama.cpp, so consumer-hardware testing is already possible. However, one commenter testing on a Ryzen 395 with Vulkan had to apply four unmerged llama.cpp PRs plus a small source patch for roughly a 30% speed boost, and measured about 27 tokens/s decode; another reported about 10 tokens/s at q4 on a 32GB M1 Pro, so throughput and patch requirements will vary by setup.

**「Community discussion」** Reaction ranges from enthusiasm — one commenter called the results &quot;bonkers good if these benchmarks hold up&quot; — to mixed hands-on reports, including clean output on a CSV-sorting coding task but a failure on a harder coin-identification test after roughly 12,000 tokens of inconclusive output. A local-inference tester noted that several llama.cpp pull requests affecting the model are still unmerged and posted a small patch for about a 30% speed boost, while another commenter argued that a fully open-weight looped model is unusual enough to invite questions about safety and interpretability.

<details><summary>References</summary>
<ul>
<li><a href="https://thinkingmachines.ai/news/inkling-2-mini/">Introducing Inkling 2 Mini - Thinking Machines Lab</a></li>
<li><a href="https://thinkingmachines.ai/inkling/">Inkling - Thinking Machines Lab</a></li>
<li><a href="https://unsloth.ai/docs/models/inkling-2-mini">Inkling 2 Mini - Run Locally Guide | Unsloth Documentation</a></li>
<li><a href="https://huggingface.co/blog/inkling2mini">Welcome Inkling 2 Mini, Cutting-edge Performance for your ...</a></li>

</ul>
</details>

**Tags**: `#open-weight models`, `#looped transformers`, `#local inference`, `#llama.cpp`, `#AI model release`

---

<a id="item-tech-news-2"></a>
### [GitHub repo claims finite-time blow-up for unforced Navier–Stokes equations](https://github.com/tristanbuckmaster/navier-stokes/) ⭐️ 8.0/10

A GitHub repository \(tristanbuckmaster/navier-stokes\) linked on Hacker News purports to establish finite-time blow-up for the Navier–Stokes equations, a result that would settle the existence-and-smoothness Millennium Prize problem in the negative if it holds. The supplied item contains only the repository link — no paper, proof text, preprint venue, or peer-review status — so neither the argument nor its precise scope could be verified from the available material. Commenters describe the work as addressing the unforced equations, distinguishing it from a forced blow-up construction they attribute to an earlier OpenAI release.

hackernews · trotro · Nov 20, 15:34 · [Discussion](https://news.ycombinator.com/item?id=50576232)

**「Context: the Millennium problem and forced vs. unforced blow-up」** The Navier–Stokes existence and smoothness problem asks whether smooth three-dimensional initial data always produces a smooth solution for all time, and it is one of the Clay Mathematics Institute&\#x27;s Millennium Prize problems. Earlier finite-time blow-up constructions were &quot;forced&quot;: they built the singularity around a deliberately chosen external force term rather than the unforced equations. According to Wikipedia&\#x27;s account of the priority dispute, both the forced and unforced results still leave gaps relative to the original problem, which excludes Euler-equation constructions and requires any external force to be smooth; the unforced claim itself is a 79-page paper posted by Tristan Buckmaster and Levent Alpöge and remains unverified.

**「What the claim must clear」** Because the Clay Mathematics Institute defined its $1 million Millennium Prize around four specific formulations — two without external force and two with a smooth external force — any assessment of this repository turns on which instance its blow-up construction actually covers; the unforced case is one of the four, but a prize requires community acceptance of a published solution, not a repository posting. The claim also arrives alongside a disputed priority situation: OpenAI&\#x27;s September 8, 2026 announcement presented an internally produced proof with a Lean formalization, so readers comparing the two should treat both as claims awaiting independent verification rather than as settled results.

**「Community discussion」** Commenters concentrated on the distinction between the unforced problem and a forced construction they credit to an earlier OpenAI release, with tancop calling the unforced case &quot;more realistic.&quot; Others asked whether a numerical simulation could actually render the blow-up in real time, and Ericson2314 proposed a physical demonstration as an exhibit, while remarks about other same-day results and a rumored Anthropic Millennium problem remained unverified speculation.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_priority_controversy">Navier–Stokes priority controversy - Wikipedia</a></li>
<li><a href="https://magica.com/news/alpoge-buckmaster-navier-stokes-unforced-blowup-claim">Alpöge and Buckmaster’s unverified Navier–Stokes claim | Magica</a></li>
<li><a href="https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_existence_and_smoothness">Navier–Stokes existence and smoothness - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_priority_controversy">Navier–Stokes priority controversy - Wikipedia</a></li>
<li><a href="https://openai.com/index/navier-stokes-solution/">On the Navier–Stokes Millennium Prize Problem | OpenAI</a></li>

</ul>
</details>

**Tags**: `#Navier–Stokes equations`, `#mathematics`, `#fluid dynamics`, `#research result`, `#Hacker News`

---

<a id="item-tech-news-3"></a>
### [KVM CVE-2026-99312 exposes AMD host memory via nested virtualization](https://thehackernews.com/2026/11/new-linux-kvm-flaw-cve-2026-99312-lets.html) ⭐️ 8.0/10

Linux KVM has a vulnerability, CVE-2026-99312, that lets a guest read host memory on AMD systems when nested virtualization is enabled; researchers demonstrated reading about 127 GB of host memory from a virtual machine on DigitalOcean. An upstream fix shipped on November 18 in stable kernel 7.3.5 and related stable releases, but Debian and Ubuntu distribution kernels were still unpatched at the time of the report. Operators who cannot yet apply a fixed kernel should disable nested virtualization as a mitigation.

telegram · zaihuapd · Nov 20, 14:23

**「Background」** KVM is the hypervisor built into the Linux kernel, and nested virtualization—the configuration this vulnerability requires—lets a guest run its own hypervisor. Terra Security&\#x27;s analysis describes the defect as a stale pointer that had been present in the kernel for just under four years and was introduced by an earlier security fix.

**「Impact」** For AMD KVM hosts that allow nested virtualization, a tenant-controlled guest could expose host memory until the distribution kernel is updated; operators should verify that their kernel includes the fix or turn off nested virtualization, which may break workloads that require guests to run their own hypervisors.

<details><summary>References</summary>
<ul>
<li><a href="https://www.terra.security/blog/kvm-guest-to-host-escape">KVM Guest-to- Host Escape | Terra Security Research</a></li>
<li><a href="https://www.digitalocean.com/blog/cve-2026-99312-kvm-patch">Virtualization , Responsible Disclosure, and CVE - 2026 - 99312</a></li>

</ul>
</details>

**Tags**: `#KVM`, `#Linux kernel`, `#CVE`, `#virtualization security`, `#AMD`

---

<a id="item-tech-news-4"></a>
### [Tao post links unforced Euler/Navier-Stokes singularities to generalized Riemann Hypothesis](https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/) ⭐️ 7.0/10

Terence Tao has published a post titled “Unforced Euler Singularity, Unforced Navier-Stokes Singularity, and the Generalized Riemann Hypothesis” dated 20 November 2026. The supplied item contains no article body, so the post’s specific claims, whether it presents a proof, conjecture, or survey, and any technical conditions cannot be verified here. The surrounding Hacker News discussion focuses on Lean formal verification and AI-assisted theorem proving rather than on an independently confirmed mathematical result.

hackernews · archon1410 · Nov 20, 17:21 · [Discussion](https://news.ycombinator.com/item?id=50578358)

**「Earlier context」** Tao’s October 4, 2026 post examined classical solutions and singularity formation in incompressible fluids, establishing the Euler/Navier–Stokes blow-up setting that the November 20 post revisits in an “unforced” form. In this context, a singularity means a finite-time breakdown of a smooth solution; the newer post adds a connection to the generalized Riemann Hypothesis.

**「Community discussion」** Commenters pressed on what Lean acceptance actually establishes: one said two independent kernels accepting a result makes kernel-bug exploitation unlikely, while another asked how a large Lean development can be checked for proving the intended theorem rather than a trivial one. Others described the moment as exciting but career-uncertain and asked how new mathematical abstractions arise.

<details><summary>References</summary>
<ul>
<li><a href="https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/">Unforced Euler singularity, unforced Navier-Stokes ...</a></li>
<li><a href="https://terrytao.wordpress.com/2026/10/04/on-classical-solutions-and-singularity-formation-in-incompressible-fluids/">On classical solutions and singularity formation in ...</a></li>

</ul>
</details>

**Tags**: `#mathematics`, `#Lean theorem prover`, `#formal verification`, `#AI-assisted theorem proving`, `#Navier-Stokes`

---

<a id="item-tech-news-5"></a>
### [Aaronson post examines claimed LLM-assisted Riemann Hypothesis proof in Lean](https://scottaaronson.blog/?p=10344) ⭐️ 7.0/10

Scott Aaronson&\#x27;s blog post examines an apparent Riemann Hypothesis proof produced with LLM-style stochastic systems and Lean, and the Hacker News discussion treats it as a question about AI theorem proving rather than a confirmed result. The supplied item provides no proof details, Lean version, verification record, or independent confirmation, so the claim remains unverified. For mathematicians and AI theorem-proving researchers, the central issue is whether such systems can produce a checkable formal proof rather than only a search-driven candidate.

hackernews · stratos123 · Nov 20, 20:03 · [Discussion](https://news.ycombinator.com/item?id=50581084)

**「Background」** The phrase “stochastic parrots” comes from a 2021 critique of large language models, and Aaronson’s post notes that social-media users were ironically asking whether systems so labeled had just “proved the Riemann Hypothesis.” The relevant technical backdrop is formal theorem proving: a result counts only if it can be expressed as a machine-checkable derivation in a proof assistant such as Lean, not merely as a persuasive natural-language argument.

**「Impact」** Researchers should not treat the claim as a mathematical result until a complete Lean proof artifact and independent verification are available.

**「Community discussion」** Commenters debated whether combining Lean with a stochastic predictor amounts to a brute-force theorem solver, with one comparing the approach in spirit to AlphaGo. Another raised the difficulty of comprehending a large Lean development in its entirety.

<details><summary>References</summary>
<ul>
<li><a href="https://scottaaronson.blog/?p=10344">Shtetl-Optimized » Blog Archive » The stochastic parrots have ...</a></li>

</ul>
</details>

**Tags**: `#AI theorem proving`, `#LLMs`, `#Lean`, `#formal verification`, `#scientific discovery`

---

<a id="item-tech-news-6"></a>
### [Ravi Vakil announces early draft of proposed Riemann Hypothesis proof](https://simonwillison.net/2026/Nov/20/ravi-vakil/) ⭐️ 7.0/10

Ravi Vakil announced that Alessandro Masullo has a proposed proof of the Generalized Riemann Hypothesis and that the current draft is being released early. Vakil said Brian Conrad has examined the work closely for months, provided extensive feedback that is being incorporated, and that it is so far looking good. The note says the work is entirely human, with no AI, and that the original plan was to spend a year at Stanford polishing the writing and gathering more review before announcing; the announcement itself provides no technical detail or the paper.

rss · Simon Willison · Nov 20, 19:21

**「Background」** The Generalized Riemann Hypothesis is a stronger, harder extension of the 167-year-old Riemann Hypothesis. It became the subject of dueling same-day claims—one human, one AI-associated—and reporting cited in the search results said neither proof had been accepted.

**「Impact」** Mathematicians now have an early draft to scrutinize while feedback is still being incorporated, but the announcement does not supply the proof or technical details, so the conjecture should not be treated as proved on the basis of this note alone.

<details><summary>References</summary>
<ul>
<li><a href="https://www.scientificamerican.com/article/dueling-claims-of-riemann-hypothesis-proofs-emerge/">Dueling claims of Riemann hypothesis proofs ... | Scientific American</a></li>
<li><a href="https://www.youtube.com/watch?v=ptivrqGvoV8">Just in: Claimed Second Riemann Hypothesis Proof , 940... - YouTube</a></li>
<li><a href="https://techcrunch.com/2026/11/20/ai-claimed-a-solution-to-the-167-year-old-riemann-hypothesis-and-a-human-did-too/">AI claimed a solution to the 167-year-old Riemann Hypothesis — and...</a></li>

</ul>
</details>

**Tags**: `#mathematics`, `#Generalized Riemann Hypothesis`, `#research announcement`, `#proof verification`

---

<a id="item-tech-news-7"></a>
### [Levent Alpöge Claims Claude-Assisted Riemann Hypothesis Proof](https://simonwillison.net/2026/Nov/20/levent-alpoge/) ⭐️ 7.0/10

Levent Alpöge claims in a PDF note that he and Claude discovered a proof of the Riemann Hypothesis, and that the method extends to the Generalized Riemann Hypothesis, with the Extended Riemann Hypothesis expected with more time. He also says they formalized the arguments without assumptions. The supplied item provides no proof, technical detail, or independent verification, so the claim remains unconfirmed.

rss · Simon Willison · Nov 20, 16:30

**「Background」** The Riemann Hypothesis, posed in 1859, is one of mathematics&\#x27; most famous unsolved problems. Alpöge&\#x27;s argument was posted as a Lean proof, which lets software mechanically check each step, but as Scientific American notes, issues can arise in how a result is encoded in Lean, so experts still need to confirm that the formalization faithfully states the hypothesis.

**「Verification burden」** Mathematicians now face a concrete verification task: Alpöge’s claim rests on a 14-part computer-file formalization linked from his website, so reviewers would need to inspect that full development and check it independently before the Riemann Hypothesis can be treated as resolved.

<details><summary>References</summary>
<ul>
<li><a href="https://www.scientificamerican.com/article/anthropic-mathematician-claims-to-prove-riemann-hypothesis-most-famous-problem-in-all-of-math/">Anthropic mathematician claims to prove Riemann hypothesis , most...</a></li>
<li><a href="https://www.clarin.com/us-news/who-is-levent-alpoge-the-anthropic-mathematician-who-claims-solved-the-riemann-hypothesis-with-claude_0_2WdGvYKBVM.html">Who is Levent Alpöge ? The Anthropic mathematician who claims he...</a></li>
<li><a href="https://www.nacionale.com/en/articles/has-riemann-hypothesis-been-proved-levent-alpoge-claude-anthropic-claim-lean">Riemann hypothesis proof claimed with Claude , unverified</a></li>
<li><a href="https://kingy.ai/blog/levent-alpoge-claude-riemann-hypothesis-proof/">Levent Alpöge claims a Riemann hypothesis proof with Claude</a></li>

</ul>
</details>

**Tags**: `#AI-assisted mathematics`, `#Riemann Hypothesis`, `#Claude`, `#AI for science`, `#unverified claim`

---

<a id="item-tech-news-8"></a>
### [Apple reportedly developing proactive AI agent for late 2027](https://www.bloomberg.com/news/articles/2026-11-19/apple-is-working-on-ai-agent-for-device-control-apps-browsing-and-coding) ⭐️ 7.0/10

Apple is reportedly developing a proactive AI agent that can write code, browse the web, and control apps, with a launch targeted as early as late 2027. Bloomberg based the report on new job listings this week for a senior engineering manager to lead the effort, and the project is still described as early-stage. Separately, macOS 27.3 adds a warning page and increases the steps a third-party agent must complete to gain Mac control permissions from four to 14, according to the report.

telegram · zaihuapd · Nov 20, 08:59

**「Background」** Apple&\#x27;s reported project would enter a field where the source says Meta Muse and OpenAI already offer comparable agents. It also comes as macOS 27.3 adds a warning screen and raises the number of steps a third-party agent must complete to obtain Mac control from four to 14, underscoring that OS-level app control is both the agent&\#x27;s core capability and a permission Apple is tightening.

**「Impact」** Developers of third-party AI agents for macOS will have to account for the longer 14-step permission flow and warning page in macOS 27.3, which adds friction for users granting app-control access.

<details><summary>References</summary>
<ul>
<li><a href="https://www.straitstimes.com/business/apple-is-working-on-ai-agent-for-device-control-apps-browsing-and-coding">Apple working on AI agent for device control, apps, browsing ...</a></li>
<li><a href="https://www.moneycontrol.com/news/business/apple-is-building-its-own-ai-agent-and-making-it-harder-for-rivals-to-control-macs-14085248.html">Apple is building its own AI agent and making it harder for ...</a></li>

</ul>
</details>

**Tags**: `#Apple`, `#AI agents`, `#macOS`, `#platform security`, `#Bloomberg report`

---

<a id="item-tech-news-9"></a>
### [TSMC Reportedly Pauses 16nm-and-Below Orders From Chinese Firms](https://appleinsider.com/articles/26/11/20/apple-supplier-tsmc-cuts-off-china-chip-orders-amid-tighter-export-controls) ⭐️ 7.0/10

TSMC has reportedly notified customers that it is pausing 16nm-and-below chip orders from Chinese companies, which would require a prior U.S. export license or exemption under tightened U.S. semiconductor export rules. The report says Chinese firms would be left with 28nm and 40nm processes and would not be able to use the high-bandwidth memory needed for AI data centers. It adds that the U.S. approved list includes Apple, AMD and Nvidia but no Chinese companies, and that TSMC said it will comply. The account comes from a brief Telegram aggregation citing a secondary report, with no primary-source confirmation of the customer notice.

telegram · zaihuapd · Nov 21, 02:01

**「Background」** The report says the tightened rules shift responsibility: TSMC previously could assess whether a customer&\#x27;s design met exemption conditions, but customers must now apply in advance. That change in how exemptions are handled is the specific policy shift behind the reported order pause.

**「Impact」** For Chinese companies, the report describes a split in access: 28nm and 40nm processes remain available, while 16nm-and-below work requires a U.S. license or exemption. Companies unable to obtain one would have to keep products on older nodes or lose access to TSMC&\#x27;s advanced capacity.

**Tags**: `#semiconductors`, `#export-controls`, `#TSMC`, `#China`, `#AI-hardware`

---

<a id="item-tech-news-10"></a>
### [Microsoft previews RDMA over USB4 for pooled local AI inference on Windows](https://videocardz.com/newz/microsoft-brings-rdma-over-usb4-to-windows-allowing-multiple-pcs-to-run-one-local-ai-model) ⭐️ 7.0/10

Microsoft released a Windows developer preview of RDMA over USB4 that lets multiple PCs share memory and GPU resources to run one local AI model without a dedicated network card or switch. In a Microsoft demo, three AMD Ryzen AI Max+ 395 machines ran Qwen3-235B-A22B at 4-bit quantization at about 18.5 tokens per second. The preview is set to roll out through Windows Insider, and Microsoft has not detailed broader hardware support or general availability.

telegram · zaihuapd · Nov 21, 06:13

**「Background」** RDMA lets one computer directly access another computer&\#x27;s memory with minimal CPU or operating-system involvement; it has generally required data-center fabrics such as InfiniBand or RoCE. USB4 provides a high-bandwidth, peer-to-peer-capable link, which is the prerequisite for applying RDMA to ordinary Windows PCs without a dedicated NIC or switch.

**「Impact」** Developers evaluating local large-model inference can test pooling three PCs over ordinary USB4 connections instead of deploying RDMA-capable networking hardware, but the Insider preview status means it is not yet a production deployment option.

<details><summary>References</summary>
<ul>
<li><a href="https://club.dns-shop.ru/digest/189601-windows-11-nauchili-obedinyat-pamyat-i-gpu-pk-cherez-usb4-dlya-lok/">Windows 11 научили объединять память и GPU ПК через...</a></li>

</ul>
</details>

**Tags**: `#RDMA`, `#USB4`, `#local AI inference`, `#Windows`, `#distributed computing`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Why Caching LLM Output Repetition Saves Little](https://seangoedecke.com/why-output-caching-doesnt-work/) ⭐️ 6.0/10

rss · Sean Goedecke · Nov 21, 00:00

**「Background」** LLM inference economics already relies on caching inputs in the KV cache so conversation history is not recomputed, and output tokens are much more expensive to generate than input tokens are to ingest. Agents often repeat code snippets or evidence documents, making output caching look like a natural next saving.

**「Solution」** Sean Goedecke argues that output caching targets only visible repetition: in his rough breakdown of his own agent histories, about 6% of output tokens are visible, while 50% are reasoning tokens and 44% are tool calls. By Amdahl&\#x27;s law, even an implausibly optimistic two-thirds saving on visible output would cut only about 4% of total output tokens. He suggests models could be prompted or fine-tuned to emit references such as file line ranges that the harness expands, but this still optimizes only the visible sliver. The larger 94% is invisible, and he argues it is mainly an intelligence problem: smarter models need fewer reasoning and tool-call tokens, so a model that costs 5x more per token but uses 6x fewer tokens can be cheaper overall. He flags uncertainty about whether frontier models repeat themselves internally and about repetition inside tool calls.

**「Takeaway」** The author concludes that output caching is bounded by Amdahl&\#x27;s law and cannot deliver large savings; the useful lever is reducing invisible reasoning and tool-use tokens, largely through more capable models.

**Tags**: `#LLM inference economics`, `#output caching`, `#Amdahl&\#x27;s law`, `#token costs`, `#AI agents`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Fed Officials Push for Rate Hikes as Warsh Avoids Forward Guidance](https://www.cnbc.com/2026/11/20/warsh-fed-forward-guidance-rate-hikes.html) ⭐️ 7.0/10

Federal Reserve officials are publicly advocating near-term rate hikes while Chair Kevin Warsh continues to withhold forward guidance, and traders are pricing a 100% chance of at least a quarter-point increase at the December meeting, according to CME Group&\#x27;s FedWatch. A Bank of America analysis cited by CNBC found more Fedspeak in the past two weeks than in any comparable period since the start of 2025, with inflation running above 3% against the Fed&\#x27;s 2% target.

rss · CNBC Finance · Nov 20, 21:10

**「Background」** Warsh, who became Fed chair in 2026, scrapped forward guidance from the central bank’s policy statement, reducing it to 132 words. The Fed had used such guidance in its post-meeting statements since the early 2000s to signal the likely direction of interest rates.

**「Impact」** With traders pricing a 100% chance of at least a quarter-point increase at the December meeting, according to CME Group&\#x27;s FedWatch, consumers and businesses with variable-rate debt — from credit cards to small-business loans — would see interest costs rise if the committee follows through.

<details><summary>References</summary>
<ul>
<li><a href="https://www.financialexpress.com/market/global-market-pulse/why-fed-chair-warsh-scrapped-forward-guidance-in-a-132-word-pivot/4272071/">Why Fed Chair Warsh scrapped forward guidance in a 132-word ...</a></li>
<li><a href="https://www.federalreserve.gov/faqs/what-is-forward-guidance-how-is-it-used-in-the-federal-reserve-monetary-policy.htm">What is forward guidance, and how is it used in the Federal ...</a></li>

</ul>
</details>

**Tags**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#FOMC communication`, `#Kevin Warsh`

---

<a id="item-finance-news-2"></a>
### [U.S. companies shift from buybacks to net share issuance](https://www.cnbc.com/2026/11/20/equity-issuance-bull-market-problem.html) ⭐️ 7.0/10

U.S. companies have switched from buying back shares to net equity issuance, with net new stock equal to 3.1% of total market capitalization as of late last week, according to Acadian Asset Management.

rss · CNBC Finance · Nov 20, 14:15

**「Background」** Investors had cited buybacks—which reduce shares available to trade and lift earnings per share by shrinking the share count—as one reason the four-year-old bull market could keep rising; that flow has now reversed.

**Tags**: `#equity issuance`, `#share buybacks`, `#IPO market`, `#AI infrastructure financing`, `#US stock market`

---

<a id="item-finance-news-3"></a>
### [Beijing Opens Comment on Draft Lease Rules Barring Normal Wear Deposit Deductions](https://mp.weixin.qq.com/s/PmGxh5knIyxiBRhpRoJnoQ) ⭐️ 7.0/10

Beijing’s housing and market regulators opened public comment on Nov. 20 on a revised model housing lease contract that would bar landlords from deducting deposits for normal wear and tear caused by ordinary use. The draft, which also requires subletting rental firms to pay rent and deposits into supervised accounts, is not yet final.

telegram · zaihuapd · Nov 20, 13:46

**「Background」** A &quot;model contract&quot; \(示范文本\) is a template drafted by Beijing&\#x27;s housing commission and market regulator that landlords and tenants can choose to adopt; this version is a draft open for public comment from Nov 20 and is not yet binding. Chinese localities have issued such rental templates before — Henan published a trial version in 2017 — typically to set default terms where individual contracts leave gaps.

<details><summary>References</summary>
<ul>
<li><a href="https://www.chinanews.com.cn/house/2017/08-02/8293898.shtml">河南 住 房 租 赁 合 同 范 本 出炉 明确 租 金 不得随 意 上涨-中新网</a></li>

</ul>
</details>

**Tags**: `#housing rental`, `#Beijing policy`, `#tenant protections`, `#deposit regulation`, `#public consultation`

---