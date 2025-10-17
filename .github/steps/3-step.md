## Step 3: AgentモードとGitHub MCPサーバーで課題を解決しましょう

リサーチとコラボレーションの機会を見つける作業、お疲れさまでした
課外活動を整理するための新しいアイデアも見つかり、しかも素早くできました

これで楽しいこと、つまり素晴らしい生徒たちに教えることに集中できますね！🌱

さて、先生たちも活発に活動しているようです
バグやリクエストがいくつか提出されています！完璧です！🚀

それでは、MCPサーバーのツールとCopilotを使って、トリアージや作業を進めましょう

### :keyboard: アクティビティ: 重要な課題を簡単に実装しましょう

1. **Copilot Chat** パネルが開いていて **Agent** モードが選択されていること、MCPサーバーツールが利用可能なことを確認してください

1. CopilotにこのリポジトリのオープンなIssue数を尋ねてください

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > 私のリポジトリには未解決のissueがいくつありますか？
   > ```

   > 🪧 **注意:** List Issuesツールが正しいパラメータで呼び出されているか確認してください

1. Copilotに重要なIssueを要約するよう依頼してください

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > えぇぇ、、、それは一人で対処するには多すぎますね！ Issueのリストを取得して、説明とコメントを確認、最も重要な上位3件を選んでください。
   > ```

   <details>
   <summary> <b> 💡 ヒント:</b> ツールの事前承認</summary><br/>

   Copilotがツールを頻繁に使う場合、会話セッション中は事前に許可を与えることができます

   <img width="350" src="https://github.com/user-attachments/assets/d741191e-4d98-489d-92d2-f1069fd6c34e"/>

   </details>

1. 提案されたIssueを確認してください。Copilotが具体的な提案をしなかった場合は、フィードバックを与えて結果を絞り込んでください

1. 絞り込んだリストから、CopilotにIssueの実装を依頼してください。**Monaは変更が動作するかどうかではなく、試みがなされたかどうかだけを評価します**

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > #codebase とりあえず１つ目にとりかかってください。以下のステップに従ってください:
   > 1. 変更を加えるために新しいローカルブランチをチェックアウトします。
   > 2. 変更を加えたら、それが正しいかどうか私に確認してください。
   > 3. 変更をプッシュして、プルリクエストを開始してください。
   > ```

   > ⚠️ **警告:** Copilotが実行しようとしているアクションは必ず確認してください。特にMCPサーバーによる外部操作には元に戻す手段がない場合があります

1. プルリクエストが作成されたら、Monaが作業をチェックし始めます。コメント欄で進捗情報や次のステップを確認してください

<details>
<summary>トラブルシューティング</summary><br/>

- ツールがリクエストされない場合は、MCPの設定が正しいか確認してください
- Copilotが結果を取得できない場合は、このCodespaceのトークンまたは適切な権限を持つPersonal Access Token（PAT）を使っているか確認してください。デフォルトでは、このリポジトリにのみアクセス権があります

</details>
