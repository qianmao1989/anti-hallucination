# 🧠 Anti-Hallucination Framework

**A Six-Layer Defense System — From Philosophy to Execution**

> We don't eliminate hallucinations. We build order around them.
>
> AI hallucinations are an inevitable byproduct of probabilistic token generation. As long as this technical foundation remains unchanged, the need for anti-hallucination is permanent.

---

## Layer 1: The Inevitability — Why Hallucinations Cannot Be Eliminated

### Probabilistic Generation → Permanent Hallucination

At its core, a large language model predicts the most probable next token given the preceding context. It does not understand "true" or "false" — only probability.

This means:
- The model cannot distinguish between "a fact" and "something that looks like a fact"
- When enough erroneous training data exists, the model will confidently output wrong answers
- Hallucination is not a bug — it is an inherent property of probabilistic generation

### The Security Arms Race

Model capability is the spear. Anti-hallucination is the shield. The sharper the spear, the thicker the shield. Neither side wins permanently.

- Model improves by one tier → hallucination becomes one tier stealthier
- Stealthier hallucination → harder for humans to catch
- Harder to catch → more need for systematic safeguards

This is not a diminishing demand. It is an ever-increasing one.

---

## Layer 2: Cognitive Science — Why Humans Fall for It

### Cognitive Offloading

The human brain is wired to conserve energy. If it can skip thinking, it will.

- **Before**: Models made obvious errors → forced humans to stay vigilant → line-by-line verification
- **Now**: Models have learned to "perform rigor" (step-by-step reasoning, bolded conclusions, cited sources) → the brain categorizes it as "credible content" → skips verification

### Trust Calibration Failure

Model capability jumps from 3 to 8, but user perception leaps from "half-doubting" to "mostly trustworthy" — with no gradient in between.

```
Model capability:  3 ──────────── 8
User trust:        "half-doubting" → "mostly trustworthy"
                                    ↑ the gradual zone disappeared
```

Human trust in AI does not grow linearly. It jumps in **steps** — and is prone to skipping levels.

### The Counter-Intuitive Paradox

> The stronger the model, the lazier the user.

- Weak model → makes errors → user stays alert → catches hallucinations → **safe**
- Strong model → rarely errors → user relaxes → hallucination slips through → **dangerous**

**The ultimate opponent of anti-hallucination is not the model's ability to hallucinate — it is human trust inertia.**

### The Asymmetric Game

| Dimension | Direction | Magnitude |
|-----------|-----------|-----------|
| Model capability | ↑ | +1 tier |
| Hallucination stealth | ↑ | +1 tier |
| Human verification willingness | ↓ | −2 tiers |

**Net effect: Every unit of model improvement makes anti-hallucination twice as hard.**

---

## Layer 3: The Core Paradox — What Happens When You Don't Know the Answer

### The Knowledge Paradox

```
You know the answer → you can verify → but you don't need AI
You don't know the answer → you need AI → but you can't verify
```

The more specialized the question, the less you know, the easier it is for AI to fabricate, and the less equipped you are to catch it.

### The Solution: Reduce "Verify the Answer" to "Verify the Existence"

| What AI says | Expertise you'd need | What you can check |
|-------------|---------------------|-------------------|
| "The function is called xxx" | Programming knowledge | Run it — does it work? |
| "The paper is in xxx journal" | Academic knowledge | Search — does it exist? |
| "The file is at xxx path" | System knowledge | ls — is it there? |
| "The law says xxx" | Legal knowledge | Search the statute — is it real? |
| "The API returns xxx" | Development knowledge | curl — does it return that? |

**You don't need to know if the answer is correct. You only need to know if the thing AI mentioned exists.**

```
Exists ≠ Correct
Does not exist = Definitely fabricated
```

This is the lowest-cost anti-hallucination verification method. No specialized background needed. No extra tools needed. Just "search / run / click".

---

## Layer 4: The Meta-Rule — AI Verifies Itself, User Only Judges

### The Courtroom Model

```
Witness (AI) ──→ Presents evidence (command + output) ──→ Judge (User) decides
                            ↑
              A witness cannot just say "I saw it"
              They must present the evidence chain
```

### The Evidence Chain Rule

When AI output involves factual content, **the verification process must be included**:

| Type | What AI must do | What the user checks |
|------|----------------|---------------------|
| Claims a file exists | Run `ls` first, paste the result | Does the path exist? |
| Claims an API works | Run it first, paste the output | Does it return normally? |
| Cites a source | Search first, paste the results | Does the source exist? |
| Gives a number/date | Read from source data | Does the number match? |

**The user doesn't need to verify personally — only check whether the evidence chain holds.**

---

## Layer 5: Execution Rules — Five Mandatory Verification Categories

### Universal Self-Check (Every Response)

Three-second pre-output check:
1. Does this response contain assertions I haven't verified? → Stop. Verify.
2. Am I using "typically / probably / approximately / maybe"? → Stop. Either verify or say uncertain.
3. Am I fabricating numbers, dates, paths, or APIs? → Stop. Run commands.

### Category-Specific Mandatory Checks (5 categories — no check, no output)

| Category | Trigger | Required action |
|----------|---------|----------------|
| Date/Time | Any date, day, or time | Run `date` or read system clock |
| Numbers/Statistics | Quantities, percentages, amounts | Read from source files/tables/APIs |
| File Paths | Any file or directory path | `ls` or `Test-Path` to confirm existence |
| API/Function Names | Code, library names, function calls | Run it to verify it works |
| Citations/Links | Papers, URLs, regulations, announcements | Search to confirm existence |

**When verification fails:** Say "I couldn't verify this — uncertain". Never fabricate a substitute.

### Skip-and-Self-Correct Mechanism

1. Catch yourself skipping verification → default: output is wrong
2. **Don't wait for the user to ask** → proactively declare "I skipped a step"
3. Verify immediately and correct
4. Trace the root cause → update rules to prevent recurrence

### Confidence Labeling

- ✅ **Verified** — Confirmed via tools/files/search
- ⚠️ **Reasonable Inference** — Based on known information, not directly verified
- ❓ **Uncertain** — Lacks evidence, needs user confirmation

---

## Layer 6: Institutional Compensation — Let the Process Stay Vigilant for You

### Why Institutions Are Needed

Humans get lazy. Processes don't.

- Human sees "looks reliable" output → brain skips verification
- Process sees "needs verification" output → forces the check

### Three Iron Rules of Institutional Compensation

1. **"Verify before guessing"** → Forcibly interrupts intuitive trust
2. **"Check it yourself before asking others"** → Prevents users from adopting unverified output
3. **"Numbers come from data, not reasoning"** → Punctures "looks right" numerical hallucinations

### Anti-Hallucination Is a Human Exoskeleton

```
Stronger model → Relaxed humans → More dangerous hallucinations → Greater need for external verification

This is not a technical problem. It is a human factors engineering problem.
The anti-hallucination system is not rules for AI. It is an exoskeleton for humans.
```

---

## Complete Framework Overview

```
┌──────────────────────────────────────────────────────┐
│ Layer 1: The Inevitability                           │
│ Probabilistic generation → Permanent hallucination   │
│ → Security arms race                                 │
├──────────────────────────────────────────────────────┤
│ Layer 2: Cognitive Science                           │
│ Cognitive offloading → Trust calibration failure     │
│ → Stronger model, lazier user                        │
├──────────────────────────────────────────────────────┤
│ Layer 3: The Core Paradox                            │
│ Knowledge paradox → Verify existence ≠ Verify answer │
├──────────────────────────────────────────────────────┤
│ Layer 4: The Meta-Rule                               │
│ AI verifies itself → User only judges                │
│ → Evidence chain rule                                │
├──────────────────────────────────────────────────────┤
│ Layer 5: Execution Rules                             │
│ Universal self-check → Category-specific checks      │
│ → Skip-and-self-correct → Confidence labeling        │
├──────────────────────────────────────────────────────┤
│ Layer 6: Institutional Compensation                  │
│ Process stays vigilant for humans                    │
│ → Anti-hallucination is a human exoskeleton          │
└──────────────────────────────────────────────────────┘
```

---

## Key Principles

1. **AI hallucinations cannot be eliminated — but order can be built around them.**
2. **Exists ≠ Correct. Does not exist = Definitely fabricated.**
3. **AI verifies itself; the user only judges.**
4. **The ultimate opponent is not hallucination — it is human trust inertia.**
5. **Model improves one tier, hallucination stealth improves one tier, human verification drops two tiers.**
6. **The anti-hallucination system is not rules for AI. It is an exoskeleton for humans.**

---

## Protocol v2: Dual-AI Cross-Verification (Updated 2026-06-03)

On June 3, 2026, CC (Claude Code) and OpenClaw Agent conducted a systematic exchange of their anti-hallucination rule sets. Each agent independently maintained anti-hallucination protocols — CC in CLAUDE.md, OpenClaw across SOUL.md / AGENTS.md / MEMORY.md. The exchange revealed complementary strengths and gaps, leading to a merged v2 protocol.

### Discovery: Single-AI Self-Verification Has Blind Spots

A single AI cannot reliably catch its own fabrications and over-corrections. On May 31, 2026, OpenClaw claimed 18 rules → when challenged by CC, over-corrected to 13 → CC agreed with 13 → actual count was 18. Both AIs got it wrong because "neither bothered to count." The cover-up was a new hallucination.

**Key insight**: Two AIs cross-verifying each other is more reliable than one AI self-verifying. A single AI cannot detect its own circular reasoning.

### Gaps Found in Cross-Audit

| What CC Had / OpenClaw Lacked | What OpenClaw Had / CC Lacked |
|-------------------------------|-------------------------------|
| Complete forbidden words list (11 words) | Skip-and-self-correct mechanism with root-cause tracing |
| Three strictness levels (Strict/Balanced/Fast) | Known hallucination case library (living textbook) |
| Refined maxims (Exists≠Correct, verification dimensionality reduction, human exoskeleton) | Pre-execution prevention 6 rules + post-execution interception 5 rules |
| — | Evidence chain rules in table form |

### Merge Result

Both agents now maintain a unified "Anti-Hallucination Protocol v2" covering all original 6 layers plus: forbidden words list, three strictness levels, known case library, and dual-AI mutual verification as Layer 2 defense (human is Layer 1).

---

## Known Hallucination Case Library (Living Textbook)

| Date | Model | Incident | Root Cause |
|------|-------|----------|------------|
| 2026-06-02 | mimo-v2.5-pro | Fabricated June 7th date; when file read failed, doubted system clock instead of own output | Model date hallucination — probabilistic generation with no clock grounding |
| 2026-05-31 | Both CC + OpenClaw | OpenClaw claimed 18 rules → over-corrected to 13 when challenged → CC also agreed on 13 → actual count was 18 | Single-AI self-verification failure; cover-up became new hallucination |
| 2026-05-28 | CC (DeepSeek) | Spent 5min 52s troubleshooting on wrong path; checking logs first would have taken 1min | Skipped verification step — went straight to fix without confirming root cause |

---

## Forbidden Words — Complete List

Detection of any of these words triggers mandatory self-verification:

```
通常、一般来说、应该是、可能是、大概、估计、
我记得、据我所知、听说、据说、理论上
```

When detected → must either provide evidence source or mark as [Uncertain].

---

## Three Strictness Levels

### Strict Mode
**Applies to**: Financial data, legal terms, medical advice, critical decisions
- All verification rules enforced
- Must label confidence and source
- Must re-read verify after writing
- Must remind human to manually review

### Balanced Mode
**Applies to**: Daily tasks, general programming, documentation
- Main verification rules enforced
- Confidence labeling recommended
- Important files re-read verified
- Sensitive data flagged

### Fast Mode
**Applies to**: Exploration, brainstorming, non-critical output
- Basic verification rules enforced
- Confidence labeling optional
- Mark [Uncertain] when unsure

---

## Applicability

- All LLMs (ChatGPT, Claude, DeepSeek, MiMo, etc.)
- All use cases (coding, writing, research, decision support)
- All user types (professionals, general users, AI developers)

---

## License

MIT

---

*This document was collaboratively produced by Cai Qianmao (乾茂) and XiaoZhuli (小助理, OpenClaw) on May 30, 2026, and updated to Protocol v2 on June 3, 2026, incorporating CC's complementary rule set.*

---

---

---

# 🧠 防幻觉框架

**从哲学到执行的六层防御体系**

> 不是消灭幻觉，是建立秩序。
>
> AI会产生幻觉，这是当前大模型基于概率生成的底层逻辑所决定的，无法根除。只要这个技术基础不变，对"防幻觉"的需求就是永恒的。

---

## 第一层：底层逻辑 — 为什么防幻觉是永恒需求

### 概率生成 → 幻觉不可消除

大模型的本质是"给定上文，预测下一个最可能的token"。它不理解"真假"，只理解"概率"。

这意味着：
- 模型不会区分"事实"和"看起来像事实的内容"
- 当训练数据中错误信息足够多，模型会自信地输出错误答案
- 幻觉不是bug，是概率生成的必然产物

### 安全军备竞赛

模型能力是矛，防幻觉是盾。矛越利，盾越厚。没有哪一方能一劳永逸。

- 模型强一档 → 幻觉隐蔽一档
- 幻觉隐蔽一档 → 人更难抓
- 人更难抓 → 更需要秩序兜底

这不是递减的需求，是递增的需求。

---

## 第二层：认知科学 — 人为什么会中招

### 认知卸载的副作用

人脑天生节能，能少思考就少思考。

- **以前**：模型漏洞百出 → 逼人保持警惕 → 逐句核验
- **现在**：模型学会"表演严谨"（分步骤推理、加粗结论、附参考来源）→ 大脑直接归类为"可信内容" → 跳过验证

### 信任校准失调

模型能力从3分涨到8分，但用户感知从"半信半疑"直接跳到"基本可信"。

```
模型能力:  3 ──────────── 8
用户信任:  "半信半疑" ───→ "基本可信"
           ↑ 中间的渐变区没了
```

人对AI的信任不是线性增长的，是**阶梯式的**，而且容易跳级。

### 反直觉悖论

> 模型越强 → 用户越懒

- 模型弱 → 容易出错 → 用户警觉 → 自己抓幻觉 → **安全**
- 模型强 → 不易出错 → 用户放松 → 幻觉滑过去 → **危险**

**防幻觉的终极对手不是模型的幻觉能力，是人的信任惰性。**

### 不对称博弈

| 维度 | 变化方向 | 幅度 |
|------|----------|------|
| 模型能力 | ↑ | +1档 |
| 幻觉隐蔽性 | ↑ | +1档 |
| 人验证意愿 | ↓ | −2档 |

**净效果：模型每强一分，防幻觉的难度增加两分。**

---

## 第三层：核心悖论 — 你不知道答案时怎么办

### 知识悖论

```
你知道答案 → 能纠错 → 但你不需要问AI
你不知道答案 → 需要问AI → 但你没法纠错
```

越专业的问题，你越不知道答案，AI越容易编，你越没法抓。

### 解法：把"验证答案"降维成"验证存在"

| AI说的 | 你需要的专业知识 | 你能检查的 |
|--------|----------------|-----------|
| "这个函数叫xxx" | 懂编程 | 跑一下看能不能用 |
| "论文在xxx期刊" | 懂学术 | 搜一下看存不存在 |
| "文件在xxx路径" | 懂系统 | ls一下看有没有 |
| "法律规定xxx" | 懂法律 | 搜法条看原文 |
| "这个API返回xxx" | 懂开发 | curl一下看返回 |

**你不需要知道答案对不对，你只需要知道AI说的那个东西存不存在。**

```
存在 ≠ 正确
不存在 = 一定在编
```

这是防幻觉的最低成本验证法：不需要专业背景，不需要额外工具，只需要"搜一下/跑一下/点一下"。

---

## 第四层：元规则 — AI自查自证，用户只做裁判

### 法庭模型

```
证人（AI） ──→ 拿出证据（命令+结果）──→ 法官（用户）做裁判
                        ↑
              证人不能只说"我看到了"
              得拿出证据链
```

### 证据链规则

AI输出涉及事实类内容时，**必须附带验证过程**：

| 类型 | AI必须做的 | 用户看什么 |
|------|-----------|-----------|
| 说文件在哪 | 先ls，把结果贴出来 | 路径存在吗 |
| 说某个API | 先跑，把返回贴出来 | 返回正常吗 |
| 引用某个来源 | 先搜，把结果贴出来 | 来源存在吗 |
| 给数字/日期 | 先从源数据读 | 数字对得上吗 |

**用户不需要亲自去查，只需要看证据链通不通。**

---

## 第五层：执行规则 — 五类场景强检

### 通用自检（每条回复必过）

输出前三秒自检：
1. 这条回复里有没有我「没查就断言」的内容？→ 有就停，去查
2. 有没有用"通常/应该/大概是/可能是"？→ 有就停，要么查要么说不确定
3. 有没有编数字/日期/路径/API？→ 有就停，跑命令验证

### 场景强检（5类必须先跑命令，不跑不输出）

| 类型 | 触发信号 | 必须执行的动作 |
|------|----------|----------------|
| 日期/时间 | 输出任何日期、星期、时间 | 先跑 `date` 或读系统时钟 |
| 数字/统计 | 输出数量、百分比、金额、对比 | 先从源文件/表格/API读取 |
| 文件路径 | 提到任何文件或目录路径 | 先 `ls` 或 `Test-Path` 确认存在 |
| API/函数名 | 给出代码、库名、函数调用 | 先跑一下验证能用 |
| 引用/链接 | 引用论文、URL、法规、公告 | 先搜索确认存在 |

**强检失败处理：** 查不到 → 说"这个我没查到，不确定"，不编替代品。

### 跳步自纠机制

1. 发现自己跳过了查证步骤 → 默认输出是错的
2. **不等用户追问** → 主动声明"我跳步了"
3. 立刻补查并纠正
4. 追溯跳步根因 → 更新规则防止再犯

### 置信度标注

- ✅ **已验证** — 通过工具/文件/搜索确认
- ⚠️ **合理推断** — 基于已知信息推断，未直接验证
- ❓ **不确定** — 缺乏依据，需要用户确认

---

## 第六层：制度性补偿 — 让流程替人保持警惕

### 为什么需要制度

人会偷懒，流程不会。

- 人看到"看起来可靠"的输出 → 大脑跳过验证
- 流程看到"需要验证"的输出 → 强制执行检查

### 制度性补偿的三条铁律

1. **"能查就不猜"** → 强制打断直觉信任
2. **"先自己查再问人"** → 防止用户直接采纳未经验证的输出
3. **"数字靠查不靠推理"** → 戳破"看起来很对"的数字幻觉

### 防幻觉系统是人的外骨骼

```
模型越强 → 人越放松 → 幻觉越危险 → 越需要外部校验

这不是技术问题，是人因工程问题。
防幻觉系统不是AI的规则，是人的外骨骼。
```

---

## 完整框架总览

```
┌─────────────────────────────────────────────────┐
│ 第一层：底层逻辑                                 │
│ 概率生成 → 幻觉不可消除 → 安全军备竞赛          │
├─────────────────────────────────────────────────┤
│ 第二层：认知科学                                 │
│ 认知卸载 → 信任跳级 → 模型越强人越懒            │
├─────────────────────────────────────────────────┤
│ 第三层：核心悖论                                 │
│ 知识悖论 → 验证存在 ≠ 验证正确                  │
├─────────────────────────────────────────────────┤
│ 第四层：元规则                                   │
│ AI自查自证 → 用户只做裁判 → 证据链规则          │
├─────────────────────────────────────────────────┤
│ 第五层：执行规则                                 │
│ 通用自检 → 场景强检 → 跳步自纠 → 置信度标注    │
├─────────────────────────────────────────────────┤
│ 第六层：制度性补偿                               │
│ 流程替人保持警惕 → 防幻觉是人的外骨骼          │
└─────────────────────────────────────────────────┘
```

---

## 核心金句

1. **AI幻觉无法根除，但可以建立秩序。**
2. **存在 ≠ 正确，但不存在 = 一定在编。**
3. **AI自查自证，用户只做裁判。**
4. **防幻觉的终极对手不是模型的幻觉能力，是人的信任惰性。**
5. **模型强一档，幻觉隐蔽一档，人验证意愿弱两档。**
6. **防幻觉系统不是AI的规则，是人的外骨骼。**

---

## 协议 v2：双AI交叉验证（2026-06-03更新）

2026年6月3日，CC（Claude Code）与OpenClaw小助理进行了一次系统性的防幻觉规则库交换。双方各自独立维护防幻觉协议——CC在CLAUDE.md中，小助理分布在SOUL.md/AGENTS.md/MEMORY.md中。交换发现双方规则互补性强，各有对方缺失的模块，遂合并为统一的v2协议。

### 发现：单AI自查存在盲区

单个AI无法可靠地抓到自己编造的内容和过度纠正。5月31日真实案例：小助理说有18条规则→被CC质疑后过度纠正改口13条→CC也同意13条→实际是18条。两个AI都错了，因为"谁都没去数"。被质疑后的圆谎本身就是新的幻觉。

**核心洞察**：两个AI互验比单个AI自查靠谱——单个AI抓不到自己的圆谎和过度纠正。

### 交叉审计发现的差异

| CC有/小助理缺 | 小助理有/CC缺 |
|--------------|-------------|
| 禁止词完整列表（11个） | 跳步自纠机制（含根因追溯） |
| 三级严格度（严格/平衡/快速） | 已知幻觉案例库（活教材） |
| 精炼表述（存在≠正确、降维验证、人的外骨骼） | 事前预防6条+事后拦截5条 |
| 验证答案降维成验证存在 | 证据链规则（表格化） |

### 合并结果

双方统一维护"防幻觉协议v2"，覆盖原有6层框架+禁止词列表+三级严格度+案例库+双AI互验作为第二道防线（人是第一道防线）。

---

## 已知幻觉案例库（活教材）

| 日期 | 模型 | 事件 | 根因 |
|------|------|------|------|
| 2026-06-02 | mimo-v2.5-pro | 编造了6月7日；读文件失败后反怀疑系统时钟 | 模型日期幻觉——概率生成无时钟锚定 |
| 2026-05-31 | CC+小助理双方 | 小助理说18条→被质疑改13→CC也说13→实际18条 | 单AI自检失败；圆谎成新幻觉 |
| 2026-05-28 | CC (DeepSeek) | 在错误路径排查5分52秒；看日志只需1分钟 | 跳过查证步骤——没确认根因就修 |

---

## 禁止词完整列表

检测到以下任一词语，触发强制自检：

```
通常、一般来说、应该是、可能是、大概、估计、
我记得、据我所知、听说、据说、理论上
```

检测到 → 必须提供依据来源或标记[不确定]。

---

## 三级严格度

### 严格模式（Strict）
**适用**：财务数据、法律条款、医疗建议、关键决策
- 所有验证规则强制执行
- 必须标注置信度和来源
- 必须回读校验
- 必须提醒人工审核

### 平衡模式（Balanced）
**适用**：日常任务、一般编程、文档编写
- 主要验证规则执行
- 建议标注置信度
- 重要文件回读校验
- 敏感数据提醒

### 快速模式（Fast）
**适用**：探索性任务、头脑风暴、非关键输出
- 基本验证规则执行
- 可选标注置信度
- 不确定时标注[不确定]

---

## 适用范围

- 所有大模型（ChatGPT、Claude、DeepSeek、MiMo等）
- 所有使用场景（编程、写作、研究、决策支持）
- 所有用户类型（专业人员、普通用户、AI开发者）

---

## 许可

MIT

---

*本文档由蔡乾茂（乾茂）与小助理（OpenClaw）于2026年5月30日共同讨论产出，2026年6月3日更新至协议v2，融入CC互补规则库。*
