# システム概要

## 目的

AtomS3R から音声を収録し、Raspberry Pi 5 経由で OpenAI API を呼び出し、
応答音声を AtomS3R に返して再生する音声対話システムを運用する。

## 構成要素

- クライアント: AtomS3R + Atomic Voice Base + Dual Button Unit
- サーバー: Raspberry Pi 5 (`openai-voice-terminal`)
- 外部API: OpenAI (Speech-to-Text / LLM / Text-to-Speech)

## 現在の操作モデル

- A ボタン: 押下中のみ録音 (PTT)
- B ボタン: キャンセル要求
  - 録音中: チャンク境界で中断
  - 応答受信中: 受信ループで中断
  - 再生中: 再生チャンク境界で中断
  - 送信中 (`http.POST` 呼び出し中): ライブラリ都合で即時中断不可

## データフロー

1. AtomS3R で音声録音
2. WAV 生成
3. Pi5 の HTTP エンドポイントへ multipart POST
4. Pi5 が OpenAI API 呼び出し
5. Pi5 が WAV を返却
6. AtomS3R が返答音声を再生
