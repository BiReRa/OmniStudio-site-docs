# OmniStudio 文档中心

OmniStudio 当前有两条并行的使用形态，这套站点文档也按这两条主线组织：

- **Windows / macOS 客户端**
  以图形界面为主，适合桌面端交互式使用
- **Linux CLI**
  以 `./omniinfer` 和本地 Gateway 为主，适合终端、自动化和开发集成

## 如何阅读这套文档

如果你使用的是桌面客户端，请从：

- [Windows 与 macOS 客户端](02-Windows与macOS客户端/README.md)

开始。

如果你使用的是 Linux CLI，请从：

- [Linux CLI](03-Linux-CLI/README.md)

开始。

## 文档设计原则

- 让不同平台形态共存，而不是互相覆盖
- 用户先进入自己的主线，再阅读对应的功能、开发和排障内容
- 当前 OmniInfer 已落地能力与未来规划能力分开表述
- 所有实现相关说明尽量对齐当前仓库行为

## 站点结构

左侧目录由 [SUMMARY.md](./SUMMARY.md) 驱动。

推荐理解方式是：

1. 先明确你使用的是客户端还是 Linux CLI
2. 进入对应的大类
3. 在该主线下继续阅读模型、API、性能和排障章节
