# 流式输出与 Thinking

## 流式输出

CLI 默认会把对话结果以流式方式打印到终端。

这适合：

- 交互式问答
- 长回答场景
- 观察模型实时输出节奏

如果你想关闭流式输出：

```bash
./omniinfer chat --no-stream --message "Hello"
```

## Thinking 默认值

OmniInfer 支持查看和设置默认 thinking 状态：

```bash
./omniinfer thinking show
./omniinfer thinking set on
./omniinfer thinking set off
```

## 单次请求覆盖

```bash
./omniinfer chat --think on --message "Explain your reasoning briefly."
./omniinfer chat --think off --message "Just answer directly."
```

## 你需要知道的一点

不同模型对 thinking 的模板支持并不完全一致。

因此：

- CLI 和 Gateway 会尽量统一开关语义
- 但最终呈现仍取决于具体模型模板与后端行为
