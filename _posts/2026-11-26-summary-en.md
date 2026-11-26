---
layout: default
title: "Horizon Summary: 2026-11-26 (EN)"
date: 2026-11-26
lang: en
---

> From 38 items, 15 important content pieces were selected

---

**Technology News**
1. [1Password Says Attacker Pushed Malicious Backend Code, Stole Account Data](#item-tech-news-1) ⭐️ 8.0/10
2. [Shortened Lean formalization tied to Anthropic&\#x27;s GRH work draws scrutiny](#item-tech-news-2) ⭐️ 8.0/10
3. [FCC approves SpaceX&\#x27;s 1 million-satellite Starmind data-center constellation](#item-tech-news-3) ⭐️ 8.0/10
4. [Neuralink Gets FDA Clearance for Pivotal ALS Trial](#item-tech-news-4) ⭐️ 8.0/10
5. [Nvidia Halts AI Server Shipments to Four Southeast Asian Countries](#item-tech-news-5) ⭐️ 8.0/10
6. [Scott Aaronson Post Flags Claimed 9/4 Matrix Multiplication Exponent](#item-tech-news-6) ⭐️ 7.0/10
7. [Slow Ubuntu security patches prompt Debian migration debate](#item-tech-news-7) ⭐️ 7.0/10
8. [Lean audit of Clojure core reports bugs; commenters dispute two](#item-tech-news-8) ⭐️ 7.0/10
9. [Preprint claims polynomial Hirsch conjecture is false](#item-tech-news-9) ⭐️ 7.0/10
10. [SemiAnalysis&\#x27;s GDPx benchmark debuts with Opus 5.5 at 12%](#item-tech-news-10) ⭐️ 7.0/10
11. [Samsung and SK Hynix reportedly to use YMTC&\#x27;s Xtacking NAND tech](#item-tech-news-11) ⭐️ 7.0/10
12. [Huawei to Present HBM Research Claiming Doubled Data-Pin Density](#item-tech-news-12) ⭐️ 7.0/10
13. [China sets 2030 targets for 5G-A, satellite internet and timely 6G buildout](#item-tech-news-13) ⭐️ 7.0/10

**Financial News**
1. [Court Documents Report Commerce Department Pressure on Intel to Surrender 10% Equity Stake](#item-finance-news-1) ⭐️ 9.0/10
2. [美国计划依据第301条对14个贸易伙伴加征新关税](#item-finance-news-2) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [1Password Says Attacker Pushed Malicious Backend Code, Stole Account Data](https://1password.com/blog/update-on-nov-2026-security-incident) ⭐️ 8.0/10

1Password has confirmed that an attacker compromised an employee&\#x27;s corporate GitHub account and used that access to push malicious code to backend services, leading to the download of some customer account information. The exposed records include names, email addresses, account identifiers, and account creation and last-login timestamps; 1Password says customer vaults and their contents were not affected and has not disclosed how many users were affected. The company began investigating on Nov. 19, disabled the account, rotated or revoked potentially exposed internal credentials, and strengthened verification codes for invitation and recovery emails, while telling users they do not need to change their accounts but should watch for phishing.

hackernews · lxhrstn · Nov 25, 17:18 · [Discussion](https://news.ycombinator.com/item?id=50644817)

**「Background」** 1Password is a password manager that keeps customer credentials in encrypted vaults; the data the company says was taken in this incident—names, email addresses, account identifiers, and account creation and last-login times—is account metadata rather than vault contents. The disclosed path is a SaaS supply-chain one: an employee&\#x27;s enterprise GitHub account gave an attacker access to source code and a way to push malicious code into backend services, making source-control and deployment permissions the route to production data.

**「Phishing risk for affected customers」** Customers whose records were among the downloaded data should treat unsolicited messages that cite their name, email address, account identifier, or login timestamps as potential targeted phishing, since the attacker obtained those details. 1Password says vault contents were not accessed and users do not need to change their accounts, but it has not disclosed how many customers are affected.

**「Community Discussion」** Commenters described compromised employee infrastructure that can push code into production as a standard SaaS breach pattern and questioned whether 1Password had branch-protection or deployment controls that should have blocked the push. Others criticized the disclosure for not plainly saying whether encrypted vaults were downloaded, while a longtime user said the incident reinforced their choice to keep a local-only vault.

<details><summary>References</summary>
<ul>
<li><a href="https://1password.com/blog/update-on-nov-2026-security-incident">Update on a security incident involving 1Password’s backend ...</a></li>
<li><a href="https://thehackernews.com/2026/11/1password-hacked-customer-data-and.html">1Password Hacked, Customer Data and Source Code Stolen in ...</a></li>

</ul>
</details>

**Tags**: `#1Password`, `#security incident`, `#SaaS security`, `#supply chain security`, `#password managers`

---

<a id="item-tech-news-2"></a>
### [Shortened Lean formalization tied to Anthropic&\#x27;s GRH work draws scrutiny](https://github.com/lsernau/grh-lean) ⭐️ 8.0/10

A repository by lsernau, grh-lean, presents a much shorter Lean formalization associated with Anthropic&\#x27;s GRH work. Commenters describe the reduction as going from roughly 17 million lines to about 76,000 lines, with one thread participant computing a 99.56% decrease. The repository is also said to include human-readable documentation and an explicit separation between &quot;known math&quot; and &quot;new math.&quot; Whether the shorter version is valid and how it connects to existing libraries is unresolved: one commenter notes that Main.lean does not appear to import mathlib directly, raising the question of how it refers to mathlib&\#x27;s statement of the Riemann hypothesis. The submitted item is a repository and discussion thread; no independent verification of the proof is presented.

hackernews · nb-t · Nov 25, 21:48 · [Discussion](https://news.ycombinator.com/item?id=50648050)

**「Background」** Lean is an interactive theorem prover that mechanically checks proofs, so a Lean formalization of the generalized Riemann hypothesis \(GRH\) is executable proof code rather than a conventional paper argument. A prior Lean formalization of RH/GRH associated with Anthropic ran to roughly 17 million lines, making it difficult to review; the repository discussed here presents a version reduced to about 76,000 lines.

**「Impact」** For readers assessing the formalization, the open import question is the practical blocker: confirming that the development proves the intended statement requires tracing the import chain to mathlib&\#x27;s RiemannHypothesis definition rather than assuming it from the repository layout. Until that is checked, the line-count reduction and documentation improvements make the proof easier to read but do not by themselves establish that it proves the same theorem.

**「Community Discussion」** Commenters welcomed the readability gains, with spootydooty highlighting the &quot;known math&quot; versus &quot;new math&quot; split and the human-readable documentation as aids to digesting the proof. Jaxan questioned provenance instead, asking how Main.lean refers to mathlib&\#x27;s RiemannHypothesis when the file does not seem to import mathlib directly; gre separately asked whether streamlined, LLM-golfed proofs answer Tao&\#x27;s earlier concern that huge proofs lacking insight are a problem.

<details><summary>References</summary>
<ul>
<li>Much shorter version of GRH Lean verification from Anthropic - Hacker News</li>
<li>Anthropic has achieved a remarkable 99.56% reduction in the formalization of the Riemann Hypothesis in Lean : r/singularity - Reddit</li>

</ul>
</details>

**Tags**: `#Lean`, `#formal verification`, `#GRH`, `#AI-assisted mathematics`, `#proof engineering`

---

<a id="item-tech-news-3"></a>
### [FCC approves SpaceX&\#x27;s 1 million-satellite Starmind data-center constellation](https://www.geekwire.com/2026/fcc-clears-spacex-million-satellites-starmind-data-center/) ⭐️ 8.0/10

The FCC approved SpaceX to deploy up to 1 million satellites for Starmind, an in-orbit data-processing network, at altitudes of 500 to 1,002 km. The FCC described it as the first U.S. approval of a space data-center constellation and attached conditions including communications backup arrangements, periodic progress reports, and detailed orbital-debris mitigation plans. SpaceX must have the first satellite operational by 2033 and the full constellation running by 2040; the FCC rejected objections from Amazon, Viasat, and the American Astronomical Society. This is an authorization, not evidence that the satellites have been built or launched, and the available item is a brief summary of a GeekWire report without further technical detail.

telegram · zaihuapd · Nov 26, 04:45

**「Background」** Starmind is described as a network of orbital compute modules meant to process large amounts of data in space and return results for use on Earth. That distinguishes the authorization from a conventional communications constellation, in which satellites mainly relay traffic between ground terminals.

**「Impact」** The phased deadlines mean SpaceX cannot treat the one-million-satellite figure as an immediate deployment target: it must show progress toward an operational first satellite by 2033 and a complete constellation by 2040 while meeting the debris-mitigation conditions.

<details><summary>References</summary>
<ul>
<li>US grants SpaceX approval for 1 million space data centres | Elon Musk News - Al Jazeera</li>

</ul>
</details>

**Tags**: `#SpaceX`, `#FCC`, `#space data centers`, `#satellite constellations`, `#orbital computing`

---

<a id="item-tech-news-4"></a>
### [Neuralink Gets FDA Clearance for Pivotal ALS Trial](https://www.bloomberg.com/news/articles/2026-11-25/neuralink-gets-clearance-for-brain-implant-trial-in-als-patients?srnd=phx-technology) ⭐️ 8.0/10

Neuralink announced that the FDA has cleared a pivotal U.S. trial of its LINK brain implant in ALS patients, describing it as the first approved pivotal trial of its kind for a brain-computer interface in the United States. The trial aims to convert brain signals directly into computer control commands, and its data are intended to form the core basis for a future medical-device marketing application. Neuralink said earlier research had implanted the device in more than 30 paralyzed patients worldwide; no results from the pivotal ALS trial have been reported.

telegram · zaihuapd · Nov 26, 07:15

**「Background」** ALS \(amyotrophic lateral sclerosis\) progressively destroys the motor neurons that drive voluntary movement, often leaving patients cognitively intact but unable to move or speak — the condition brain-computer interfaces are designed to address by decoding neural activity into control signals. Neuralink said its earlier feasibility work had implanted devices in more than 30 paralyzed patients worldwide, establishing early safety experience that precedes the pivotal stage cleared here, which is intended to generate the core data for a future medical-device marketing application.

**「Impact」** For ALS patients, near-term access is limited to trial participants rather than general availability. Broader use would depend on the study producing data sufficient to support a future FDA marketing submission, and those results are not yet available.

**Tags**: `#Neuralink`, `#brain-computer interface`, `#FDA clinical trial`, `#ALS`, `#neurotechnology`

---

<a id="item-tech-news-5"></a>
### [Nvidia Halts AI Server Shipments to Four Southeast Asian Countries](https://www.ft.com/content/7838a715-07d4-4605-aa60-21f5af2b2370) ⭐️ 8.0/10

Nvidia has reportedly told major manufacturing partners to pause AI server shipments to Malaysia, Singapore, Thailand and Indonesia, and assemblers including Dell and Supermicro have notified buyers in those countries that orders cannot leave the factory. Three people familiar with the matter said the freeze is tied to a new round of U.S. export controls, though it remains unclear whether the measure is temporary. The four countries are transshipment points for Chinese AI companies seeking Nvidia&\#x27;s most advanced processors, which cannot be exported directly to mainland China; the U.S. Commerce Department issued rules a week earlier requiring regional cloud providers to obtain export licenses within 90 days and verify that customers do not include restricted Chinese entities.

telegram · zaihuapd · Nov 26, 07:38

**「Background」** U.S. export controls bar Nvidia&\#x27;s most advanced processors from being shipped directly to mainland China, making Malaysia, Singapore, Thailand and Indonesia transit points for China-linked AI capacity. The reported halt follows a Commerce Department rule issued the previous week that requires regional cloud providers to obtain export licenses within 90 days and verify that customers do not include restricted Chinese entities.

**「Shipment and compliance pressure」** Buyers in Malaysia, Singapore, Thailand and Indonesia that ordered Nvidia-based AI servers from Dell, Supermicro or other assemblers now face stalled deliveries, forcing data-center and cloud operators to re-plan capacity and check whether their workloads and customers fall under the new U.S. licensing regime. Regional cloud providers serving Chinese AI customers have 90 days to obtain export licenses and verify those customers are not restricted Chinese entities, so procurement and customer contracts may need compliance review before shipments resume.

<details><summary>References</summary>
<ul>
<li>Washington&#x27;s AI chip crackdown spells trouble for a multibillion dollar cloud business helping to power Southeast Asia&#x27;s data center boom. The new rulebook applies to data centers in plac</li>
<li>US to curb China&#x27;s access to AI chips as Trump heads to Asia | Reuters</li>

</ul>
</details>

**Tags**: `#Nvidia`, `#AI servers`, `#export controls`, `#Southeast Asia`, `#supply chain`

---

<a id="item-tech-news-6"></a>
### [Scott Aaronson Post Flags Claimed 9/4 Matrix Multiplication Exponent](https://scottaaronson.blog/?p=10379) ⭐️ 7.0/10

Scott Aaronson published a post whose available content consists only of a pointer to a paper titled &quot;The matrix multiplication exponent is nine fourths,&quot; so the post&\#x27;s own argument and any claim it endorses cannot be assessed from the supplied material. A value of ω = 9/4 \(2.25\) would sit below the best recently published upper bounds on the matrix multiplication exponent, which have hovered near 2.37, making the linked preprint a significant claim if it survives review — but the item provides no proof details, authorship, venue, or peer-review status, and the hyperbolic post title is not evidence that the result has been verified. The accompanying Hacker News thread debates what such a result would mean for AI in mathematics, for cryptography, and for existential risk, but those comments are speculation rather than confirmation of either the complexity claim or any cryptographic break.

hackernews · Kotlopou · Nov 25, 19:11 · [Discussion](https://news.ycombinator.com/item?id=50646108)

**「Context: the claimed 9/4 bound」** Scott Aaronson’s post appears on his Shtetl-Optimized blog, and the item points to a paper titled “The matrix multiplication exponent is nine fourths.” In complexity theory, that exponent—usually written ω—sets the asymptotic cost of multiplying large matrices, so a 9/4 bound would be a fundamental result; a Hacker News comment reports that Aaronson said it could take years to understand the proofs. The supplied item does not include the post body or the paper itself, so the claimed proof cannot be assessed from the available text.

**「What changes for algorithm researchers」** If the preprint&\#x27;s matching lower bound holds, the asymptotic race is closed: no algorithm could beat n^2.25 for large square matrices over any field in the formal arithmetic-circuit model, so researchers and library authors would shift effort from chasing the exponent toward practical constants, small-matrix base cases, and hardware-aware implementations. Because this is a 111-page preprint claim rather than a peer-reviewed proof, teams should treat it as unconfirmed until the argument has been independently checked.

**「Community Discussion」** Commenters split on what the episode implies: jsLavaGoat argued that strength at axiomatic mathematics does not establish that AI systems will master other fields or pose the existential risk depicted in science fiction, while nickysielicki said he saw no evidence that AI labs currently hold fundamental cryptanalytic breaks, reasoning that organizations of their size could not keep such a result secret. Nevermark took the opposite framing, contending that humans are poorly equipped to register the scale of change underway and are likely to underreact by orders of magnitude.

<details><summary>References</summary>
<ul>
<li><a href="https://scottaaronson.blog/?p=10379">Shtetl-Optimized » Blog Archive » HOLY SHIT HOLY SHIT HOLY...</a></li>
<li><a href="https://news.ycombinator.com/item?id=50646108">Holy shit holy shit holy shit holy shit : The magnitude... | Hacker News</a></li>
<li><a href="https://dev.to/axrisi/openais-claim-that-the-matrix-multiplication-exponent-is-exactly-94-and-what-has-been-checked-398j">OpenAI&#x27;s claim that the matrix multiplication exponent is ...</a></li>
<li><a href="https://interestingengineering.com/culture/openai-exact-2-25-matrix-multiplication-exponent">OpenAI establishes exact 2.25 exponent for matrix multiplication</a></li>
<li><a href="https://cryptobriefing.com/openai-matrix-multiplication-exponent-9-4/">OpenAI preprint claims the matrix multiplication exponent is ...</a></li>

</ul>
</details>

**Tags**: `#AI for mathematics`, `#matrix multiplication`, `#computational complexity`, `#cryptography`, `#AI risk`

---

<a id="item-tech-news-7"></a>
### [Slow Ubuntu security patches prompt Debian migration debate](https://www.openwall.com/lists/oss-security/2026/11/25/9) ⭐️ 7.0/10

A Hacker News thread linked to an oss-security mailing-list post centers on complaints that Ubuntu&\#x27;s security patches arrive slowly. Commenters say they have moved server images or generic VMs from Ubuntu to Debian because of the delays, while others caution that regression testing is time-consuming and that Debian has had its own regression bugs. The supplied discussion gives no specific patch timeline, affected package, or Ubuntu response, so the evidence is practitioner complaint rather than a measured comparison.

hackernews · gslin · Nov 25, 20:38 · [Discussion](https://news.ycombinator.com/item?id=50647181)

**「Why patch timing is contested」** The complaint sits within a long-running dispute over how Linux distributions deliver security fixes: a stable-kernel maintainer argued in 2025 that systems must follow all stable/LTS releases because cherry-picking patches can leave known and unknown vulnerabilities unfixed. Ubuntu backports and regression-tests fixes for its supported releases, so the debate turns on whether its delay is an avoidable failure or the cost of limiting breakage.

**「Impact」** For teams considering the same move, the thread frames migration as a tradeoff rather than a clean fix: Debian may address perceived patch latency, but commenters point to its limited QA resources and a regression bug as operational risks.

**「Community discussion」** Commenters describe moving server images or generic VMs to Debian over the delays, while others defend slower cadence as the cost of regression testing and cite a Debian regression bug as evidence that switching is not risk-free. One commenter also quotes a stable-kernel maintainer warning that cherry-picking patches can leave a system less secure, and another asks whether Ubuntu Livepatch covers the vulnerabilities; the thread gives no answer.

**Tags**: `#Ubuntu`, `#Linux distributions`, `#security response`, `#open source`, `#Debian`

---

<a id="item-tech-news-8"></a>
### [Lean audit of Clojure core reports bugs; commenters dispute two](https://s.conao3.com/blog/2026/e4f733) ⭐️ 7.0/10

A blog post reports using the Lean proof assistant to audit Clojure&\#x27;s core library and surface bugs that had not previously been reported. The article itself was not supplied, so the individual findings and the method used to derive them could not be independently checked; the account rests on the post&\#x27;s own claims as summarized in the item.

hackernews · encyclopedism · Nov 25, 14:56 · [Discussion](https://news.ycombinator.com/item?id=50642939)

**「Background」** Lean is a dependently typed proof assistant used to state properties and have them machine-checked, which differs from example-based unit testing. Auditing Clojure&\#x27;s core with it means modeling standard-library functions and their intended behavior as formal specifications, then checking the implementation against those specifications.

**「Impact」** For Clojure users and maintainers, the report is not a confirmed defect list: at least two entries turn on argument types rather than library behavior, so each item needs triage before it is treated as a core bug. The disputed examples involve passing a Long to \`.indexOf\` on a byte array and expecting different behavior from \`get\` on a string when the key is coerced to an integer.

**「Community Discussion」** Commenter rvprasad argued that two of the listed findings are incorrect usage rather than bugs and that eyeball type checking would have flagged them, suggesting the exercise would be more useful with less noise. Another commenter, yababa\_y, linked a comparable audit that found dozens of issues in the Common Lisp implementations SBCL, Clozure, and ACL2, while networked asked whether Lean has displaced Rocq \(formerly Coq\) for this kind of verification work and whether language models write Lean more reliably.

**Tags**: `#Clojure`, `#Lean`, `#formal verification`, `#programming languages`, `#software testing`

---

<a id="item-tech-news-9"></a>
### [Preprint claims polynomial Hirsch conjecture is false](https://github.com/openai/math/blob/main/preprints/Superpolynomial-graph-diameter-of-simple-polytopes-November-24-2026/paper.pdf) ⭐️ 7.0/10

A preprint posted in OpenAI&\#x27;s math GitHub repository claims the polynomial Hirsch conjecture is false, claiming that simple polytopes can have superpolynomial graph diameter. If correct, it would rule out any polynomial worst-case bound on the number of vertex-to-vertex steps in a simplex pivot path, and therefore a polynomial-time simplex algorithm that follows such paths. It would not by itself show that linear programming lacks polynomial-time algorithms, and the item provides no peer review, independent confirmation, or source text beyond the PDF link.

hackernews · acossta · Nov 25, 17:34 · [Discussion](https://news.ycombinator.com/item?id=50644980)

**「Background」** The Hirsch conjecture, stated by Warren M. Hirsch in 1957 in the context of the simplex method, bounded the number of edges needed to travel between any two vertices of a d-dimensional polytope with n facets by n − d, and Francisco Santos disproved it in 2010 with an explicit counterexample. The polynomial Hirsch conjecture is the relaxed version asking whether some fixed polynomial bound in n and d always suffices, and reference sources described it as still open after Santos&\#x27;s result. The new preprint&\#x27;s own file path frames the claim as superpolynomial graph diameter of simple polytopes, and the repository listing carries no description of the method or independent verification.

**「Impact」** The consequence is concentrated in worst-case analysis of simplex methods: the preprint, if verified, would remove a polynomial diameter guarantee for edge-following simplex pivot rules. Anyone relying on the claim should check that the constructed family is simple and that the superpolynomial lower bound is uniform over the relevant parameters.

**「Community discussion」** Commenters frame the preprint as incremental: GIFtheory calls it &quot;more of a mopping up result&quot; after the 2010 disproof of the original Hirsch conjecture and says it means there is no polynomial-time simplex algorithm. tensegrist explains the result through graph diameter, and the thread does not establish consensus on the preprint&\#x27;s correctness.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Hirsch_conjecture">Hirsch conjecture - Wikipedia</a></li>
<li><a href="https://arxiv.org/pdf/1006.2814">A counterexample to the Hirsch conjecture</a></li>
<li><a href="https://letsdatascience.com/news/openai-posts-preprint-claiming-polynomial-hirsch-conjecture-6465d7de">OpenAI posts preprint claiming polynomial Hirsch conjecture ...</a></li>

</ul>
</details>

**Tags**: `#theoretical computer science`, `#linear programming`, `#polytope theory`, `#complexity theory`, `#Hirsch conjecture`

---

<a id="item-tech-news-10"></a>
### [SemiAnalysis&\#x27;s GDPx benchmark debuts with Opus 5.5 at 12%](https://newsletter.semianalysis.com/p/evaluating-recent-model-releases) ⭐️ 7.0/10

SemiAnalysis has launched GDPx, a benchmark it says measures frontier-model progress across 11 domains chosen for AI&\#x27;s likely economic impact—chip design, cybersecurity, biology, finance, legal, quant trading, recursive self-improvement, hardware design, materials science, alignment, and software engineering—rather than the GDP-share or O\*NET categories it says GDPVal and Agent&\#x27;s Last Exam rely on. The benchmark consists of 206 tasks built with 14 specialized data partners, and SemiAnalysis says it deliberately excludes areas such as government and real estate. On release day, Opus 5.5 was the highest-scoring model at just 12%, which the authors present as evidence that GDPx is unsaturated and can still discriminate between future models. The post says new releases from Anthropic, OpenAI, Google&\#x27;s Gemini 4 series, Alibaba, and Moonshot have been added to the leaderboard since the November 1 launch, but the supplied text does not give those scores; it also states that safety classifiers depressed overall scores for Fable 5.2 and GPT-6.2 Astra.

rss · Semianalysis · Nov 26, 00:05

**「Benchmark landscape before GDPx」** GDPx launched on November 1 with 206 tasks built with 14 specialized data partners, and this post is SemiAnalysis&\#x27;s first follow-up scoring models released since then. The benchmark was designed as an alternative to single-domain agentic evaluations such as coding or legal suites, and to comprehensive efforts like OpenAI&\#x27;s GDPVal and Agent&\#x27;s Last Exam, which SemiAnalysis argues pick domains by share of GDP or the O\*NET taxonomy rather than by where frontier models actually produce value. SemiAnalysis also frames benchmark saturation as the problem GDPx targets, citing Terminal Bench 4.0 as an example of a suite whose top scores leave little room to separate newer models.

**「Impact」** Teams using GDPx to compare models will need to look beyond a single aggregate score: SemiAnalysis says safety classifiers on cyber, biology, and alignment lowered overall results for Fable 5.2 and GPT-6.2 Astra, and that excluding those domains while switching legal and finance from binary to partial grading produces a different leaderboard. The practical consequence is that anyone selecting a model for agentic work should check per-domain results and which grading variant was used rather than treating one GDPx total as a like-for-like ranking.

**Tags**: `#AI benchmarks`, `#frontier models`, `#agentic AI`, `#model evaluation`, `#AI economics`

---

<a id="item-tech-news-11"></a>
### [Samsung and SK Hynix reportedly to use YMTC&\#x27;s Xtacking NAND tech](https://tech.ifeng.com/c/8yLRPKxQy4L) ⭐️ 7.0/10

Samsung and SK Hynix have reportedly agreed, through a cross-licensing arrangement, to use parts of YMTC&\#x27;s Xtacking technology in 3D NAND flash. All three companies declined to comment, so the scope and terms of any license remain unconfirmed. Xtacking fabricates the memory array and CMOS control circuitry on separate wafers and joins them by bonding, allowing each part to be produced and optimized independently. An Omdia senior analyst said this lets a manufacturer build the memory array itself and assign logic to a foundry, gaining access to more advanced processes.

telegram · zaihuapd · Nov 25, 14:33

**「Background」** Xtacking is YMTC&\#x27;s approach to 3D NAND: the memory array and the CMOS control circuitry are fabricated on separate wafers and then bonded together. This differs from the usual flow, in which the array and peripheral logic are built on one wafer, and it lets each half use its own process and be optimized separately.

**「Manufacturing flexibility, pending confirmation」** If the reported cross-license is confirmed, Samsung and SK Hynix would gain a production-tested wafer-bonding route that separates the NAND array from CMOS logic, potentially easing the single-wafer constraints they face at hundreds of layers and allowing logic production at foundries. Because all three companies declined to comment, the licensing scope and whether it covers current or future products remain unverified, so suppliers and customers should treat adoption as reported rather than shipped.

<details><summary>References</summary>
<ul>
<li><a href="https://aiweekly.co/alerts/samsung-and-sk-hynix-tap-ymtcs-xtacking-tech-in-cross-license">Samsung and SK Hynix cross-license YMTC&#x27;s Xtacking 3D NAND</a></li>
<li><a href="https://www.techpowerup.com/355199/samsung-and-sk-hynix-to-license-ymtcs-xtacking-technology">Samsung and SK hynix to License YMTC&#x27;s Xtacking Technology</a></li>

</ul>
</details>

**Tags**: `#3D NAND`, `#Xtacking`, `#YMTC`, `#Samsung/SK Hynix`, `#semiconductor manufacturing`

---

<a id="item-tech-news-12"></a>
### [Huawei to Present HBM Research Claiming Doubled Data-Pin Density](https://www.bloomberg.com/news/articles/2026-11-26/huawei-teases-next-gen-ai-memory-chip-to-take-on-samsung-hynix) ⭐️ 7.0/10

Huawei plans to present a research paper in February at a conference in San Francisco describing a new high-bandwidth memory chip whose data-pin density is claimed to be twice that of mass-production HBM from Samsung and SK Hynix, according to the paper title cited in the Bloomberg report. The claim, if borne out, would theoretically increase memory bandwidth substantially, but it comes from a planned presentation rather than a shipped product or independently measured result. Huawei is also pushing to produce HBM domestically as the component is subject to US sanctions. No product name, availability date, capacity, or performance figures beyond the pin-density comparison were disclosed.

telegram · zaihuapd · Nov 26, 05:30

**「Background」** High-bandwidth memory stacks DRAM dies vertically and moves data over very wide interfaces, so pin count and pin density directly shape the bandwidth a memory package can deliver.

**「Impact」** For Chinese AI hardware developers, a domestic HBM alternative remains at the research-paper stage: the source gives no product name, sampling date, capacity, or measured bandwidth, so the doubled data-pin density claim cannot yet be used for system design or procurement planning.

<details><summary>References</summary>
<ul>
<li>Scaling the Memory Wall: The Rise and Roadmap of HBM</li>

</ul>
</details>

**Tags**: `#Huawei`, `#HBM`, `#AI hardware`, `#semiconductors`, `#export controls`

---

<a id="item-tech-news-13"></a>
### [China sets 2030 targets for 5G-A, satellite internet and timely 6G buildout](https://www.news.cn/politics/20261126/9fe827a2d98741acb60f62d36ba89cf7/c.html) ⭐️ 7.0/10

China&\#x27;s Ministry of Industry and Information Technology, Cyberspace Administration and National Development and Reform Commission, with State Council approval, issued the Implementation Plan for Next-Generation Communications Network Construction, published Nov. 26. The plan sets 2030 goals to build a well-covered, performance-leading network, actively promote 5G-A scale coverage, carry out 6G network construction in due course, basically complete a low-orbit satellite internet system, and scale up converged industrial internet and vehicle-network deployments. It also calls for faster standards work on 6G, satellite internet and compute-network integration, and deeper integration with brain-computer interfaces, embodied intelligence and intelligent connected vehicles. The same source also carries a Guangdong Mobile notice that its 2G network in the province will begin phased withdrawal 30 days after the announcement.

telegram · zaihuapd · Nov 26, 06:30

**「Context」** 5G-A \(5G-Advanced\) is the enhanced phase of 5G positioned between current 5G networks and eventual 6G, which is why the plan pairs scaled 5G-A coverage with a conditional, later 6G build-out. The plan&\#x27;s scope also extends beyond terrestrial mobile access to low-orbit satellite internet and industrial and vehicle networks, reflecting a converged-network approach rather than a single radio-generation upgrade.

**「Impact」** Operators and vendors will need to align 5G-A rollout, low-orbit satellite internet, and 6G standards work with the plan&\#x27;s 2030 deadlines rather than treating them as separate programs. The accompanying Guangdong Mobile notice gives a concrete migration concern: 2G-dependent devices and users in the province must move off the network after the 30-day notice.

**Tags**: `#6G`, `#telecom policy`, `#satellite internet`, `#5G-A`, `#China tech`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Court Documents Report Commerce Department Pressure on Intel to Surrender 10% Equity Stake](https://www.wired.com/story/inside-trumps-demands-to-another-chips-ceo/) ⭐️ 9.0/10

Court documents reportedly show that a U.S. Commerce Department lawyer told Intel&\#x27;s chief financial officer in an August 2025 call that the administration was not &quot;negotiating&quot; and that the board could refuse but should expect unpredictable consequences; days later the board handed over the stake. President Trump then said the U.S. government &quot;fully owns and controls&quot; 10% of Intel without having paid for it, shares the government now values at about $11 billion.

telegram · zaihuapd · Nov 25, 13:25

**「Background」** The stake is linked to roughly $8.9 billion in federal semiconductor funding Intel had already been awarded, according to allegations in a shareholder lawsuit filed over the 2025 transaction. The suit claims the government received about a 9.9% stake in Intel in connection with the release of that previously awarded money, rather than as a conventional share purchase.

**「Impact」** The 10% holding makes the U.S. government Intel&\#x27;s largest shareholder, and Forbes reports Washington now holds equity in roughly 30 companies, a template that exposes shareholders in other strategic firms to state ownership and influence.

<details><summary>References</summary>
<ul>
<li><a href="https://www.dandodiary.com/2026/03/articles/shareholders-derivative-litigation/intel-derivative-suit-tests-governance-implications-of-government-equity-stakes/">Intel Derivative Suit Tests Governance Implications of ...</a></li>
<li><a href="https://www.gate.com/news/detail/intel-lawsuit-reveals-trumps-alleged-10-stake-demand-for-chips-act-funds-25863723">Intel Lawsuit Reveals Trump&#x27;s Alleged 10% Stake Demand for ...</a></li>
<li><a href="https://www.forbes.com/sites/frankholmes/2026/08/03/the-us-government-now-owns-stakes-in-30-companies-intel-is-just-the-beginning/">The U.S. Government Now Owns Stakes In 30 Companies. Intel Is ...</a></li>
<li><a href="https://www.softwareseni.com/us-government-equity-stakes-in-intel-industrial-policy-or-nationalisation/">US Government Equity Stakes in Intel: How a $8.9B Grant ...</a></li>

</ul>
</details>

**Tags**: `#Intel`, `#US Commerce Department`, `#semiconductor industry`, `#government equity stake`, `#industrial policy`

---

<a id="item-finance-news-2"></a>
### [美国计划依据第301条对14个贸易伙伴加征新关税](https://www.cnbc.com/2026/11/25/us-tariffs-trump-section-301.html) ⭐️ 8.0/10

据报道，美国正准备依据第301条对包括中国、欧盟、日本和印度在内的14个贸易伙伴加征新关税，并按国家分别设定税率，而非实行统一税率。该提案将在中国现有25%关税之上再加征20%，且如果中国违反2025年10月在韩国釜山达成的贸易休战协议，对中国的新关税税率可能升至40%。

telegram · zaihuapd · Nov 25, 13:59

**「Background」** Section 301 of the Trade Act of 1974 lets the U.S. impose tariffs after investigations into unfair trade practices; this proposal follows an eight-month investigation into alleged structural excess capacity in manufacturing.

**「Who is affected」** Importers of manufactured goods from the 14 partners would face higher landed costs, with Chinese goods carrying a proposed extra 20% on top of the 25% imposed in 2018; because this remains a proposal, no new duty applies yet.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/25/us-tariffs-trump-section-301.html">U . S . unveils new Section 301 tariffs targeting China , EU and others</a></li>
<li><a href="https://www.foxbusiness.com/fox-news-global-economy/trump-admin-raise-tariffs-china-eu-other-trading-partners">Trump administration proposes sweeping Section 301 tariffs on China ...</a></li>
<li><a href="https://www.cnbc.com/2026/11/25/us-tariffs-trump-section-301.html">U . S . unveils new Section 301 tariffs targeting China , EU and others</a></li>
<li><a href="https://www.theguardian.com/business/live/2026/nov/25/rise-energy-bills-britain-2166-impossible-high-millions-households-stocks-tumble-as-ai-rally-fizzles-live-updates">US proposes new tariffs on 14 trading partners , including China ...</a></li>

</ul>
</details>

**Tags**: `#US tariffs`, `#Section 301`, `#US-China trade`, `#EU-Japan-India trade`, `#trade policy`

---