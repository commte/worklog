# log

当日の作業ログを会話から抽出して `private/作業ログ/YYYY-MM-DD.md` に書く Agent Skills 形式のスキル。
Claude Code / Codex / Cursor などから `/log` で呼べる。作業の区切りや終了時に使う。

書くもの

- 何を実装・修正したか（ファイルパス付き）
- 意思決定とその理由
- 持ち越した作業

同じ日に2回呼べば、既存のログに追記する。重複は書かない。

## 入れる

```bash
npx skills add commte/log
```

手で入れるなら、このリポジトリを `.claude/skills/log/` に置くか、シンボリックリンクを貼る。

```bash
ln -s ~/Projects/log <repo>/.agents/skills/log
```

## 置き場所を変える

既定は `private/作業ログ/`（`private` を gitignore しているリポジトリ向け）。
変えたいプロジェクトは、その CLAUDE.md に一行書く。

    作業ログは docs/log/ に置く

## 書き方の規律

本体は [SKILL.md](SKILL.md)。

- 箇条書きで短く。ファイルパスはバッククォート
- 太字・区切り線・絵文字は使わない
- 追記のときは既存のセクション構造に合わせる
