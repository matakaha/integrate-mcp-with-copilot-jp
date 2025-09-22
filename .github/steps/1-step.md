## Step 1: MCPの紹介と環境セットアップ

<img width="150" align="right" alt="copilot logo" src="https://github.com/user-attachments/assets/4d22496d-850b-4785-aafe-11cba03cd5f2" />

[Getting Started with GitHub Copilot](https://github.com/skills/getting-started-with-github-copilot) 演習では、Mergington High Schoolの課外活動ウェブサイトを紹介しました。このサイトでは生徒がイベントに申し込むことができます

そして今、私たちは問題に直面していますが…良い問題です！より多くの先生がこのサイトを使いたいと希望しています 🎉

先生たちからたくさんのアイデアが寄せられていますが、すべてのリクエストに対応しきれていません 😮 この課題を解決するために、GitHub CopilotをアップグレードしてModel Context Protocol（MCP）を有効化しましょう。具体的には、GitHub MCPサーバーを追加し、課題管理とウェブサイトのアップグレードを組み合わせたワークフローを実現します 🧑‍🚀

さっそく始めましょう！

### Model Context Protocol（MCP）とは？

[Model Context Protocol (MCP)](https://modelcontextprotocol.io/introduction) は「AIのためのUSB-C」とも呼ばれています。GitHub Copilot（や他のAIツール）が他のサービスとシームレスに連携できるユニバーサルコネクタです

本質的には、サービスの機能や要件を記述する方法であり、AIツールがどのメソッドを使うべきか、どんなパラメータを渡すべきかを簡単に判断できるようにします。MCPサーバーがそのインターフェースを提供します

```mermaid
graph LR
    A[Developer] -->|Uses| B[GitHub Copilot]
    B -->|Unified API| MCP[Model Context Protocol]

    MCP <-->|Unique API| C[(GitHub)]
    MCP <-->|Unique API| D[(Slack)]
    MCP <-->|Unique API| E[(Figma)]

    style B fill:#4CAF50,stroke:#333,stroke-width:2px

    subgraph "Less Context Switching, More Coding"
        B
        MCP
        C
        D
        E

    end
```

### :keyboard: アクティビティ: 環境を確認しましょう

MCPに進む前に、開発環境を起動し、課外活動アプリケーションを再確認しましょう

1. 下のボタンを右クリックして **Create Codespace** ページを新しいタブで開いてください。デフォルト設定のまま使ってください

   [![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/{{full_repo_name}}?quickstart=1)

1. **Copilot Chat** と **Python** 拡張機能がインストールされ有効になっていることを確認してください

   <img width="300" alt="copilot extension for VS Code" src="https://github.com/user-attachments/assets/ef1ef984-17fc-4b20-a9a6-65a866def468" /><br/>
   <img width="300" alt="python extension for VS Code" src="https://github.com/user-attachments/assets/3040c0f5-1658-47e2-a439-20504a384f77" />

1. アプリケーションが修正前に動作することを確認してください。左サイドバーで **Run and Debug** タブを選択し、**Start Debugging** アイコンを押してください

   <details>
   <summary>📸 スクリーンショットを表示</summary><br/>

   <img width="300" alt="run and debug" src="https://github.com/user-attachments/assets/50b27f2a-5eab-4827-9343-ab5bce62357e" />

   </details>

   <details>
   <summary>🤷 トラブルシューティング</summary><br/>

   **Run and Debug** エリアが空の場合は、VS Codeをリロードしてみてください。コマンドパレット（`Ctrl`+`Shift`+`P`）を開き、`Developer: Reload Window` を検索してください

   <img width="300" alt="empty run and debug panel" src="https://github.com/user-attachments/assets/0dbf1407-3a97-401a-a630-f462697082d6" />

   </details>

1. **Ports** タブでウェブページのアドレスを探し、開いて動作を確認してください

   <details>
   <summary>📸 スクリーンショットを表示</summary><br/>

   <img width="350" alt="ports tab" src="https://github.com/user-attachments/assets/8d24d6b5-202d-4109-8174-2f0d1e4d8d44" />

   ![Screenshot of Mergington High School WebApp](https://github.com/user-attachments/assets/5cb88d53-d948-457e-9f4b-403d697fa93a)

   </details>

### :keyboard: アクティビティ: GitHub MCPサーバーを追加しましょう

1. Codespace内で **Copilot Chat** パネルを開き、**Agent** モードが選択されていることを確認してください

   <img width="200" alt="image" src="https://github.com/user-attachments/assets/201e08ab-14a0-48bf-824e-ba4f8f43f8ab" />

   <details>
   <summary>Agentモードが見つからない場合</summary><br/>

   - VS Codeが `v1.99.0` 以上であることを確認してください
   - Copilot拡張機能が `v1.296.0` 以上であることを確認してください
   - [ユーザーまたはワークスペース設定](https://code.visualstudio.com/docs/configure/settings#_workspace-settings)でAgentモードが有効になっているか確認してください

      <img width="300" alt="image" src="https://github.com/user-attachments/assets/407a79dd-707e-471b-b56b-1938aece4ad8" />

   </details>

1. Codespace内で `.vscode` フォルダに移動し、新しいファイル `mcp.json` を作成してください。以下の内容を貼り付けてください

   📄 **.vscode/mcp.json**

   ```json
   {
     "servers": {
       "github": {
         "type": "http",
         "url": "https://api.githubcopilot.com/mcp/"
       }
     }
   }
   ```

1. `.vscode/mcp.json` ファイル内で **Start** ボタンをクリックし、GitHubで認証するプロンプトを承認してください。これでGitHub CopilotにMCPサーバーの機能が通知されました

   <img width="350" alt="mcp.json file showing start button" src="https://github.com/user-attachments/assets/15a3d885-1c13-40b4-8d59-87b478ddd8a0" />

   <img width="350" alt="allow authentication prompt" src="https://github.com/user-attachments/assets/f5ec128d-9924-454b-8ab4-3f43ebc83cfc" /><br/>

   <img width="350" alt="mcp.json file showing running server" src="https://github.com/user-attachments/assets/c413c52d-94dc-429f-91e0-3486141908b9" />

1. Copilotサイドパネルで **🛠️ アイコン** をクリックし、追加機能を表示してください

   <img width="350" alt="image" src="https://github.com/user-attachments/assets/b1be8b80-c69c-4da5-9aea-4bbaa1c6de10" />

   <img width="350" alt="image" src="https://github.com/user-attachments/assets/99178d1b-adbe-4cf4-ab9c-3a4d29918a13" />

1. `.vscode/mcp.json` ファイルを **コミット** し、`main` ブランチに **プッシュ** してください

   > 🪧 **注意:** `main` へ直接プッシュするのは推奨される運用ではありません。この演習を簡単にするためだけです

1. MCPサーバーの設定をGitHubにプッシュしたので、Monaが作業をチェックし始めているはずです。コメント欄で進捗情報や次のレッスンを確認してください

> [!NOTE]
> 次のステップではGitHub Issueの作成が含まれます。通知メールを避けたい場合は、リポジトリのウォッチを解除してください

<details>
<summary>トラブルシューティング</summary><br/>

以下を確認してください

- `.vscode/mcp.json` ファイルが例と同じ内容になっていること
- 変更を `main` ブランチにプッシュしたこと

</details>
