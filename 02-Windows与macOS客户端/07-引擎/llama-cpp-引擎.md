# llama.cpp 引擎

`llama.cpp` 仍然是当前 OmniStudio 客户端形态下最核心的后端家族之一。

## 特点

- 支持 GGUF 格式模型
- CPU 推理稳定，并支持多种 GPU 相关后端
- 可运行在 Windows、macOS、Linux
- 支持从 `Q2_K` 到 `F16` 的多种量化
- 具备 OpenAI 兼容 server 语义

## Windows / macOS 相关 backend

- Windows：`llama.cpp-cpu`、`llama.cpp-cuda`、`llama.cpp-vulkan`、`llama.cpp-sycl`、`llama.cpp-hip`、`llama.cpp-windows-arm64`
- macOS：`llama.cpp-mac`、`llama.cpp-mac-intel`

## 查看当前 runtime 版本

源码仓库模式下，典型路径例如：

```powershell
.\.local\runtime\windows\llama.cpp-cpu\bin\llama-server.exe --version
```

或在发布包中：

```powershell
.\runtime\llama.cpp-cpu\bin\llama-server.exe --version
```

macOS 同理，可在对应 `runtime` 或 `.local/runtime` 目录下查看。
