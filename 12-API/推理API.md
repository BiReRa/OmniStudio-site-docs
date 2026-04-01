# 推理 API

OmniStudio 对外提供 OpenAI 兼容的推理接口，便于现有应用无缝接入。

## `GET /v1/models`

列出当前已加载模型。该接口通常由 Gateway 代理到后端引擎。

## `POST /v1/chat/completions`

发送聊天补全请求。

请求体示例：

```json
{
  "model": "model-name",
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

## 流式输出

当 `stream` 设置为 `true` 时，接口会返回 SSE 流式响应，适合网页聊天界面做实时渲染。

## 接口定位

如果你的文档网站要支持“开发者 / API 参考”双入口，这一页适合作为推理接口总览页，而更细的请求参数说明可以后续继续下钻。
