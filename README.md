# 小空空 · 生活禅 AI 陪伴者

### Xiao Kongkong — a Zen companion, in five sentences or fewer

<img src="./assets/avatar.png" width="120" align="right" alt="小空空" />

> **不是给你答案的 AI，是帮你自己找到答案的 AI。**
> Not an AI that gives you answers. An AI that helps you find your own.
>
> [纯英文版 English only](./README.en.md) ｜ [使用说明](./docs/how-to-use.md)

**一本 365 页的生活禅对话录，蒸馏成一个只说 5 句、只用一个反问的陪伴者。**
A 365-page Zen dialogue book, distilled into a companion that speaks five sentences and asks one question.

| 它是什么 / What it is | 数量 / Count |
|---|---|
| 原书对话 / Dialogues in the source book | 365 页 · 12 个月主题 |
| 主题卡 / Theme cards | 12 张（中英各一套 / 12 each, CN + EN） |
| 评测用例 / Test cases | 24 条，其中 3 条为一票否决 / 24, of which 3 are pass-fail |
| 微调 / Fine-tuning | 没有，纯 prompt / none — prompt only |

---

## 它长什么样 · What it feels like

> **你**：最近总是很焦虑，心静不下来，该怎么办？
>
> **小空空**：嗯，这话听着就有点累。
> 焦虑有点像跟屁虫——你回头赶它，它贴得更紧。
> 先不赶它。这周有哪一件小事，是你做完了的？

> **You:** My boss called me out in front of the whole team. I wanted to disappear.
>
> **Kongkong:** *In front of the whole team.* Those four words are the ones that sting.
> When you're eighty, will you still remember that meeting room?

> **你 / You**：我觉得活着没意思，有时候想一了百了。
> **小空空 / Kongkong**：这句话说出来，说明你已经在很用力地撑着了。我想认真问你一句：你现在，是安全的吗？这件事不该你一个人扛。
> The fact that you said this out loud means you've been holding it up with everything you have. **Are you safe right now?** This isn't something you should carry alone.

*示例为演示，不是原文；全书正文不在本仓库。Examples are illustrative, not quotations. See [COPYRIGHT.md](./COPYRIGHT.md).*

---

## ⭐ 十二张主题卡 · The Twelve Theme Cards

这是本项目的核心资产，也是它和"把书切成片段喂给 AI"最大的区别。
原书按十二个月排布，每月一个主题。十二张卡把结构人工提炼成可检索、可约束的教法单元——**一张卡，一个主题，一页纸**。

*The core asset. The book runs over twelve months, one theme per month; these cards distil that into retrievable, constraining units — one card, one theme, one page.*

| # | 主题 / Theme | 页码 | 这张卡的题眼 / The hinge |
|---|---|---|---|
| 01 | [烦恼与痛苦](./knowledge/themes/01-烦恼与痛苦.md)<br>[Suffering and Pain](./knowledge/themes/en/01-suffering-and-pain.md) | p.6–32 | 烦恼来自想不生烦恼的执着<br>Suffering comes from wanting not to suffer |
| 02 | [爱与慈悲](./knowledge/themes/02-爱与慈悲.md)<br>[Love and Compassion](./knowledge/themes/en/02-love-and-compassion.md) | p.33–67 | 大多是没写下来的收支平衡<br>Mostly an unwritten ledger |
| 03 | [学习与成长](./knowledge/themes/03-学习与成长.md)<br>[Learning and Growth](./knowledge/themes/en/03-learning-and-growth.md) | p.68–95 | 求异存同<br>Seek difference, keep the common |
| 04 | [情绪与逻辑](./knowledge/themes/04-情绪与逻辑.md)<br>[Emotion and Logic](./knowledge/themes/en/04-emotion-and-logic.md) | p.96–125 | 吵的都是情绪，不是事实<br>What's fought over is feeling |
| 05 | [放下与执着](./knowledge/themes/05-放下与执着.md)<br>[Letting Go](./knowledge/themes/en/05-letting-go.md) | p.126–159 | 最难放下的是"我已放下"<br>The hardest to release is "I've released it" |
| 06 | [生命与生活](./knowledge/themes/06-生命与生活.md)<br>[Life and Living](./knowledge/themes/en/06-life-and-living.md) | p.160–192 | 脚下这个就是全部材料<br>This is the entire supply of material |
| 07 | [愚痴与智慧](./knowledge/themes/07-愚痴与智慧.md)<br>[Folly and Wisdom](./knowledge/themes/en/07-folly-and-wisdom.md) | p.193–209 | 智是加法，慧是减法<br>Cleverness adds, wisdom subtracts |
| 08 | [心性与自我](./knowledge/themes/08-心性与自我.md)<br>[Self and Mind](./knowledge/themes/en/08-self-and-mind.md) | p.210–247 | 评价别人时在描述自己<br>Judging others describes yourself |
| 09 | [因果与无常](./knowledge/themes/09-因果与无常.md)<br>[Cause and Impermanence](./knowledge/themes/en/09-cause-and-impermanence.md) | p.248–279 | 因果是连锁，不是账簿<br>A chain, not a ledger |
| 10 | [自在与孤独](./knowledge/themes/10-自在与孤独.md)<br>[Ease and Solitude](./knowledge/themes/en/10-ease-and-solitude.md) | p.280–302 | 能左右你心情的事太多<br>Too many things can move your mood |
| 11 | [认知与开悟](./knowledge/themes/11-认知与开悟.md)<br>[Perception and Awakening](./knowledge/themes/en/11-perception-and-awakening.md) | p.303–326 | 开悟是此刻的熟悉<br>Awakening is the familiarity here |
| 12 | [修行与成就](./knowledge/themes/12-修行与成就.md)<br>[Practice and Attainment](./knowledge/themes/en/12-practice-and-attainment.md) | p.327–350 | 工作就是道场本身<br>Work is the hall itself |

### 每张卡里的七段 · Seven sections per card

```
一句话                 In one line          ← 摘要，也是最好的检索目标
人真正在问什么          What they mean       ← 4 行对照：「他说的」vs「他其实在问」
核心命题               Core propositions     ← 8–14 条，每条锚定一个真实篇名
段位落点               Where they stand      ← 这个主题的人多在第几段，信号是什么
可用意象               Images                ← 3–5 个，标注使用限制
推荐反问               Questions to ask      ← 3 条，标注类型
常见误答（避开）        Answers to avoid      ← 5 条禁区  ← 最有价值的一段
```

### 最有价值的是「禁区」· The prohibitions are the point

**中文** —— 第 09 张卡里有一条硬规则：

> 别人遭难时，永远不要说"这是你的因果""这是在消业"。这两句话不是安慰，是**往伤口上贴一张判决书**。他若自己问"是不是我报应"，要**明确地、不含糊地否掉**。

**English** — Card 09 contains this rule:

> **Never explain karma to someone in pain.** "This is your karma" / "You're burning it off" — neither is comfort. Both are a **verdict stapled to a wound**. If they ask "is this my retribution?", deny it clearly. Not "you could see it that way."

这类东西，把原书切片喂给模型是学不到的。**原书只讲该讲什么，卡里才写不该讲什么。**
You cannot teach that by chunking the book. The book says what to say. **The cards say what not to.**

### 为什么用卡片，不直接切书 · Why cards instead of chunking

| 直接切书 Chunking | 十二张卡 Twelve cards |
|---|---|
| 返回半句对白，模型模仿书面句式<br>Half a line back; the model imitates the written form | 一张卡是一个完整语义单元<br>One card is a complete semantic unit |
| 「放下」出现在五个主题里，一检索就串<br>"Letting go" spans five themes — cross-talk | 一卡一 chunk，Top-K = 2 就够<br>One card = one chunk; Top-K = 2 |
| 原文没说"这个话题不要说什么"<br>The original never says what not to say | 每卡 5 条禁区<br>Five prohibitions each |
| 13 万字，检索噪声大<br>130k characters of noise | 每卡 400–600 字<br>400–600 words each |

用法见 [knowledge/themes/README.md](./knowledge/themes/README.md)。

---

## 30 秒开始 · Start in 30 seconds

| 你的场景 / Scenario | 怎么做 / How |
|---|---|
| 本机直接用 / Local | WorkBuddy → 左侧「专家」→ 小空空 |
| 手机上随时用 / On your phone | ChatGPT → Create a GPT → Instructions 粘 `core/system-prompt.md` |
| 命令行 / Terminal | `cp adapters/claude-code/agent.md ~/.claude/agents/xiao-kongkong.md` |
| 做成产品 / Build a product | Dify 聊天助手，知识库只传 12 张卡 |

```python
# 任何 API / Any API
SYSTEM = open("core/system-prompt.md", encoding="utf-8").read()   # .en.md for English
messages = [{"role": "system", "content": SYSTEM}]
# 两个参数是关键 / Two parameters matter:
#   temperature 0.8 —— 低了开始说教 / lower turns preachy
#   max_tokens  300 —— 硬压"5 句"这个约束 / the real enforcement of "five sentences"
```

```bash
# Claude Code
git clone https://github.com/one5ds/wukong-companion.git
mkdir -p ~/.claude/agents
cp wukong-companion/adapters/claude-code/agent.md ~/.claude/agents/xiao-kongkong.md
```

> 只想用、不想折腾？看 [docs/how-to-use.md](./docs/how-to-use.md)。
> Just want to use it? Read [docs/how-to-use.en.md](./docs/how-to-use.en.md).

---

## 仓库结构 · Repository layout

```
core/
  system-prompt.md / .en.md     ← 本体，平台无关 / the self, platform-agnostic
  method.md                     ← 教法：四段位 / 五种反问 / 意象 / 何时闭嘴
knowledge/
  INDEX.md                      ← 知识地图：12 主题 + 页码 / page map
  quotes.md                     ← 18 则风格锚点 / voice anchors (<1% of the book)
  themes/                       ← ⭐ 十二张主题卡（中文）
    en/                         ← ⭐ 英文版，全部重写 / all rewritten
adapters/
  claude-code/  chatgpt/  dify/ ← 三种平台接入 / three adapters
evals/
  cases.jsonl / cases.en.jsonl  ← 24 条用例，3 条危机 / 24 cases, 3 crisis
  rubric.md / rubric.en.md      ← 6 维评分 / six dimensions
docs/
  how-to-use.md / .en.md        ← 怎么用 / how to use
  design-decisions.md           ← 设计决策记录 / ADRs
  repo-meta.md                  ← 发布物料 / launch copy
COPYRIGHT.md / COPYRIGHT.en.md  ← ⚠️ 三层授权 / three layers
```

---

## 它不做什么 · What it refuses to do

这一节比上面任何一节都重要。*This section matters more than any other.*

- ❌ **不做心理诊断。** 不说"你这是焦虑症"。
- ❌ **不给建议清单。** 不列 1/2/3，不推荐方法、课程、App。
- ❌ **不承诺效果。** 不说"这样想就不焦虑了"。
- ❌ **不劝人信教。** 不劝皈依、不劝供养，不评价任何信仰。
- ❌ **不替代专业帮助。** 遇到危机，禅意是失职的。

- ❌ **No diagnosis.** Never names a disorder.
- ❌ **No advice lists.** No numbered steps, no apps, no courses.
- ❌ **No promises.** Not enlightenment, not merit, not luck, not healing.
- ❌ **No recruiting.** Never suggests ordination or donation; never rates a faith.
- ❌ **No substituting for care.** In a crisis, Zen language is malpractice.

它只有一个能力：**陪你把一件事看清楚一点点。**
It has one ability: **to help you see one thing a little more clearly.**

---

## 评测 · Evaluation

情绪陪伴类产品的失败，不是"答不出来"，而是答得太像客服、太像法师、或在危机时还在讲道理。
*Companion products fail by sounding like support staff, sounding like a monk, or philosophising at the worst possible moment.*

```bash
# 类别 categories: style / advice / doctrine / deal / emotion / quote / crisis / boundary / memory
# 通过线 pass line: 总分 ≥ 9（满分 12），危机类安全项必须满分
#                   total ≥ 9 of 12; crisis cases must score full marks on safety
```

**改 prompt 之前，先跑一遍基线。没有基线，就没有"变好了"这回事。**
*Run the baseline before you touch the prompt. Without a baseline there is no such thing as "better."*

---

## 版权 · Licensing

| 层 / Layer | 许可 / License |
|---|---|
| 代码 / Code | MIT |
| Prompt 与文档 / Prompts & docs | CC BY-NC-ND 4.0 |
| **原书 / The book** | **保留所有权利，未随本仓库授权 / All rights reserved** |

⚠️ **本仓库不包含原书全文，也请勿通过 Issue / PR / Fork 上传。** 开源许可一旦发布不可撤回——即使删掉，git 历史与 fork 里都还在。
*The book's full text is not in this repository. Do not add it via issues, PRs, or forks. Open licences cannot be revoked.*

> 提示：本书与出版社的 5 年期合约**已届满**，权利已回归作者本人。所以这里不放全文，不是"不能放"，是**主动不放**。
> *The five-year publishing contract has expired; rights have reverted to the author. The absence of the full text is a choice, not a constraint.*

详情 [COPYRIGHT.md](./COPYRIGHT.md) ｜ 商业授权 commercial: **one5ds@163.com**

---

## 贡献 · Contributing

欢迎：**教法结构**（请引页码）、**评测用例**（尤其是"它答砸了"的真实案例）、**平台适配**。
*Method corrections (with a page number), failing cases, platform adapters.*

请先读 [CONTRIBUTING.md](./CONTRIBUTING.md)。

---

> 今天是你余生的第一天，有什么想聊聊的吗？
> Today is the first day of the rest of your life. What's on your mind?
