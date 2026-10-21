# Joint-spec Development: ten principles

[中文](../PRINCIPLES.md)

1. **Change four layers together**  
   Semantics in `docs/SPEC.md`; shape in `schema/<name>.vN.schema.json`; validate with `schema/fixtures/{valid,invalid}`; ship SDK and tests. Examples may run but are not the shape source of truth.

2. **Protocol repo ≠ product host**  
   The protocol does not require one UI or one transport. Product hosts may reimplement the wire; they must not become the schema source.

3. **Capability flags**  
   Closed boolean map; missing key means false. Unsupported routes return fixed `capability_unsupported`. Never fake support with empty lists.

4. **Versioning**  
   See [VERSIONING.md](VERSIONING.md). Stable `protocol` string plus integer `version` on the envelope. Breaking shape changes get a new schema filename and integer. No silent dual-read.

5. **Identity hygiene**  
   Cross-device and local ids live in separate fields.

6. **Errors**  
   Use `application/problem+json`. Unknown fields fail validation; do not ignore them.

7. **Extension bags**  
   Vendor fields go in `annex` or `ext`; keep the core schema clean.

8. **Conformance**  
   Black-box suites against any compliant `baseUrl`.

9. **Federation stays on the client**  
   The protocol describes one origin. Merging providers is orchestrator work.

10. **No product state machine in the protocol**  
    Protocols own lifecycle and opaque payloads; hosts own business state. Executors do not branch on business labels.

## When agents create fast

Do not freeze UI, stores, or demo data into the joint. Freeze discovery, capabilities, lifecycle, event shapes, and error codes. Domain objects stay on the host or in opaque tags; executors do not interpret them.
