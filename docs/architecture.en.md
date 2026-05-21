# Architecture

## Logical Structure

```text
AtomS3R (recording, playback, button UI)
  -> Wi-Fi / HTTP multipart
Raspberry Pi 5 FastAPI Server
  -> OpenAI Speech-to-Text
  -> OpenAI LLM
  -> OpenAI Text-to-Speech
Raspberry Pi 5
  -> WAV response
AtomS3R (playback)
```

## Repository Split

- `openai-voice-terminal`:
  - Pi5 server implementation
  - OpenAI API integration
  - Audio conversion processing
- `ATOMS3R-OpenAI-VoicePTT-HTTP`:
  - AtomS3R firmware
  - Recording, upload, and playback
  - A/B button operation
- `openai-voice-terminal-system`:
  - Cross-repository operation documents
  - Setup, operation, and troubleshooting guides

## Design Constraints

- AtomS3R is constrained by PSRAM and heap limits
- HTTP upload with `HTTPClient::POST` is blocking
- Playback interruption is implemented by chunked playback
- Recording uses PTT plus a maximum duration guard
