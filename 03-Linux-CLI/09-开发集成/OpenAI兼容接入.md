# OpenAI 兼容接入

## 为什么这一层重要

OmniStudio Linux CLI 适合人工使用，而 OpenAI 兼容 API 适合：

- 现有应用接入
- 脚本自动化
- 本地 agent / workflow
- IDE 插件或工具链适配

## Base URL

```text
http://127.0.0.1:9000
```

## 你通常只需要替换什么

- `base_url`
- `api_key` 策略（本地环境通常不强制）
- 模型加载流程

如果你的应用默认只会调用 `POST /v1/chat/completions`，接入成本通常很低。

## 推荐做法

- 启动前先通过 `/health` 或 `/omni/state` 做本地探活
- 把模型选择与加载作为应用启动或首个请求前置步骤
- 长会话应用自己维护 `messages`
