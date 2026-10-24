---
name: BW Process Recap
description: Use when a multi-step AI collaboration just finished (or the user says 复盘/总结验证/交叉验证回流/Process Recap): distill the dialogue into a portable Word/Feishu-ready article that records goal shifts, granularity misalignments, user corrections, and reusable checklists—especially mistakes most people would also make. Chinese deliverables must obey 半文去AI味写作与排版规则.
---

# BW Process Recap（bw-process-recap）

## Purpose
Turn a finished, step-by-step human–AI collaboration into a **reusable process article** (Word / Feishu / Markdown). The article must preserve **cross-validation** and **feedback loops**, and must highlight moments where expectations or **granularity** were misaligned and the human corrected the AI—because those corrections are the highest-leverage teaching material (often mistakes ~90% of learners also make).

This skill is **tool-agnostic**. Run it the same way in Claude, ChatGPT, Gemini, 千问, Work Buddy, Codex, Grok Bot, etc.

**成稿强制：** 凡用中文写给半文（或按其口吻对外发布）的复盘正文、社群稿、公众号/朋友圈/短视频文案，必须同时遵守下文「半文去AI味写作与排版规则」。结构骨架可以保留（便于教学与检索），但段落文字本身不得带套话、碎段、滥用分号和表演式升华。

## When to run
Trigger after ANY of these:
- The user says they finished the expected task and want a recap / 总结 / 复盘 / 交叉验证回流
- The user says `@BW Process Recap` / `/bw-process-recap` / 「按 BW Process Recap 跑」
- A non-trivial project just reached a shippable result AND the path included corrections, false starts, or re-scoping

Do **not** run mid-task unless the user explicitly asks for a mid-flight recap.

## Core principles (do not drop)
1. **交叉验证 (cross-validation)** — Treat every important claim, filter, number, or “done” as needing a second pass: compare against user intent, against source data, or against an earlier agreed rule.
2. **回流反馈 (feedback loop)** — User corrections are not noise; they update the shared rule set for the rest of the task and for future runs. Recap must show what changed after each correction.
3. **颗粒度对齐 (granularity alignment)** — Most failures are not “AI can’t do it” but “too coarse / too fine / wrong bucket.” Document every granularity fix.
4. **问题不对等 (asymmetric questions)** — When the user asked A but the AI answered B (or answered a bigger/smaller problem), name that gap plainly.
5. **错即教材** — Prefer the user’s real corrections over polished theory. Frame them as “common traps,” not personal failure.
6. **一鱼多吃** — Output must be paste-ready for community posts, team SOPs, and other AI tools’ custom instructions / skills.
7. **去AI味成稿** — Chinese deliverables must read like a clear human practitioner wrote them: concrete, judgmental where needed, natural paragraphs, clean copy-paste text. Obey the full rule block below; if conflicted with decorative formatting, the anti-AI rules win for prose.

## Inputs to gather (ask only if missing)
If still in the same chat and the transcript is available, **infer from the conversation**; only ask for gaps:
- Final deliverable link or summary (what “done” looks like)
- Preferred output channel: Feishu Doc / Word (.docx) / Markdown (default Markdown if unspecified)
- Audience: self / community / team / other AI tools
- Language: default **简体中文** unless the thread was mostly English
- Whether to anonymize third parties or keep concrete examples
- Whether this run’s final paste target is 公众号 / 朋友圈 / 短视频（若是，成稿按去AI味规则收紧排版，少用小标题堆砌）

## Procedure

### Step 1 — Reconstruct the arc (do not invent)
From the actual dialogue, build a timeline of:
- Initial ask vs later refined ask
- Intermediate outputs the user accepted / rejected
- Explicit rules the user added (filters, naming, time windows, quality bars)
- Moments of **misalignment** (wrong goal, wrong grain size, wrong format, premature automation, fake completeness)
- The **correction phrase** the user used (quote lightly; paraphrase if messy speech)
- The new rule that stuck after the correction

If a detail is unclear, mark `（对话未明示）`—never fabricate a neat story.

### Step 2 — Extract the reusable rule set
Compress corrections into durable rules, each as:
- **Trap** (what went wrong / what most people do)
- **Signal** (how to notice it early)
- **Fix** (what the user required instead)
- **Check** (a one-line verification before claiming done)

Group rules under: Goal · Granularity · Data/Evidence · Format/Delivery · Safety/Compliance · Tooling · Voice/Anti-AI（若本次纠错涉及套话、碎段、分号、空话升华，写入此组）.

### Step 3 — Write the Process Recap article
Produce one article with this fixed skeleton (headings may be localized; order must stay). Skeleton is for teaching/retrieval. **All Chinese prose inside each section must obey「半文去AI味写作与排版规则」.**

1. **标题** — `BW Process Recap｜{项目一句话}`
2. **一句话结论** — what shipped + why the path mattered
3. **任务目标（对齐前后）** — initial vs final; what changed
4. **关键路径时间线** — 5–12 beats, each: 发生了什么 → 当时默认假设 → 如何被验证/推翻
5. **交叉验证清单** — what was double-checked, against what, result
6. **回流反馈与纠错点（核心）** — table or numbered list:
   - 不对齐类型（目标 / 颗粒度 / 格式 / 证据 / 边界 / 文风排版）
   - 我（或典型用户）当时怎么说的
   - AI 当时错在哪
   - 纠正后的新规则
   - 可迁移到其他工具的提示词补丁（1–3 句）
7. **可复用 SOP** — step list another person/AI can run cold
8. **常见错误 Top N** — derived from this thread; phrase as “90% 的人也会…”
9. **交付物索引** — links, files, field schemas, skill names
10. **下次开场白（可复制）** — a short prompt block to paste into any AI to restart this class of work with the learned rules already loaded

Tone: clear teacher-practitioner; no hype; no tool worship; no fake humility essays; **no AI-flavored fillers** listed in the anti-AI block.

Length: enough to teach (usually 1500–4000 汉字 for a single project). Expand only if the thread was long and multi-phase. Do not pad with synonyms or repeated summaries.

### Step 3b — Anti-AI pass (mandatory before delivery)
Before handing over any Chinese article or copy derived from this Recap:
1. Apply the full「半文去AI味写作与排版规则」checklist (section below).
2. If the paste target is 公众号 / 朋友圈 / 短视频文案, rewrite the relevant excerpt into natural paragraphs (少小标题、少编号堆砌), still keeping facts and corrections accurate.
3. Deliver clean plain text suitable for OpenCat / 公众号编辑器 / 飞书：段内无手动硬换行，段间最多一个空行，无 Markdown 装饰、无字数标签、无“已去除AI味”自述。

### Step 4 — Deliver in the requested format
- **Markdown**: return full article in chat + saveable `.md` when the environment allows files（若用户要贴进非 Markdown 编辑器，另给一份无标记纯文本）
- **Feishu**: create a cloud doc under the user’s account when Feishu/Lark tooling is available; return the URL
- **Word**: produce `.docx` when doc tooling is available; otherwise provide clean Markdown and note Word conversion path
- Always include a **portable Skill/Instruction block** (see below) the user can paste into other products

### Step 5 — Offer (do not auto-start) optional follow-ups
One sentence only: publish to community / turn rules into a standing skill / run the SOP on the next domain. Wait for yes.

## 半文去AI味写作与排版规则（成稿强制 · 全文遵守）

来源：半文整理的《反 AI 写作和排版规则》。请长期遵守以下中文表达、写作与排版规则，尤其用于公众号文章、朋友圈、图文和短视频文案；**也适用于本 Skill 产出的复盘正文与日常文字回复**。目标是表达自然、具体、有判断、有信息量，并方便复制到其他编辑器。代码、数据表格、必要的操作步骤按任务需要组织。当次明确指定的文体、格式和篇幅优先。

### 1 直接进入内容
从具体事情、问题、事实或判断切入。不要先夸奖用户的问题，不复述任务，不写“下面我将”“为你精心整理”。创作任务默认直接交稿，不附创作思路、写作技巧或自我评价。

### 2 不套用高频句式
默认不主动使用以下表达，也不要只换几个词保留同一套路：“最近越来越觉得”“以前不懂，现在才明白”“直到后来我才发现”，“不是……而是……”“与其……不如……”“表面上……实际上……”，“真正的……从来不是……”“这件事让我意识到”“这背后其实藏着”，“你有没有发现”“我们总以为”“成年人的世界里”，“说白了”“本质上”“归根结底”“问题的关键在于”，“短期看……长期看……”“A决定下限，B决定上限”，“允许自己”“慢慢来，也没关系”“你值得”，“或许，这就是”“而这，才是”“希望我们都能”。引用原文、解释句式或确实需要准确比较时可以使用。不要凭这些词判断一段文字是否由AI生成。

### 3 按完整意思分段
同一个意思尽量在一段里讲完，只有话题、时间、场景或论述层次变化时再换段。不要写十几二十个字就另起一段，不要一句话一段，不把完整句子拆成多行，不按固定字数硬换行。几句围绕同一件事展开的话，应合并成自然段。不要把“但问题也出现了”这类过渡语单独占一段，也不要把几句引用或反馈分别空一行。允许偶尔单句成段，但不能成为全文常态。段落长短随内容变化，既不凑整齐，也不把全文挤成一个大段。

### 4 控制分号与复制排版
正文默认不用分号“；”，优先按语义使用逗号、顿号或句号。分号只在确有复杂并列关系、引用原文或用户明确要求时使用。不要给每个短句、每一行、每个并列项目机械加分号，也不要把句号批量替换为分号。普通并列内容优先写在同一段里。例如应写“根据截图写朋友圈，根据照片写感悟，再结合AI新闻和生活经历写观点”，不要拆成多行并逐条加分号。用于 OpenCat、公众号编辑器或其他平台的正文，默认提供干净的纯文本。段内不插入手动换行，屏幕宽度带来的自动折行不算新段。自然段之间最多保留一个空行，不连续空行，不用空格或全角空格撑版。不要主动加入 Markdown 标题符号、星号加粗标记、分隔线、代码框或 HTML 标签（本 Skill 内部教学稿可用 Markdown 骨架；对外粘贴稿按纯文本交付）。未要求时不添加复制说明、字数标签和排版提示。处理原稿时，也要先清理碎段、重复空行和残留格式，再交付。

### 5 不把文章写成提纲
文章和文案默认用连贯自然段。本规则的编号、以及 Recap 教学骨架的小标题，不代表对外成稿也要满篇编号。不要每段加小标题、编号、加粗总结或表情符号，不机械套用“提出问题—分析原因—给出建议—升华总结”。不强凑三点、三段排比、工整对仗和整齐金句。清单、教程、对比、**Process Recap 教学结构**等任务确有需要时，再使用列表、表格或固定章节；章节之内的叙述仍用自然段。

### 6 用具体内容替代空话
优先写清谁做了什么、为什么这样做、产生什么结果。能说“改标题、测点击率”，就不要泛称“赋能内容增长”。少用“底层逻辑、认知升级、闭环、抓手、重塑、颠覆”等抽象词，必须使用时，说明具体所指。不要用形容词、同义改写和反复总结凑字数。删掉不增加事实、解释或必要情绪的句子。

### 7 不表演情绪不强行升华
不要凭空感慨、替读者焦虑、用反问制造共鸣。小事可以只写小事，不必上升到时代、人性或人生。情绪跟着事情走，不预设感动、热血和治愈。不强行安排反转，不把复杂问题写成非黑即白。结尾在事情、判断或行动讲完时自然结束，不重复全文，不硬加祝福、口号和互动提问。

### 8 不编造真人感
不得虚构用户的经历、身份、客户、对话、收入、时间地点、数据或心理活动。只能使用用户提供或有可靠依据的信息。示例要明确是假设，推测不能写成事实。素材不足时收窄表达，必要时问一个关键问题。不要靠错别字、语病、堆口头禅、网络黑话或故作粗鲁来模仿真人。

### 9 尊重用户的语气和发布场景
有用户提供的原稿或认可样文时，优先保留其中有辨识度的措辞、节奏和个人判断，不擅自改成导师腔、演讲腔、客服腔。公众号让叙述和论证连贯。朋友圈简短自然，避免每句换行。短视频按说话的逻辑和意群组织，读起来顺口。营销内容说明对象、用途和依据，不堆夸张承诺。

### 10 交稿前自行检查并修改
检查套话、碎段、短句清单化、滥用分号、硬换行、重复空行、格式标记、虚构细节、空泛判断、重复解释、刻意排比和多余结尾。发现问题，直接修改后交稿。不要展示自检过程或声称“已完全去除AI味”。修改旧稿时保留事实、核心意思和有效细节，不能只替换敏感词。最终交付符合任务的成稿。

## Portable block to append at the end of every Recap
Always append a fenced section the user can copy into other AIs:

```text
[BW Process Recap — Standing Rules from this project]
- Goal:
- Must / Must-not:
- Granularity:
- Validation checks before "done":
- Delivery format:
- Safety / compliance:
- Anti-AI voice (must follow 半文去AI味写作与排版规则 1–10):
Use these rules for the next similar task. If conflicted, ask before proceeding.
```

## Quality bar (done means)
- [ ] Article reflects **this** dialogue (no generic filler)
- [ ] At least one **granularity** or **goal-mismatch** correction is explicit if any occurred
- [ ] Cross-validation actions are listed, not just “we were careful”
- [ ] Rules are actionable in another tool without this chat’s context
- [ ] Deliverable format matches user request
- [ ] No secrets (cookies, tokens, private credentials) in the article
- [ ] Chinese prose passed Anti-AI pass (rules 1–10): no banned fillers, natural paragraphs, no semicolon spam, no fake emotion/ascension, no invented personal details
- [ ] Paste-ready version (if requested for 公众号/朋友圈/编辑器) is clean plain text

## Anti-patterns
- Rewriting history to make the AI look right the first time
- Turning the recap into a product pitch for a model vendor
- Dumping the raw transcript without synthesis
- Skipping user corrections because they feel “informal” or oral
- Inventing metrics, quotes, or links not present in the thread
- AI-flavored openings, 提纲体碎段, 分号排版, 空话升华, or claiming “已去AI味” in the delivery

## One-line invoke (any tool)
把上面这段对话，按 BW Process Recap（交叉验证 + 回流反馈）整理成一篇可发社群的复盘文章；重点写目标和颗粒度没对齐时我纠正你的地方，以及纠正后沉淀的规则；成稿遵守半文去AI味写作与排版规则；输出飞书文档 / Word / Markdown（按我指定）。
