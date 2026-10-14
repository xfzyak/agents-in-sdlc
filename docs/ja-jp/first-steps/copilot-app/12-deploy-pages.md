---
title: "レッスン 12 - GitHub Pages でサイトをデプロイする"
description: "Copilot に Pages ワークフローを設定させ、プルリクエストを確認し、公開された Space Quiz を検証します。"
authors:
  - jamesmontemagno
lastUpdated: 2026-10-12
---

GitHub Pages で Space Quiz を公開し、誰でもアクセスできるようにします。Copilot はワークフローを準備してデプロイを案内できますが、変更を確認し、サイトが公開されたことを確かめるのはあなたです。

このレッスンでは、次のことを行います。

- Copilot に GitHub Pages のデプロイを設定させます。
- マージする前にワークフローとプルリクエストを確認します。
- デプロイの進行状況を追跡し、公開されたサイトを検証します。

## シナリオ

Space Quiz はすでに GitHub リポジトリにありますが、他の人が簡単に試せるようにする必要があります。単一ファイルのサイトを GitHub Pages で公開すれば、サーバーやランタイム依存関係を追加せずに、公開 URL からアクセスできるようになります。

## Copilot にサイトをデプロイさせる

`space-quiz` の Copilot アプリ セッションで、次のプロンプトを送信します。

```plaintext
Enable GitHub Pages for this repository. Create a GitHub Actions workflow that builds the website if needed and deploys it to GitHub Pages. Add a README describing the app and how to run it locally if one does not already exist. Create a pull request with these changes and merge it after required checks pass. Monitor the deployment until it succeeds, then report the final URL of the live website. If you lack permission to enable Pages or merge, tell me exactly what I need to approve or do; do not report success until the site is live.
```

![3 段階の図: space-quiz のプルリクエストがマージされた状態、Build website、Upload artifact、Deploy to Pages の各ステップを含む GitHub Actions の Deploy website 実行の成功、yourname.github.io/space-quiz/ で公開された Space Quiz。](../../../_images/first-steps-app-pages-deploy.svg)

> [!WARNING]
> このプロンプトは、エージェントにプルリクエストの作成とマージ、およびリポジトリの Pages 設定の変更を依頼します。続行する前に、diff、デプロイ権限、GitHub の承認要求を確認してください。

## ワークフローを確認してデプロイを検証する

1. リポジトリに README がまだない場合にのみ、README が追加されていることを確認します。
2. ワークフローのビルドとデプロイの手順を含め、プルリクエストの変更を確認します。
3. 必須のプルリクエスト チェックがすべて成功してからマージします。
4. GitHub Actions のデプロイ実行が成功するまで追跡します。
5. 表示された URL を開き、Space Quiz が読み込まれることを確認します。

エージェントが Pages の有効化やプルリクエストのマージを実行できない場合は、提示された具体的な手順に従ってください。デプロイが成功し、公開サイトが読み込まれるまでは、作業を完了したと見なさないでください。

## まとめと次のステップ

Space Quiz が公開サイトとして利用可能になり、エージェントの報告だけに頼らずデプロイを検証できました。続けて、[レッスン 13: 振り返りと次のステップ][next-lesson]に進みます。

[next-lesson]: ../13-review/
