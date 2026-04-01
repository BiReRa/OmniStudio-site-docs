# Backend 配置文件

## 作用

Backend profile 用于保存 backend-native 的高级参数，不用于保存基础用户输入。

这些 profile 会被创建在：

```text
~/.config/omniinfer/backend_profiles/<backend>.json
```

## 一个典型示例

```json
{
  "schema_version": 2,
  "backend": "llama.cpp-linux",
  "family": "llama.cpp",
  "load": {
    "extra_args": ["-ngl", "99", "-t", "8"]
  },
  "infer": {
    "extra_args": ["--top-k", "40", "--top-p", "0.9"]
  }
}
```

## 应该放什么

- backend 启动参数
- backend 原生推理参数

## 不应该放什么

- `-m/--model`
- `-mm/--mmproj`
- `--message`
- `--image`

这些基础输入应继续放在 CLI 主命令里。
