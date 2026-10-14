# moomoo センチメント温度計 Skill インストールガイド

本ドキュメントは、moomoo センチメント温度計 Skill を Claude Code 環境へ導入する手順を説明します。

## 前提条件

- Claude Code CLI がインストール済みであること
- moomoo OpenAPI の認証設定が完了していること
- UNIX 系コマンド(curl, openssl, date)が利用可能であること(Windows の場合は Git Bash 環境を推奨)

## インストール手順

### Step 1: リポジトリのクローン

以下のコマンドをターミナルで実行し、Skill ファイルをローカルに取得します。

```bash
git clone https://github.com/alicialin0420/moomoo-comment-sentiment.git
```

### Step 2: Skill ディレクトリへの配置

クローンした `SKILL.md` を Claude Code の Skill 格納ディレクトリに配置します。

#### macOS / Linux の場合

```bash
cp moomoo-comment-sentiment/SKILL.md ~/.claude/skills/moomoo-comment-sentiment/SKILL.md
```

#### Windows の場合

```powershell
Copy-Item moomoo-comment-sentiment\SKILL.md $env:USERPROFILE\.claude\skills\moomoo-comment-sentiment\SKILL.md
```

### Step 3: 設定の反映

Claude Code を再起動する、または新しいセッションを開始することで、Skill が認識されます。

### Step 4: 動作確認

Claude Code 上で以下のように呼び出し、Skill が反応することを確認します。

```
moomoo のコミュニティセンチメントを US.NVDA で取得して
```

## アンインストール手順

Skill ディレクトリから `SKILL.md` を削除してください。

```bash
rm ~/.claude/skills/moomoo-comment-sentiment/SKILL.md
```

## トラブルシューティング

### Skill が認識されない場合

- `~/.claude/skills/moomoo-comment-sentiment/` ディレクトリが存在するか確認してください
- ディレクトリ名が `moomoo-comment-sentiment` になっているか確認してください
- Claude Code を完全に再起動してください

### API 認証エラーが出る場合

- moomoo OpenAPI の認証設定が完了しているか確認してください
- 環境変数 `FUTUOPEND_API_KEY` 等が必要に応じて設定されているか確認してください

## サポート

不具合や改善要望は本リポジトリの Issue よりご報告ください。
