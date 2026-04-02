# Curl 与 Python 示例

## Curl

```bash
curl -X POST http://127.0.0.1:9000/v1/chat/completions \
  -H "Content-Type: application/json" \
  -d '{
    "messages": [
      {"role": "user", "content": "Say hello in one short sentence."}
    ],
    "stream": false,
    "think": false,
    "max_tokens": 64,
    "temperature": 0.2
  }'
```

## Python

```python
from openai import OpenAI

client = OpenAI(
    base_url="http://127.0.0.1:9000/v1",
    api_key="omniinfer-local",
)

resp = client.chat.completions.create(
    model="local-model",
    messages=[
        {"role": "user", "content": "Say hello in one short sentence."}
    ],
    stream=False,
)

print(resp.choices[0].message.content)
```

如果你的应用会自己控制本地模型加载，则也可以先调用控制平面接口，再走这里的推理接口。
