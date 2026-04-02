# Linux 工作方式

## 与桌面客户端的区别

当前 OmniStudio 在 Linux 上没有独立图形客户端，主入口是 CLI。

你通常会这样使用它：

1. 准备一个本地 runtime backend
2. 运行 `./omniinfer backend list`
3. 选择 backend
4. 加载模型
5. 通过 `./omniinfer chat` 或本地 API 发起请求

## CLI 与 Gateway 的关系

Linux、macOS、Windows 的桌面模式都遵循同一条主链路：

- `./omniinfer` 是用户入口
- CLI 会自动检查本地 Gateway 是否已启动
- 如果未启动，CLI 会自动拉起 Gateway
- Gateway 再去管理具体 backend 进程或 embedded runtime

这意味着日常使用时，你通常不需要手动单独启动服务。

## Linux 上的主要价值

- 脚本友好，适合 shell、CI、本地自动化
- 易于显式管理模型路径、运行时路径和日志
- 更适合与已有开发环境、服务进程、终端工具集成
