# OmniStudio 文档中心

这套文档面向当前 **OmniStudio Linux 形态** 编写。

在 Linux 上，OmniStudio 不是图形化客户端，而是基于 [OmniInfer](https://github.com/omnimind-ai/OmniInfer) 的一套本地 CLI 与 Gateway 工作流：

- 用户主要通过 `./omniinfer` 命令完成后端选择、模型加载和对话推理
- 本地 Gateway 负责统一管理后端生命周期，并暴露 OpenAI 兼容 API
- 模型、运行时、配置和日志都围绕 CLI 与 Gateway 组织

## 文档设计原则

- 以 Linux CLI 的真实操作路径为主，而不是桌面前端页面流程
- 先讲快速开始和核心任务，再进入 API、架构、性能和排障
- 尽量只记录当前 OmniInfer 已实现、已验证的能力
- 对规划中的后端能力单独归档，避免与当前可用能力混淆

## 你会在这里看到什么

- 如何准备 Linux 运行环境
- 如何列出和选择后端
- 如何获取、加载和切换模型
- 如何通过 CLI 进行文本和多模态推理
- 如何配置 Gateway、查看状态和定位日志
- 如何使用本地 OpenAI 兼容 API
- 如何理解当前引擎、性能和限制

## 文档导航

左侧目录入口以 [SUMMARY.md](./SUMMARY.md) 为准。

如果你是第一次使用，建议按下面顺序阅读：

1. `概览`
2. `快速开始`
3. `后端与运行时`
4. `模型与量化`
5. `获取与加载`
6. `对话与多模态`
7. `本地 API`
