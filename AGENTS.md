# AGENTS.md — tts-api

## Project Summary

Protocol Buffer definitions for the Techmo TTS (Text-to-Speech) gRPC API v3. This is a proto-only repository — it contains no Python, no build system, and no runnable code. It serves as the single source of truth for the API contract and is consumed as a git submodule by downstream repos.

**API version:** `VERSION.md`
**Proto package:** `techmo.tts.api.v3`

## Repo Layout

```
proto/
  techmo_tts.proto   # full gRPC service definition
doc/
  Documentation.md   # human-readable API reference
VERSION.md           # single version source (semver, plain text)
CHANGELOG.md         # API change history
```

## gRPC Service

The `TTS` service exposes:

| RPC | Type | Purpose |
|-----|------|---------|
| `GetServiceVersion` | unary | Server version string |
| `GetResourcesId` | unary | Resource bundle identifier |
| `ListVoices` | unary | Available synthesis voices |
| `ListSoundIcons` | unary | Available sound icons |
| `ListRecordings` | unary | Custom recordings inventory |
| `ListLexicons` | unary | Pronunciation lexicons inventory |
| `Synthesize` | unary | Full audio response |
| `SynthesizeStreaming` | server-streaming | Incremental audio chunks |
| `GetChannelsUsage` | unary | Concurrency / license info |
| `PutRecording` / `DeleteRecording` / `GetRecording` | unary | Custom recording CRUD |
| `PutLexicon` / `DeleteLexicon` / `GetLexicon` | unary | Lexicon CRUD |

## How This Repo Is Used

Consumed as a git submodule at path `submodules/tts-service-api` in:
- **tts-api-python** — generates Python gRPC stubs, published as the `tts-api` package
- **tts-client-python** — generates stubs locally for use in the Python client

When this proto changes, both downstream repos must regenerate their stubs and release new versions.

## Versioning

`VERSION.md` contains the semver string (e.g. `3.2.0`). The major version tracks breaking API changes. Tag releases as `vX.Y.Z` after updating `VERSION.md` and `CHANGELOG.md`.

## Commit Conventions

`feat:`, `fix:`, `chore:`, `docs:` — conventional commits. No generated files are ever committed here.
