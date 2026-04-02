# llama.cpp

`llama.cpp` 是当前 OmniStudio Linux 形态下最核心、最成熟的后端家族。

## 当前 Linux 相关 backend

- `llama.cpp-linux`
- `llama.cpp-linux-rocm`
- `llama.cpp-linux-vulkan`
- `llama.cpp-linux-s390x`
- `llama.cpp-linux-openvino`

## 它为什么重要

- 支持 GGUF
- 同时覆盖文本和多模态链路
- 自带 OpenAI 兼容 server 语义
- 在 Linux 上容易通过脚本构建与打包

## 常见路径

排查或手动配置时，常见路径包括：

- `scripts/platforms/linux/...`
- `.local/runtime/linux/...`
- `runtime/...`

而不是旧的 `platform/...` 路径。
