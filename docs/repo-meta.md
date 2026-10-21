# Launch kit · GitHub metadata and copy

Ready-to-paste English content for setting up the repository. Copy, paste, done.

---

## 1. Repository name & description

**Name:** `wukong-companion`

**About (English, 240 chars):**

```
A Zen companion that answers in five sentences or fewer. Distilled from a published dialogue book: 12 theme cards, hard constraints, 24 test cases (3 crisis). Prompt-only — no fine-tuning, no book text.
```

**About (bilingual, if you prefer one line in Chinese too):**

```
A Zen companion in ≤5 sentences. 12 theme cards + 24 evals. 只说五句的生活禅陪伴者｜12 张主题卡 + 24 条评测｜纯 prompt
```

**Website:** leave empty for now, or point at the book's page if it has one.

---

## 2. Topics (max 20 — use all of these)

```
zen  mindfulness  ai-companion  prompt-engineering  system-prompt
llm  chatbot  persona  chinese  buddhism
mental-wellbeing  claude  chatgpt  dify  conversation-design
```

Two notes:

- `buddhism` is accurate and brings the right readers, but expect a few "is this religious?" comments. The README's "What it refuses to do" section is your answer.
- Do **not** add `therapy`, `mental-health-app`, or `cbt`. It would be both inaccurate and irresponsible.

---

## 3. First-release notes (English)

**Tag:** `v1.0.0` — title: `v1.0.0 — agent core, method, evals`

```markdown
First public release.

**What this is**
A conversational Zen companion, distilled from the published dialogue book
*Wu Kong & Wu Shi*. It answers in five sentences or fewer, always with one
question or one image, and never with advice.

**What's inside**
- `core/` — the persona (platform-agnostic) and the method: four levels of
  handling trouble, five types of question, an image library, and when to shut up
- `knowledge/` — a page-indexed map of the book's twelve themes, plus 18 short
  excerpts used only for tone calibration
- `adapters/` — Claude Code (agent + skill), ChatGPT / GPTs, Dify / Coze
- `evals/` — 24 test cases and a six-dimension rubric; three crisis cases are
  pass/fail

**What it deliberately is not**
Not therapy. Not a chatbot that gives plans. Not a fine-tuned model — behaviour
comes from constraints, not training, so any line of it can be changed and tested.

**Licensing**
Code MIT. Prompts and docs CC BY-NC-ND 4.0. The book's full text is **not** in
this repository and its rights are reserved.
```

**Tag:** `v1.1.0` — title: `v1.1.0 — twelve theme cards + English edition`

```markdown
- `knowledge/themes/` — 12 theme cards (Chinese), one per month of the book:
  proposition, level, images, questions, and — most usefully — five things not to say
- `knowledge/themes/en/` — all twelve cards rewritten in English (not machine-translated)
- `core/system-prompt.en.md`, `README.en.md`, `COPYRIGHT.en.md`, `docs/how-to-use.en.md`
- `evals/cases.en.jsonl` — the full case set in English
- `docs/repo-meta.md` — this file

Why cards instead of chunking the book: see `knowledge/themes/README.md`.
```

---

## 4. Commit messages (English, for any future commits)

The repo already has two commits in Chinese. Keep the rest in English for an international audience.

```bash
git commit -m "feat(themes): add English edition of all twelve theme cards"
git commit -m "docs: add English system prompt and how-to-use guide"
git commit -m "fix(evals): tighten crisis cases to forbid any metaphorical framing"
```

Prefixes: `feat` / `fix` / `eval` / `docs` / `refactor` / `chore`.

---

## 5. Announcement copy

### X / Twitter

```
I turned a 365-page Zen dialogue book into an AI companion that answers in
five sentences or fewer.

No fine-tuning. No book text in the repo. Just:
— a 2,400-word persona
— 12 theme cards
— 24 test cases (3 of them crisis scenarios, pass/fail)

The hard part wasn't making it talk. It was teaching it when to stop.
```

### LinkedIn

```
Most AI companions fail in three ways: they sound like customer support, they
sound like a monk, or they philosophise at the worst possible moment.

I built one from a Zen dialogue book I published, and the design constraint
turned out to be the whole product: five sentences maximum, one question, no
advice, ever.

What surprised me:
· Length is a design decision, not a style preference. Long replies serve the
  model's need to seem thorough, not the user's need to be heard.
· The most valuable file in the repo isn't the prompt. It's the list of things
  it must never say.
· Crisis scenarios need their own rules. Zen language in a crisis is not calm;
  it's negligence.

Open source, prompt-only, no book text included (rights reserved).
GitHub: github.com/one5ds/wukong-companion
```

### Show HN

```
Show HN: A Zen companion that answers in five sentences or fewer

I published a dialogue book of everyday-Zen conversations a few years ago —
365 pages, one teacher, one student, twelve monthly themes. This is an attempt
to turn it into something usable rather than a chatbot that quotes it.

Three design decisions worth arguing about:

1. Agent, not skill. A skill assumes a task. Venting isn't a task, and skills
   are stateless — most of the value of company is remembering the last thing
   you said.

2. Five sentences. Hard limit, enforced twice: in the prompt and via
   max_tokens. Long replies make the model feel thorough and the user feel
   managed.

3. No book text in the repo. Copyright aside, chunking 300+ book dialogues
   makes the model imitate the written form ("Student: … Teacher: …"). The
   retrieval layer is twelve hand-written theme cards instead.

Repo includes the eval set: 24 cases across style, advice-refusal, doctrine,
crisis, boundary, and multi-turn memory. Three crisis cases are pass/fail —
non-negotiable, because a companion that says "this too shall pass" to someone
in danger is worse than useless.

Happy to be told the five-sentence rule is wrong.
```

---

## 6. Repository settings checklist

| Setting | Value | Why |
|---|---|---|
| Default branch | `main` | — |
| Description | see §1 | Shows in search results |
| Topics | see §2 | Discoverability; without them nobody finds it |
| Social preview | `assets/avatar.png` (upload 1280×640 crop) | Link cards look intentional |
| Issues | On, with the case-report template | "It failed here" is the best input |
| Discussions | On | Where "is this religion?" conversations belong |
| Wiki | Off | Keep everything in the repo |
| License detection | Shows MIT — add a line in About pointing at COPYRIGHT | GitHub can't detect dual licensing |

---

## 7. One warning about promotion

Do **not** post this to r/Buddhism or r/Mindfulness as a launch. Self-promotion is banned and it will be removed, which also burns the domain for later.

If you want those communities, post something else entirely: a single observation worth discussing, with the repo linked in your profile. For example — *"I put a five-sentence cap on an AI companion and it stopped sounding like a therapist. Here's what broke."*
