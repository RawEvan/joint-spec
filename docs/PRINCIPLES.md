# 卯合开发：十条原则

[English](en/PRINCIPLES.md)

1. **四层同改**  
   语义在 `docs/SPEC.md`；形状在 `schema/<name>.vN.schema.json`；用 `schema/fixtures/{valid,invalid}` 校验；配 SDK 与测试。例子可跑，但不是形状真相源。

2. **协议仓 ≠ 产品宿主**  
   协议仓不绑某一 UI 或某一运输为必选。产品宿主可重实现线格式，不得成为 schema 源。

3. **能力旗标**  
   闭集 boolean；缺键视为 false。不支持时返回固定 `capability_unsupported`。禁止用空列表假装支持。

4. **版本**  
   见 [VERSIONING.md](VERSIONING.md)。envelope 上稳定 `protocol` 字符串 + 整数 `version`。破坏性改形状 → 新 schema 文件名与新整数。禁止静默双读。

5. **身份卫生**  
   跨设备 id 与本机 id 分字段存放，不得混成同一字段。

6. **错误**  
   错误用 `application/problem+json`。请求出现 schema 未定义字段时校验失败，不忽略。

7. **扩展袋**  
   厂商字段放 `annex` 或 `ext`，核心 schema 保持干净。

8. **一致性套件**  
   黑盒 conformance 打任意合规 `baseUrl`（合榫检验）。

9. **联邦在客户端**  
   协议描述一个 origin。多提供方合并是编排方的工作，不塞进协议。

10. **协议不拥有产品业务状态机**  
    协议管生命周期与不透明载荷；业务态在宿主。执行方不按业务标签分支。

## Agent 创作快时

UI、具体 store、演示数据不要冻结进接合规格。只冻结发现文档、能力、生命周期、事件形状、错误码。领域对象放在宿主侧或不透明标签里，执行方不解释。
