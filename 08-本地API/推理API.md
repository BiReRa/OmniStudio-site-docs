# 推理 API

## 主入口

当前稳定的推理入口是：

```text
POST /v1/chat/completions
```

这是一个 OpenAI 兼容接口。

## 最小请求体

```json
{
  "messages": [
    {
      "role": "user",
      "content": "Hello"
    }
  ],
  "stream": false
}
```

如果当前尚未加载模型，也可以在请求里直接带上：

- `model`
- `backend`
- `mmproj`
- `ctx_size`

## OmniInfer 扩展字段

为了兼容本地 runtime 管理，OmniInfer 在标准 OpenAI 风格之上扩展了几个字段：

- `backend`
- `mmproj`
- `launch_args`
- `request_defaults`
- `ctx_size`
- `think`

## 关于 `GET /v1/models`

当前 OmniInfer **不维护** `GET /v1/models`。

如果你需要查看状态或当前加载模型，请改用：

- `GET /health`
- `GET /omni/state`
