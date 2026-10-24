---
name: BW Process Recap
id: bw-process-recap
description: Use when a multi-step AI collaboration just finished (or the user says 复盘/总结验证/交叉验证回流/Process Recap): distill the dialogue into a portable Word/Feishu-ready article that records goal shifts, granularity misalignments, user corrections, and reusable checklists—especially mistakes most people would also make.
---

# BW Process Recap（bw-process-recap）

## Purpose
Turn a finished, step-by-step human–AI collaboration into a **reusable process article** (Word / Feishu / Markdown). The article must preserve **cross-validation** and **feedback loops**, and must highlight moments where expectations or **granularity** were misaligned and the human corrected the AI—because those corrections are the highest-leverage teaching material (often mistakes ~90% of learners also make).

This skill is **tool-agnostic**. Run it the same way in Claude, ChatGPT, Gemini, 千问, Work Buddy, Codex, Grok Bot, etc.

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

## Inputs to gather (ask only if missing)
If still in the same chat and the transcript is available, **infer from the conversation**; only ask for gaps:
- Final deliverable link or summary (what “done” looks like)
- Preferred output channel: Feishu Doc / Word (.docx) / Markdown (default Markdown if unspecified)
- Audience: self / community / team / other AI tools
- Language: default **简体中文** unless the thread was mostly English
- Whether to anonymize third parties or keep concrete examples

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

Group rules under: Goal · Granularity · Data/Evidence · Format/Delivery · Safety/Compliance · Tooling.

### Step 3 — Write the Process Recap article
Produce one article with this fixed skeleton (headings may be localized; order must stay):

1. **标题** — `BW Process Recap｜{项目一句话}`
2. **一句话结论** — what shipped + why the path mattered
3. **任务目标（对齐前后）** — initial vs final; what changed
4. **关键路径时间线** — 5–12 beats, each: 发生了什么 → 当时默认假设 → 如何被验证/推翻
5. **交叉验证清单** — what was double-checked, against what, result
6. **回流反馈与纠错点（核心）** — table or numbered list:
   - 不对齐类型（目标 / 颗粒度 / 格式 / 证据 / 边界）
   - 我（或典型用户）当时怎么说的
   - AI 当时错在哪
   - 纠正后的新规则
   - 可迁移到其他工具的提示词补丁（1–3 句）
7. **可复用 SOP** — step list another person/AI can run cold
8. **常见错误 Top N** — derived from this thread; phrase as “90% 的人也会…”
9. **交付物索引** — links, files, field schemas, skill names
10. **下次开场白（可复制）** — a short prompt block to paste into any AI to restart this class of work with the learned rules already loaded

Tone: clear teacher-practitioner; no hype; no tool worship; no fake humility essays.

Length: enough to teach (usually 1500–4000 汉字 for a single project). Expand only if the thread was long and multi-phase.

### Step 4 — Deliver in the requested format
- **Markdown**: return full article in chat + saveable `.md` when the environment allows files
- **Feishu**: create a cloud doc under the user’s account when Feishu/Lark tooling is available; return the URL
- **Word**: produce `.docx` when doc tooling is available; otherwise provide clean Markdown and note Word conversion path
- Always include a **portable Skill/Instruction block** (see below) the user can paste into other products

### Step 5 — Offer (do not auto-start) optional follow-ups
One sentence only: publish to community / turn rules into a standing skill / run the SOP on the next domain. Wait for yes.

## Portable block to append at the end of every Recap
Always append a fenced section the user can copy into other AIs:

```text
[BW Process Recap — Standing Rules from this project]
- Goal:
- Must / Must-not:
- Granularity:
- Validation checks before “done”:
- Delivery format:
- Safety / compliance:
Use these rules for the next similar task. If conflicted, ask before proceeding.
```

## Quality bar (done means)
- [ ] Article reflects **this** dialogue (no generic filler)
- [ ] At least one **granularity** or **goal-mismatch** correction is explicit if any occurred
- [ ] Cross-validation actions are listed, not just “we were careful”
- [ ] Rules are actionable in another tool without this chat’s context
- [ ] Deliverable format matches user request
- [ ] No secrets (cookies, tokens, private credentials) in the article

## Anti-patterns
- Rewriting history to make the AI look right the first time
- Turning the recap into a product pitch for a model vendor
- Dumping the raw transcript without synthesis
- Skipping user corrections because they feel “informal” or oral
- Inventing metrics, quotes, or links not present in the thread

## One-line invoke (any tool)
把上面这段对话，按 BW Process Recap（交叉验证 + 回流反馈）整理成一篇可发社群的复盘文章；重点写目标和颗粒度没对齐时我纠正你的地方，以及纠正后沉淀的规则；输出飞书文档 / Word / Markdown（按我指定）。
