# llama.cpp 引擎

`llama.cpp` 是当前 OmniStudio 的默认推理后端，基于 [ggerganov/llama.cpp](https://github.com/ggerganov/llama.cpp) 构建。

## 特点

- 支持 GGUF 格式模型
- CPU 推理性能稳定，支持 GPU 加速
- 可运行在 Windows、macOS、Linux
- 支持多种量化格式，从 `Q2_K` 到 `F16`
- 自带 OpenAI 兼容 API 服务能力

## Windows 构建工具链

- 推荐：Visual Studio 2022 Build Tools
- 备选：MinGW-w64（`posix` 线程模型）
- 不推荐：MinGW-w64（`win32` 线程模型）

## 查看当前引擎版本

```bash
curl http://127.0.0.1:9000/health
OmniInfer/platform/Windows/llama.cpp-CPU/bin/llama-server.exe --version
```

建议在版本更新说明中同步记录 `llama-server` 的来源版本和对应兼容性变化。
