# 怎么开新协议

[English](en/NEW_PROTOCOL.md)

1. 复制 [templates/protocol-repo/](../templates/protocol-repo/) 到新仓。
2. 填写 `docs/SPEC.md`（语义）与 `schema/<name>.v1.schema.json`（形状）。
3. 准备 `schema/fixtures/valid` 与 `invalid`；用校验器锁住。
4. 提供薄 SDK（类型 + 校验即可）与可跑的 example；example 不是真相源。
5. 写黑盒 conformance，对任意合规 `baseUrl` 可跑。
6. 在本仓 [PROTOCOL_INDEX.md](PROTOCOL_INDEX.md) 增补链接（仅公开、已存在的协议仓）。
7. 变更时四层同改：SPEC、schema、fixtures、SDK、测试。见 [PRINCIPLES.md](PRINCIPLES.md)。
8. 版本按 [VERSIONING.md](VERSIONING.md)。

## 变更清单（协议仓 AGENTS 可拷贝）

修改行为或字段时同时更新：

- `docs/SPEC.md`（及英文镜像若有）
- `schema/<name>.vN.schema.json` 与 `schema/fixtures/`
- SDK
- 相关测试与 conformance
