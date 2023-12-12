 ---
title: Slackにカスタマイズした承認ボットアクセラレーターのカスタマイズ方法 {: #main :}
date: 2022-12-03 00:00:00
topicType: task
---

# Slackにカスタマイズした承認ボットアクセラレーターのカスタマイズ方法 {: #main :}

Slackで**承認ボットアクセラレーター**を実装する予定の場合、以下のレシピを設定する必要があります。

- [ABS | Call-006 | Slack Update Homepage](#update-homepage)
- [ABS | REC-001 | Slack Request Parent Recipe](#parent-recipe-modify)
- [ABS | REC-003 | Slackからの承認/拒否リクエスト](#request-recipe-modify)

::: note デフォルトの承認ワークフロー

このアクセラレーターの承認ワークフローは、デフォルトでGoogle Sheetsの新規/更新された行からトリガーされます。承認ワークフローの基盤としてGoogle Sheets以外のアプリケーションを使用する場合は、前述のレシピの接続も変更する必要があります。サポートが必要な場合は、カスタマーサクセスにお問い合わせください。
:::

---

## レシピ **ABS | Call-006 | Slack Update Homepage** の設定 {: #update-homepage :}

このレシピを変更して、承認ダッシュボードに会社のメールアドレスを含めるようにカスタマイズします。このレシピでは、`support@workato.com`をプレースホルダーとして使用しています。

会社のメールアドレスを追加するには:

<Stepper>
<Step>

レシピビルダーで、**ステップ18**の**アプリのホームビューを公開**を選択します。

</Step>
<Step>

**テキスト**フィールドをチームのサポートメールアドレスに更新します。

</Step>
</Stepper>	

---

## レシピ **ABS | REC-001 | Slack Request Parent Recipe** の設定 {: #parent-recipe-modify :}

このレシピは、Google Sheetsのシートに新しい/更新された行がある場合に**ABS | Call-002 | Request to Slack**レシピを呼び出します。

![Slack Request Parent Recipe](~@img/parent-recipe.png)_Slack Request Parent Recipe_

このレシピを設定するには:

<Stepper>
<Step>

*オプション* Google Sheets以外のアプリケーションを使用する場合は、**ステップ1**でGoogle Sheetsを選択したアプリケーションに置き換えます。

</Step>
<Step>

データピルを特定のアプリケーションにマッピングします。

![データピルをマッピング](~@img/datapill-map.png)_データピルをマッピング_

Workatoの入力フィールドは、Google Sheetsのヘッダーに対応しています。他のアプリケーションも同様のフィールドを含んでいる必要があります。

<dl>
	<dt>リクエスター</dt>
	<dd>承認リクエストを送信した人です。</dd>
	<dt>リクエスターのメールアドレス</dt>
	<dd>承認リクエストを送信した人のメールアドレスです。</dd>
	<dt>リクエストアプリ</dt>
	<dd>リクエスターが承認を求めているアプリです。</dd>
	<dt>リクエストの説明</dt>
	<dd>承認リクエストに添えられたメッセージです。</dd>
	<dt>リクエスト日</dt>
	<dd>承認リクエストの日付です。</dd>
	<dt>承認者</dt>
	<dd>承認リクエストを処理するために指定した人です。</dd>
	<dt>承認者のメールアドレス</dt>
	<dd>承認リクエストを処理するために指定した人のメールアドレスです。</dd>
	<dt>リクエストURL</dt>
	<dd>リクエストのURLです。</dd>
	<dt>承認日</dt>
	<dd>承認者がリクエストを承認した場合、これは承認日です。</dd>
	<dt>拒否日</dt>
	<dd>承認者がリクエストを拒否した場合、これは拒否日です。</dd>
	<dt>リクエストID</dt>
	<dd>リクエストに属する一意のIDです。</dd>
</dl>

</Step>
</Stepper>

---

## レシピ **ABS | REC-003 | Slackからの承認/拒否リクエスト** の設定 {: #request-recipe-modify :}

このレシピを設定するには、以下の手順に従ってください:

<Stepper>
<Step>

*オプション* Google Sheets以外のアプリケーションを使用する場合は、シートの接続を選択したアプリケーションに変更します。

</Step>	
<Step>

**ステップ16**と**ステップ21**で結果（承認または拒否）をアプリケーションにマッピングします。

![ステップ16とステップ21を変更](~@img/recipe-steps-modify.png)_ステップ16とステップ21を変更_

</Step>
<Step>

*オプション* **Sheetコネクター**を使用していない場合は、**ステップ11**を削除します。

</Step>	
</Stepper>