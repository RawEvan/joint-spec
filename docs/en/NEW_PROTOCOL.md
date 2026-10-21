# Starting a new protocol

[中文](../NEW_PROTOCOL.md)

1. Copy [templates/protocol-repo/](../../templates/protocol-repo/) into a new repository.
2. Fill `docs/SPEC.md` (semantics) and `schema/<name>.v1.schema.json` (shape).
3. Add `schema/fixtures/valid` and `invalid`; lock them with a validator.
4. Ship a thin SDK (types + validation) and a runnable example; the example is not the source of truth.
5. Write black-box conformance against any compliant `baseUrl`.
6. Add a link in this repo’s [PROTOCOL_INDEX.md](PROTOCOL_INDEX.md) (only public, already-existing protocol repos).
7. Change four layers together: SPEC, schema, fixtures, SDK, tests. See [PRINCIPLES.md](PRINCIPLES.md).
8. Version per [VERSIONING.md](VERSIONING.md).

## Change checklist (copy into a protocol AGENTS.md)

When behavior or fields change, update together:

- `docs/SPEC.md` (and English mirror if any)
- `schema/<name>.vN.schema.json` and `schema/fixtures/`
- SDK
- Related tests and conformance
