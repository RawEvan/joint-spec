# \<Protocol Name\> 1

Replace this file with protocol semantics.

- Protocol string: `\<protocol-id\>`
- Version: integer `1`
- Success media type: `application/vnd.\<id\>+json`
- Errors: `application/problem+json`

## Discovery

Document discovery path, capabilities (boolean map), and version advertisement.

## Versioning

Follow Joint-spec Development versioning: breaking shape → new `schema/*.vN.schema.json` and new integer; no silent dual-read.
