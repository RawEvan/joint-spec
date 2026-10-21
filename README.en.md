# Joint-spec Development

Swappable implementations; shared joints.

The joint (SPEC, schema, conformance) is durable. Implementations are swappable tenons. People or agents define the joint; agents produce conforming, replaceable implementations. Interop is proven by conformance suites, not by freezing one UI or store.

This repository is **concepts and practice** only: principles, versioning, scaffolding for new protocols, and a protocol family index. It does not host wire-protocol JSON Schemas.

[中文](README.md)

## Versus Spec-Driven Development

| | Spec-Driven Development | Joint-spec Development |
| --- | --- | --- |
| Spec role | One product intent | Shared joint across parties |
| Implementation | Generate and lock one | Swappable conforming builds |
| Proof | Product acceptance | Conformance |

## What to read

| Doc | Content |
| --- | --- |
| [docs/en/PRINCIPLES.md](docs/en/PRINCIPLES.md) | Ten principles |
| [docs/en/VERSIONING.md](docs/en/VERSIONING.md) | Versioning (three layers) |
| [docs/en/NEW_PROTOCOL.md](docs/en/NEW_PROTOCOL.md) | Starting a new protocol |
| [docs/en/PROTOCOL_INDEX.md](docs/en/PROTOCOL_INDEX.md) | Protocol family index |
| [templates/protocol-repo/](templates/protocol-repo/) | Copyable protocol-repo skeleton |

## License

MIT. See [LICENSE](LICENSE).
