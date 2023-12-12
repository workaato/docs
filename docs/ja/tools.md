 # ツール

Workatoのツールは、3つの主な機能を実行するのに役立ちます：レシピの作成、アプリの接続、およびレシピの共同作業と管理。画面左側のナビゲーションバーから「ツール」を選択して、ツールの完全なリストにアクセスできます。

![Workatoツール](~@img/features/tools/tools-menu.png)
*`ツール`メニューの下にすべてのツールがあります*

## レシピの作成

レシピの作成には、コネクタ、トリガー、およびアクションに関連付けられたツールがよく使用されます。たとえば、ツールでルックアップテーブルを設定すると、レシピ内のコネクタを使用してルックアップテーブルに行を追加、削除、または更新するアクションを使用できます。

![ルックアップテーブルの使用](~@img/features/tools/add-entry-to-lookup-table.png)
*レシピ内で「エントリーを追加」アクションを使用すると、既存のルックアップテーブルに新しい行が作成されます*

これらのツールは、人間の承認機能を備えたレシピを強化するだけでなく、同じアカウント内のレシピ間でデータを再利用することも可能にします。

以下は、このカテゴリに分類されるものです：

<table class="unchanged rich-diff-level-one">
  <thead>
    <tr>
        <th width='25%'>入力フィールド</th>
        <th>説明</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td> <a href = "features/account-properties.html">プロパティ</a></td>
      <td>
        アカウント全体で使用できるプロパティを定義し、レシピ内で変数として使用できます。<a href = "features/account-properties.html">詳細を見る</a>
      </td>
    </tr>
    <tr>
      <td> <a href = "features/lookup-tables.html">ルックアップテーブル</a></td>
      <td>
        レシピが追加の情報を取得するために簡単に参照できるルックアップテーブルを定義します。<a href = "features/lookup-tables.html">詳細を見る</a>
      </td>
    </tr>
    <tr>
      <td> <a href = "workflow.html">People Task</a></td>
      <td>
        続行する前に指定された人間の承認が必要なレシピにステップを追加します。<a href = "workflow.html">詳細を見る</a>
      </td>
    </tr>
    <tr>
      <td> <a href = "features/message-template.html">メッセージテンプレート</a></td>
      <td>
        複数のレシピで使用できるHTML/テキスト/JSON/XMLの静的メッセージテンプレートを作成します。<a href = "features/message-template.html">詳細を見る</a>
      </td>
    </tr>
    <tr>
      <td> <a href = "features/common-data-model.html">共通データモデル</a></td>
      <td>
        顧客などのオブジェクトのスキーマを作成し、複数のレシピで使用できるようにします。<a href = "features/common-data-model.html">詳細を見る</a>
      </td>
    </tr>
    <tr>
      <td><a href = "connectors/pubsub.html">Pub/Sub</a></td>
      <td>
        他のレシピが発行するイベントにレシピが購読できるようにし、レシピ間の依存関係や変更のトリクルダウン効果を減らします。<a href = "connectors/pubsub.html">詳細を見る</a>
      </td>
    </tr>
    <tr>
      <td><a href = "workbot/workbot.html">Slack用Workbot</a></td>
      <td>
        ユーザーと対話して複雑なワークフローを実行できるSlack上のチャットボットを作成します。<a href = "workbot/workbot.html">詳細を見る</a>
      </td>
    </tr>
    <tr>
      <td> <a href = "workbot-for-teams/workbot.html">Microsoft Teams用Workbot</a></td>
      <td>
        ユーザーと対話して複雑なワークフローを実行できるMicrosoft Teams上のチャットボットを作成します。<a href = "workbot-for-teams/workbot.html">詳細を見る</a>
      </td>
    </tr>        
  </tbody>
</table>


## アプリの接続

アプリの接続に関するツールは、ユーザーがカスタムアプリケーション、オンプレミスアプリケーション、およびAPIエンドポイントを追加および管理できるようにします。

以下は、このカテゴリに分類されるものです：

<table class="unchanged rich-diff-level-one">
  <thead>
    <tr>
        <th width='25%'>入力フィールド</th>
        <th>説明</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href = "developing-connectors/sdk.html">コネクタSDK</a></td>
      <td>
        Workatoのソフトウェア開発キットを使用して、現在サポートしていないアプリケーションに接続するための堅牢なカスタムアプリケーションコネクタを作成します。<a href = "developing-connectors/sdk.html">詳細を見る</a>
      </td>
    </tr>
    <tr>
      <td><a href = "on-prem.html">オンプレミスエージェント</a></td>
      <td>
        ファイアウォールの背後に隠れたデータベースなどのアプリケーションに簡単かつ安全に接続します。<a href = "on-prem.html">詳細を見る</a>
      </td>
    </tr>
    <tr>
      <td><a href = "api-management.html">APIプラットフォーム</a></td>
      <td>
        Workato上のレシピまたはレシピのコレクションを、公開できるAPIエンドポイントに変換します。<a href = "api-management.html">詳細を見る</a>
      </td>
    </tr>
  </tbody>
</table>

## レシピの共同作業と管理

このセクションのツールは、チーム間の共同作業、チームの役割の管理、およびチームアカウント間でのレシピと依存関係の共有を可能にします。

以下は、このカテゴリに分類されるものです：

<table class="unchanged rich-diff-level-one">
  <thead>
    <tr>
        <th width='25%' >入力フィールド</th>
        <th>説明</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href = "recipe-development-lifecycle.html">レシピライフサイクル管理</a></td>
      <td>
        Workatoで新しいワークフローを計画し、開発し、テストし、展開します。 <a href = "recipe-development-lifecycle.html">詳細を見る</a>
      </td>
    </tr>
    <tr>
      <td><a href = "user-accounts-and-teams/team-collaboration.html">チーム</a></td>
      <td>
         複数のユーザーと協力して共有のワークスペースでレシピを作成します。 <a href = "user-accounts-and-teams/team-collaboration.html">詳細を見る</a>
      </td>
    </tr>
  </tbody>
</table>