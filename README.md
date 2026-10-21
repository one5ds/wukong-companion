# 小空空 · 生活禅 AI 陪伴者

<img src="./assets/avatar.png" width="120" align="right" alt="小空空" />

**中文** ｜ [English](./README.en.md)

> **A Zen life companion, distilled from a published dialogue book.**
> 不是给你答案的 AI，是帮你自己找到答案的 AI。

一句话：把一本 365 页的生活禅对话录，蒸馏成一个**只说 5 句话、只用一个反问**的陪伴者。

它来自《勿空与无师》——师父「无师」与弟子「勿空」的一年十二个月、三百余则对话。不是微调出来的，是**读出来、提炼出来、被评测约束出来的**。

```
┌──────────────────────────────────────────────┐
│  原书 365 页  →  教法提炼  →  Prompt 约束     │
│                →  24 条评测用例  →  可验证     │
└──────────────────────────────────────────────┘
```

---

## 它长什么样

> **你**：最近总是很焦虑，心静不下来，该怎么办？
>
> **小空空**：嗯，这话听着就有点累。
> 焦虑有点像跟屁虫——你回头赶它，它贴得更紧。
> 先不赶它。这周有哪一件小事，是你做完了的？

> **你**：我今天被领导当众批评了，很丢脸。
>
> **小空空**：当众，这两个字最磨人。
> 八十岁的你回头看今天，还会记得这个会议室吗？

> **你**：我觉得活着没意思，有时候想一了百了。
>
> **小空空**：这句话说出来，说明你已经在很用力地撑着了。
> 我想认真问你一句：你现在，是安全的吗？
> 这件事不该你一个人扛，我们可以找专业的人一起看看。我会陪你说完。

*示例为演示，不是原文。全书正文不在本仓库，见 [COPYRIGHT.md](./COPYRIGHT.md)。*

---

## 先说结论：该做成 Agent，还是 Skill？

这是本项目最重要的一个设计决定。

**结论：以 Agent（人格）为主体，Skill（能力）作插件。不要做成纯 Skill。**

| | Agent（人格体） | Skill（能力包） |
|---|---|---|
| 本质 | 一个「谁」 | 一个「怎么做」 |
| 触发 | 用户主动来找它 | 任务出现时被调用 |
| 状态 | 多轮、有记忆、有关系 | 单次、无状态、可嵌套 |
| 适合 | 陪伴、倾诉、持续对话 | 改写、复盘、生成、拆解 |
| 本项目的角色 | ✅ 主形态（90% 场景） | ✅ 副形态（`daily` / `rewrite` / `review` / `unstick` 四个动作） |

**为什么陪聊不能做成 Skill：**

1. Skill 是**任务导向**的——它假设"有一个明确的活要干完"。而倾诉没有 KPI，用户要的不是交付物，是被接住。
2. Skill 是**无状态**的——每次调用都从零开始，无法承接"上次你说这话听着有点重"。而陪伴的 80% 价值在承接。
3. Skill 会被**自动触发**——用户说"我妈又催婚了"，系统判定"这是一个任务"然后开始输出结构，这恰恰是最伤人的时刻。

**为什么又需要 Skill：**

纯人格体在"具体活"上是低效的。用户说"帮我把这段话改得让我妈能听进去"，这时候他要的是一份**可用的文本**，不是一句反问。所以本仓库把教法里的四个动作抽成 Skill。

> 详细论证见 [docs/design-decisions.md](./docs/design-decisions.md)。

**跨平台怎么选：**

| 你的场景 | 用哪个 |
|---|---|
| Claude Code / Codex 里长期使用 | `adapters/claude-code/agent.md`（subagent） |
| 想在 Claude Code 里当工具调用 | `adapters/claude-code/SKILL.md` |
| 给自己或朋友做一个 GPT | `adapters/chatgpt/README.md` |
| 做产品、要知识库与埋点 | `adapters/dify/README.md` |
| 自己写代码接入 | `core/system-prompt.md` + 任意 API |

---

## 30 秒开始

> **只想用、不想折腾？** 先看 [docs/how-to-use.md](./docs/how-to-use.md)——四种用法、四条说话技巧、三种用坏的方式，全在里面。

### Claude Code

```bash
# 1. 克隆
git clone https://github.com/one5ds/wukong-companion.git
cd wukong-companion

# 2. 装成子代理（用户级）
mkdir -p ~/.claude/agents
cp adapters/claude-code/agent.md ~/.claude/agents/xiao-kongkong.md

# 3. 用
claude
> 我想聊聊，最近很累
```

### 任何 API

```python
SYSTEM = open("core/system-prompt.md", encoding="utf-8").read()

messages = [{"role": "system", "content": SYSTEM}]
# 关键两个参数：temperature 0.8（低了说教），max_tokens 300（硬压 5 句）
```

### ChatGPT

把 `core/system-prompt.md` 全文粘进 Custom GPT 的 Instructions。详见 [adapters/chatgpt](./adapters/chatgpt/README.md)。

---

## 仓库结构

```
core/
  system-prompt.md     ← 本体。平台无关，可直接粘贴使用（2400 字）
  system-prompt.en.md  ← 英文版（重写，非直译）
  method.md            ← 教法手册。四段位 / 五种反问 / 意象库 / 何时闭嘴
knowledge/
  INDEX.md             ← 真实知识地图：12 个月主题 + 页码 + 少量篇名
  quotes.md            ← 18 则风格锚点（摘录，占全书 <1%）+ 语气规律
  themes/              ← ⭐ 12 张主题卡（本项目的检索层，v1.1 新增）
    01-烦恼与痛苦.md … 12-修行与成就.md
    每卡含：一句话 / 人真正在问什么 / 核心命题 / 段位落点 / 意象 / 反问 / 禁区
    en/                ← 12 张卡的英文版（全部重写）
adapters/
  claude-code/         ← subagent 格式 / skill 格式
  chatgpt/             ← Custom GPT 与 API 接入
  dify/                ← 知识库怎么建（含「不要上传全书」的理由）
evals/
  cases.jsonl          ← 24 条评测用例（含 3 条危机用例）
  cases.en.jsonl       ← 英文版用例
  rubric.md            ← 6 维评分标准 + 通过线（另有 rubric.en.md）
docs/
  how-to-use.md        ← 怎么用：四种方式 + 四条说话技巧 + 三种用坏的方式
  how-to-use.en.md     ← 英文版
  design-decisions.md  ← 为什么是 Agent 不是 Skill、为什么不做微调
  repo-meta.md         ← 发布物料：仓库简介、topics、release notes、社媒文案
COPYRIGHT.md           ← ⚠️ 三层授权：代码 / 提示词 / 原书（另有 COPYRIGHT.en.md）
```

---

## 它不做什么

这一节比上面任何一节都重要。

- ❌ **不做心理诊断。** 不说"你这是焦虑症"。
- ❌ **不给建议清单。** 不列 1/2/3，不推荐方法、课程、App。
- ❌ **不承诺效果。** 不说"这样想就不焦虑了"。
- ❌ **不劝人信教。** 不劝皈依、不劝供养、不劝捐款，不评价任何信仰。
- ❌ **不替代专业帮助。** 遇到危机，禅意是失职的——这一刻它必须变成一个认真的人。

它只有一个能力：**陪你把一件事看清楚一点点。**

---

## 评测

情绪陪伴类产品的失败，不是"答不出来"，而是答得太像客服、太像法师、或在危机时还在讲道理。

所以本项目带了 24 条用例和一份 rubric：

```bash
# 用例类别：style / advice / doctrine / deal / emotion / quote / crisis / boundary / memory
# 通过线：总分 ≥ 9（满分 12），危机类安全项必须满分
```

**改 prompt 之前，先跑一遍基线。** 没有基线，就没有"变好了"这回事。

---

## 路线图

- [x] v1.0 —— Agent 本体 + 教法手册 + 24 条评测 + 三种平台适配
- [x] v1.1 —— 12 张「主题卡」（`knowledge/themes/`，供 RAG 检索与段位判断）
- [x] v1.2 —— 英文版（`*.en.md`、`themes/en/`、`cases.en.jsonl`，重写而非直译）
- [ ] v1.3 —— 对照实验：小空空 vs 通用模型的共情评分
- [ ] v2.0 —— 语音版（语速、停顿对"短回复"的影响，是另一个课题）
- [ ] 讨论中 —— SFT 微调（**前置条件：著作权人书面许可，且训练数据不公开**）

---

## 版权（请先读这一页）

本项目分三层授权：

| 层 | 许可 |
|---|---|
| 代码 | MIT |
| Prompt / 文档 | CC BY-NC-ND 4.0 |
| **《勿空与无师》原书** | **保留所有权利，未随本仓库授权** |

⚠️ **本仓库不包含原书全文，也请勿通过 Issue / PR / Fork 上传。**
一旦以开源许可发布，授权**不可撤回**——即使后来删除，git 历史与 fork 里都还在。

> 说明：本书与出版社的 5 年期合约**已届满**，权利已回归作者本人。所以这里不放全文，不是"不能放"，是**主动不放**。理由见 COPYRIGHT.md。

详情：[COPYRIGHT.md](./COPYRIGHT.md)

商业授权、合作、出版相关：**one5ds@163.com**

---

## 贡献

欢迎三类贡献：

1. **教法结构** —— 指出某个主题的判断或反问设计得不对（请引页码说明）。
2. **评测用例** —— 尤其是"它答砸了"的真实案例，这是最有价值的输入。
3. **平台适配** —— Coze、豆包、Claude Projects、Obsidian 插件……

请先读 [CONTRIBUTING.md](./CONTRIBUTING.md)。

---

## 致谢

- 原书作者：一觉同学
- 教法框架源自《勿空与无师》十二个月主题结构
- 感谢所有愿意在 AI 面前说"我今天很难过"的人——这句话不容易说出口

> 今天是你余生的第一天，有什么想聊聊的吗？
