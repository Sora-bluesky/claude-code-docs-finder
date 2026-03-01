# Claude Code Docs Finder

Claude Code の公式ドキュメントを日本語で検索できるツール。  
HTMLファイル1つで動作し、claude.ai の Artifact として使う。

## どんなツール？

検索ボックスに日本語で質問を入力すると、AIが [llms.txt](https://code.claude.com/docs/llms.txt)（公式ドキュメントの全ページ一覧）をリアルタイムで取得し、関連ページを3〜5件カード表示する。

キーワード検索ではなく **意味検索** なので、「エージェントチームについて知りたい」と入力すれば `agent-teams` のページがヒットする。

## 使い方（PCのみ）

1. このリポジトリの `claude-code-docs-search.html` を開く
2. 右上の **「Download raw file」** ボタンでダウンロード
3. PCブラウザで [claude.ai](https://claude.ai) を開く
4. チャット欄にHTMLファイルを添付して **「このHTMLをArtifactとして開いて」** と送信
5. Artifactが表示されたら、検索ボックスに日本語で質問を入力

> **スマホでは動きません。** モバイルアプリのArtifact環境はAPIリクエストの中継方式がPC版と異なり、レスポンス形式が変わるためJSONパースに失敗します。

## 必要なもの

- **Claude Pro / Max / Team** のいずれかのプラン
- APIキーは不要（claude.aiが認証を代行）
- 追加費用なし（サブスクリプションに含まれる）

## 仕組み

```
日本語で質問を入力
    ↓
Artifact内のJavaScriptがClaude APIにリクエスト
（claude.aiが認証を代行するのでAPIキー不要）
    ↓
AIが web_search で llms.txt をリアルタイム取得
    ↓
関連ページを3〜5件選定 → カード表示
    ↓
クリックで日本語版の公式ドキュメントへ
```

## ダークモード対応

デバイスのダークモード設定に自動で追従する。

## 解説記事

開発の試行錯誤（静的版→リアルタイム取得→APIキー問題の発見）の詳細は Zenn 記事で公開予定。

## ライセンス

MIT
