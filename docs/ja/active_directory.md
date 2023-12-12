 ---
title: Workatoコネクター - Active Directory
date: 2018-03-18 06:00:00 Z
---

# Active Directory
Active Directoryは、ネットワーク内のリソースへのアクセスを管理するためにMicrosoftが開発したディレクトリサービスです。このサービスはWindows Server上で実行されます。

## WorkatoでActive Directoryに接続する方法
Active Directoryコネクターは、オンプレミスエージェントを介してのみ利用可能なLDAPプロトコルで認証を行います。

::: tip Workatoでクラウドプロファイルを使用して直接接続を設定する場合
オンプレミスの設定ファイルを編集する必要はありません。以下に示すように、すべてのプロパティをWorkatoで直接設定してください。
:::

![設定済みのActive Directory接続](~@img/active_directory/connection.png)

<table class="unchanged rich-diff-level-one">
  <thead>
    <tr>
        <th width='25%'>フィールド</th>
        <th>説明</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>接続名</td>
      <td>このActive Directory接続に一意の名前を付けて、接続されているActive Directoryインスタンスを識別します。</td>
    </tr>
    <tr>
      <td>オンプレミスグループ</td>
      <td>直接接続が許可されていないネットワークでデータベースを実行している場合は、オンプレミスグループを選択してください。接続を試行する前に、アクティブなオンプレミスエージェントがあることを確認してください。詳細については、<a href="/on-prem.html">オンプレミスエージェント</a>ガイドを参照してください。</td>
    </tr>
    <tr>
      <td>オンプレミスLDAP接続プロファイル</td>
      <td>オンプレミスエージェントの<code>config.yml</code>ファイルで定義されたプロファイル名です。このオプションは、<a href="/on-prem/groups/create-group.html#manually-in-each-agent-connection-profiles">接続プロファイル</a>をサポートするオンプレミスグループを選択した場合に表示されます。</td>
    </tr>
    <tr>
      <td>URL</td>
      <td>URLは、ldap://myserver.example.com:389またはSSLの場合はldaps://myserver.example.com:636の形式である必要があります。</td>
    </tr>
    <tr>
      <td>ユーザー名</td>
      <td>LDAPサーバーとの認証に使用するユーザー名（プリンシパル）です。通常、これは管理者ユーザーの識別名になります。</td>
    </tr>
    <tr>
      <td>パスワード</td>
      <td>LDAPサーバーとの認証に使用するパスワード（資格情報）です。</td>
    </tr>
     <tr>
      <td>ベース</td>
      <td>すべてのリクエストのベースDNです。この属性が設定されている場合、LDAP操作に提供されるすべての識別名は、このLDAPパスを基準とした相対パスになります。</td>
    </tr>
    <tr>
      <td>証明書</td>
      <td>PEMエンコードされた証明書または信頼できるCAのパス</td>
    </tr>
    <tr>
      <td>SSL証明書</td>
      <td>PEMエンコードされたクライアント証明書の完全な内容</td>
    </tr>
    <tr>
      <td>SSL証明書キー</td>
      <td>相互SSLセットアップ用のプライベートキー。SSL証明書が提供されている場合は必須です。</td>
    </tr>
     <tr>
      <td>すべてを信頼</td>
      <td>自己署名証明書を有効にするにはtrueを選択します。</td>
    </tr>
  </tbody>
</table>

## Active Directoryコネクターの使用方法

### オブジェクトの種類
Active Directoryコネクターは、すべての種類のオブジェクトと連携します。

### サンプルエントリDN
このフィールドを使用して、操作/トリガーの入力および/または出力フィールドを決定するために使用するオブジェクトを定義します。この入力フィールドの値は、Active Directoryインスタンス内の実際のエントリである必要があります。

サンプルユーザーエントリのDNは次のようになります：

```
CN=Workato Integrations,CN=Users,DC=workato,DC=local
```