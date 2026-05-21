# セットアップ手順

## 1. リポジトリ配置を確認

- Pi5 サーバー: [omiya-bonsai/openai-voice-terminal](https://github.com/omiya-bonsai/openai-voice-terminal)
- AtomS3R: [omiya-bonsai/ATOMS3R-OpenAI-VoicePTT-HTTP](https://github.com/omiya-bonsai/ATOMS3R-OpenAI-VoicePTT-HTTP)
- 統合ドキュメント: `openai-voice-terminal-system`

## 2. Pi5 サーバーの準備

`openai-voice-terminal` で実施:

1. Python 仮想環境を作成
2. `requirements.txt` をインストール
3. `.env` に OpenAI API キー等を設定
4. サーバーを起動

実行コマンドは `openai-voice-terminal` 側 README の記載を正とする。

## 3. AtomS3R 側の準備

`ATOMS3R-OpenAI-VoicePTT-HTTP` で実施:

1. `config.h` を設定
2. `VOICE_SERVER_URL` を Pi5 の URL に合わせる
3. 必要ライブラリを導入
4. 書き込み後に動作確認

## 4. 疎通確認

1. Pi5 サーバーが待ち受けている状態にする
2. AtomS3R で A 押下録音 -> 送信 -> 応答再生まで確認
3. B キャンセルが各状態で期待どおりか確認
