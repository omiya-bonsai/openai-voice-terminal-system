# Repository Policy

## Responsibilities

- `openai-voice-terminal`:
  - Pi5 implementation code
  - API integration behavior
  - server-side behavior changes
  - GitHub: [omiya-bonsai/openai-voice-terminal](https://github.com/omiya-bonsai/openai-voice-terminal)
- `ATOMS3R-OpenAI-VoicePTT-HTTP`:
  - device implementation code
  - button interaction
  - recording and playback control
  - GitHub: [omiya-bonsai/ATOMS3R-OpenAI-VoicePTT-HTTP](https://github.com/omiya-bonsai/ATOMS3R-OpenAI-VoicePTT-HTTP)
- `openai-voice-terminal-system`:
  - cross-repository documentation
  - setup, operations, and troubleshooting
  - summarized change history

## Change Workflow

1. Decide which repository owns the change
2. Implement and verify in the code repository
3. Update this documentation repository when the operating procedure or specification changes
4. Verify consistency across the three repositories when tagging or releasing

## Version Consistency

Always record the following together:

- AtomS3R tag
- Pi5 commit or tag
- Documentation repository commit

This makes it possible to trace a reproducible combination when troubleshooting.
