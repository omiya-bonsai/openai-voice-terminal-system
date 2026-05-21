# System Overview

## Purpose

Operate a voice interaction system where AtomS3R records audio, Raspberry Pi 5 calls OpenAI APIs, and reply audio is returned to AtomS3R for playback.

## Components

- Client: AtomS3R + Atomic Voice Base + Dual Button Unit
- Server: Raspberry Pi 5 (`openai-voice-terminal`)
- External API: OpenAI (Speech-to-Text / LLM / Text-to-Speech)

## Current Interaction Model

- Button A: push-to-talk recording (record while pressed)
- Button B: cancel request
  - During recording: cancels at chunk boundaries
  - During reply receive: cancels in receive loop
  - During playback: cancels at playback chunk boundaries
  - During upload (`http.POST` call): immediate cancel is not available due to library behavior

## Data Flow

1. Record voice on AtomS3R
2. Build WAV
3. Send multipart POST to Pi5 HTTP endpoint
4. Pi5 calls OpenAI APIs
5. Pi5 returns WAV
6. AtomS3R plays reply audio
