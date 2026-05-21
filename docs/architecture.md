# アーキテクチャ

## 論理構成

```text
AtomS3R (録音・再生・ボタンUI)
  -> Wi-Fi / HTTP multipart
Raspberry Pi 5 FastAPI Server
  -> OpenAI Speech-to-Text
  -> OpenAI LLM
  -> OpenAI Text-to-Speech
Raspberry Pi 5
  -> WAV返却
AtomS3R (再生)
```

## リポジトリ分割

- `openai-voice-terminal`:
  - Pi5 側サーバー実装
  - OpenAI API 連携
  - 音声変換処理
- `ATOMS3R-OpenAI-VoicePTT-HTTP`:
  - AtomS3R 側ファームウェア
  - 録音/送信/再生
  - A/B ボタン操作
- `openai-voice-terminal-system`:
  - 統合運用ドキュメント
  - セットアップ/運用/障害対応手順

## 設計上の制約

- AtomS3R 側はメモリ制約 (PSRAM/Heap) が強い
- HTTP 送信中 (`HTTPClient::POST`) はブロッキング
- 再生中の中断はチャンク化で実現
- 録音は PTT + 最大秒数制限で暴走防止
