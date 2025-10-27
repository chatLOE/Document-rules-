---
layout: page
title: "FAQ"
permalink: /docs/faq/
nav_order: 3
---

# FAQ（よくある質問）

プロジェクトで頻出する質問と回答を整理しておくと、問い合わせ対応の負荷を軽減できます。以下は記入例です。

## Q1. ドキュメントの編集フローは？

- GitHub 上で新しいブランチを作成し、必要な Markdown ファイルを更新または追加します。
- Pull Request を提出し、レビューを通過したら `main` ブランチへマージします。
- GitHub Pages が自動デプロイを実行し、数分以内に公開内容へ反映されます。

## Q2. 画像を追加したい

`assets/images/` ディレクトリを作成し、その中に画像ファイルを配置してください。ページから参照する際は相対パスで `![代替テキスト](../assets/images/sample.png)` のように指定します。

## Q3. ナビゲーションの順序を変更したい

各ページの Front Matter にある `nav_order` を調整するか、`_config.yml` の `header_pages` に並べる順番を変更してください。

その他の質問は適宜追加・更新してください。
