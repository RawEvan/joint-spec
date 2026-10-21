# Versioning

[中文](../VERSIONING.md)

Three layers; do not collapse them into one number.

| Layer | Where version lives | How it advances |
| --- | --- | --- |
| **Wire shape** | `protocol` + integer `version` on discovery/envelope; file `schema/<name>.vN.schema.json` | Breaking: new `vN+1` file and integer; keep old `vN` until deprecation. Non-breaking (optional fields old clients ignore): same integer; note compatibility in SPEC. |
| **This practice repo** | `CHANGELOG.md` and dates | Principle changes go in the changelog; never issued as wire versions |
| **Product builds** | Their own semver / app versions | Orthogonal to protocol integers; SDKs may declare a minimum protocol version |

## Negotiation and failure

- Clients declare the protocol version they speak, or accept only the version advertised by discovery.
- Servers serve only advertised versions. Mismatch → explicit error (e.g. `protocol_version_unsupported` plus the advertised list). No silent parse as another version.
- Sub-protocols on one origin each have their own version; discovery lists each.
- Conformance: one fixture suite per supported `vN`; delete the suite after deprecation.

## Deprecation

- After a new integer ships, keep the previous integer for an explicit window. Put the rule in that protocol’s SPEC (recommended: at least 90 days after the next integer publishes).
- During the window, discovery may advertise multiple versions; afterward, only the current one.
- Never silently try a new version then fall back to an old one in the same process for the same resource.
