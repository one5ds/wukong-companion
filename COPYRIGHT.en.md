# Copyright & Usage

This project licenses **three separate layers**. Please read this page before using, distributing, or building on it.

---

## 1. Three layers, three licences

| Layer | Content | Licence | You may |
|---|---|---|---|
| **A. Code** | scripts, build, CI, eval runners | [MIT](./LICENSE) | Commercial use, modify, distribute, embed in closed source |
| **B. Prompts & docs** | `core/`, `adapters/`, `evals/`, `docs/`, all original prose in this repo | [CC BY-NC-ND 4.0](./LICENSE-CONTENT.md) | Reproduce with attribution, non-commercially, unmodified. Commercial use needs permission. |
| **C. The book** | *Wu Kong & Wu Shi* — full text, cover, illustrations, characters | **All rights reserved. Not licensed here.** | Short quotation only, as permitted by law. No reproduction, adaptation, or training. |

In one line: **code is free, prompts are free to use but not to modify and sell, the book is not included at all.**

---

## 2. Why the full text is not here

1. **Copyright.** The book is a published work. Uploading a 365-page PDF to a public repository is "making a work available to the public" — free of charge does not make it fair use.
2. **The publishing contract has expired.** The five-year term with the publisher has ended; exclusive publishing rights and the right of network dissemination have reverted to the author. In other words, the author is now **entitled** to publish the full text.

   Even so, this repository chooses not to. It is a **deliberate trade-off**:

   - **Open licences cannot be revoked.** Once released under MIT / CC, the grant is permanent. "Everyone can download the whole book for free" is in direct conflict with "this book can still be published and read properly."
   - **The product doesn't need it.** Kongkong's quality comes from the method, not from volume. Adding 130,000 characters makes it imitate written prose.
   - **Leave a door for the serious.** Someone who wants the whole book should read the whole book. That's what it's for.

   > Put differently: it used to be "cannot." Now it is "will not." The first is law. The second is a choice.

3. **Open licences are irreversible in practice.** Even if a file is deleted later, it lives in git history and in every existing fork. This is the kind of mistake that must be avoided *before* the first push.

Accordingly, the repository keeps only:

- **A knowledge map** (`knowledge/INDEX.md`): twelve themes, page ranges, a small number of chapter titles (bibliographic information, for navigation);
- **Voice anchors** (`knowledge/quotes.md`): 18 short excerpts, under 1% of the book, for tone calibration and evaluation;
- **Method distillation** (`core/`, `knowledge/themes/`): original writing about *how to use it*, not reproduced text.

---

## 3. Explicitly not permitted

- ❌ Uploading the full text (PDF / TXT / OCR output) anywhere in this repo — issues, PRs, discussions, wiki, or forks.
- ❌ Packaging the book's content as a public dataset, or using it to train or fine-tune any model that is then distributed.
- ❌ Using the content in paid courses, paid communities, or paid AI products without written permission.
- ❌ Registering the book title, character names (Wukong, Wushi), or the IP artwork as trademarks, domains, or merchandise.
- ❌ Publishing anything in this project's name that promises awakening, merit, healing, or luck.

## 4. Explicitly permitted

- ✅ Fork it, rewrite the prompts, plug in your own model and front end (subject to layer B).
- ✅ Quote short lines in articles, courses, or podcasts with attribution (*Wu Kong & Wu Shi*, page number).
- ✅ Personal practice, internal team training, non-commercial research.
- ✅ Issues and PRs improving the method, the eval set, or translations.

## 5. About "training"

**No model was fine-tuned for this project.** Its behaviour comes from:

```
reading the book → distilling the method (core/) → 18 voice anchors (quotes.md)
→ prompt constraints → evaluation loops
```

That is **prompt engineering plus knowledge organisation**, not training. If fine-tuning happens later, the training data requires written permission from the rights holder **and must not be published**.

## 6. Takedown

If you are a rights holder and believe something here exceeds fair quotation, open an issue or email the maintainer. We will remove the material within **72 hours**.

## 7. Disclaimer

This is a **conversational companion grounded in everyday Zen**. It is not psychotherapy, medical care, or religious activity. Users should exercise their own judgement; for serious psychological distress, please seek professional help.

---

**Rights holder / maintainer:** 一觉同学 (Yijue)
**Contact:** one5ds@163.com ｜ GitHub: [@one5ds](https://github.com/one5ds)
**Status of rights:** the five-year publishing contract has expired; copyright is fully held by the author, and every licensing decision in this repository is the author's own.
