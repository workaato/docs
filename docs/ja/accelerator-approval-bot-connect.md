 ---
title: Approval Bot accelerator - 接続
date: 2022-19-03 00:00:00
topicType: task
---

# アプリケーションとの接続 {: #main :}

::: note 必要なアプリケーション
Approval bot acceleratorを実装するアプリケーションによって、接続する必要のあるアプリケーションが異なります。例えば、SlackでApproval botを実装する場合は、SlackをWorkatoワークスペースに接続する必要があります。同様に、MS TeamsでApproval botを実装する場合は、MS Teamsに接続する必要があります。
:::

## Slackへの接続 {: #slack-connect :}

以下の手順に従って、Workatoワークスペースにカスタムボットを追加し、Workatoインスタンスに接続します。

<Stepper>
<Step>

**ツール**に移動し、**Workbot**を選択します。

![Workbotの作成](~@img/approval-workbot-create.png)

</Step>
<Step>

Workbotプロファイルを設定します。詳細な手順については、[Workbot for Slackのセットアップガイド](/ja/workbot/workbot-for-slack-setup.md)を参照してください。

</Step>
<Step>

**Approval Bot > Slack > Connections**に移動し、**ABS | CON-001 | Workbot for Slack**を選択します。

</Step>
<Step>

**Approval Botプロファイル**を選択します。

</Step>
<Step>

**接続**をクリックします。

</Step>
</Stepper>

### MS Teamsへの接続 {: #teams-connect :}

<Stepper>
<Step>

Workatoで**Assets > Approval bot/MS Teams Workspace**フォルダに移動します。

</Step>
<Step>

**ABT | CON-001 | Teams Connection**を選択します。

</Step>
<Step>

Microsoftの認証を使用してTeamsに接続します。

![Teamsへの接続](~@img/approval-connect-teams.png)

</Step>
</Stepper>

## Google Sheetsへの接続 {: #spreadsheet-connect :}

<Stepper>
<Step>

スプレッドシートに接続します。

![Google Sheetsへの接続](~@img/approval-bot-connect-gsheets.png)_Google Sheetsへの接続_

</Step>
<Step>

GoogleがWorkatoへのアクセスを許可するように求めます。**許可**をクリックします。

</Step>
</Stepper>

::: note カスタマイズ可能なコネクタ
スプレッドシートコネクタは、選択した承認ワークフローのプレースホルダです。[Slack用Approval botのカスタマイズ](/ja/accelerator-approval-bot-customize-slack.md)または[Teams用Approval botのカスタマイズ](/ja/accelerator-approval-bot-customize-teams.md)を参照して、Google Sheetsを選択したアプリケーションに置き換える手順をご覧ください。サポートが必要な場合は、カスタマーサクセスにお問い合わせください。
:::