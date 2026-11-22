---
layout: default
title: "Horizon Summary: 2026-11-22 (EN)"
date: 2026-11-22
lang: en
---

> From 24 items, 7 important content pieces were selected

---

**Technology News**
1. [Reported Lean formalization of Riemann Hypothesis faces checker scrutiny](#item-tech-news-1) ⭐️ 9.0/10
2. [Zhejiang University reports first real-machine QRAM prototype](#item-tech-news-2) ⭐️ 8.0/10
3. [GnuPG advisory covers GPGME double-free before 2.3.0](#item-tech-news-3) ⭐️ 7.0/10
4. [Monitor&\#x27;s USB Hub Latency Cut Ethernet Download Speed by 75%](#item-tech-news-4) ⭐️ 7.0/10
5. [OpenRouter Warns MiniMax Prompts May Have Been Read by Third Parties](#item-tech-news-5) ⭐️ 7.0/10
6. [FT Report Alleges Prince Group Figure Smuggled Nvidia Chips to China](#item-tech-news-6) ⭐️ 7.0/10

**Technology Blog**
1. [Good Programming Is About Avoiding Blunders, Not Cleverness](#item-tech-blog-1) ⭐️ 6.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Reported Lean formalization of Riemann Hypothesis faces checker scrutiny](https://leanprover-community.github.io/blog/posts/riemann-hypothesis/) ⭐️ 9.0/10

According to a Lean community blog post, Levent Alpöge released a Lean formalization of the Riemann Hypothesis on November 20, 2026, with a repository of about 17 million lines. On November 21, the Lean FRO and Mathlib Initiative reportedly certified that the formal statement matches Mathlib&\#x27;s RiemannHypothesis, that the code compiles without errors, and that multiple independent proof checkers accept the proof. The supplied material does not include an independent peer review of the underlying mathematics, and commenters describe the work as heavily AI-assisted. The central dispute is whether the checkers are independent enough to rule out a shared bug or a mis-stated theorem.

hackernews · g-b-r · Nov 21, 14:36 · [Discussion](https://news.ycombinator.com/item?id=50589618)

**「Background」** Lean is an interactive theorem prover that checks proofs mechanically, and Mathlib is the community library of formalized mathematics on which such proofs depend. Mathlib already contains a formal statement called \`RiemannHypothesis\`, so a claimed proof must show that its theorem matches that statement and that the proof compiles without errors; compilation has generally been treated as strong confirmation, though questions can remain.

**「Impact」** For Lean and Mathlib users, the immediate practical concern is auditing the statement alignment and rechecking the roughly 17 million-line development with independent kernels; the community debate shows that acceptance by a single checker is not being treated as sufficient on its own.

**「Community discussion」** Commenters split on how much the multiple checkers prove: one argued that a bug-exploiting proof is now vanishingly unlikely because several independently implemented kernels, some with consistency proofs, would all have to fail, while another noted that a fake Collatz refutation previously passed an independent checker and that the published claim&\#x27;s four points do not depend on human involvement. Others credited Alpöge with getting the most out of Claude and suggested the formalization may cover a large swath of modern mathematics.

<details><summary>References</summary>
<ul>
<li><a href="https://leanprover-community.github.io/blog/posts/riemann-hypothesis/">Lean verification of the Riemann Hypothesis | Lean community blog</a></li>
<li><a href="https://www.scientificamerican.com/article/the-ai-riemann-hypothesis-proof-is-almost-certainly-true-independent-mathematicians-attest/">The AI Riemann hypothesis proof is true... | Scientific American</a></li>

</ul>
</details>

**Tags**: `#Lean`, `#formal verification`, `#Riemann Hypothesis`, `#AI-assisted mathematics`, `#theorem proving`

---

<a id="item-tech-news-2"></a>
### [Zhejiang University reports first real-machine QRAM prototype](https://finance.sina.com.cn/stock/2026-11-21/doc-iniznhsk3530826.shtml) ⭐️ 8.0/10

Researchers at Zhejiang University report that they demonstrated a quantum random-access memory \(QRAM\) prototype on a superconducting quantum chip, &quot;Tianmu-2,&quot; which the team made in-house. The work, published in Nature Physics, reportedly marks the first real-machine implementation of QRAM. The prototype retrieved 4-bit and 8-bit data with accuracies of 80.9% and 60.4%, respectively; its circuit depth was more than 30% lower than that of an unoptimized approach, and the team also reported the first validation of local noise resistance in this architecture. The team says its next step is to scale up the QRAM research.

telegram · zaihuapd · Nov 21, 08:31

**「Background」** QRAM is a proposed quantum memory that retrieves data from multiple addresses in superposition, a capability sought for quantum algorithms that need to access classical or quantum data. The bucket-brigade architecture was proposed to make such memory more hardware-efficient and noise-tolerant, but it had not previously been operated on real quantum hardware. The Zhejiang University experiment implemented the architecture on the “Tianmu 2” superconducting chip, with prototypes addressing 16 and 256 storage cells, and reported experimental evidence for its noise resilience.

**「Impact」** For quantum-hardware researchers, the result offers a superconducting-circuit design for testing whether QRAM can be scaled; however, 60.4% accuracy for 8-bit retrieval means the prototype is not yet suitable for algorithm-level or fault-tolerant use.

<details><summary>References</summary>
<ul>
<li><a href="https://news.mydrivers.com/1/1167/1167501.htm">news.mydrivers.com/1/1167/1167501.htm</a></li>

</ul>
</details>

**Tags**: `#quantum computing`, `#QRAM`, `#superconducting qubits`, `#hardware research`

---

<a id="item-tech-news-3"></a>
### [GnuPG advisory covers GPGME double-free before 2.3.0](https://lists.gnupg.org/pipermail/gnupg-announce/2026q4/000517.html) ⭐️ 7.0/10

The GnuPG project has published a security advisory for a double-free vulnerability in GPGME, with the affected range reported as versions before 2.3.0. The advisory is said to cover software that links GPGME as a shared library, DLL, or static library; a commenter lists Gpg4win, GnuPG Desktop, GnuPG VS-Desktop, most mail clients, many XMPP clients, Samba, and Flatpak as examples. A comment attributed to the project side says Johan Carlsson discovered the flaw and GitLab notified maintainers on 2026-11-12, with disclosure moved to 2026-11-20 from 2026-11-25 because GitLab had to update earlier amid the Ruby2Shell bug.

hackernews · gdgghhhhh · Nov 21, 08:32 · [Discussion](https://news.ycombinator.com/item?id=50587208)

**「Background」** GPGME is the library many applications use to invoke GnuPG&\#x27;s OpenPGP functions, so a flaw in it can surface in mail clients, Samba, and signed-commit verification rather than only in the gpg command. The advisory tracks CVE-2026-129975, a double free triggered by an OpenPGP key with a crafted very long user ID, and states that all software using GPGME before version 2.3.0 is affected whether the library is shared, a Windows DLL, or statically linked.

**「Upgrade scope」** Every application that uses GPGME before 2.3.1 is affected, whether it loads the library as a shared object, a DLL, or a statically linked copy, so replacing a system package does not cover statically linked builds, which must be rebuilt against the fixed release. The advisory&\#x27;s example path is signed data passed into an application, but it does not say which programs do that without a manual key import, so each integrator has to identify its own GPGME call sites.

**「Community discussion」** Commenters focused on downstream exposure: one highlighted GitLab&\#x27;s signed-commit support and a GitLab Omnibus patch, calling code execution in that path &quot;pretty bad,&quot; while another disputed treating the bug as an RCE chain and said it is a double free. A separate commenter claimed Red Hat had fixed the issue in its packaging five years earlier but upstream missed it, a claim the supplied advisory does not confirm.

<details><summary>References</summary>
<ul>
<li><a href="https://lists.gnu.org/archive/html/info-gnu/2026-11/msg00006.html">GnuPG Security Advisory for GPGME (T8557,CVE-2026-129975)</a></li>
<li><a href="https://thehackernews.com/2026/11/gnupg-warns-critical-gpgme-flaw-could.html">GnuPG Warns Critical GPGME Flaw Could Expose App Data via ...</a></li>
<li><a href="https://seclists.org/oss-sec/2026/q4/804">oss-sec: Fwd: GnuPG Security Advisory for GPGME (T8557,CVE ...</a></li>
<li><a href="https://thehackernews.com/2026/11/gnupg-warns-critical-gpgme-flaw-could.html">GnuPG Warns Critical GPGME Flaw Could Expose App Data via...</a></li>
<li><a href="https://www.phoronix.com/news/GnuPG-GPGME-Critical">GnuPG&#x27;s GPGME Affected By Critical Security Bug In Turn... - Phoronix</a></li>

</ul>
</details>

**Tags**: `#security advisory`, `#GPGME`, `#GnuPG`, `#memory safety`, `#open source`

---

<a id="item-tech-news-4"></a>
### [Monitor&\#x27;s USB Hub Latency Cut Ethernet Download Speed by 75%](https://blog.tymscar.com/posts/studiodisplayethernet/) ⭐️ 7.0/10

A debugging write-up traces a roughly 75% download-speed loss to latency introduced by routing Ethernet through a monitor&\#x27;s USB hub. The added delay prevented the laptop from acknowledging packets quickly enough, causing the Ethernet adapter&\#x27;s buffer to fill and drop packets. Switching to a different adapter that required less frequent acknowledgment fixed the problem. The finding concerns the USB network path rather than the monitor&\#x27;s display, and commenters noted that the monitor itself is incidental to the diagnosis.

hackernews · soheilpro · Nov 21, 10:36 · [Discussion](https://news.ycombinator.com/item?id=50587875)

**「Why It Matters」** USB-to-Ethernet adapters are common on laptops without built-in Ethernet, and they depend on timely host acknowledgment and buffering to sustain throughput. When round-trip latency rises, the adapter can accumulate packets faster than they are acknowledged, fill its buffer, and drop traffic, which sharply reduces effective download speed.

**「What to Check」** For users seeing unexplained throughput collapse on a USB Ethernet adapter, the case suggests testing the adapter connected directly to the host instead of through a hub or monitor, and trying an adapter with different acknowledgment behavior. In this instance, replacing the adapter resolved the issue; the monitor was not the component to reconfigure.

**「Community Discussion」** Commenter manarth argued the post is more accurately described as a USB network switch cutting download speed, with the monitor largely irrelevant, while fancyfredbot summarized the latency-to-buffer-to-packet-loss chain to correct misreadings. Another commenter, nagisa, reported a similar packet-drop problem with multigig copper SFP+ modules that advertise 10Gbps to the NIC but negotiate lower speeds on the copper side.

**Tags**: `#USB networking`, `#hardware debugging`, `#network latency`, `#packet loss`, `#ethernet`

---

<a id="item-tech-news-5"></a>
### [OpenRouter Warns MiniMax Prompts May Have Been Read by Third Parties](https://news.ycombinator.com/item?id=50585962) ⭐️ 7.0/10

OpenRouter has reportedly emailed users that prompts sent to MiniMax models may have been read by third parties, according to a Telegram summary; the warning has not been published on OpenRouter&\#x27;s website. Security researchers who sent prompts containing test URLs to MiniMax models between July and October 2026 found that third parties accessed those URLs 40 to 130 hours later. OpenRouter attributed the issue to MiniMax and forwarding providers AtlasCloud, Novita and StreamLake, removed zero-data-retention labels from the affected endpoints, and advised users with sensitive credentials to rotate API keys and passwords.

telegram · zaihuapd · Nov 21, 06:53

**「Background」** OpenRouter acts as a routing layer in which one model can be served by several upstream inference providers; its listing for MiniMax M2.5 names StreamLake and AtlasCloud among five providers. That means a zero-data-retention label depends on how each upstream handles prompts, the part of the chain the warning implicates. The source does not identify which MiniMax model or which user requests were affected.

**「Impact」** According to the reported email, users who sent sensitive credentials or personal data to MiniMax models through OpenRouter should treat those prompts as potentially exposed and rotate affected API keys and passwords; the removal of zero-data-retention labels means the affected endpoints can no longer be treated as covered by that guarantee.

<details><summary>References</summary>
<ul>
<li><a href="https://openrouter.ai/minimax/minimax-m2.5">MiniMax M2.5 - API Pricing &amp; Benchmarks | OpenRouter</a></li>

</ul>
</details>

**Tags**: `#AI privacy`, `#API security`, `#OpenRouter`, `#MiniMax`, `#data retention`

---

<a id="item-tech-news-6"></a>
### [FT Report Alleges Prince Group Figure Smuggled Nvidia Chips to China](https://www.ft.com/content/f3ad8a81-3890-4a8a-8853-ff0a94b08ba9?syn-25a6b1a6=1) ⭐️ 7.0/10

The Financial Times, citing people familiar with the matter, reported that Hu Xiaowei—whom the U.S. Treasury has described as the &quot;number two&quot; figure in Cambodia&\#x27;s Prince Group—is alleged to have helped move Nvidia chips into China. Trade data cited by the newspaper show that Megaspeed&\#x27;s Malaysian subsidiary imported goods with a declared value of about $4.6 billion between December 2024 and December 2025, with some chips reportedly reaching China&\#x27;s black market. Prince Group denied that Hu worked for it and said the allegations about an illegal network and private-jet smuggling lacked factual basis; the report&\#x27;s central allegations were not independently confirmed in the supplied material.

telegram · zaihuapd · Nov 22, 04:34

**「Background」** The allegations sit against U.S. export controls that restrict sales of advanced Nvidia AI chips to China without a license. A secondary report says Nvidia has blacklisted Megaspeed and restricted sales to Aivres.

<details><summary>References</summary>
<ul>
<li><a href="https://finance.biggo.com/news/f9dfb753-be17-4663-b99d-7c131d82dfe4">Nvidia Chip Smuggling Network Exposed: Prince Group Figure ...</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#芯片走私`, `#出口管制`, `#AI硬件`, `#柬埔寨太子集团`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Good Programming Is About Avoiding Blunders, Not Cleverness](https://seangoedecke.com/to-code-well-avoid-blunders/) ⭐️ 6.0/10

rss · Sean Goedecke · Nov 22, 00:00

**「Background」** Sean Goedecke argues that good programming depends less on brilliant insights or elegant new abstractions than on avoiding catastrophic mistakes, particularly in large commercial codebases worked on by big teams.

**「Solution」** He compares programming to chess and tennis: steady players who never blunder can beat most opponents without producing brilliant combinations or winners. Programming lacks a durable winning advantage, he argues, because one bad decision can turn an elegant codebase into a janky one. His examples include introducing a parallel system for the same task, creating a second source of truth, making a safe synchronous operation delicately asynchronous, adding subtle failure points, and complicating a key interface. The cardinal sins are inconsistency and unnecessary requirements. Even slight inconsistency breaks trust, forcing engineers to hunt for surprises instead of assuming sensible behavior. Unnecessary requirements are sticky because later engineers lack the context to remove them safely, and they interact combinatorially with new features, making large codebases hard to change. The author&\#x27;s prescription is to identify where a task fits most naturally and trim it to the smallest set of requirements. He treats the thought “I could implement this with a clever pattern” as a warning sign of distraction. He also notes that current coding agents are roughly human-level at consistency but worse at avoiding unnecessary requirements.

**「Takeaway」** Goedecke&\#x27;s thesis is that great programming work does not require cleverness and may even be hindered by it; what matters is attention to detail and a laser focus on avoiding blunders by maintaining consistency and skipping unnecessary requirements.

**Tags**: `#software engineering`, `#code quality`, `#codebase maintainability`, `#engineering judgment`, `#requirements management`

---