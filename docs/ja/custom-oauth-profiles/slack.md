 ---
title: SlackのカスタムOAuthプロファイル
date: 2018-04-9 10:23:00 Z
---

# カスタムOAuthプロファイルとは何ですか？
カスタムOAuthプロファイルを使用すると、SlackアプリはWorkato Slackコネクタを裏で利用できます。Slackアプリのアイデンティティを完全にカスタマイズできます。具体的には、以下の項目です：
- ブランディング（ボット名、ボットのロゴ、背景色）
- 権限

# いつSlackのカスタムOAuthプロファイルが必要ですか？
1. ワークスペースのオーケストレーションを自動化する複数のアプリが必要な場合、例えば、会話の作成/アーカイブなどを行うアプリがあります。例えば、エスカレーションボットは、プライベートな会話を作成し、危機管理チームのメンバーを招待し、問題が解決したらアーカイブします。同時に、バースデーボットも同じアクションを実行できますが、目的は大きく異なります。

2. アプリのブランディングと外観を制御したい場合

3. ボットの権限を制御したい場合。最適な使用のための最小限の権限は、以下の表に示されています。
<table>
<thead>
  <tr>
    <th>トークンの種類</th>
    <th>スコープ</th>
    <th>理由</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>ボット</td>
    <td>なし</td>
    <td>ボットのスコープは必要ありません。</td>
  </tr>
  <tr>
    <td rowspan="11">ユーザー</td>
    <td><code>channels:read</code></td>
    <td>公開会話のリストを取得します。</td>
  </tr>
  <tr>
    <td><code>channels:write</code></td>
    <td>公開会話を作成/更新します。</td>
  </tr>
  <tr>
    <td><code>groups:read</code></td>
    <td>プライベート会話のリストを取得します。</td>
  </tr>
  <tr>
    <td><code>groups:write</code></td>
    <td>プライベート会話を作成/更新します。</td>
  </tr>
  <tr>
    <td><code>im:read</code></td>
    <td>ダイレクトメッセージのリストを取得します。</td>
  </tr>
  <tr>
    <td><code>im:write</code></td>
    <td>ダイレクトメッセージを作成/更新します。</td>
  </tr>
  <tr>
    <td><code>mpim:write</code></td>
    <td>マルチパーティーグループ会話を作成/更新します。</td>
  </tr>
  <tr>
    <td><code>mpim:read</code></td>
    <td>マルチパーティーグループ会話のリストを取得します。</td>
  </tr>
  <tr>
    <td><code>chat:write</code></td>
    <td>ユーザーとしてメッセージを投稿します。</td>
  </tr>
  <tr>
    <td><code>users:read</code></td>
    <td>ユーザー情報を取得します。</td>
  </tr>
  <tr>
    <td><code>users:read.email</code></td>
    <td>メールアドレスでユーザー情報を取得します。</td>
  </tr>
</tbody>
</table>

::: warning グラニュラースコープへの移行
Slackは2020年1月22日に[グラニュラー権限](https://api.slack.com/docs/token-types#granular_bot)をリリースしました。Workatoに接続されている既存のカスタムSlackアプリを移行する必要があるかもしれません。詳細については、[移行ガイド](/connectors/slack/slack-granular-permissions.md)を参照してください。
:::

# セットアップの要件
カスタムOAuthプロファイルを作成するには、Workatoの[カスタムOAuthプロファイル](https://app.workato.com/custom_oauth_keys)にアクセスする必要があります。

別のデータセンターを使用している場合は、そのデータセンターのカスタムプロファイルにログインしてください：

- [EUDCカスタムOAuthプロファイル](https://app.eu.workato.com/custom_oauth_keys)
- [JPDCカスタムOAuthプロファイル](https://app.jp.workato.com/custom_oauth_keys)
- [SGDCカスタムOAuthプロファイル](https://app.sg.workato.com/custom_oauth_keys)
- [AUDCカスタムOAuthプロファイル](https://app.au.workato.com/custom_oauth_keys)

::: warning ワークスペースでカスタムOAuthプロファイルが表示されない場合
カスタムOAuthプロファイルは追加機能です。ワークスペースでこの機能が有効になっていることを確認するために、Workato CSMに確認してください。
:::

# カスタムOAuthプロファイルの作成
## ステップ1：Slackを選択する

<Stepper>
<Step>

始める前に、ブラウザから[Slackワークスペースにサインイン](https://slack.com/signin#/signin)してください。

</Step>
<Step>

Workatoの**ツール > カスタムOAuthプロファイル**に移動します。

</Step>
<Step>

**新しいカスタムプロファイル**をクリックします。

</Step>
<Step>

**新しいカスタムプロファイル**ページで以下を入力します：

- ステップ1で**Slack**を選択します。
- ステップ2で新しいアプリの名前を入力し、**新しいアプリを作成**をクリックします。これにより、https://api.slack.com/appsに移動する新しいタブが開きます。Workatoのタブとこの新しいタブの両方を開いたままにしておいてください - 残りのステップを完了するために両方が必要です。

</Step>
</Stepper>

## ステップ2：新しいSlackアプリを作成する

<Stepper>
<Step>

新しいタブで、アプリを開発するワークスペースを選択し、**次へ**をクリックします。

</Step>
<Step>

**作成**をクリックします。

</Step>
<Step>

「アプリの設定へようこそ」のポップアップで、**了解**をクリックします。

</Step>
<Step>

アプリの**基本情報**ページに移動します。**アプリの資格情報**までスクロールし、次のステップを完了するためにここにある情報が必要です。

</Step>
</Stepper>

## ステップ3：WorkatoをSlackアプリと連携する

<Stepper>
<Step>

Workatoのタブに戻り、ステップ3を完了します。

</Step>
<Step>

ステップ3で以下を入力します：

- **クライアントID**：Slackからの**クライアントID**の値をこのフィールドに貼り付けます。
- **クライアントシークレット**：Slackからの**クライアントシークレット**の値をこのフィールドに貼り付けます。
- **検証トークン** **ステップ4: Workatoでの接続を完了する**

ほとんど完了です！残りは、Workatoでの接続を完了するだけです。

<Stepper>
<Step>

開いているWorkatoタブで、**完了**をクリックします。新しいSlack接続を作成するために、任意のプロジェクトフォルダに移動します。

</Step>
<Step>

Slack接続に名前を付けます。**カスタムOAuthプロファイル**フィールドで、新しく作成したOAuthプロファイルを選択します。**接続**をクリックします。

</Step>
<Step>

許可の付与画面で、**許可する**をクリックします。

</Step>
</Stepper>

---