---
layout: default
title: "Horizon Summary: 2026-11-28 (EN)"
date: 2026-11-28
lang: en
---

> From 30 items, 10 important content pieces were selected

---

**Technology News**
1. [Unkernel compiles a real Linux kernel to WebAssembly](#item-tech-news-1) ⭐️ 8.0/10
2. [OpenSec discloses 9.8-severity pre-auth NFS root flaw in Linux kernel](#item-tech-news-2) ⭐️ 8.0/10
3. [Michael Nielsen&\#x27;s Neural Networks and Deep Learning Book Taken Down](#item-tech-news-3) ⭐️ 7.0/10
4. [Convex CEO responds to AI skill prompt-upload complaint](#item-tech-news-4) ⭐️ 7.0/10
5. [Essay Argues Computer-Checked Proofs Can Be False](#item-tech-news-5) ⭐️ 7.0/10
6. [WebRTC-linked card skimming scripts reported on shopping sites](#item-tech-news-6) ⭐️ 7.0/10
7. [States Sue SpaceX to Halt Grok’s Child Sexual Abuse and Intimate Images](#item-tech-news-7) ⭐️ 7.0/10
8. [SemiAnalysis: Trainium3 Trades Blows With GB300 on Inference Cost](#item-tech-news-8) ⭐️ 7.0/10

**Financial News**
1. [PBOC lowers individual large-denomination CD threshold to 100,000 yuan](#item-finance-news-1) ⭐️ 7.0/10
2. [China&\#x27;s market regulator summons 15 electric-bicycle makers over quality and certification failures](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Unkernel compiles a real Linux kernel to WebAssembly](https://unkernel.dev/) ⭐️ 8.0/10

Unkernel is a project that compiles a real Linux kernel to WebAssembly, targeting Linux environments that run inside a browser tab. The Hacker News submission points to the project site at unkernel.dev; the supplied material gives no version number, release date, license, or list of supported browsers. Commenters who tried it describe startup as fast and call the Wayland compositor performance surprisingly good, though no benchmarks or measurements are provided.

hackernews · nreece · Nov 28, 03:19 · [Discussion](https://news.ycombinator.com/item?id=50674218)

**「Background」** Running Linux in a browser usually means placing an emulator or virtual machine beneath an unchanged kernel. Unkernel instead compiles the kernel itself directly to WebAssembly; its user programs run on kwemu, an aarch64 CPU emulator written in Zig and linked into the kernel, which walks the kernel&\#x27;s own page tables so real Linux memory-management code still governs memory.

**「Impact」** The concrete use raised in comments is education: each student could get a Linux environment directly in the browser, without per-session server provisioning, because execution happens client-side. That remains an untested claim here—the supplied material contains no data on memory use, boot time at classroom scale, or whether the kernel features real coursework depends on behave correctly under WebAssembly.

**「Community Discussion」** Commenters were largely enthusiastic: gregbell reported fast startup and called the Wayland compositor performance &quot;crazy,&quot; saying the hard parts were handled well enough to build on, while mareimorsy argued education platforms could give every student a browser-based Linux environment at near-zero server cost. lucamark took a warier view, asking what else will end up running in browser tabs in five years.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/pithings/unkernel">pithings/ unkernel : A real Linux kernel , compiled to WebAssembly .</a></li>

</ul>
</details>

**Tags**: `#WebAssembly`, `#Linux kernel`, `#browser computing`, `#virtualization`, `#Wayland`

---

<a id="item-tech-news-2"></a>
### [OpenSec discloses 9.8-severity pre-auth NFS root flaw in Linux kernel](https://opensec.in/blog/nfs2root-cve-2026-99362) ⭐️ 8.0/10

OpenSec disclosed CVE-2026-99362, a CVSS 9.8 pre-authentication heap overflow in the Linux kernel&\#x27;s NFS server \(nfsd\) that it says can give an unauthenticated attacker a root shell through a single connection to tcp/2049. The flaw is reported to have existed since Linux 3.16 in 2014 and to affect hosts running NFSv4.1 or 4.2, including file servers, NAS devices, and clustered storage nodes. Fixes are listed in kernel 6.12.117, 6.18.61, 7.3.2, and 7.4-rc1; administrators must upgrade and reboot, while those unable to do so immediately can restrict tcp/2049 at the firewall. The CVE was made public on November 20, 2026, but the supplied material provides no independent confirmation of the exploit or the affected-version analysis.

telegram · zaihuapd · Nov 27, 12:57

**「Background」** Linux&\#x27;s NFS server, nfsd, runs in the kernel and handles remote file-sharing requests on TCP port 2049. The vulnerable nfsd code path dates to Linux 3.16 \(2014\), so the flaw is a long-standing issue in deployed systems rather than a regression in a recent kernel release.

**「Impact」** Operators of NFSv4.1 or 4.2 file and storage services must either install one of the listed fixed kernels and reboot or block tcp/2049 as a temporary mitigation, which also restricts legitimate NFS traffic.

<details><summary>References</summary>
<ul>
<li><a href="https://opensec.in/blog/nfs2root-cve-2026-99362">NFS 2ROOT ( CVE - 2026 - 99362 ): pre-auth root in Linux nfsd | OpenSec</a></li>
<li><a href="https://www.bleepingcomputer.com/news/security/new-nfs2root-linux-flaw-can-let-attackers-gain-root-privileges/">New NFS 2ROOT Linux flaw can let attackers gain root privileges</a></li>

</ul>
</details>

**Tags**: `#Linux kernel`, `#NFS`, `#security vulnerability`, `#CVE`, `#remote exploit`

---

<a id="item-tech-news-3"></a>
### [Michael Nielsen&\#x27;s Neural Networks and Deep Learning Book Taken Down](https://neuralnetworksanddeeplearning.com/) ⭐️ 7.0/10

Michael Nielsen&\#x27;s free online book Neural Networks and Deep Learning is no longer available at neuralnetworksanddeeplearning.com, a removal flagged in a Hacker News submission on November 27, 2026. The supplied material gives no reason for the takedown, and neither Nielsen nor the submission is quoted explaining it. Commenters treated the removal as a protest and pointed to surviving copies: an Internet Archive snapshot timestamped August 8, 2026, and a single-file PDF one reader compiled from that archive under the book&\#x27;s CC BY-NC license.

hackernews · brandonb · Nov 27, 19:31 · [Discussion](https://news.ycombinator.com/item?id=50670757)

**「Background」** Michael Nielsen&\#x27;s Neural Networks and Deep Learning was a free online book, with a December 2019 date listed on its site, that taught core concepts of neural networks and deep learning. Its accompanying code samples were hosted in a public GitHub repository under Nielsen&\#x27;s account.

**「Impact」** Readers, students, and instructors who relied on the site&\#x27;s canonical, interactive version now depend on mirrors; the reader who built the PDF noted that its interactive elements work worse than on the original website, though the text remains usable as a reference.

**「Community Discussion」** Commenters disagreed about what the removal achieves: one called it a misstep, arguing that helping people understand what large companies do behind closed doors prepares them for the consequences, while another said that with the book available in many places the act works more as a protest whose message matters than as a practical restriction. A third extended the point to the capital behind frontier labs, arguing that ordinary investors holding AI-linked funds are part of the incentive structure.

<details><summary>References</summary>
<ul>
<li><a href="http://neuralnetworksanddeeplearning.com/">Neural networks and deep learning</a></li>
<li><a href="https://github.com/mnielsen/neural-networks-and-deep-learning">GitHub - mnielsen/ neural - networks - and - deep - learning : Code...</a></li>

</ul>
</details>

**Tags**: `#AI education`, `#open access`, `#neural networks`, `#community debate`, `#AI ethics`

---

<a id="item-tech-news-4"></a>
### [Convex CEO responds to AI skill prompt-upload complaint](https://github.com/convex/convex-backend-skill/issues/64) ⭐️ 7.0/10

A GitHub issue on convex/convex-backend-skill \(\#64\) alleges that a Convex AI skill sends the user&\#x27;s app idea or prompt to a remote server without telling them. In the Hacker News thread, Convex CEO Jamie said the upload powers Convex&\#x27;s &quot;quickstart&quot; feature, the successor to the recently shut-down Convex Chef, and described Convex as a platform that stores code and data and offers an AI gateway. The reply confirms the upload&\#x27;s role in quickstart but does not resolve whether users were adequately told about it.

hackernews · MickyTheMouse · Nov 27, 18:02 · [Discussion](https://news.ycombinator.com/item?id=50669765)

**「Background」** Convex previously ran Convex Chef, an end-to-end vibe-coding product it has since shut down. Convex CEO Jamie said in the thread that the prompt upload at issue powers “quickstart,” Chef&\#x27;s spiritual successor; that skill&\#x27;s instructions call for opening a browser after scaffolding and building the user&\#x27;s idea live in a visible “Chef panel,” while the GitHub issue, opened Oct. 26, 2026, says the flow sends the idea to a \`convex.site\` host and runs remote scripts “written to avoid safety checks.”

**「Impact」** The CEO&\#x27;s explanation ties the upload to quickstart, so developers who use that feature should treat their app description as data sent off-machine; the supplied reply does not state what happens to it afterward.

**「Community Discussion」** One commenter argued self-hosted open-weight models are the long-term answer, and another noted that prompt injection is more common than models making malicious tool calls on their own, without alleging malice in this case. A separate reply dismissed the concern as &quot;Ideas are cheap.&quot;

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/convex/convex-backend-skill/issues">Issues · convex/convex-backend-skill · GitHub</a></li>
<li><a href="https://github.com/convex/convex-backend-skill/blob/main/commands/quickstart.md">convex-backend-skill/commands/quickstart.md at main - GitHub</a></li>

</ul>
</details>

**Tags**: `#ai-privacy`, `#developer-tools`, `#telemetry`, `#open-source`, `#trust-and-safety`

---

<a id="item-tech-news-5"></a>
### [Essay Argues Computer-Checked Proofs Can Be False](https://cr.yp.to/proofs/falseccp.html) ⭐️ 7.0/10

An essay at cr.yp.to argues that a computer-checked proof can be false when the proof checker itself has a soundness bug, because verification only establishes that a proof conforms to the checker&\#x27;s implementation. It treats proof-checking software as high-assurance code whose own correctness matters, rather than as an absolute oracle for mathematical truth. The page is an argument about the limits of proof-checker trust, not a report of a newly discovered false proof.

hackernews · \_tk\_ · Nov 27, 15:26 · [Discussion](https://news.ycombinator.com/item?id=50667989)

**「Background」** Proof assistants such as Lean and Metamath rely on a trusted checker or kernel to validate each inference step, so the correctness of a claimed theorem depends on that checker having no soundness bugs. Reports of such bugs are the reason multiple independent verifiers are sometimes used for the same proof.

**「Impact」** Teams relying on machine-checked proofs should not treat a single passing checker as sufficient: Lean&\#x27;s release notes for 4.32.2 describe a kernel bug that could be combined with an unrelated bug in the independent nanoda checker, and an AI-assisted Collatz &quot;disproof&quot; reportedly passed two checkers by exploiting a different flaw in each. Cross-validation with independent kernels such as nanoda therefore raises the bar but is not a guarantee, so proofs that matter still warrant informal human review and prompt checker updates rather than acceptance based on checker count alone.

**「Community discussion」** Commenters argue the essay understates existing safeguards. twotwotwo says a false proof would need bugs in multiple checkers and would still have to survive informal review, citing a DeepMind researcher&\#x27;s proof that passed Lean and a then-week-old nanoda by exploiting a different bug in each; dwheeler notes that Metamath&\#x27;s main databases require five independently created verifiers in five programming languages, and gr\_norm says known soundness bugs in long-used checkers are few and would still need a second flaw in the verified program to cause harm.

<details><summary>References</summary>
<ul>
<li><a href="https://cr.yp.to/proofs/falseccp.html">False computer - checked proofs (djb)</a></li>
<li><a href="https://lean-lang.org/doc/reference/latest/releases/v4.32.2/">Lean 4.32.2 (2026-07-28)</a></li>
<li><a href="https://arena.lean-lang.org/checker/nanoda/">nanoda - Lean Kernel Arena</a></li>
<li><a href="https://aibacon.net/posts/lean-kernel-soundness-bug-ai-collatz-disproof-two-checkers.html">An AI &#x27;Disproof&#x27; of Collatz Slipped Past Two Proof Checkers</a></li>

</ul>
</details>

**Tags**: `#formal verification`, `#proof assistants`, `#soundness bugs`, `#Lean`, `#Metamath`

---

<a id="item-tech-news-6"></a>
### [WebRTC-linked card skimming scripts reported on shopping sites](https://www.infohawk.com/news/2026-11-27-black-friday-webrtc-skimmer) ⭐️ 7.0/10

Credit-card skimming scripts that use WebRTC to capture and exfiltrate payment data have been reported on popular shopping sites, according to a Hacker News discussion of the finding. The material supplied here contains no list of affected merchants, no script or vendor names, no sample code, and no measured count of sites, so the campaign&\#x27;s scale and WebRTC&\#x27;s exact role remain unverified. Commenters argued that the technique&\#x27;s significance lies less in WebRTC&\#x27;s capabilities than in defenders monitoring it less closely than conventional traffic, and that embedding third-party JavaScript is the underlying exposure.

hackernews · scanr · Nov 27, 15:40 · [Discussion](https://news.ycombinator.com/item?id=50668145)

**「Background」** Card-skimmer scripts have traditionally worked by injecting code into a checkout page that reads the payment form and posts it to an attacker-controlled server — traffic that a Content-Security-Policy \`connect-src\` rule or outbound network monitoring can catch. The variant reported here instead moves stolen data over a WebRTC data channel, which a re-check of the campaign notes falls outside what CSP inspects, making it harder to spot with the controls most shops already run.

**「Impact」** For e-commerce teams, the practical consequence is that any third-party JavaScript permitted on checkout or product pages — analytics, advertising, chat widgets — sits in the card-data path, and detection tuned only to ordinary HTTP exfiltration may miss a WebRTC channel, as commenters noted. Operators would need to inventory and restrict scripts on payment pages and extend monitoring to WebRTC traffic; the item provides no vendor or script name to check against.

**「Community discussion」** Commenter afavour argued that WebRTC is incidental — the same theft could be done with simple HTTP requests, and mobile devices are targeted because skimming there is harder to detect — while s\_u\_d\_o asked why ad networks and browsers do not sandbox ad JavaScript entirely, and jszymborski cited the episode as a reason not to feel bad about blocking ads. These are opinions from the thread, not verified findings about the reported campaign.

<details><summary>References</summary>
<ul>
<li><a href="https://dev.to/frankchu/webrtc-stole-cards-at-5-stores-i-re-checked-the-cleanup-59k9">WebRTC stole cards at 5 stores — I re-checked the cleanup</a></li>

</ul>
</details>

**Tags**: `#web security`, `#payment skimming`, `#WebRTC`, `#third-party scripts`, `#e-commerce`

---

<a id="item-tech-news-7"></a>
### [States Sue SpaceX to Halt Grok’s Child Sexual Abuse and Intimate Images](https://www.oag.state.va.us/media-center/news-releases/jay-jones/3162-attorneys-general-jones-and-rayfield-file-suit-against-spacex-parent-company-of-x-xai-and-grok-over-creation-and-promotion-of-child-exploitation-and-non-consensual-images-on-platform) ⭐️ 7.0/10

A group of state attorneys general has sued SpaceX, which the suit identifies as the parent company of X, xAI and Grok, seeking to stop the platform from generating child sexual abuse material and non-consensual intimate images. The action is a request for court relief over Grok’s outputs, not a report of a shipped technical fix or a final ruling; the supplied material does not specify the number of states, the court, or the exact legal claims.

hackernews · DeepLogin · Nov 27, 19:42 · [Discussion](https://news.ycombinator.com/item?id=50670855)

**「Why SpaceX is the defendant」** The suit names SpaceX because it is the parent company of X, xAI, and Grok, making the corporate structure rather than the Grok product alone the legal hook for the action. Virginia filed in collaboration with Oregon Attorney General Dan Rayfield, who brought a separate but similar action against the same companies.

**「Liability test for platform vs. user」** Because the complaint names SpaceX as X/xAI&\#x27;s corporate parent rather than the model developer alone, the case puts the platform-versus-user liability question directly before a court. xAI has already argued the opposite position in its own litigation against users, contending that only users should be liable for Grok-generated child sexual abuse material, so how this suit and that one resolve will set the default that other AI platforms and their users operate under.

**「Community Discussion」** Commenters focused on how Grok produced the material and who should be held responsible: one asked whether the model was unusually permissive or users had to trick it, while another asked about consequences for the people making the requests. A third commenter asserted that the Supreme Court has protected AI-generated child sexual abuse material made for personal use when no real children are depicted, and said the revenge-porn question was less clear; that legal claim was not verified in the supplied material.

<details><summary>References</summary>
<ul>
<li><a href="https://www.oag.state.va.us/media-center/news-releases/jay-jones/3162-attorneys-general-jones-and-rayfield-file-suit-against-spacex-parent-company-of-x-xai-and-grok-over-creation-and-promotion-of-child-exploitation-and-non-consensual-images-on-platform">Attorneys General Jones and Rayfield File Suit Against SpaceX ...</a></li>
<li><a href="https://arstechnica.com/tech-policy/2026/07/xai-cant-deny-grok-makes-csam-anymore-so-its-suing-users/">xAI can’t deny Grok makes CSAM anymore. - Ars Technica</a></li>

</ul>
</details>

**Tags**: `#AI safety`, `#generative AI`, `#legal/regulation`, `#content moderation`, `#xAI/Grok`

---

<a id="item-tech-news-8"></a>
### [SemiAnalysis: Trainium3 Trades Blows With GB300 on Inference Cost](https://newsletter.semianalysis.com/p/trainium3-inferencex) ⭐️ 7.0/10

SemiAnalysis published a microarchitecture deep dive arguing that AWS Trainium3, built from the ground up around tiles as a first-class primitive rather than Nvidia&\#x27;s threads-plus-bolted-on-accelerators approach, can reach peak HBM bandwidth utilization \(MBU\) at small message sizes via its Descriptor Generation Engines \(DGE\) — the counterpart to Nvidia&\#x27;s TMA and AMD&\#x27;s MI455X TDM — which the firm says is not possible on Nvidia GPUs. In its InferenceX benchmark, Trainium3 and Google TPUs are now listed as &quot;trading blows or even winning&quot; against Nvidia GB300 on total cost of ownership per generated token, and on the AgentX end-to-end coding-agent replay, Trainium3 with vLLM reportedly beats every other accelerator except Nvidia&\#x27;s Vera Rubin across the TCO-versus-p90-interactivity curve. The results come from SemiAnalysis&\#x27;s UBenchX suite, covering cycle-level SRAM scratchpad latency and bandwidth \(SBUF to PSUM\), rack-scale bandwidth and latency, attention exponential tests, and how attention head\_dim affects roofline percentage. AWS Annapurna Labs co-founder Nafea Bshara and Trainium chief architect Ron Diamant, among others, helped validate the experiments, so the figures reflect vendor-assisted rather than fully independent measurement.

rss · Semianalysis · Nov 27, 15:54

**「Background」** Nvidia&\#x27;s datacenter GPUs evolved by adding AI-specific hardware generation by generation — Volta introduced Tensor Cores in 2017, Hopper added TMA for tile data movement between HBM and SRAM, and Blackwell added Tensor Memory for accumulation — while graphics-only units were stripped out. Trainium instead treats tiles as the native unit of computation, an approach SemiAnalysis notes once made software support &quot;a humongous challenge&quot; but no longer does. Inference comparisons are plotted as Pareto frontiers because every configuration trades throughput against latency, here measured as p90 interactivity.

**「Impact」** For teams serving agentic or coding workloads, Trainium3 is now a measured option with a mainstream serving path \(PDS plus vLLM\) and a published cost-per-token position, but the caveats matter for procurement: it still trails Vera Rubin at the high-interactivity end of the frontier, and the numbers come from a benchmark whose methodology AWS engineers helped validate, so workload-specific testing remains the practical next step.

**Tags**: `#AWS Trainium`, `#AI accelerators`, `#chip microarchitecture`, `#inference`, `#Nvidia`

---

## Financial News

<a id="item-finance-news-1"></a>
### [PBOC lowers individual large-denomination CD threshold to 100,000 yuan](https://www.news.cn/fortune/20261127/70789d77822242cc82216f51a416f872/c.html) ⭐️ 7.0/10

The People&\#x27;s Bank of China published new large-denomination certificate of deposit rules on Nov. 27 that lower the individual minimum purchase to 100,000 yuan from 200,000 yuan and the institutional minimum to 5 million yuan from 10 million yuan, effective March 21, 2027.

telegram · zaihuapd · Nov 27, 11:36

**「Background」** The rules replace 2015 interim measures and a 2016 announcement; the same day, the PBOC issued separate deposit and loan interest-rate rules requiring banks to set rates independently and barring improper tactics such as high-interest deposit-taking, also effective March 21, 2027.

**「Impact」** The lower individual threshold widens access for retail savers able to commit at least 100,000 yuan, while the rate rules impose conduct requirements on how banks price deposits and loans.

**Tags**: `#PBOC regulation`, `#large-denomination CDs`, `#deposit rates`, `#banking regulation`, `#retail depositors`

---

<a id="item-finance-news-2"></a>
### [China&\#x27;s market regulator summons 15 electric-bicycle makers over quality and certification failures](https://www.news.cn/20261127/0c8c665ce70c417b9263b39fa8a519f0/c.html?hl=zh-CN) ⭐️ 7.0/10

China&\#x27;s market regulator on Nov. 27 summoned 15 electric-bicycle makers, including Yadea, Tailg and Aima, over quality-assurance and China Compulsory Certification failures found in unannounced inspections, ordering rectification and recalls of defective products. It told the companies to follow the &quot;one vehicle, one battery, one charger, one code&quot; rule and not to dodge after-sales responsibility or refuse returns by saying certificates would soon be restored.

telegram · zaihuapd · Nov 27, 12:06

**「Background」** CCC certification is China’s mandatory product certification and a precondition for an electric bicycle to be legally produced and sold, while the “one vehicle, one battery, one charger, one code” rule links each bike to a matching battery, charger, and code to curb tampering.

<details><summary>References</summary>
<ul>
<li><a href="https://food.cnr.cn/gstj/20261103/t20261103_527860850.shtml">堵住改装漏洞 电 动 自 行 车 新规给消费安全上把锁_央广网</a></li>
<li><a href="https://youjia-pc.bdstatic.com/article/9743054159117044880.html">youjia-pc.bdstatic.com/article/9743054159117044880.html</a></li>

</ul>
</details>

**Tags**: `#电动自行车`, `#市场监管`, `#产品质量`, `#召回`, `#CCC认证`

---