# Setup Guide

## 1. Confirm Repository Locations

- Pi5 server: [omiya-bonsai/openai-voice-terminal](https://github.com/omiya-bonsai/openai-voice-terminal)
- AtomS3R client: [omiya-bonsai/ATOMS3R-OpenAI-VoicePTT-HTTP](https://github.com/omiya-bonsai/ATOMS3R-OpenAI-VoicePTT-HTTP)
- Integration documentation: `openai-voice-terminal-system`

## 2. Prepare the Pi5 Server

In `openai-voice-terminal`:

1. Create a Python virtual environment
2. Install `requirements.txt`
3. Configure OpenAI API credentials in `.env`
4. Start the server

Use the commands documented in the `openai-voice-terminal` README as the source of truth.

## 3. Prepare AtomS3R

In `ATOMS3R-OpenAI-VoicePTT-HTTP`:

1. Configure `config.h`
2. Set `VOICE_SERVER_URL` to the Pi5 endpoint
3. Install the required libraries
4. Flash the firmware and verify behavior

## 4. Connectivity Check

1. Ensure the Pi5 server is listening
2. Verify AtomS3R can record, upload, and play a reply
3. Verify B-button cancellation works as expected in supported phases
