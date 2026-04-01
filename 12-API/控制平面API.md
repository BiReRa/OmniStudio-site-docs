# 控制平面 API

OmniInfer Gateway 提供一组控制平面 API，用于查看系统状态、选择后端和切换模型。

## `GET /health`

返回 Gateway 和后端引擎的运行状态。

## `GET /omni/state`

返回当前系统状态，包括：

- 当前选中的后端
- 当前加载的模型
- 当前运行时状态

## `GET /omni/backends`

列出所有支持的后端引擎及其选中状态。

## `POST /omni/backend/select`

选择指定后端。

请求体示例：

```json
{"backend": "llama.cpp(CPU)"}
```

## `POST /omni/backend/stop`

停止当前运行的后端进程。

## `GET /omni/models`

列出模型目录下所有可用的 GGUF 模型。

## `POST /omni/model/select`

选择并加载模型。Gateway 会自动停止当前模型、启动后端进程并加载新模型。

请求体示例：

```json
{
  "model": "model-name.gguf",
  "mmproj": "mmproj-F32.gguf"
}
```

参数说明：

- `model`：必填，模型文件名或绝对路径
- `mmproj`：可选，VLM 多模态投影文件，省略时自动检测
