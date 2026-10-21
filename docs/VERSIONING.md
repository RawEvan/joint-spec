# 版本管理

[English](en/VERSIONING.md)

管三层，不要混成一个数字。

| 层 | 版本写在哪 | 怎么升 |
| --- | --- | --- |
| **线协议形状** | discovery / envelope 的 `protocol` + 整数 `version`；文件 `schema/<name>.vN.schema.json` | 破坏性改形状：新 `vN+1` 文件 + 新整数；旧 `vN` 保留到弃用日。非破坏（只加可选字段且旧客户端可忽略）：同整数，SPEC 注明兼容。 |
| **本教法仓** | `CHANGELOG.md` 与日期 | 原则变更写 changelog；不向 discovery 发号 |
| **产品实现** | 各自 semver / 应用版本 | 与协议整数正交；SDK 可声明「最低支持的协议 version」 |

## 协商与失败

- 客户端声明自己会的协议 version，或只认 discovery 通告的那一个。
- 服务端只服务通告过的 version。对不上 → 明确错误（如 `protocol_version_unsupported` + 通告列表）。禁止静默按另一 version 解析。
- 同一 origin 上的多份子协议各自有 version；discovery 写清每一份。
- Conformance：每个仍支持的 `vN` 各跑一套 fixtures；弃用后删除 suite。

## 弃用节奏

- 新整数发布后，上一整数至少再保留一个明确窗口。窗口规则写进该协议的 SPEC（推荐：下一整数发布后再保留至少 90 天）。
- 窗口内 discovery 可同时通告多个 version；窗口外只通告当前。
- 禁止同一进程对同一资源「先试新 version 再回退旧 version」的静默双读。
