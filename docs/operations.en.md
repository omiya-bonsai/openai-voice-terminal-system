# Operations Guide

## Normal Startup

1. Start the Pi5 server
2. Boot AtomS3R
3. Confirm Wi-Fi connection
4. Start a conversation with button A

## Button Behavior

- A: push-to-talk recording
- B: cancel

Current cancel behavior:

- During recording: supported
- During reply receive: supported
- During playback: supported
- During HTTP upload: immediate cancellation is not supported

## Troubleshooting Flow

1. Check whether AtomS3R is connected to Wi-Fi
2. Check whether `VOICE_SERVER_URL` is correct
3. Check whether the Pi5 server is running
4. Check whether the OpenAI API key is configured correctly on Pi5
5. Check whether returned WAV format matches AtomS3R playback assumptions

## Logs To Inspect

- AtomS3R serial log:
  - button events
  - upload start/end
  - cancel detection
- Pi5 server log:
  - request receipt
  - OpenAI API call flow
  - returned audio size
