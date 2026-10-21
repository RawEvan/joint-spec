# Joints on the delivery path

[中文](../PROJECT_JOINTS.md)

Four protocols cover the path from source material to a customer review. Each protocol is one origin. This repository explains how they fit. It does not store their JSON Schemas.

| Protocol | String | Resources |
| --- | --- | --- |
| Open Case | `open-case` | intake container, immutable sources, analyses that cite those sources |
| Open Work | `open-work` | claimable work items |
| Open Run | `open-run` | one execution. Mid-run human input is not in version 1 |
| Open Procedure | `open-procedure` | one step list, evidence, edition snapshots, reviews |

Evidence and reader editions share the Open Procedure step list. An edition copies the steps at publish time. Evidence does not change step text.

A resource may carry `links[]`: `rel`, `protocol`, `version`, `origin`, `id`. `rel` is only `derived_from`, `executes`, `evidenced_by`, `published_as`, or `reviewed_by`. Each protocol embeds that object in its own schema.

The orchestrator writes the links. A protocol does not fetch another origin's body.

The index lists only public repositories that can be fetched. See [PROTOCOL_INDEX.md](PROTOCOL_INDEX.md).
