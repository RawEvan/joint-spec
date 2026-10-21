# 卯合开发（Joint-spec Development）

实现可换，接合共用。

*Swappable implementations; shared joints.*

接合规格（SPEC、schema、conformance）是耐久的卯；实现是可换的榫。人（或 Agent）定接合；Agent 做出守约且可替换的实现。对接靠一致性套件，不靠某一份 UI 或 store 冻结。

本仓只提供**概念与做法**：原则、版本管理、开新协议的脚手架、协议族索引。不承载某一线协议的 JSON Schema。

[English](README.en.md)

## 与 Spec-Driven Development 的差别

| | Spec-Driven Development | 卯合开发 |
| --- | --- | --- |
| 规格角色 | 一份产品意图 | 多方共用的接合面 |
| 实现 | 生成并盯牢一份 | 可换的守约实现 |
| 对接 | 产品验收 | conformance（合榫检验） |

## 读什么

| 文档 | 内容 |
| --- | --- |
| [docs/PRINCIPLES.md](docs/PRINCIPLES.md) | 十条原则 |
| [docs/VERSIONING.md](docs/VERSIONING.md) | 版本管理（三层分号） |
| [docs/NEW_PROTOCOL.md](docs/NEW_PROTOCOL.md) | 怎么开新协议 |
| [docs/PROJECT_JOINTS.md](docs/PROJECT_JOINTS.md) | 交付链上的四份协议 |
| [docs/PROTOCOL_INDEX.md](docs/PROTOCOL_INDEX.md) | 协议族索引 |
| [templates/protocol-repo/](templates/protocol-repo/) | 可拷贝的协议仓骨架 |

## 许可证

MIT。见 [LICENSE](LICENSE)。
