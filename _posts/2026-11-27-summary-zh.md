---
layout: default
title: "Horizon Summary: 2026-11-27 (ZH)"
date: 2026-11-27
lang: zh
---

> 从 35 条内容中筛选出 7 条重要资讯。

---

**科技新闻**
1. [Google 拟开放 Workspace MCP，Gmail 发信限制存疑](#item-tech-news-1) ⭐️ 7.0/10
2. [智谱、月之暗面新模型或因反蒸馏与算力限制延期](#item-tech-news-2) ⭐️ 7.0/10

**科技博客**
1. [谁有权判定内容是否由 AI 写成？](#item-tech-blog-1) ⭐️ 5.0/10

**财经新闻**
1. [德银分析：2026 年首季全球芯片出口额首次超过油气](#item-finance-news-1) ⭐️ 8.0/10
2. [国常会提出加力发挥“国家队”稳市作用，优化中央汇金类“平准基金”功能](#item-finance-news-2) ⭐️ 8.0/10
3. [荷兰大臣称不接受美国限制 ASML 对华销售的法案](#item-finance-news-3) ⭐️ 7.0/10
4. [蜜雪冰城 5 亿元入股 DeepSeek 报道称新一轮融资约千亿](#item-finance-news-4) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Google 拟开放 Workspace MCP，Gmail 发信限制存疑](https://techstackups.com/articles/google-workspace-ai-agents-mcp/) ⭐️ 7.0/10

据报道，Google 计划让 AI 代理通过其 MCP 服务器访问 Workspace 能力，但文章所称“Gmail 的 MCP 服务器不能发送邮件”并未得到一致确认。评论中有读者称 Gmail API 已支持发送邮件，认为相关限制可能是合作伙伴策略而非安全必需；也有人指出，即便没有官方发送工具，代理仍可操作浏览器完成发信。目前可确认的细节仅限于报道标题和社区讨论，Google 的具体上线范围、时间表和限制条件仍不明确。

hackernews · ritzaco · 11月26日 09:44 · [社区讨论](https://news.ycombinator.com/item?id=50653477)

**「背景」** MCP（Model Context Protocol）是一个开放协议，用于让 AI 应用以标准化方式连接外部数据源和工具；Google 近期推出的 Workspace MCP 服务器即基于该标准，覆盖 Gmail、Drive、Docs、Sheets、Slides、Calendar、Chat 和 Tasks 等服务。这些服务器让 AI agent 既能读取数据，也能执行创建草稿邮件、上传文件、安排会议等操作，并继承用户权限；对于发送邮件、修改共享日历事件、共享或删除文件等敏感操作，Google 采用由服务器驱动的 MCP 表单 elicitation 进行人工确认。

**「影响」** 对希望让代理自动发信的开发者来说，如果 Gmail 发送工具只向合作伙伴开放，他们就得改用 Gmail API 或让代理操作浏览器；前者受 API 权限和条款约束，后者更易出错且成本更高。

**「社区讨论」** 评论的焦点是 Gmail 发送限制是否真有必要：perdy 指出 MCP 的 elicitation 可在工具调用前暂停并要求用户确认，因此把发送工具设为合作伙伴专属更像商业决策。bugthe0ry 则称 Gmail API 现已支持发送，暗示文章信息可能已过时；Schnitz 认为开发者会转而用浏览器自动化绕过限制。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://developers.google.com/workspace/gmail/api/guides/configure-mcp-server">Configure the Gmail MCP server | Google for Developers</a></li>
<li><a href="https://developers.google.com/workspace/guides/configure-mcp-servers">Configure the Google Workspace MCP servers</a></li>
<li><a href="https://workspaceupdates.googleblog.com/2026/11/mcp-servers-cli-standardized-usage-tiers-now-available.html">Google Workspace Updates: Simplifying agent access while ...</a></li>

</ul>
</details>

**标签**: `#MCP`, `#Google Workspace`, `#AI agents`, `#Gmail API`, `#developer platforms`

---

<a id="item-tech-news-2"></a>
### [智谱、月之暗面新模型或因反蒸馏与算力限制延期](https://www.reuters.com/world/china/us-chip-curbs-distillation-crackdown-threaten-chinese-ai-model-development-2026-11-26/) ⭐️ 7.0/10

路透社报道，受反蒸馏防护措施趋严和算力限制等因素影响，智谱原计划本月发布的约 3 万亿参数旗舰模型 GLM-5.5 可能推迟至 2027 年第一季度或更晚；月之暗面下一代旗舰 Kimi K4 内部预计或推迟至 2027 年年中。报道还称，若完全失去海外算力，月之暗面重大版本发布间隔会从 6 个月拉长到一年以上，且 Anthropic 与 OpenAI 的反蒸馏措施增加训练数据获取难度，该公司已转向蒸馏谷歌和 Meta 的模型。智谱方面通过网传朋友圈截图否认相关说法，这些延期判断目前来自知情人士和内部预计，并非两家公司正式公告。

telegram · zaihuapd · 11月26日 15:14

**「背景」** 知识蒸馏是指用能力更强的模型产出的数据来训练另一个模型，从而以更低成本逼近其表现；正因如此，前沿实验室有动力限制别人批量获取自己的模型输出。据路透社报道，Anthropic 与 OpenAI 已加强反蒸馏措施，使中国实验室获取训练数据更困难；与此同时，美国对华高端芯片出口管制又限制了可用的算力。这两项约束叠加，构成了智谱和月之暗面调整新模型发布节奏的直接背景。

**「影响」** 对计划基于 GLM-5.5 或 Kimi K4 安排产品集成和算力预算的团队而言，当前只能把发布时间视为不确定项，并准备替代模型或延后上线方案。

**标签**: `#Chinese AI labs`, `#model release delays`, `#export controls`, `#knowledge distillation`, `#AI industry`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [谁有权判定内容是否由 AI 写成？](https://seangoedecke.com/who-gets-to-decide-if-something-is-written-by-ai/) ⭐️ 5.0/10

rss · Sean Goedecke · 11月27日 00:00

**「背景」** 围绕一篇作品是否由 AI 写成，几乎每天都有争议：获奖小说被指 AI 生成、作者因手稿被 Pangram 标红而失去合同、推文真伪也常被争论。作者认为，检测工具可靠性和检测伦理只是表层，真正冲突在于“谁有权判定”。

**「方案」** 作者把反 AI 者对 Pangram 的反感解释为权力问题：判定权意味着能否获奖、通过课程、进入公共讨论。反 AI 者不信任工具化方案也并非无理，因为 Pangram 属于他们所警惕的科技行业，而过去几十年社会本就从社区式判断转向由软件和流程裁决。作者的立场是，工具检测虽有缺陷，但在作者看来，唯一现实替代是社区自我监管；而非 AI 使用者往往不熟悉 AI 文本特征，容易把长而礼貌的推文误判为 AI，也会漏掉明显的 AI 痕迹。因此，若真想挡住 AI 内容，就应使用最强工具，或推动开源、政府自建检测平台，而不是把判定交给不可靠的群体直觉。

**「启示」** 作者的结论是，AI 检测之争本质上是治理权之争：问题不在于检测工具是否完美，而在于由谁掌握判定资格。拒绝工具、退回社区裁决，在他看来只会让更多 AI 生成内容留在文学、教育和公共话语中。

**标签**: `#AI detection`, `#AI-generated content`, `#sociotechnical systems`, `#content moderation`, `#power and governance`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [德银分析：2026 年首季全球芯片出口额首次超过油气](https://www.cnbc.com/2026/11/26/semiconductor-chips-are-the-new-oil-heres-why.html) ⭐️ 8.0/10

德意志银行基于国际贸易中心数据的分析显示，2026 年第一季度全球半导体出口额首次超过石油和天然气，按滚动四季度计算约为 1.61 万亿美元，后者为 1.53 万亿美元。

rss · CNBC Finance · 11月26日 17:52

**「背景」** 这一变化发生在 AI 数据中心建设推高芯片需求之际；德银称，伊朗战争后霍尔木兹海峡石油供应受扰也拉大了差距，美国能源信息署数据显示该海峡第二季度日均石油流量从 2025 年第四季度的 2160 万桶降至 490 万桶，降幅近 77%。

**标签**: `#semiconductors`, `#global trade`, `#AI investment`, `#market volatility`, `#macro-financial flows`

---

<a id="item-finance-news-2"></a>
### [国常会提出加力发挥“国家队”稳市作用，优化中央汇金类“平准基金”功能](https://www.tmtpost.com/nictation/8220182.html) ⭐️ 8.0/10

11 月 27 日，国务院总理李强主持召开国务院常务会议，会议提出加力发挥“国家队”稳市作用，进一步优化中央汇金公司的类“平准基金”功能，并提供充足流动性保障。会议还要求推动上市公司加大分红回购力度，完善保险、企业年金、社保基金等中长期资金入市的引导支持政策；不过，会议未披露具体规模、时间表或实施细则。

telegram · zaihuapd · 11月27日 05:35

**「背景」** 中央汇金公司曾于 4 月 7 日公告再次增持交易型开放式指数基金（ETF），并表示将继续增持以维护资本市场平稳运行，这类以买入提供流动性、托底市场的操作，正是会议所称的类“平准基金”功能。

**「影响」** 如果相关政策落地，上市公司将面对更明确的分红与回购要求，其现金分配和股东回报会随之受到影响；保险、企业年金和社保基金等机构投资者的权益资产配置空间，则取决于中长期资金入市支持政策的具体安排。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.jfdaily.com/wx/detail.do?id=889783">“ 稳 市 ”28小时！ 发生了什么</a></li>

</ul>
</details>

**标签**: `#China capital markets`, `#State Council policy`, `#Central Huijin`, `#market stabilization`, `#long-term funds`

---

<a id="item-finance-news-3"></a>
### [荷兰大臣称不接受美国限制 ASML 对华销售的法案](https://www.bloomberg.com/news/articles/2026-11-26/netherlands-plans-to-fight-rollout-of-proposed-us-curbs-on-asml) ⭐️ 7.0/10

荷兰外贸与发展合作大臣 Sjoerd Sjoerdsma 11 月 26 日在议会表示，荷兰不会接受美国拟议中的 MATCH Act 进一步限制 ASML 对华销售，并反对该法案的域外管辖效力。该两党法案要求荷兰、日本等盟友收紧对华出口管制，否则美方将单方面限制其半导体设备；中国约占 ASML 今年销售额的 20%，美国国会预计 12 月中旬表决。

telegram · zaihuapd · 11月26日 14:56

**「背景」** MATCH Act 由美国两党议员提出，要求荷兰、日本等盟友收紧对华半导体设备出口，否则美方将单方面限制；支持者认为现有管制存在漏洞，中国厂商正用较旧的 DUV 设备通过多重曝光逼近 EUV 的效果。Sjoerdsma 此前已在访美期间会见美国商务部长 Lutnick，并向多名国会议员说明荷兰的关切。

**「影响」** 若该法案通过，ASML 约 20% 的对华销售将直接受美国单边限制约束，荷兰半导体设备行业及配合美国出口管制的盟友企业也会受到影响。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://calgarytribune.com/asml-and-netherlands-lobby-us-congress-to-drop-match-act-curbs/">ASML and Netherlands Lobby US Congress to Drop MATCH Act Curbs</a></li>
<li><a href="https://stereoeffect.net/diplomatic-collision-the-netherlands-challenges-u-s-semiconductor-restrictions-in-high-stakes-lobbying-effort/">Diplomatic Collision: The Netherlands Challenges U.S. Semiconductor...</a></li>

</ul>
</details>

**标签**: `#export controls`, `#semiconductors`, `#ASML`, `#Netherlands`, `#US-China tech policy`

---

<a id="item-finance-news-4"></a>
### [蜜雪冰城 5 亿元入股 DeepSeek 报道称新一轮融资约千亿](https://m.sohu.com/a/1107027659_115479) ⭐️ 7.0/10

据搜狐网一篇报道，DeepSeek 已完成第二轮融资，募资额约 1000 亿至 1055 亿元人民币、投后估值约 6155 亿元，新增 31 家出资人，其中蜜雪冰城股份有限公司认缴 5 亿元。报道未说明这些数字是否经 DeepSeek 或蜜雪方面确认。

telegram · zaihuapd · 11月27日 06:33

**「背景」** 据 IT 之家援引《The Information》，DeepSeek 已在今年 6 月完成约 510 亿元人民币的首轮融资；观察者网援引企查查信息称，本轮 1055 亿元的募资规模刷新了中国 AI 行业单轮融资纪录。此前已参投的砺思资本本轮继续通过旗下天津砺思星深基金获得份额，蜜雪的 5 亿元即经由该基金投入。

**「影响」** 按报道所述，蜜雪的 5 亿元是通过砺思资本管理的天津砺思星深基金投入，属间接出资而非直接持股，因此这家茶饮连锁对 DeepSeek 的敞口取决于该基金的安排。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.ithome.com/1/020/251.htm">曝 DeepSeek 第二轮 融 资 1055 亿 元 ： 估 值 6155 亿 元 ， vivo ...</a></li>
<li><a href="https://www.guancha.cn/CaiJing/2026_11_19_909123.shtml">31 名股东排队参 投 ， DeepSeek 最新 估 值 超6000 亿</a></li>
<li><a href="https://www.cls.cn/detail/2525279">75.2 亿 元 、40名LP， 砺 思 又拿到了 DeepSeek 投 资 份额</a></li>

</ul>
</details>

**标签**: `#DeepSeek`, `#financing round`, `#AI investment`, `#Mixue`, `#China tech`

---