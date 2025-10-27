# GitHub Pages ドキュメント雛形

このリポジトリは、GitHub Pages（Jekyll）でチームドキュメントを公開するための最小構成の雛形です。必要な設定ファイルとページ構造を含んでいるため、内容を書き換えるだけで素早くドキュメントサイトを立ち上げられます。

## セットアップ

1. **依存パッケージのインストール**
   ```bash
   bundle install
   ```
2. **ローカルプレビューの起動**
   ```bash
   bundle exec jekyll serve
   ```
   `http://127.0.0.1:4000` にアクセスすると、生成されたサイトをブラウザで確認できます。

## ディレクトリ構成

- `_config.yml` — Jekyll 全体の設定。サイト名やメタ情報、テーマなどを定義します。
- `index.md` — トップページ。全体概要と主要リンクを掲載します。
- `docs/` — ドキュメント本文を格納するディレクトリ。ページを増やしたい場合はこの配下に Markdown ファイルを追加してください。
- `assets/css/style.scss` — Minima テーマのスタイルを上書きするための Sass ファイル。
- `Gemfile` — GitHub Pages 互換の Jekyll 環境をローカルで再現するための依存定義。

## コンテンツ更新のコツ

- 各ページの先頭 Front Matter（`---` で囲まれた設定ブロック）で、ページタイトル・パーマリンク・ナビゲーション順序を管理できます。
- 画像や添付ファイルを追加する場合は `assets/` にまとめて配置すると整理しやすくなります。
- サイト共通のスタイル調整は `assets/css/style.scss` で行ってください。テーマ本体を直接編集するより安全です。

## GitHub Pages での公開

1. GitHub 上でリポジトリを作成し、本テンプレートを push します。
2. GitHub のリポジトリ設定から「Pages」を開き、`main` ブランチのルート（`/`）を公開対象に設定します。
3. 数分後に公開 URL が発行されるので、共有しましょう。

## 次のステップ

- チームやプロジェクトに合わせて `title` や `description` などのメタ情報を `_config.yml` で更新してください。
- ドキュメントページを増やす場合は `docs/` 配下に Markdown ファイルを追加し、`header_pages` に追記するとナビゲーションに反映されます。
- SEO や SNS カード向けに `jekyll-seo-tag` の Front Matter を活用すると効果的です。

## CI / GitHub Actions

このリポジトリには、`main` ブランチへ push すると自動で Jekyll をビルドして GitHub Pages にデプロイする GitHub Actions ワークフローを追加しています。

基本的な確認手順:

1. 変更を commit & push してください。

   ```bash
   git add .
   git commit -m "Update site content"
   git push origin main
   ```
2. GitHub のリポジトリページで「Actions」タブを開き、ワークフローの実行状況を確認します（ビルド → deploy の順で進みます）。

3. 成功すると GitHub Pages に公開されます。公開 URL はリポジトリの Settings > Pages で確認できます。

備考:

- ワークフローは Bundler のキャッシュを利用しているため、2 回目以降のビルドが速くなります。
- カスタムドメイン（CNAME）を利用する場合は、リポジトリに `CNAME` ファイルを追加するか、Settings の Pages でドメインを設定してください。
