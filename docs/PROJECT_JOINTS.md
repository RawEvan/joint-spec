# 交付链上的接合

[English](en/PROJECT_JOINTS.md)

从客户资料到交付裁定，用四份协议，每份一个 origin。本仓只说明它们怎么拼，不放线协议的 JSON Schema。

| 协议 | 字符串 | 资源 |
| --- | --- | --- |
| Open Case | `open-case` | 录入容器、不可改的原始资料、引用这些资料的分析稿 |
| Open Work | `open-work` | 可领取的工作项 |
| Open Run | `open-run` | 一次执行。中途人机输入不在 version 1 |
| Open Procedure | `open-procedure` | 一条步骤脊柱、证据、成稿快照、客户裁定 |

测试证据和读者成稿共用 `open-procedure` 的步骤表。成稿复制发布当时的步骤，证据不改步骤正文。

资源可选 `links[]`：`rel`、`protocol`、`version`、`origin`、`id`。`rel` 只允许 `derived_from`、`executes`、`evidenced_by`、`published_as`、`reviewed_by`。各协议把这组字段写进自己的 schema。本仓不另做一份汇总正文的协议。

编排方把链接写上。协议不代为拉取另一个 origin 的正文。

索引只收录已经公开、且能取回的仓库。见 [PROTOCOL_INDEX.md](PROTOCOL_INDEX.md)。
