---
title: "レッスン 10 - 振り返りと次のステップ"
description: "Copilot CLI のワークフロー、2 つのプルリクエスト、再利用可能なカスタマイズ、その他のリソースを振り返ります。"
authors:
  - geektrainer
lastUpdated: 2026-09-29
---

Tailspin Toys の一連のワークフローで GitHub Copilot CLI を使用しました。このレッスンでは、次の操作を行いました。

- Codespace を準備し、Copilot CLI をインストールしてプロジェクトを確認し、用意されていたフィルタリングの Issue を見つけました。
- 星評価を追加し、ポートフォワーディングしたブラウザーで結果を確認して、最初のプルリクエスト (PR) を手動でマージしました。
- フィルタリングの Issue から始め、Plan モードでアプローチを定め、Autopilot モードで実装し、Interactive モードでレビューしました。
- カスタム指示でエージェントをガイドし、既存の `quality-checks` skill をカスタマイズして、ユニットテスト、lint、型チェックを実行しました。
- Playwright Model Context Protocol (MCP) server を追加し、実際のブラウザーでフィルタリングを確認しました。
- 品質保証 (QA) 用のカスタムエージェントを作成して選択し、要件、カバレッジ、skill の結果、ブラウザーでの検証を評価しました。
- フィルタリングの変更全体をレビューし、Agent Merge を承認してフィルタリングの PR をマージしました。
- コンテキスト、モデル、共有、オプションのクラウドへの委任に使う slash command を確認しました。

## 完成した内容

このワークショップでは、更新済みの `main` からそれぞれ作成した別々のブランチで、2 つの PR を完了します。

1. **星評価:** 既存の `starRating` と未評価の状態をゲームカードに表示します。
2. **フィルタリングと品質ワークフロー:** フィルタリングを実装し、指示を更新して機能に適用します。`quality-checks` のレポートをカスタマイズし、QA プロファイルを作成して、関連するテストを追加します。

フィルタリングを計画してから PR を作成するまで、同じ会話とブランチを使用しました。ワークショップを簡潔にするため、この作業を 1 つの PR にまとめました。

## さまざまな検証方法

自動テスト、自分でのブラウザー確認、MCP を介した Copilot のブラウザー操作など、いくつかの方法でコードを確認しました。`quality-checks` skill はユニットテスト、lint、型チェックを実行し、新しい形式で結果を報告しました。QA は PR の前に、要件とテストカバレッジのレビュー結果をこれらの結果とまとめました。

追加するテストは実際の不足を補うものである必要があります。QA の実行で追加テストが不要と判断される場合もあります。マージを承認する前にコードと検証結果をレビューし、変更後は影響を受ける検証結果を更新してください。

## ベスト プラクティス

Copilot に提供するコンテキストとツールが、作業の結果を左右します。このワークショップでは、指示を更新し、skill をカスタマイズし、QA プロファイルを作成し、MCP server を構成しました。これらのカスタマイズを複数の会話で再利用し、チームのニーズに合わせて調整しましょう。指示は標準を定め、skill は繰り返し実行する作業を説明し、カスタムエージェントは専門的な役割を定義し、MCP server は外部ツールに接続します。エージェントの要約だけでなく、実際の変更とツールの結果を確認してください。

タスクに合った**モードとモデル**を選びます。実装前にアプローチを検討するときは **Plan**、範囲の明確な変更を進めながら確認するときは **Interactive**、範囲の明確なタスクを任せるときは **Autopilot** を使います。定型的な編集には高速なモデルを、複雑なタスクにはより高性能なモデルを選びます。

コンテキストは、インフラストラクチャと同じくらい重要です。*何を*、*なぜ*、*どのように*作るのかを明確に伝えると、出力は大きく変わります。

## さらに確認する

基本的なワークフローを学びました。Copilot CLI の次の機能も試してみましょう。

- `/review` でコードレビューエージェントに変更を分析してもらいます。
- `/rubber-duck` で問題について話し合い、別の視点を得ます。
- `/fleet` で独立したサブタスクを並行して調整します。
- `/worktree` で別のタスクを分離します。
- `/delegate` で Copilot cloud agent にタスクを送ります。

## 次のステップ

どのツールも、使い続けることで上達します。本番コードや個人のプロジェクト、何年も作りたいと思いながら手を付けていなかった小さなアプリで使ってみましょう。学んだことをチームと共有し、チームからも学びましょう。そして、いつものようにドキュメントを確認してください。

ターミナルから Tailspin Toys を拡張する場合は、オプションの [Foundry Backer Concierge シリーズ][foundry]に進みます。別の環境を比較する場合は、[VS Code ワークショップ][vscode]、[GitHub Copilot app ワークショップ][app]、または [Copilot cloud agent ワークショップ][cloud]を確認してください。

## リソース

- [GitHub Copilot CLI について][about-cli]
- [Copilot CLI コマンド リファレンス][cli-reference]
- [Copilot CLI のカスタマイズ][customize-cli]
- [Copilot CLI でプルリクエストを管理する][manage-prs]

[previous-lesson]: ../9-cli-power-tools/
[foundry]: ../8-foundry-agent/
[vscode]: ../../vscode/
[app]: ../../app/
[cloud]: ../../cloud/
[about-cli]: https://docs.github.com/copilot/concepts/agents/about-copilot-cli
[cli-reference]: https://docs.github.com/copilot/reference/copilot-cli-reference/cli-command-reference
[customize-cli]: https://docs.github.com/copilot/how-tos/copilot-cli/customize-copilot
[manage-prs]: https://docs.github.com/copilot/how-tos/copilot-cli/use-copilot-cli/manage-pull-requests
