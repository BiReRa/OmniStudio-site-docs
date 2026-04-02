# Gateway 配置

## 配置文件位置

Gateway 会从应用根目录读取：

```text
config/omniinfer.json
```

在源码仓库里，这通常就是仓库根目录下的 `config/omniinfer.json`。

## 常见配置项

当前 OmniInfer 的稳定配置重点包括：

- `host`
- `port`
- `default_backend`
- `default_thinking`
- `window_mode`
- `startup_timeout`
- `runtime_root`
- `backends`

## Linux 常见环境变量覆盖

如果你只想快速覆盖某个 Linux backend 的关键位置或参数，也可以直接使用环境变量。

以 `llama.cpp-linux` 为例，常见变量包括：

- `OMNIINFER_LLAMA_CPP_LINUX_LAUNCHER_PATH`
- `OMNIINFER_LLAMA_CPP_LINUX_MODELS_DIR`
- `OMNIINFER_LLAMA_CPP_LINUX_NGL`
- `OMNIINFER_LLAMA_CPP_LINUX_CTX_SIZE`
- `OMNIINFER_LLAMA_CPP_LINUX_PARALLEL`
- `OMNIINFER_LLAMA_CPP_LINUX_CACHE_RAM`

## 常见命令行参数

如果你直接启动 Gateway：

```bash
python3 omniinfer_gateway.py --host 127.0.0.1 --port 9000
```

常见参数包括：

- `--host`
- `--port`
- `--default-backend`
- `--default-thinking`
- `--force-backend`
- `--window-mode`
- `--verbose`
- `--debug-body`
- `--startup-timeout`

日常 CLI 使用时，通常不需要手动启动 Gateway。

## 手动前台启动

```bash
./omniinfer serve
```

这在调试 Gateway 启动过程时很有用。
