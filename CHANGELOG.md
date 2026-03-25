# Techmo TTS Service API repository changelog

For organizational reasons, the description of previous API changes (for all the versions below 3.0.0) can be found in a separate repository: https://github.com/techmo-pl/tts-client


## [3.2.0] - 2024-03-26

### Added

- Support of SSML `<mark>` tags in service response


## [3.1.0] - 2023-12-04

### Added

- RTF (**R**eal **T**ime **F**actor) throttling and maximum frame size control


## [3.0.0] - 2023-10-04

### Added

- Handling of voice variants
- `VoiceProfile` message which contains `voice_name`, `voice_variant`, and `language` fields
- `language_code` field in addition to `voice_name` and `voice_variant` for recording identification
- `GetServiceVersion()`, `GetResourcesId()`, `GetChannelsUsage()`, and `ListSoundIcons()` calls
- Calls for configuration of predefined recordings
- `OGG_OPUS`, `A_LAW`, and `MU_LAW` audio encodings
- Array of warnings returned by `Synthesize()` and `SynthesizeSteaming()`
- `NoLookupBehaviour` field in lexicons handling calls
- Configuration parameter for silence duration between segments

### Changed

- Change package name to `techmo.tts.api.v3`
- Move `AudioConfig` out of `SynthesisConfig` and renamed it to `OutputConfig`
- `gender` and `age` in `Voice` are now optional
- Simplify `SynthesizeResponse` message
- Some minor renamings and clarifications

### Removed

- `GENDER_UNSPECIFIED` and `AGE_UNSPECIFIED` enumerators


## [2.0.0]

Reserved for compatibility with TTS services 2.x, now obsolete.


## [1.0.0]

Reserved for compatibility with TTS services 1.x, now obsolete.
