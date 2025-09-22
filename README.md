# Integrate MCP with GitHub Copilot

_GitHub Copilotの開発ワークフローを拡張するためのツールを追加する方法を学びます。1時間以内で完了します！_

## ようこそ

- **対象者**: AIアシスト開発ワークフローを強化したい開発者、GitHub Copilotユーザー、AI愛好家
- **学べること**: MCPの基本、GitHub MCPサーバーのセットアップ、Copilot Agent Modeとの統合を紹介します
- **作成するもの**: GitHub Copilotを使って課題管理を行いながら、Mergington High Schoolの課外活動Webサイトをアップグレードする混合開発ワークフロー
- **前提条件**: [Getting Started with Copilot](https://github.com/skills/getting-started-with-github-copilot) 演習
- **所要時間**: この演習は1時間以内で完了します

この演習で行うこと:

1. GitHub MCPサーバーをGitHub Copilotと統合する
2. Copilotに類似プロジェクトの調査や課題の作成を委任する
3. 重要な課題を見つけて、アイデアからPull Requestまで実装するようCopilotに依頼する
4. 最近クローズされた課題にコメントを追加する

### この演習の始め方

> [!IMPORTANT]
> この演習は[GitHub Copilot](https://github.com/features/copilot)の基本的な知識があることを前提としています。未経験の場合は、[Getting Started with Copilot](https://github.com/skills/getting-started-with-github-copilot) 演習をおすすめします

エクササイズを自分のアカウントにコピーし、お気に入りのOctocat (Mona) に**約20秒**待ってもらい、最初のレッスンが準備できたら**ページをリフレッシュ**してください

[![](https://img.shields.io/badge/Copy%20Exercise-%E2%86%92-1f883d?style=for-the-badge&logo=github&labelColor=197935)](https://github.com/new?template_owner=matakaha&template_name=integrate-mcp-with-copilot-jp&owner=%40me&name=skills-integrate-mcp-with-copilot-jp&description=演習:+Model+Context+Protocol+をGitHub+Copilot+に統合する&visibility=public)

<details>
<summary>トラブルシューティング 🤷</summary><br/>

エクササイズをコピーする際は、以下の設定をおすすめします

- オーナーには自分の個人アカウントまたはリポジトリをホストする組織を選択してください

- 公開リポジトリの作成をおすすめします。プライベートリポジトリの場合、Actionsの利用分が消費されます

20秒経っても演習が準備できていない場合は、[Actions](../../actions) タブを確認してください

- ジョブが実行中かどうか確認してください。少し時間がかかる場合もあります

- ページに失敗したジョブが表示されている場合は、Issueを提出してください。バグを見つけてくれてありがとう！🐛

</details>

---

&copy; 2025 GitHub &bull; [Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [MIT License](https://gh.io/mit)
