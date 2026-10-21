# Twelve Theme Cards · English

> This is the **retrieval layer** of the project.
> `core/method.md` says *how to speak*. These twelve cards say *what to say about what.*

## Why cards instead of the raw book

Chunking the book's 300+ dialogues directly into a vector store runs into three problems:

1. **Broken chunks** — retrieval returns half a line of `Wukong: … / Wushi: …`, and the model imitates the *form*.
2. **Cross-talk** — "letting go" appears in five different themes. One query pulls all of them.
3. **No guardrails** — the original text never says *what not to say about this topic*, so the model has no idea where the minefield is.

The cards are a hand-built structure: one theme per card, with propositions, level, images, questions, and prohibitions. Shorter than the book. Far more precise.

## Index

| # | Theme | Month | Pages | The hinge |
|---|-------|-------|-------|-----------|
| 01 | [Suffering and Pain](./01-suffering-and-pain.md) | Jan | 6–32 | Suffering comes from wanting not to suffer |
| 02 | [Love and Compassion](./02-love-and-compassion.md) | Feb | 33–67 | Mostly an unwritten ledger |
| 03 | [Learning and Growth](./03-learning-and-growth.md) | Mar | 68–95 | Seek difference |
| 04 | [Emotion and Logic](./04-emotion-and-logic.md) | Apr | 96–125 | What's fought over is feeling |
| 05 | [Letting Go](./05-letting-go.md) | May | 126–159 | The hardest to release is "I've released it" |
| 06 | [Life and Living](./06-life-and-living.md) | Jun | 160–192 | This is the entire supply of material |
| 07 | [Folly and Wisdom](./07-folly-and-wisdom.md) | Jul | 193–209 | Cleverness adds, wisdom subtracts |
| 08 | [Self and Mind](./08-self-and-mind.md) | Aug | 210–247 | Judging others describes yourself |
| 09 | [Cause and Impermanence](./09-cause-and-impermanence.md) | Sep | 248–279 | A chain, not a ledger |
| 10 | [Ease and Solitude](./10-ease-and-solitude.md) | Oct | 280–302 | Too many things can move your mood |
| 11 | [Perception and Awakening](./11-perception-and-awakening.md) | Nov | 303–326 | Awakening is the familiarity here |
| 12 | [Practice and Attainment](./12-practice-and-attainment.md) | Dec | 327–350 | Work is the hall itself |

## Card structure

Every card has the same seven sections — **the fixed shape is what makes retrieval reliable**:

```
In one line        ← summary; also the best retrieval target
What they're actually asking   ← 4 rows, "what they say / what they mean"
Core propositions  ← 8–14 items, each anchored to a real chapter title
Where they usually stand       ← which level, and the tell
Images you can use ← 3–5, with usage limits noted
Questions to ask   ← 3, typed (zoom out / redirect / swap / hypothetical)
Answers to avoid   ← 5. This is the most valuable section.
Adjacent themes    ← when to hand off
```

## Using these in RAG

| Practice | Why |
|---|---|
| **One card = one chunk** | Don't split by line. A card is a complete semantic unit. |
| **Top-K = 2** | One is enough. Higher K causes cross-talk. |
| **Route, then retrieve** | Classify with the twelve "in one line" summaries first, then pull that card whole. Much more accurate than pure vector search. |
| **Cards only, not the book** | See [../../INDEX.md](../../INDEX.md) for why. |

Platform specifics: [adapters/dify/README.md](../../../adapters/dify/README.md).

## Division of labour with method.md

```
Someone types something painful
   │
   ├─ 1. Which card? (12 → 1)              ← themes/
   ├─ 2. Which level? (4 → 1)              ← method.md
   ├─ 3. Which type of question? (5 → 1)   ← method.md
   └─ 4. Does it hit a prohibition? (5)    ← themes/
```

**Card first, method second.** Reverse the order and you get a machine that says "let it go" to everyone.

## Contributing

If a proposition reads wrong, give **the page number, what the original says, and your reasoning.**
"I don't feel right about it" can't be acted on.

## Copyright

These twelve cards are **original structural distillations by the author**, not reproduced text. They cite roughly 100 chapter titles, which are bibliographic information and short quotation.

See [COPYRIGHT.en.md](../../../COPYRIGHT.en.md).
