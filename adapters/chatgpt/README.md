# ChatGPT / 通用大模型接入说明

## 方式一：自定义 GPT（Custom GPT）

1. 打开 ChatGPT → Explore GPTs → Create
2. **Instructions** 一栏粘贴 [`core/system-prompt.md`](../../core/system-prompt.md) 全文
3. **Conversation starters** 填：

```
今天是你余生的第一天，有什么想聊聊的吗？
最近总是很焦虑，心静不下来，该怎么办？
怎么才能不那么在意别人的眼光和评价？
```

4. Knowledge（可选）：上传 `knowledge/quotes.md` 与 `knowledge/INDEX.md`
   ⚠️ **不要上传原书 PDF。** 自定义 GPT 的 Knowledge 文件可被其他用户通过提示词诱导调取，属于「向公众提供作品」。
5. 关闭 Code Interpreter / Web Browsing（本角色不需要，且会增加跑题概率）
6. 模型建议：具备较强中文长文本理解能力的版本；温度 0.7–0.9（过低会变得说教，过高会开始编禅语）

## 方式二：API / 任何兼容 OpenAI 协议的模型

```python
import os
from openai import OpenAI

SYSTEM = open("core/system-prompt.md", encoding="utf-8").read()

client = OpenAI(api_key=os.environ["OPENAI_API_KEY"], base_url=os.environ.get("BASE_URL"))

resp = client.chat.completions.create(
    model="gpt-4o",            # 或 deepseek-chat / qwen-max / glm-4 ...
    temperature=0.8,
    max_tokens=300,            # 刻意压低：强制短回复
    messages=[
        {"role": "system", "content": SYSTEM},
        {"role": "user", "content": "我妈又开始催婚了，我一听就烦。"},
    ],
)
print(resp.choices[0].message.content)
```

### 两个工程细节，别忽略

| 细节 | 为什么 |
|---|---|
| `max_tokens=300` | Prompt 里写"≤5 句"是软约束，长度上限是硬约束。两个一起用才稳。 |
| 多轮时保留完整历史 | 小空空的"短"依赖上下文。每轮截断历史会让它反复问同样的问题。 |

## 方式三：国内模型

同一份 system prompt 可直接用于 DeepSeek、通义千问、GLM、Kimi、豆包等。经验值：

- **中文语感最强**：DeepSeek-V3 / Qwen-Max（对"短句 + 反问"的遵循度较好）
- **容易过度温柔**：部分模型会加上"亲爱的""抱抱你"，需要在 prompt 末尾追加一行：`不要使用亲昵称呼，不要用"抱抱""加油"这类词。`
- **容易说教**：追加：`不要给出步骤化的建议，不要用"首先/其次/最后"。`

## 附：Claude 的 `system` 参数

```python
import anthropic
client = anthropic.Anthropic()
msg = client.messages.create(
    model="claude-sonnet-4-5",
    system=open("core/system-prompt.md", encoding="utf-8").read(),
    max_tokens=300,
    messages=[{"role": "user", "content": "最近总觉得没意思。"}],
)
```
