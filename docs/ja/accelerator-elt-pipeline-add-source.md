 ---
title: ソースとオブジェクトの追加
date: 2022-12-12 00:00:00
topicType: task
---

# ソースとオブジェクトの追加 {: #add-source :}

::: note ユーザー権限
このガイドでは、**管理者** 権限を持つユーザーのみが利用できる機能について説明しています。
:::

ソースとオブジェクトを追加するには:

<Stepper>

<Step>

SlackまたはMS Teamsで、**アプリのホームページ**に移動します。

</Step>
<Step>

**ソースとオブジェクトの追加**を選択します。

</Step>
<Step>

**ソースとオブジェクトの追加**インターフェースで、入力フィールドを設定します。

<dl>
	<dt>ソースシステム</dt>
		<dd>データを抽出するソースシステムです。</dd>
		<dd><dl class="horizontal-dl"><dt>サンプル値:</dt>
			<dd><ul><li>Salesforce</li><li>Files</li><li>Microsoft SQL Server</li></ul></dd></dl></dd>
	<dt>オブジェクト</dt>
		<dd>ソースシステム内でサポートされている任意のオブジェクトです。Salesforceではオブジェクト、SQL ServerとPostgreSQLではテーブル名です。</dd>
		<dd><dl class="horizontal-dl"><dt>サンプル値:</dt>
			<dd><ul><li>Leads</li><li>Accounts</li></ul></dd></dl></dd>
	<dt>プライマリキー</dt>
		<dd>データソースがSQL ServerまたはPostgreSQLの場合、これはテーブルのプライマリキーです。他のソースシステムを使用する場合、ELT Pipeline Botはこのフィールドのエントリを無視します。</dd>
		<dd><dl class="horizontal-dl"><dt>サンプル値:</dt>
			<dd><code>primary_key</code></dd></dl></dd>
</dl>

</Step>
<Step>

**送信**をクリックします。

</Step>
</Stepper>