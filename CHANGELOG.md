# Techmo TTS Service API repository changelog

For organizational reasons, the description of previous API changes (for all the versions below 3.0.0) can be found in a separate repository: https://github.com/techmo-pl/tts-client

## [3.0.0] - 2023-10-04

### Added
- Handling of voice variants
- `OGG_OPUS`, `A_LAW` and `MU_LAW` audio encodings
- Phonemes pitch and duration control values in synthesize config
- ServiceVersion and ResourcesId calls
- ListSoundIcons call
- VoiceProfile message which contains `voice_name`, `voice_variant`, and `language_code` fields
- Calls for configuration of predefined recordings
- GetChannelsUsage() cal
- Array of warnings returned by Synthesize, SynthesizeSteaming
- Per phoneme volume control
- NoLookupBehaviour field in lexicons handling calls
- Moved AudioConfig out of SynthesisConfig and renamed it to OutputConfig

### Removed
- Phoneme Modifiers array in SynthesisConfig (now should be passed as custom attributes in SSML <phoneme> tag)

### Changed
- change package name to techmo.tts.api.v3
- Reorganized SynthesizeConfig message (breaking change from 2.x)
- Simplified SynthesizeResponse message (breaking change from 2.x)
- Separated listing requests and responses between SoundIcons and Recordings
- gender and age in Voice are now optional
- Moved documentation out of comments in protos to the separate file