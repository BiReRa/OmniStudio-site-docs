# 控制平面 API

本地 Gateway 默认监听：

```text
http://127.0.0.1:9000
```

## `GET /health`

返回 Gateway 健康状态，以及当前 backend / model 快照。

## `GET /omni/state`

返回：

- 当前选中的 backend
- 当前加载模型
- `ctx_size`
- `request_defaults`
- backend 是否 ready
- 本地可见 backend 列表

## `GET /omni/backends`

列出当前机器上的本地 backend 及其状态。

## `GET /omni/supported-models`

按系统返回 backend 分组的支持模型 catalog。

常见形式：

```text
GET /omni/supported-models?system=linux
```

## `GET /omni/supported-models/best`

返回经过 OmniInfer 选择后的“最佳 backend 视图”，便于直接看每个量化的推荐 backend。

## `GET /omni/thinking`

读取默认 thinking 状态。

## `POST /omni/thinking/select`

更新默认 thinking 状态，例如：

```json
{"enabled": false}
```

## `POST /omni/backend/select`

切换当前 backend，例如：

```json
{"backend": "llama.cpp-linux"}
```

## `POST /omni/model/select`

加载模型，可选指定：

- `backend`
- `mmproj`
- `launch_args`
- `request_defaults`
- `ctx_size`

## `POST /omni/backend/stop`

停止当前 runtime。

## `POST /omni/shutdown`

停止本地 Gateway。
