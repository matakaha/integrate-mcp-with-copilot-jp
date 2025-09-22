## Step 2: AgentモードとGitHub用MCPサーバー

素晴らしいです！あなたは最初のMCPサーバーをGitHub Copilotに接続できました 🎉

🚨 先生たちがバグやリクエストをどんどん送ってきています！良いアイデアがたくさんあります！これらを確認し、他のアップグレードの調査も始めましょう

幸い、GitHub用のMCPサーバーがあれば、これらのトリアージやリサーチもすぐにできるはずです 🕵️

### MCPサーバーのツールはどう使うのですか？

良いニュースです！Copilotとやり取りするのと同じように自然言語で使えます。利用可能な機能やトークンの権限制限だけは意識してください

つまり、MCPサーバーが使えることで、コード以外のこともCopilotに頼めるようになりました。例えばこんなことができます

- 説明、コメント、いいねを考慮したIssueの検索
- 他のリポジトリでIssueを開く、更新する、閉じる
- リポジトリの比較
- 一緒に作業している他の作者について知る
- Issueを取得し、ブランチで変更してプルリクエストを開始する

すごいですよね？！それではやってみましょう 👩‍🚀

### :keyboard: アクティビティ: アイデアを素早く見つけて保存しましょう

1. Codespace内で開いているファイルをすべて閉じてください。不要なコンテキストを減らすためです

1. **Copilot Chat** パネルが開いていて **Agent** モードが選択されていること、MCPサーバーツールが利用可能なことを確認してください

1. Copilotに、これと似たプロジェクトをGitHubで検索するよう依頼してください

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > Search for any other repositories for organizing extra curricular activities
   > ```

1. MCPツールが必要な場合、Copilotが許可を求めてきます。**リクエスト内容を確認**し、必要に応じて修正し、**Continue** をクリックしてください

   <img width="250" alt="request permission dialog" src="https://github.com/user-attachments/assets/229473af-c206-47a4-b356-943b9c9bd946" />

1. Copilotにプロジェクトの1つを説明するよう依頼してください。気に入るものが見つかるまで探索してください

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > Please look at the code for the 3rd option and give me a detailed description of the features.
   > ```

1. Copilotを使って、機能を比較し、強化案のアイデアを出してください

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > Please compare these features to our project. Which would be new?
   > ```

1. いいですね！CopilotにこれらのアイデアでIssueを作成してもらいましょう

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > I like it. Let's create issues for these in my repository.
   > ```

1. CopilotがリポジトリにIssueを作成する許可を求めてきます。新しいIssueごとに **Continue** をクリックしてください。**リクエスト内容を確認**してから実行してください

   <img width="250" alt="request permission dialog" src="https://github.com/user-attachments/assets/52635294-950a-4168-b71e-498eb769f3af" />

1. 調査が終わったので、チャットセッションを終了してコンテキストをクリアしましょう。**Copilot Chat** パネル上部の **New Chat** アイコン（プラス記号）をクリックしてください

1. 新しいIssueが作成されたら、Monaが作業をチェックし始めているはずです。コメント欄で進捗情報や次のレッスンを確認してください

> [!NOTE]
> Model Context Protocol（MCP）の状況は急速に進化しています。[Official GitHub MCP server](https://github.com/github/github-mcp-server) を含む多くのサーバーが活発に開発中で、安定APIと完全な互換性がない場合があります