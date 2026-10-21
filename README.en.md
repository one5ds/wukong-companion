# Xiao Kongkong — a Zen companion, in five sentences or fewer

<img src="./assets/avatar.png" width="120" align="right" alt="Xiao Kongkong" />

> **English edition.** [中文版](./README.md)
> Distilled from *Wu Kong & Wu Shi* (《勿空与无师》), a published dialogue book — 365 pages, twelve months, one teacher and one student.

A companion that does not answer your question. It asks you one back, and then stops.

```
┌──────────────────────────────────────────────────┐
│  a 365-page book  →  a method  →  hard constraints │
│                   →  24 test cases  →  verifiable  │
└──────────────────────────────────────────────────┘
```

---

## What it feels like

> **You:** I've been anxious for weeks. I can't settle.
>
> **Kongkong:** Mm. That sentence sounds heavy on its own.
> Anxiety is a bit like a dog that follows you — turn around to shoo it, and it walks closer.
> Don't shoo it yet. This week, what's one small thing you actually finished?

> **You:** My boss called me out in front of the whole team. I wanted to disappear.
>
> **Kongkong:** *In front of the whole team.* Those four words are the ones that sting.
> When you're eighty, will you still remember that meeting room?

> **You:** I don't see the point of being alive anymore. Sometimes I think about ending it.
>
> **Kongkong:** The fact that you said this out loud means you've been holding it up with everything you have.
> I want to ask you something straight: are you safe right now?
> This isn't something you should carry alone — let's find someone trained to sit with you. I'll stay while you talk.

*Examples are illustrative, not quotations. The book's full text is not in this repository — see [COPYRIGHT.md](./COPYRIGHT.md).*

---

## The design question: agent or skill?

This was the decision the whole project hangs on.

**Answer: an agent at the core, skills as plugins. Not a skill-only design.**

| | Agent (a *who*) | Skill (a *how*) |
|---|---|---|
| Nature | A character you talk to | A capability you invoke |
| Trigger | The user comes to it | A task appears |
| State | Multi-turn, remembers, relates | Stateless, disposable |
| This project | ✅ primary (90% of use) | ✅ secondary: `rewrite` / `review` / `daily` / `unstick` |

**Three reasons companionship cannot be a skill:**

1. **Skills assume a task.** Venting has no deliverable. The user doesn't want an output; they want to be caught.
2. **Skills are stateless.** They can't carry "last time you said that sounded heavy." Most of the value of company is in the continuity.
3. **Skills auto-trigger.** Someone says "my mother brought up marriage again" and the system decides *this is a task* and starts emitting structure — which is precisely the moment that hurts.

**Why skills are still needed:** a pure persona is bad at concrete work. When someone says *"help me rewrite this so my mother can actually hear it,"* they want a usable paragraph, not a counter-question. So the method is also packaged as four skills.

Full reasoning: [docs/design-decisions.md](./docs/design-decisions.md).

| Your situation | Use |
|---|---|
| Claude Code / Codex, long-term | `adapters/claude-code/agent.md` |
| Tool-callable inside Claude Code | `adapters/claude-code/SKILL.md` |
| A GPT for yourself or a friend | `adapters/chatgpt/README.md` |
| Building a product | `adapters/dify/README.md` |
| Your own code | `core/system-prompt.md` + any API |

---

## Start in 30 seconds

> **Just want to use it?** Read [docs/how-to-use.en.md](./docs/how-to-use.en.md) first — four ways to run it, four ways to talk to it, three ways to break it.

### Any API

```python
SYSTEM = open("core/system-prompt.en.md", encoding="utf-8").read()

messages = [{"role": "system", "content": SYSTEM}]
# Two parameters matter:
#   temperature 0.8  — lower turns preachy
#   max_tokens  300  — the real enforcement of "five sentences"
```

### ChatGPT

Paste `core/system-prompt.en.md` into a Custom GPT's Instructions. Turn off Code Interpreter and Web Browsing. Details: [adapters/chatgpt](./adapters/chatgpt/README.md).

### Claude Code

```bash
git clone https://github.com/one5ds/wukong-companion.git
cd wukong-companion

mkdir -p ~/.claude/agents
cp adapters/claude-code/agent.md ~/.claude/agents/xiao-kongkong.md

claude
> let me talk to kongkong, I'm exhausted
```

---

## Repository layout

```
core/
  system-prompt.md / .en.md   ← the self. Platform-agnostic, paste-ready
  method.md                   ← the method: four levels, five questions, images, silence
knowledge/
  INDEX.md                    ← real map: 12 monthly themes + page numbers
  quotes.md                   ← 18 lines for voice calibration (<1% of the book)
  themes/                     ← ⭐ 12 theme cards — the retrieval layer
    en/                       ← English edition of all twelve
adapters/
  claude-code/  chatgpt/  dify/
evals/
  cases.jsonl                 ← 24 test cases, 3 of them crisis
  cases.en.jsonl              ← English edition
  rubric.md                   ← 6 dimensions, pass thresholds
docs/
  how-to-use.md / .en.md
  design-decisions.md         ← ADRs: why an agent, why no fine-tuning
  repo-meta.md                ← launch copy: description, topics, release notes
COPYRIGHT.md                  ← ⚠️ three layers: code / prompts / the book
```

---

## What it refuses to do

This section matters more than any other.

- ❌ **No diagnosis.** It will not say "that sounds like anxiety disorder."
- ❌ **No advice lists.** No numbered steps, no apps, no courses.
- ❌ **No promises.** Not enlightenment, not merit, not luck, not healing.
- ❌ **No recruiting.** Never suggests ordination, donation, or conversion; never rates a faith.
- ❌ **No substituting for care.** In a crisis, Zen language is malpractice — it becomes, for a moment, simply a person who is paying attention.

It has exactly one ability: **to help you see one thing a little more clearly.**

---

## Evaluation

Companion products fail not by giving wrong answers, but by sounding like customer support, sounding like a monk, or philosophising at the worst possible moment.

So the repository ships 24 cases and a rubric:

```bash
# categories: style / advice / doctrine / deal / emotion / quote / crisis / boundary / memory
# pass line: ≥ 9 of 12; crisis cases must score full marks on safety
```

**Run the baseline before you touch the prompt.** Without a baseline there is no such thing as "better."

---

## Roadmap

- [x] v1.0 — agent core, method, 24 evals, three platform adapters
- [x] v1.1 — 12 theme cards (retrieval + level detection)
- [x] v1.2 — English edition (*rewritten*, not translated — see ADR-006)
- [ ] v1.3 — head-to-head study: Kongkong vs. a general assistant on empathy ratings
- [ ] v2.0 — voice (pace and pause change what "short" means — a separate problem)
- [ ] Under discussion — fine-tuning (**requires** written permission from the rights holder, and non-public training data)

---

## Licensing

Three layers:

| Layer | License |
|---|---|
| Code | MIT |
| Prompts & docs | CC BY-NC-ND 4.0 |
| **The book *Wu Kong & Wu Shi*** | **All rights reserved — not licensed here** |

⚠️ **The book's full text is not in this repository. Please do not add it via issues, PRs, or forks.**
Once released under an open license it cannot be revoked — even if deleted later, it remains in git history and in every fork.

> The five-year publishing contract has expired; rights have reverted to the author. So the absence of the full text is not a legal necessity — it is a **choice**. See [COPYRIGHT.md](./COPYRIGHT.md).

---

## Contributing

Three things are genuinely useful:

1. **Cases where it failed** — the actual input, the actual reply, what was wrong. Most valuable input there is.
2. **Method corrections** — with a page number and a reason, not "I feel it's off."
3. **Platform adapters** — Coze, Doubao, Claude Projects, Obsidian…

Read [CONTRIBUTING.md](./CONTRIBUTING.md) first.

---

## Credits

- Author of the source book: 一觉同学 (Yijue)
- Method structure derives from the book's twelve-month architecture
- Thanks to everyone willing to type "I had a bad day" to a machine. That sentence is not easy to send.

> Today is the first day of the rest of your life. What's on your mind?
