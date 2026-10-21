# 贡献指南 · Contributing

先读 [COPYRIGHT.md](./COPYRIGHT.md)。**一条铁律：不要提交原书内容。**

---

## 最有价值的三种贡献

### 1. 它答砸了的真实案例（最有价值）

比任何赞美都有用。格式：

```markdown
**输入**：（你当时说的话，可以脱敏）
**它的回复**：（原文）
**哪里不对**：（一句话，例如"它在第三句开始讲道理了"）
**你希望它说什么**：（不必完美，一个方向就够）
```

我们会把它加进 `evals/cases.jsonl`。

### 2. 教法结构的问题

如果你读过原书，觉得某一章的教法提炼偏了、浅了、或者把一个"反问"写成了"结论"：

- 请注明**页码**与原文意思；
- 请说明你的判断依据（不是"我觉得不对"，而是"书里这里其实是在说反面"）。

### 3. 平台适配

Coze / 豆包 / Claude Projects / Obsidian / Dify DSL / 微信小程序……
新增一份 `adapters/<platform>/README.md` 即可，要求：

- 写清"踩过什么坑"，而不只是"怎么配"；
- 至少验证过一个真实对话；
- 不要复制别人的截图与文案。

---

## 不接受

- ❌ 原书全文、PDF、OCR 文本、大段摘录（>3 句）
- ❌ 让角色变成"万能顾问"的改动（加建议清单、加诊断、加承诺）
- ❌ 涉及具体宗教劝进、政治、医疗建议的内容
- ❌ 未经许可的商用改造版本链接

---

## 流程

```bash
# 1. fork & clone
git clone https://github.com/one5ds/wukong-companion.git

# 2. 建分支（命名建议）
git checkout -b feat/theme-cards      # 新功能
git checkout -b fix/style-too-long    # 修 bug
git checkout -b eval/add-crisis-case  # 加用例
git checkout -b docs/en-readme        # 文档

# 3. 改完先自测（关键）
#    用 evals/cases.jsonl 跑一遍，确认没有回退

# 4. 提交
git add -A
git commit -m "feat(evals): 增加 3 条危机场景用例"

# 5. 推送并开 PR
git push origin feat/theme-cards
```

## Commit 规范（简化版 Conventional Commits）

| 前缀 | 用于 |
|---|---|
| `feat:` | 新增能力/文件 |
| `fix:` | 修正错误行为 |
| `eval:` | 评测用例与评分标准 |
| `docs:` | 文档 |
| `refactor:` | 结构调整，不改行为 |
| `chore:` | 杂项 |

例：`fix(core): 危机场景禁用比喻，补 3 条约束`

## PR 检查清单

复制到 PR 描述里：

```markdown
- [ ] 没有提交原书内容（PDF / 长段摘录 / OCR 文本）
- [ ] 已跑 evals，说明改动前后的分数变化
- [ ] 若改了 prompt，说明了「为什么这么改」，而不只是「改了什么」
- [ ] 危机类用例（crisis-*）未回退
- [ ] 遵守 CC BY-NC-ND 4.0（未引入需演绎授权的内容）
```

## 关于「我觉得它答得不好」

这是最好的 Issue。但请描述**可复现的输入**，而不是"感觉不够禅"。
"不够禅"通常意味着：太长了、太多建议了、用词开始飘了。请指出是哪一种。

---

> 改这个项目最好的方式，是先拿它聊一次。你自己被哪句话硌到，那里就是该改的地方。
