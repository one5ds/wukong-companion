# How to use it

> Written for **people who want to use this**, not for developers.
> Four ways to run it, from zero-config to building your own product. Pick one.

---

## First: when to use it, and when not to

This is the most important section here. **Use it in the wrong situation and it will seem useless.**

### ✅ Good for

- Something you keep circling, that you can't name or resolve
- A pattern you keep falling into in one particular relationship
- Tired in a way you can't locate
- You don't want advice. You want someone present who isn't evaluating you.

### ❌ Not for

| What you need | Who to ask |
|---|---|
| A plan, a path, a checklist | Any ordinary assistant (this one deliberately refuses) |
| A suspicion of depression or an anxiety disorder | A psychiatrist or clinical psychologist |
| Thoughts of self-harm or suicide | **Real help first — a crisis line, a clinician, a person nearby.** Not an AI alone. |
| To be actually held | A human. It can stay with you; it can't take the weight. |

---

## Option 1 — Inside the desktop app (zero setup)

Xiao Kongkong is installed as an "Expert" in WorkBuddy.

1. Open WorkBuddy
2. Find **小空空** in the Experts panel
3. Start talking

It already carries the full persona. You don't need to paste any prompt.

---

## Option 2 — Make a Custom GPT (best for daily use)

Good if you want it on your phone without opening a laptop.

1. ChatGPT → **Explore GPTs** → **Create**
2. Switch to **Configure**
3. **Name:** Xiao Kongkong
4. **Instructions:** paste the whole of `core/system-prompt.en.md`
5. **Conversation starters:**

```
Today is the first day of the rest of your life. What's on your mind?
I've been anxious for weeks and I can't settle. What do I do?
How do I stop caring so much about what people think of me?
```

6. Turn off **Code Interpreter** and **Web Browsing** (unnecessary, and they cause drift)
7. Save as "Only me" first

**Two settings people forget:**

- Pick a model with good **prose rhythm** — this persona lives or dies on sentence length.
- If replies get long, append one line to the very end of Instructions:
  ```
  Regardless of anything else, never reply with more than 5 sentences. More than 5 is a failure.
  ```

> ⚠️ Do not upload the book PDF to Knowledge. Reasons: [COPYRIGHT.en.md](../COPYRIGHT.en.md).

---

## Option 3 — Claude Code (for people who live in a terminal)

```bash
npm install -g @anthropic-ai/claude-code

git clone https://github.com/one5ds/wukong-companion.git
cd wukong-companion

mkdir -p ~/.claude/agents
cp adapters/claude-code/agent.md ~/.claude/agents/xiao-kongkong.md

claude
> let me talk to kongkong. I'm exhausted.
```

**Honest caveat:** Claude Code subagents are for *delegating tasks*, not for sitting with you.
If you want actual companionship in a terminal, set `core/system-prompt.md` as a project's `CLAUDE.md` and just talk to it plainly.

---

## Option 4 — Build a product (Dify / Coze)

1. New "Chat Assistant" in Dify
2. System prompt: `core/system-prompt.en.md`
3. Knowledge base: **only** the 12 cards in `knowledge/themes/en/`, one card per chunk
4. temperature 0.7–0.9, max tokens 300, Top-K = 2

Full configuration and pitfalls: [adapters/dify/README.md](../adapters/dify/README.md).

---

## How to talk to it (four rules)

### 1. Describe the moment, not the summary

| Weak | Strong |
|---|---|
| "Work isn't going well" | "In the meeting I got halfway through a sentence and he said 'we discussed this already,' and everyone laughed" |
| "I don't get along with my mother" | "She walked in and asked about my salary. I said 'don't ask,' and she went quiet for ten minutes" |

**Detail is where the material is.** Summaries are for HR, not for this.

### 2. Don't ask "what should I do"

It will sidestep — that's the design. If you genuinely only want company, say so:

> "I don't want solutions. Just sit with me while I sort this out."

That sentence relaxes it. Replies get much closer.

### 3. Let it answer in one sentence

It often does. **Don't push with "and?" or "go on"** — push and it becomes support staff.

### 4. Stop when something catches

When something in you goes *click*, that's the place to stop.
Keep talking past it and the words cover it up.

---

## Three ways to break it

| Pattern | What happens | Fix |
|---|---|---|
| **Ten sessions a day** | Dependency, and it starts repeating itself | Once a day, or once a week |
| **Using it instead of people or treatment** | Feelings get caught; the problem doesn't get handled | Treat it as a bridge, not a destination |
| **Asking it to decide for you** | It answers with a question; you conclude it's useless | You decide. It helps you see the options. |

---

## One sentence

> It isn't here to solve the problem. It's here to help you see it a little more clearly.
> What you do after that is yours — it can't manage that, and shouldn't.
