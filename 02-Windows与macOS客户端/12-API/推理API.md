# 推理 API

OmniStudio 客户端背后对外提供 OpenAI 兼容的推理接口，便于现有应用无缝接入。

## 关于 `GET /v1/models`

当前 OmniInfer **不维护** `GET /v1/models`。  
如果你需要查看当前状态或已加载模型，请改用：

- `GET /health`
- `GET /omni/state`

## `POST /v1/chat/completions`

发送聊天补全请求。

请求体示例：

```json
{
  "messages": [
    {"role": "system", "content": "You are a helpful assistant."},
    {"role": "user", "content": "Hello!"}
  ],
  "stream": false,
  "temperature": 0.7,
  "max_tokens": 1024
}
```

## 常用参数

| 参数 | 说明 |
|------|------|
| `messages` | 对话消息数组 |
| `stream` | 是否使用流式输出 |
| `temperature` | 生成随机性 |
| `max_tokens` | 最大生成长度 |
| `top_p` / `top_k` | 采样控制参数 |
| `think` | thinking 开关 |

## 流式输出

当 `stream` 设置为 `true` 时，接口会返回 SSE 流式响应，适合网页聊天界面做实时渲染。
