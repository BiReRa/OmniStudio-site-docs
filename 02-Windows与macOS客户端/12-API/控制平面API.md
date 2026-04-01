# 控制平面 API

OmniInfer Gateway 提供一组控制平面 API，用于客户端查看状态、选择后端和切换模型。

## `GET /health`

返回 Gateway 和当前 runtime 的基本健康状态。

## `GET /omni/state`

返回当前系统状态，包括：

- 当前选中的 backend
- 当前加载的模型
- 当前 `ctx_size`
- 当前 `request_defaults`
- backend 是否 ready

## `GET /omni/backends`

列出本机可见 backend 及其状态。

## `GET /omni/thinking`

读取默认 thinking 状态。

## `POST /omni/thinking/select`

更新默认 thinking 状态。

## `POST /omni/backend/select`

选择指定 backend。

请求体示例：

```json
{"backend": "llama.cpp-cpu"}
```

## `POST /omni/backend/stop`

停止当前 runtime。

## `GET /omni/supported-models`

查看当前系统对应的 backend 分组模型 catalog。

## `GET /omni/supported-models/best`

查看经过 OmniInfer 选择后的推荐 backend 视图。

## `POST /omni/model/select`

选择并加载模型。

请求体示例：

```json
{
  "model": "C:/models/model-name.gguf",
  "mmproj": "C:/models/mmproj-F32.gguf"
}
```
